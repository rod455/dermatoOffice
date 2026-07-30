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

## Arquitetura sugerida

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
