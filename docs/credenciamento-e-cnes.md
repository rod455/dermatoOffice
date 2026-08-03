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

## O que já está resolvido (a favor de vocês)

- ✅ **PJ registrada** (CRM-MG) — falta só a adequação pra SP.
- ✅ **RQE + Título** — o que destrava o credenciamento como especialista.
- ✅ **Telefone comercial** — serve pro CNES e (com a ressalva acima) pra automação.

O que falta é, na ordem: **CREMESP → sala/endereço → licença → CNES →
credenciamento**. Os dois primeiros começam **em paralelo, agora**.
