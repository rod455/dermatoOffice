# Caminho regulatório: CRM-SP → licença → CNES → credenciamento

> Não é aconselhamento jurídico. São os requisitos gerais confirmados em fontes
> oficiais; os documentos exatos devem ser confirmados com o **CREMESP**, a
> **Vigilância Sanitária municipal** e o **coworking**. Um contador/despachante
> de saúde resolve boa parte disso rápido.

## O ponto de atenção: a PJ está no CRM-MG, a operação é em SP

Isso é um gargalo escondido que precisa ser resolvido **antes** do CNES e do
credenciamento. O estabelecimento e a atividade médica em SP são regulados pelo
**CREMESP** (CRM de São Paulo), não pelo CRM-MG. Provavelmente serão precisos
dois registros em SP:

1. **Inscrição secundária da médica no CREMESP** — mantém a inscrição primária
   em MG e abre uma secundária em SP pra poder exercer aqui. O processo começa
   pedindo o **Certificado de Regularidade no CRM-MG**, que é enviado ao CREMESP.
   (Atenção: paga-se anuidade nos dois CRMs enquanto mantiver as duas inscrições.)
2. **Registro da PJ (empresa médica) no CREMESP** — o estabelecimento que opera
   em SP precisa estar regular no CREMESP. O registro no CRM-MG cobre operação em
   MG, não em SP. **Confirmar com o CREMESP** o que exatamente é exigido pra PJ.

> Por que isso é crítico: o **Responsável Técnico (RT)** do CNES precisa ter CRM
> válido no estado, e o credenciamento dos planos exige a PJ regular no CREMESP.
> Ou seja, sem resolver o CRM-SP, nem o CNES nem o credenciamento andam. **Começa
> por aqui, em paralelo com a escolha da sala.**

## A cadeia de dependências (a ordem importa)

```
   CREMESP (inscrição secundária + PJ)        Endereço fixo (a sala)
              │                                        │
              └────────────────┬───────────────────────┘
                               ▼
                   Licença sanitária (Vigilância Sanitária municipal)
                               │
                               ▼
                             CNES  (Cadastro Nacional de Estab. de Saúde)
                               │
                               ▼
                   Credenciamento nos planos (SulAmérica, Bradesco)
```

Nada de CNES sem endereço fixo **e** sem licença sanitária. Nada de
credenciamento sem CNES. Por isso a **escolha da sala virou pré-requisito** —
saiu do "quando der" pro caminho crítico.

## Próximos passos, em ordem

### 1. CREMESP — inscrição secundária + PJ  ⭐ começa já (é o gargalo)
- Pedir **Certificado de Regularidade** no CRM-MG.
- Dar entrada na **inscrição secundária** no CREMESP.
- Confirmar com o CREMESP o **registro/adequação da PJ** pra operar em SP.
- Levar RQE + Título (já tem) — garante o credenciamento depois.

### 2. Fechar o endereço (a sala) — pré-requisito do CNES
O CNES exige "espaço físico delimitado e permanente". Ao escolher o coworking,
**perguntar diretamente** (isso decide o caminho e pode poupar semanas):
- O coworking **já tem CNES próprio** e licença sanitária no endereço?
- A **PJ dela** pode ser registrada/vinculada naquele endereço pra credenciar os
  planos, ou ela operaria sob o estabelecimento do coworking?
- O endereço permite **CNES próprio da PJ** (caso queira credenciamento direto)?

Dois modelos possíveis:
- **A) Sob o estabelecimento do coworking** — mais rápido (usa o CNES/licença
  deles), mas confirmar como fica o credenciamento da PJ dela.
- **B) CNES próprio da PJ no endereço** — mais controle e credenciamento direto,
  porém exige licença sanitária própria e mais burocracia.

### 3. Licença sanitária (Vigilância Sanitária municipal)
- É **pré-requisito do CNES** e obrigatória pra fazer **procedimento** (biópsia,
  retirada de pinta).
- Se o coworking já tem pro endereço (modelo A), agiliza muito.
- Se for CNES próprio (modelo B), tirar a licença da PJ no endereço.

