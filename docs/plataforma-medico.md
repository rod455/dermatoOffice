# Plataforma do médico (+ CRM)

A automação de WhatsApp cuida do paciente **antes** da consulta (agendar,
confirmar, lembrar). A **plataforma do médico** é o outro lado: o painel onde a
Bianca vê e opera o que acontece **dentro e depois** da consulta. As duas coisas
compartilham a mesma base de dados — o CRM — e evoluem juntas.

Responsável pela construção e manutenção: **AppFactory**.

## O que a plataforma faz (v1)

Painel simples, pensado pra ser usado no consultório, no celular ou no
computador:

- **Agenda** — a Bianca enxerga o dia/semana: horários, encaixes, retornos.
  Puxa da mesma agenda que a automação usa (plano no app da operadora +
  particular no sistema).
- **Qual paciente** — quem é o próximo, histórico rápido, se é primeira vez ou
  retorno, convênio ou particular.
- **Ficha / anotações do paciente** — onde ela anota o que precisa: o que foi
  feito, o que foi indicado, o que remarcar, observações. (Prontuário clínico
  formal, se for o caso, segue as exigências do CFM/CRM — a plataforma respeita
  isso, não substitui.)
- **CRM** — cada paciente vira um registro que acumula histórico: consultas,
  procedimentos feitos, procedimentos indicados/pendentes, data do último
  contato, se deu opt-in pra marketing.
- **Inputs dos principais clientes** — a Bianca marca/destaca os pacientes-chave
  (recorrentes, alto valor, candidatos a estética) e dá inputs sobre eles. Isso
  vira inteligência pra recompra e pra priorização.

## A evolução: visão + automação andando juntas

Aqui é o pulo do gato, e é o que você pediu: **facilitar o preenchimento do CRM
pelo próprio médico**, pra não virar trabalho chato de digitar. A plataforma e
a automação evoluem em conjunto, com o Claude no meio:

- **Anotação por voz** — a Bianca fala ("paciente João, tirei uma pinta nas
  costas, indiquei retorno em 30 dias pra biópsia"), o Claude transcreve,
  estrutura e preenche a ficha e o CRM sozinho. Ela só revisa.
- **Foto** — foto da lesão/pele anexada ao registro do paciente, organizada por
  data (útil pra acompanhar evolução de um caso ao longo do tempo). *A leitura
  clínica é sempre da Bianca — a plataforma organiza e arquiva, não diagnostica.*
- **Preenchimento assistido** — o Claude sugere o próximo passo a partir do que
  ela anotou (ex.: "quer que eu já agende o retorno e crie o lembrete?") e
  dispara a automação de WhatsApp correspondente.
- **Do CRM pra ação** — quando a Bianca destaca um paciente-chave ou marca um
  procedimento pendente, a automação puxa o retorno na hora certa
  (respeitando o consentimento registrado). O que ela anota vira follow-up
  automático, sem ela precisar lembrar.

> **A ideia central:** a Bianca fala/fotografa, o sistema estrutura, e o CRM se
> preenche quase sozinho. Menos digitação, mais dado aproveitável. O médico
> alimenta o sistema no fluxo natural do atendimento, e o sistema devolve
> agenda cheia e recompra.

## Como isso conversa com a automação de WhatsApp

```
   CONSULTA                        DEPOIS
┌────────────┐   voz/foto/nota   ┌──────────────┐
│  Bianca    │ ────────────────► │  Plataforma  │
│ (atende)   │                   │   + CRM      │
└────────────┘                   └──────┬───────┘
                                        │ gatilhos (retorno, opt-in)
                                        ▼
                                 ┌──────────────┐
                                 │  Automação   │
                                 │   WhatsApp   │  confirma, lembra,
                                 └──────────────┘  puxa retorno, reativa
```

O CRM é o coração: a plataforma do médico **alimenta** e a automação de
WhatsApp **age**. Mesma base, dois lados.

## Compliance embutido

- **LGPD** — dado clínico e lista de marketing ficam segregados; opt-in
  registrado por paciente; foto e nota são dado sensível e tratados como tal.
- **Papel clínico intocado** — a plataforma nunca diagnostica nem orienta;
  organiza, transcreve e arquiva. Decisão clínica é 100% da Bianca.

## Faseamento

A plataforma não nasce pronta. Ordem:

1. **v1** — agenda + ficha do paciente + CRM básico (texto).
2. **v2** — anotação por voz + foto no registro.
3. **v3** — preenchimento assistido + gatilhos automáticos do CRM pra
   automação de WhatsApp.

Constrói-se em cima do uso real — igual a automação de agendamento, a gente
observa como a Bianca trabalha antes de automatizar o que importa.
