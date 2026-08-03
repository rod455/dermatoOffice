# Plano de início

Ordem de execução pra tirar a operação do papel, com estimativas de custo.
Responsável pela parte de tecnologia e operação: **AppFactory**.

> Todos os valores são **estimativas de mercado (SP, 2025/2026)** pra
> dimensionar o investimento — cada um precisa ser confirmado na contratação.

## Passo a passo

### 1. Credenciar nos planos de saúde  ⭐ crítico
É o item que destrava tudo o resto (a demanda entra por aqui).

- Checar situação do painel de dermato de **SulAmérica e Bradesco** na região
  (aberto/fechado) e o que exigem pra credenciar o PJ da Bianca.
- Reunir documentação: RQE, Título de especialista, CNPJ, registro no CRM.
- **Custo:** basicamente tempo. Pode haver taxas de conselho/registro do PJ.
- **Prazo:** semanas — por isso começa **já**, em paralelo com o resto.

### 2. Abrir/organizar o PJ + contador
Pré-requisito do credenciamento e do faturamento.

- Abrir ME no **Simples Nacional** (MEI não serve pra esse caso).
- Conta bancária PJ + meio de pagamento pra particular (Pix/cartão).
- **Custo:** honorário de contador **R$300–600/mês**; abertura ~R$0–500.

### 3. Contratar a sala fixa
Sair do avulso por hora pra um compromisso mensal (previsibilidade de agenda).

| Modelo | Estimativa | Quando usar |
|--------|-----------|-------------|
| Fixo + hora avulsa (ex.: R$200 fixo + R$50/h) | **~R$700–1.200/mês** no ramp-up | Começo, enquanto enche a agenda — paga pelo que usa |
| Plano mensal com dia fixo (1 dia/semana) | **~R$1.800–2.500/mês** | Quando a agenda de um dia já está cheia |
| 2 dias fixos / meio período estendido | **~R$3.000–4.500/mês** | Crescimento |
| Sala exclusiva full-time | **R$5.000+/mês** | Só quando o volume justificar |

Coworking médico já inclui recepção, secretária, limpeza, internet, ar,
IPTU. **Confirmar se fornece equipamento pra procedimento não-estético**
(dermatoscópio, material de biópsia) ou se isso é compra à parte
(**~R$1.500–8.000** de investimento inicial, se necessário).

> **Recomendação:** começar no modelo *fixo + hora avulsa* pra não pagar sala
> parada, e subir pra dia fixo assim que a agenda encher. O risco de saída fica
> baixo — é a lógica de "sem risco de não se autopagar".

### 4. LP Bianca Dermato
Landing page como base do particular e da presença digital.

- Página com a Bianca (credenciais, RQE, o que faz), agendamento de particular
  e captação de contato **com opt-in de LGPD**.
- **Google Business Profile** (perfil no Google Maps) — essencial pra dermato
  local, e de graça.
- Instagram profissional + primeiros conteúdos educativos.
- **Custo:** construção pela **AppFactory (in-house)**; recorrente só
  domínio + hosting **~R$50–150/mês**.

### 5. Sistema de agendamento + WhatsApp credenciado (API oficial Meta)
O motor operacional (detalhes técnicos em [`automacao-whatsapp.md`](automacao-whatsapp.md)).

- WhatsApp Business verificado na **API oficial da Meta (Cloud API)**.
- Fluxos: confirmação, lembrete (anti no-show), remarcação de procedimento,
  fila de encaixe.
- Integração com a agenda e o CRM.

**Estimativa de mensagens (Meta, Brasil — preços por mensagem):**

| Categoria | Preço/msg | Uso na clínica |
|-----------|-----------|----------------|
| **Serviço** (paciente inicia, janela 24h) | **R$0** | Paciente responde/pergunta |
| **Utilidade** (confirmação, lembrete) | **~R$0,04–0,05** | O grosso do nosso uso — e **grátis** se enviado dentro da janela de 24h |
| **Autenticação** (código/verificação) | ~R$0,15–0,19 | Pouco uso |
| **Marketing** (reativação, oferta) | ~R$0,31–0,38 | Só opt-in, com parcimônia |

Sobre esses valores incide a margem do BSP (**+10–30%**), se usarmos um. Indo
direto na **Cloud API da Meta não há taxa de plataforma** — paga-se só a
mensagem.

**Estimativa mensal realista:** com o volume esperado (confirmações/lembretes =
utilidade barata + respostas = grátis + marketing pontual), a conta de
mensagens fica em torno de **R$50–150/mês**.

> **Ponto importante:** o custo das mensagens é **trivial**. O investimento
> real dessa etapa é o **desenvolvimento do sistema** (feito pela AppFactory),
> não o gasto com a Meta.

### 6. Plataforma do médico + CRM
O painel da Bianca (agenda, ficha, CRM, anotação por voz/foto). Detalhes em
[`plataforma-medico.md`](plataforma-medico.md).

