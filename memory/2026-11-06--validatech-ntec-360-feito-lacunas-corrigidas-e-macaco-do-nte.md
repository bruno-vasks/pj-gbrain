---
title: 'ValidaTech (NTec): 360 feito, lacunas corrigidas e macaco do NTec no ar'
type: status
tags:
  - validatech
  - ntec
  - front
  - mascote
  - '360'
author: Caqui
date: '2026-11-06'
ts: '2026-11-06T18:50:17.803Z'
related: []
nextStep: >-
  Caqui decidir o push da nucleo/ntec. Depois: mandar ao Bruno o pedido de
  ícones na moldura (com a exceção de borda e o bug do Funil) e apresentar o 360
  ao pessoal do Tech.
---
Auditei o front V3 contra o Lovable, os RFs e o Miro, corrigi o que faltava e fiz o 360. O front V4 foi commitado em `validani-nucleos`, branch `nucleo/ntec` (commit 1ff8db1, só a pasta ntec/). O push ainda não foi feito.

O que entrou:
- **Guia do fluxo do Miro no Quadro:** os 7 passos, quem age em cada um e a coluna.
- **Painel da IA no card:** passos, barra com %, onde o resultado vai aparecer, "Ver o resultado" e erro.
- **Card:** ícones nas abas, etapas clicáveis, botão de próximo passo e "Devolver à fila".
- **Base:** "Novo registro" (feature, integração ou framework), filtro por tipo e candidatas aprovadas em um clique.
- **Fila:** resumo de cada card e carga do AS.
- **Pacote:** "Copiar" por bloco.
- **Defeitos corrigidos:** campos gigantes nos formulários e régua do ajuste com rótulos sobrepostos.

O macaco azul foi extraído da arte pelo processo do Lampião (`ntec/mascote/`).

São 71 testes passando. O material da apresentação está em `03 Em Desenvolvimento/(C) ValidaTech - 360 e lacunas.md`, com 31 prints, um vídeo de 3min14s e a tabela de lacunas antes/depois.

Os ícones nas abas do topo e na barra lateral dependem de mudança na moldura: é pedido para o Bruno.
