---
title: 'ValidaTech (NTec): front V1 construído no validani-nucleos'
type: status
tags:
  - validatech
  - ntec
  - front-end
author: Caqui
date: '2026-11-03'
ts: '2026-11-03T16:49:08.358Z'
related: []
nextStep: >-
  Caqui revisar no navegador (localhost:5177/n/ntec), fazer commit e push na
  branch nucleo/ntec e levar ao Rivas as perguntas: brief × extração do
  protótipo e semana × sprint.
---
O front do ValidTech está construído em `validani-nucleos/apps/web/src/nucleos/ntec/`, na branch `nucleo/ntec`, ainda sem commit. A tela provisória saiu.

O que tem:
- **Quadro** com as 5 colunas do Lovable. O card abre em `?card=` e tem 8 abas, comentários, prazos D-3/D-2/D-1, as 6 etapas e o checklist de envio.
- **Aba Fila**, onde o AS assume cards.
- **Minha fila** e **Arquivados**, que mudam conforme o perfil.
- **Base de conhecimento**, como item próprio do menu.
- Seletor **"Ver como"** com CN, AS, CP, Administrador e Membro.

O que entrou dos RFs: pré-validação, veredito por feature, aceite "Revisei", pacote validado de 8 blocos e o botão do Canva desabilitado.

Verificação: build ok, 58 de 58 testes dos núcleos (16 deles das regras novas), `conferir-nucleo` ok e as telas conferidas no navegador, no computador e no celular.

As suposições estão marcadas com `ASSUMPTION` no código: 1 sprint = 1 semana, divisão dos prazos e simulações da IA e do Fathom.