### 4. CNES — Cadastro Nacional de Estabelecimentos de Saúde
- Feito via **Secretaria Municipal de Saúde de SP** / sistema SCNES (DATASUS).
- Tipo **"Consultório Isolado" (tipo 22)** → pode usar o **SCNES Simplificado**.
- Precisa: **CNPJ**, endereço, **licença sanitária** válida, **RT** (a própria
  Bianca, com CREMESP), dados de contato (**o telefone comercial** entra aqui).

### 5. Credenciar nos planos
- Com **CREMESP + CNPJ + CNES + licença sanitária**, aplicar na SulAmérica e
  Bradesco. RQE + Título destravam o credenciamento como especialista.

### 6. Telefone comercial — decidir o uso
- Entra como **contato no CNES**.
- Decidir se **esse número vira o da API oficial do WhatsApp** (Meta). Atenção:
  um número na **WhatsApp Business API não pode** estar ao mesmo tempo no app
  normal do WhatsApp. Se o número comercial já é usado no app, ou se migra ele
  pra API, ou usa um número separado pra automação.

## Cenário: alugar sala "com estrutura de consultório" em Vila Mariana

A ideia é boa (Vila Mariana é a região que eu recomendaria pra fase 1), mas tem
uma armadilha na frase "não vamos ter licença sanitária". Duas fontes deixam
claro:

> **A licença sanitária do locador NÃO é "aproveitável" pelo locatário pessoa
> jurídica — a PJ precisa de licença própria.** E cada profissional que atua num
> estabelecimento precisa estar **vinculado ao CNES** daquele estabelecimento.

Ou seja: **estrutura física (sala, maca, pia) ≠ estabelecimento de saúde
regularizado.** Ter os móveis de consultório não substitui licença + CNES. Não
dá pra "usar a licença do prédio" operando como PJ. Isso muda os caminhos:

### Caminho A — coworking que opera COMO o estabelecimento (turnkey)
Alguns coworkings médicos **são** o estabelecimento de saúde: têm CNES + licença
sanitária próprios, e os médicos atuam **vinculados ao CNES deles**. Nesse
modelo é possível **não ter licença própria** — mas só se você atua como
profissional vinculada ao estabelecimento deles, não como PJ locatária
independente. **É esse o modelo a procurar.** Perguntas obrigatórias antes de
assinar:
- Vocês têm **CNES e licença sanitária ativos** neste endereço?
- Posso ser **vinculada ao CNES de vocês** como profissional?
- Como fica o **credenciamento dos planos** — pela minha PJ ou como pessoa
  física vinculada ao estabelecimento de vocês?

### Caminho B — você opera como sua própria PJ na sala
Aí **precisa de licença sanitária própria + CNES próprio** no endereço. A licença
do locador não vale pra sua PJ. Ou seja, "não ter licença" **não é opção** nesse
caminho.

### ⚠️ A armadilha do procedimento (isso afeta a receita de vocês)
A licença/CNES do estabelecimento tem **classificação por tipo de procedimento**:
- **Grupo 1** — só consulta, sem procedimento.
- **Grupo 2** — procedimento **sem** anestesia local (peeling, toxina,
  preenchimento, crioterapia, cauterização, laser).
- **Tipo II (mais alto)** — procedimento cirúrgico de pequeno porte **com
  anestesia local**.

**Biópsia e retirada de pinta usam anestesia local → exigem o nível mais alto
(Tipo II).** Muito coworking é licenciado **só pra consulta** (Grupo 1). Se for
o caso, você poderia atender consulta e alguns procedimentos estéticos, mas
**não** faria biópsia/exérese ali — que é justamente o upside de receita e o que
a Bianca curte fazer. **Confirmar que o estabelecimento é licenciado pro nível
de procedimento que ela vai realizar** é tão importante quanto a licença existir.

### O que confirmar na sala de Vila Mariana antes de assinar
1. É um **estabelecimento de saúde regularizado** (tem CNES + licença sanitária
   próprios), ou é só uma sala com móveis de consultório?
