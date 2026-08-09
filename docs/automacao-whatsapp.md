# Automação de agendamento no WhatsApp

O objetivo dessa camada é único e mensurável: **manter a agenda cheia sem a
Bianca (nem você) precisar responder mensagem manualmente.** Utilização é a
métrica que essa automação move.

## Princípio: agendamento do plano ≠ agendamento particular

Isso é importante e muita gente erra:

- **Plano** — o agendamento oficial acontece no **app da operadora**
  (SulAmérica, Bradesco). A automação do WhatsApp aqui **não substitui** isso;
  ela serve pra **confirmar, lembrar e reduzir no-show**, e pra captar quem
  chegou por fora e redirecionar pro canal do plano.
- **Particular / estética** — aqui sim o WhatsApp é o canal de venda e
  agendamento fim a fim. É onde a automação fecha receita direto.

Tratar os dois como a mesma coisa gera problema com a operadora. Separar é o
jeito certo.

## O que a automação faz (por prioridade de impacto)

1. **Confirmação e lembrete de consulta** → ataca no-show, que é o maior
   vazamento de utilização. Mensagem 48h e 3h antes, com botão de confirmar /
   remarcar.
2. **Remarcação de procedimento** → aquele loop de ouro do plano: paciente que
   fez consulta e vai voltar pra tirar pinta/biópsia. A automação puxa esse
   retorno ativamente (e lembra que depois de 15 dias entra outra consulta).
3. **Fila de encaixe** → quando alguém cancela, oferece o horário
   automaticamente pra uma lista de espera. Transforma buraco na agenda em
   receita.
4. **Triagem inicial** → responde dúvida comum, coleta o essencial (nome,
   convênio ou particular, motivo) e roteia. Só cai pra humano o que precisa.
5. **Recompra / reativação** (fase posterior, com opt-in) → paciente que sumiu,
   oferta de retorno. **Só com consentimento** — ver doc de marketing/LGPD.

## v0 — Evolution API + IA (decidido: começar por aqui)

Pra validar rápido sem esperar a burocracia da API oficial, o v0 roda com
**Evolution API** (open-source, self-hosted) pareada com o número comercial
existente (+55 31 8218-7822), como um "WhatsApp Web programável".

### Por que faz sentido agora
- **Zero fricção com o número atual** — pareia via QR code com a conta Business
  que já existe; o app continua funcionando no celular em paralelo (multi-device).
  A Bianca/secretária vê tudo e pode assumir qualquer conversa.
- **Custo quase zero** — software livre; só a VPS (~R$30–60/mês).
- **Aprendizado real** — vemos os padrões de mensagem/no-show reais antes de
  investir na migração oficial.

### O risco, dito com todas as letras
Evolution usa o protocolo do WhatsApp Web — **não é oficial**. A Meta pode
**banir o número** se detectar automação, especialmente disparo em massa.
Regras de convivência pra reduzir o risco a quase nada:
1. **Só conversa 1:1 e responsiva** — responder quem chama, confirmar consulta
   de quem já agendou. **NUNCA disparo em massa/marketing** pelo Evolution.
2. Número já "quente" (conta ativa, com histórico) — ✔ é o caso.
3. Ritmo humano: delays entre mensagens, sem rajadas.
4. **Plano de migração pra API oficial** já no roadmap (quando tiver volume ou
   formos fazer campanhas). Marketing em massa **só** na oficial, com opt-in.

### Arquitetura v0

```
Paciente ──► WhatsApp (+55 31 8218-7822)
                 │  (pareado via QR)
                 ▼
          Evolution API (VPS)
                 │  webhook (mensagem recebida)
                 ▼
               n8n ──────────────────────────────┐
                 │                               │
                 ▼                               ▼
          Claude (IA)                     Integrações
      classifica intenção            ├─ Agenda (Google Calendar no v0)
      e redige a resposta            ├─ CRM (Supabase no v0)
                                     └─ Notificação p/ humano (handoff)
```

### O fluxo de conversa (máquina de estados)

**1. Triagem (toda mensagem que chega)** — a IA classifica a intenção:
`agendar` · `confirmar` · `remarcar/cancelar` · `dúvida` · `humano` · `fora de escopo`