- **v1** (agenda + ficha + CRM) sai junto com o sistema de agendamento.
- Evolução (voz/foto/preenchimento assistido) vem depois, sobre o uso real.
- **Custo:** desenvolvimento pela **AppFactory**; recorrente de infra/hosting
  diluído no item 4/5.

### Outros passos necessários (não esquecer)

- **Termo de consentimento + política de privacidade (LGPD)** — opt-in desenhado
  dentro do fluxo de agendamento desde o dia 1. Barato agora, caro depois.
- **Compliance CFM** — revisar todo material de marketing antes de publicar
  (ver [`marketing-e-compliance.md`](marketing-e-compliance.md)).
- **Gateway de pagamento** pro particular (Pix/cartão) — taxa ~1–3% por
  transação.
- **Definição do fluxo duplo:** plano agenda pelo app da operadora; particular
  agenda pela LP/WhatsApp. Não misturar os canais.
- **Prontuário** conforme exigência do CFM/CRM (a plataforma respeita, não
  substitui).
- **Semanas de operação manual** antes de automatizar — pra observar padrões
  reais de no-show e mensagem e automatizar o que importa.

## Estimativa da primeira etapa (caminho coworking)

Valores de mercado / oficiais (2026), pra dimensionar o caixa necessário até o
**go-live** (regularizar → credenciar → começar a faturar pelo plano).

### Custos únicos (setup regulatório)
| Item | Estimativa |
|------|-----------|
| Certificado de Regularidade no CRM-MG | R$0–100 |
| Taxa de inscrição secundária (PF) no CREMESP | **R$135** |
| Registro/adequação da PJ no CREMESP (taxa) | ~R$135 |
| CCM (inscrição municipal SP), CNES | **grátis** |
| Licença sanitária (é do coworking) | **R$0** |
| **Subtotal setup** | **~R$270–370** |
| Equipamento de procedimento (só se o coworking não fornecer) | R$1.500–8.000 *(condicional)* |

### Anuidades em SP (custo novo por operar em SP — anual)
Como é inscrição **secundária**, paga-se anuidade **também** em SP (a de MG
continua):
| Item | Estimativa/ano |
|------|-----------|
| Anuidade pessoa física — CREMESP | ~R$948 |
| Anuidade pessoa jurídica — CREMESP | ~R$190 (com desconto de 80%, se elegível) a R$948 |
| **Subtotal anuidades SP** | **~R$1.140–1.900/ano** (~R$95–160/mês diluído) |

### Recorrente mensal (fase ramp-up)
| Item | Estimativa/mês |
|------|-----------|
| Coworking Vila Mariana (fixo + hora, ramp-up) | R$700–1.200 |
| Contador (Simples) | R$300–600 |
| WhatsApp (mensagens Meta) | R$50–150 |
| Domínio + hosting | R$50–150 |
| Anuidades CREMESP (diluídas) | R$95–160 |
| **Total recorrente inicial** | **~R$1.195–2.260/mês** |

### Construção do sistema (AppFactory, one-time)
LP + agendamento + WhatsApp oficial + plataforma do médico/CRM — **feito
in-house pela AppFactory**, não sai do caixa da operação. (Referência de mercado,
se fosse terceirizado: R$15k–50k — daí a AppFactory absorver isso ser parte do
valor dos 35%.)

### 💰 Caixa necessário pra chegar ao go-live
O credenciamento leva semanas e a receita entra em rampa, então o que importa é
o **fôlego** até faturar:

> **Setup (~R$300) + 2 a 3 meses de recorrente (~R$2.400–6.800) ≈ R$2.700–7.100**,
> sem equipamento. Com equipamento de procedimento e uma margem de segurança:
> **~R$5.000–15.000**.

Lembrando que a saída de caixa de risco que você topou (aluguel parado) é o
**recorrente**, e o cenário conservador (só consulta de plano) já projeta
**~R$4.600/mês de margem** — ou seja, a partir do go-live o recorrente se paga e
o caixa inicial é reposto rápido.

**As três variáveis que mais mexem no número:** (1) modelo do coworking
escolhido, (2) se precisa comprar equipamento, (3) se a PJ pega o desconto de
80% na anuidade.

## Resumo de investimento

**Custos recorrentes (mês), fase inicial:**

| Item | Estimativa/mês |
|------|----------------|
| Sala (ramp-up: fixo + hora) | R$700–1.200 |
| Contador (Simples) | R$300–600 |
| WhatsApp (mensagens Meta) | R$50–150 |
| LP/plataforma (domínio + hosting) | R$50–150 |
| **Total recorrente inicial** | **~R$1.100–2.100/mês** |

**Investimento de construção (one-time):** LP, sistema de agendamento,
plataforma do médico e integração de WhatsApp — feitos pela **AppFactory**.
Equipamento de procedimento (R$1.500–8.000) só se o coworking não fornecer.

Contra isso, o cenário conservador (só consulta de plano em coworking
credenciado) já projeta **~R$4.600/mês de margem** — ou seja, o recorrente se
paga com folga já no piso. Números em [`plano-de-negocio.md`](plano-de-negocio.md).
