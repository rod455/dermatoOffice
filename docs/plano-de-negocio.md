# Plano de negócio — DermatoOffice

## 1. A leitura honesta da ideia

A ideia faz sentido, e faz por um motivo que vale explicitar: **você não está
apostando em gerar demanda, está apostando em capturar demanda que já existe.**
Isso muda tudo. A maioria das clínicas quebra tentando resolver marketing e
aquisição de paciente. Aqui o funil de entrada vem pronto dos planos porque a
Bianca tem RQE + Título — que é exatamente a fricção que trava 90% dos médicos
recém-especialistas. Agenda cheia nas próximas 4 sextas num primeiro dia
confirma isso na prática.

Então o risco real **não** é "vai ter paciente?". O risco é operacional e de
crescimento:

1. **Credenciamento direto** (item crítico — ver seção 3).
2. **Utilização da agenda** — hora vazia é prejuízo puro no modelo de aluguel.
3. **Conversão** consulta → procedimento → estética, que é onde a grana está.

## 2. O reframe econômico que muda o jogo

O dia de R$1.800 aconteceu num modelo de **repasse**: a clínica fica com 50%,
a Bianca fica com 50%. Ou seja, os planos foram faturados em ~R$3.600 naquele
dia e metade ficou na clínica.

No modelo **coworking + credenciamento próprio**, a lógica inverte:

- A Bianca (ou o PJ dela) é a credenciada → **recebe 100% do que o plano paga**.
- O custo é **aluguel fixo** (~R$1.000/mês por 16h), não um % do faturamento.

Isso significa que aquele mesmo dia de R$3.600 faturado passaria a render
praticamente o dobro pra ela, porque o corte de 50% da clínica vira um custo
fixo pequeno e diluído.

> **É essa a alavanca central do negócio.** Não é o Claude, não é o marketing —
> é trocar "dividir 50% do faturamento pra sempre" por "pagar R$1.000 fixos".
> A automação e o marketing são multiplicadores em cima disso.

## 3. Item crítico: credenciamento (resolver ANTES de qualquer gasto)

Todo o modelo acima depende de uma pergunta: **a Bianca consegue ser a
credenciada direta nos planos?**

Dois caminhos:

- **A) Coworking que já tem credenciamento.** Alguns coworkings médicos operam
  com CNPJ próprio já credenciado e "sublocam" o credenciamento. Mais rápido,
  porém pode voltar a ter repasse — checar a % antes.
- **B) Credenciar o PJ da Bianca.** Melhor economia (100% dela), mas planos
  grandes às vezes têm **painel fechado** ou exigem estrutura mínima/CNPJ, e o
  processo leva semanas. Vale começar já, em paralelo, mesmo que comece pelo
  caminho A.

**Ação zero:** ligar/checar com SulAmérica e Bradesco qual a situação do painel
de dermato na região e o que exigem pra credenciar um PJ individual. Sem essa
resposta, o resto é especulação.

## 4. Unit economics (com premissas rotuladas — validar cada uma)

Números redondos pra raciocinar, **não** são projeção fechada:

| Item | Premissa | Valor |
|------|----------|-------|
| Consulta de plano (faturada) | tabela do plano | ~R$100 |
| Pacientes/hora | 3–4 (você citou) | 3,5 |
| Aluguel | 16h/mês | R$1.000 |
| Ponto de equilíbrio do aluguel | ~3 h de agenda cheia | ✅ |

**Cenário conservador (só consulta, credenciamento próprio):**
16h × 3,5 pacientes × R$100 = **~R$5.600/mês** de faturamento, menos R$1.000 de
aluguel = **~R$4.600** de margem, antes de impostos (Simples/PJ) e taxa das
operadoras. Já se paga com folga.

**Onde mora o upside (as três camadas):**

1. **Procedimento simples pago por plano** (tirar pinta, biópsia): +R$50+ por
   procedimento. E o loop que você descreveu: paciente que volta depois de 15
   dias **paga outra consulta + o procedimento**. Cada conversão vale 2 receitas.