**2. Agendar** — coleta em conversa natural: nome → convênio ou particular →
- *Convênio:* orienta o agendamento pelo app da operadora (regra do plano) e
  registra o lead no CRM pra acompanhar.
- *Particular:* oferece 2–3 horários livres da agenda → paciente escolhe →
  grava na agenda + CRM → mensagem de confirmação.

**3. Confirmação/lembrete (proativo, o anti no-show)** — cron no n8n:
- 48h antes: "confirma sua consulta?" (sim / preciso remarcar)
- 3h antes: lembrete curto com endereço.
- Sem resposta na véspera → alerta pra secretária ligar.

**4. Remarcar/cancelar** — oferece novos horários; se cancelou, o horário entra
na **fila de encaixe** (oferece pra lista de espera).

**5. Dúvidas (a IA responde)** — endereço, convênios aceitos, como funciona,
preparo pra consulta. **Guardrails inegociáveis:**
- Se identifica sempre como assistente virtual da clínica.
- **NUNCA responde pergunta clínica** ("essa pinta é perigosa?", "que remédio
  tomo?") → resposta padrão: "isso é com a Dra. na consulta" + oferece agendar.
- Nunca promete resultado; não fala de preço de procedimento estético sem a
  Bianca ter definido a política.
- LGPD: registra o opt-in na primeira conversa; comando "SAIR" descadastra.

**6. Handoff (pra humano)** — gatilhos: pedido explícito, urgência/dor,
reclamação, 2 falhas seguidas de entendimento, qualquer coisa clínica →
notifica a Bianca/secretária e a IA **silencia naquela conversa** até liberar.

### Roadmap
| Fase | Canal | O que roda |
|------|-------|-----------|
| **v0 (agora)** | Evolution + número atual | Triagem IA, agendamento particular, confirmação/lembrete, dúvidas, handoff |
| **v1** | API oficial Meta (Cloud API) | Migra quando: volume alto, campanhas de marketing (opt-in), ou qualquer sinal de risco no número. Número 11 dedicado a avaliar |
| **v2** | + Plataforma do médico | CRM alimentado por voz/foto dispara os fluxos (retorno, reativação) |

## Arquitetura oficial (v1) — referência

Duas peças que já estão disponíveis neste ambiente:

- **n8n** — orquestração dos fluxos (gatilhos, agenda, lembretes, integrações).
  É onde os workflows vivem e onde dá pra versionar e evoluir sem código frágil.
- **Claude** — a camada de linguagem: entender a mensagem do paciente em
  português real, decidir a intenção e responder com naturalidade dentro das
  regras que a gente definir.

Fluxo em alto nível:

```
WhatsApp (API oficial / provedor)
        │
        ▼
     n8n  ──►  Claude (interpreta intenção + gera resposta)
        │            │
        │            ├─ agendar/confirmar/remarcar
        │            ├─ dúvida → responde ou escala
        │            └─ particular/estética → fluxo de venda
        ▼
  Agenda + base de pacientes (opt-in registrado)
```

## Decisões que a gente precisa cravar antes de construir

1. **Provedor de WhatsApp** — API oficial do WhatsApp Business (via provedor) é
   o caminho certo pra não tomar ban. Definir qual.
2. **Onde mora a agenda** — o coworking já tem uma? Integramos nela ou usamos
   uma própria pro particular? (Plano continua no app da operadora.)
3. **Até onde a automação decide sozinha** — quanto mais regra clara, menos
   atrito Bianca↔você. Ex.: "confirmar e remarcar é automático; oferecer
   estética exige toque humano". Isso a Bianca define.
4. **Registro de consentimento** — desde a primeira mensagem, guardar opt-in
   pra poder fazer recompra depois sem pisar em LGPD.

## Regra de ouro do bot

O bot **nunca** dá orientação clínica, diagnóstico ou promessa de resultado.
Ele agenda, confirma, organiza e escala. Conteúdo clínico é sempre a Bianca.
Isso protege juridicamente e mantém a qualidade da marca.

## Próximo passo concreto

Nada disso se constrói antes do credenciamento estar resolvido e da agenda
estar rodando manualmente por algumas semanas — a gente precisa **ver os
padrões reais** de mensagem e no-show pra automatizar o que importa, não o que
a gente imagina. Fase de automação começa no dia ~30 (ver checklist).