2. A **licença cobre procedimento com anestesia local** (biópsia, exérese —
   Tipo II)? Ou só consulta?
3. Posso ser **vinculada ao CNES deles** (caminho A) ou vou precisar de licença
   e CNES próprios (caminho B)?
4. O **credenciamento dos planos** pela minha PJ é viável nesse endereço?
5. Independência estrutural/funcional da sala (a VISA exige ambiente
   individualizado).

> **Resumo do cenário:** "não ter licença sanitária" só funciona no **caminho
> A** (coworking que já é o estabelecimento e te vincula ao CNES dele) **e** se a
> licença dele cobrir os procedimentos da Bianca. Fora disso, como PJ, a licença
> própria é obrigatória. Vale confirmar tudo isso com o coworking **e** com a
> Vigilância Sanitária de SP — as regras são municipais e a interpretação varia.

## Coworking: dá pra atender plano? Pago aluguel ou comissão?

**Dá pra participar de planos, sim.** O credenciamento é entre **você (ou sua
PJ) e a operadora** — não é o coworking que te credencia. Pontos confirmados:
- **Sem exclusividade e sem limite** — pode se credenciar em quantos planos
  quiser, e atender **plano e particular ao mesmo tempo**.
- O coworking entra só como **domicílio fiscal/endereço regularizado** (CNES +
  licença) que viabiliza o credenciamento. Valem as ressalvas das seções acima
  (CNES vinculado, licença cobrindo procedimento).
- **Ressalva:** nem todo coworking é montado pra plano — muitos focam em
  particular. Confirmar que aquele endereço **suporta atendimento por convênio**.

**Aluguel ou comissão? São dois modelos diferentes — não confunda:**

| | **Coworking (aluguel)** | **Clínica com repasse (comissão)** |
|---|---|---|
| O que você paga | **pelo espaço** (hora, período, dia, pacote mensal, créditos) | **% do que fatura** (ex.: os 50% do primeiro dia da Bianca) |
| Quanto você fica do plano/particular | **100%** | o que sobra depois do corte da clínica |
| Custo | **fixo/previsível** | variável, cresce com seu faturamento |
| É coworking? | **sim** | **não** — é clínica parceira/repasse |

> **Coworking de verdade = só aluguel.** Você fica com **100%** do que o plano
> ou o particular paga; o coworking não toca nesse dinheiro. A **comissão/repasse
> (50%)** é o modelo da clínica onde ela atendeu — **não** é coworking. Alguns
> lugares misturam (aluguel + taxa), então **confirme no contrato**.

Isso é o coração da economia do projeto: trocar "dividir 50% pra sempre" (repasse)
por "pagar aluguel fixo" (coworking) é o que praticamente **dobra** o que a Bianca
leva por atendimento. Ver [`plano-de-negocio.md`](plano-de-negocio.md) seção 2.

**Fique de olho (mesmo sem comissão):** taxas extras de adesão, limpeza,
secretária, materiais de procedimento — pergunte o que está **incluído no
aluguel** e o que é cobrado à parte.

## Quanto custa a licença sanitária em SP?

Depende da **classificação de risco** da atividade — e, no modelo coworking, na
prática pode **não ser um custo separado seu**:

| Classificação | Custo/processo |
|---|---|
| **Risco I (Baixo)** — ex.: consultório só de consulta | **Isento de licença** — só cadastro/autodeclaração no CEVS (Cadastro Estadual de Vigilância Sanitária) |
| **Médio risco** — procedimento de pequeno porte | Licenciamento **simplificado e automático** pelo Portal Integrador Estadual (gera o CLI, equivalente à licença) — taxa baixa ou isenta |
| **Alto risco** | Protocolo direto na Vigilância + vistoria |

**Procedimento com anestesia local (biópsia, exérese)** sobe a classificação
pra médio/alto — não é baixo risco. Então o estabelecimento precisa estar
licenciado nesse nível (o ponto que já levantamos).