2. **Volume que sobra pra ela:** os planos estão precisando de dermato que
   queira fazer procedimento **não-estético** (pinta, biópsia), porque a maioria
   dos médicos foge disso pra focar em estética particular. A Bianca **curte**
   fazer isso — ou seja, ela quer justamente o volume que os outros rejeitam.
   Isso é vantagem competitiva real dentro do plano.
3. **Estética particular** (botox, peeling, preenchimento): melhor margem de
   todas as especialidades. É o "aposentar antes da Copa" — mas é também onde
   moram os riscos de compliance (ver seção 6 e o doc de marketing).

## 5. Divisão de papéis e distribuição

Você foi direto: você e a Bianca batem cabeça no "estratégico", e pra funcionar
você precisa ficar de fora dessas discussões. Faz sentido, e dá pra desenhar:

- **Bianca — dona do clínico e da experiência do paciente.** Agenda, tipos de
  procedimento, qualidade do atendimento, decisão de o que oferecer a quem.
  Ela é a marca e o produto.
- **AppFactory — responsável pela operação, tecnologia e capital.** Banca a
  estrutura (aluguel fixo de saída, plataforma, marketing), constrói e mantém o
  sistema (plataforma do médico + automação de WhatsApp), e assume o risco
  financeiro. Fica **fora** da mesa clínica e do dia a dia estratégico do
  atendimento.
- **A automação — o operacional que não briga.** Agendamento, follow-up,
  remarketing, relatórios, CRM. A camada neutra que tira do meio decisões
  repetitivas que viram atrito.

### Distribuição dos lucros — proposta final: **65% / 35%**

- **Bianca — 65% do lucro.** Ela gera a receita e é a marca.
- **AppFactory — 35% do lucro.** Responsável por capital, tecnologia e operação.

**Lucro = receita − custos** (aluguel, plataforma/APIs, marketing, taxas das
operadoras, impostos). Os custos saem primeiro, do topo; o que sobra é dividido
65/35. Isso alinha os dois lados no mesmo incentivo: crescer receita e segurar
custo. A AppFactory só ganha se a operação der lucro de verdade — não é taxa
sobre faturamento, é participação no resultado.

A sacada aqui é que **quanto mais coisa a automação decide por regra, menos
superfície de conflito** sobra entre as partes. O sistema vira o
"terceiro sócio sem ego".

## 6. Riscos que eu não deixaria passar

1. **Credenciamento (seção 3)** — o negócio inteiro depende disso. Risco #1.
2. **Utilização** — 16h contratadas com agenda meio vazia corrói a margem.
   A automação de agendamento existe pra atacar isso diretamente.
3. **Compliance de dado sensível (LGPD).** "Coletar dados da galera do plano e
   depois ofertar estética" é a parte mais legalmente delicada da ideia. Dado de
   saúde é **dado sensível** — reaproveitar cadastro de paciente do plano pra
   marketing de estética particular **sem consentimento específico** é exposição
   real. Dá pra fazer certo, com opt-in explícito. Detalhes no doc de marketing.
4. **Publicidade médica (CFM).** Ads de estética têm regra dura (nada de
   antes/depois sensacionalista, promessa de resultado, etc.). Também no doc de
   marketing.
5. **Dependência de uma médica só.** No começo é a Bianca ou nada. Bom manter
   como risco consciente antes de escalar estrutura fixa.

## 7. Veredito

Roda. E roda com **risco baixo de não se pagar**, que é raro nesse tipo de
aposta. O piso (só consulta de plano em coworking credenciado) já cobre custo e
dá margem. O teto (conversão pra procedimento e depois estética particular, com
a automação segurando utilização e recompra) é onde está o dinheiro grande.

A ordem certa é: **credenciamento → encher agenda → automatizar agendamento →
converter procedimento → só então estética.** Não pular etapa. O checklist
90 dias detalha isso.