> **No caminho coworking (o de vocês):** a licença é do **estabelecimento
> (coworking)**, não sua. Você não paga uma licença separada — ela está
> **embutida no que o coworking cobra**, desde que ele seja o estabelecimento
> licenciado **e** a licença cubra o nível de procedimento da Bianca. Por isso a
> pergunta "a licença de vocês cobre biópsia/anestesia local?" vale ouro: é a
> diferença entre pagar R$0 a mais e ter que montar estrutura própria.

Se em algum momento vocês forem pra CNES/licença próprios (PJ locatária), o
custo tende a ser **baixo** (isento a poucas centenas de reais/ano, dado o
regime de risco simplificado de SP) — mas o "custo" real vira **processo e
vistoria**, não a taxa. Valor exato: confirmar com a **COVISA** (Av. Dr. Arnaldo
351, tel. 11 3065-4600).

## Próximos passos — caminho coworking (decidido)

### A. Regulatório e fiscal (caminho crítico — começa já)
1. **CREMESP** — ✅ **RESOLVIDO pra pessoa física**: a Bianca já tem
   **CREMESP 286882 · RQE 151282** (além do CRM-MG 83896 · RQE 70523), conforme
   o currículo. Falta só a **adequação/registro da PJ** no CREMESP pra operar em
   SP — o gargalo encolheu muito.
2. **Inscrição Municipal (CCM) na Prefeitura de SP** — pra emitir nota fiscal de
   serviço e recolher **ISS** em SP (a PJ é de MG). Confirmar com o contador.
3. **Fechar o coworking em Vila Mariana** — assinar só depois de confirmar:
   têm **CNES + licença próprios**? A licença **cobre procedimento com anestesia
   local** (biópsia/exérese)? **Te vinculam ao CNES** deles? **Suporta plano**?
   O que está **incluso no aluguel** (adesão, limpeza, secretária, materiais)?
4. **Vínculo ao CNES** do estabelecimento — RT/vínculo, com o **telefone
   comercial** como contato.
5. **Licença sanitária** — confirmada como do estabelecimento (coworking),
   cobrindo o nível de procedimento. Sem custo separado no caminho A.
6. **Credenciar nos planos** (SulAmérica, Bradesco) — com CREMESP + CNPJ + CNES
   + vínculo.

### B. Operação e tecnologia (AppFactory — em paralelo, ao fechar o endereço)
7. **Telefone comercial** — decidir se vira o número da **API oficial do
   WhatsApp** (não pode estar no app normal ao mesmo tempo) ou usar um separado.
8. **LP Bianca Dermato** + **Google Business Profile** (grátis, essencial pra
   busca local) + Instagram profissional.
9. **Sistema de agendamento + WhatsApp oficial** (confirmação, lembrete, encaixe,
   retorno de procedimento).
10. **Plataforma do médico + CRM v1** (agenda, ficha, CRM; voz/foto na evolução).
11. **LGPD** — termo de consentimento + **opt-in** no fluxo de agendamento desde
    o dia 1 + política de privacidade.
12. **Gateway de pagamento** pro particular (Pix/cartão).

### C. Go-live
13. **Semanas de operação manual** — observar padrões reais (no-show, tipos de
    mensagem) antes de automatizar.
14. **Ativar a automação** — confirmação/lembrete, fila de encaixe, retorno de
    procedimento; depois, com opt-in, reativação.

> **Os dois que começam hoje, em paralelo:** CREMESP (item 1) e a escolha do
> coworking (item 3). Eles destravam CNES → credenciamento. O resto encaixa
> atrás.

## O que já está resolvido (a favor de vocês)

- ✅ **PJ registrada** (CRM-MG) — falta só a adequação pra SP.
- ✅ **RQE + Título** — o que destrava o credenciamento como especialista.
- ✅ **Telefone comercial** — serve pro CNES e (com a ressalva acima) pra automação.

O que falta é, na ordem: **CREMESP → sala/endereço → licença → CNES →
credenciamento**. Os dois primeiros começam **em paralelo, agora**.
