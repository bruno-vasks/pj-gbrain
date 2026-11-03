---
title: 'ValidaTech (NTec): telas na largura toda e commit na nucleo/ntec'
type: status
tags:
  - validatech
  - ntec
  - front
author: Caqui
date: '2026-11-03'
ts: '2026-11-03T19:47:20.072Z'
related: []
nextStep: >-
  Caqui decidir o push da nucleo/ntec. Depois: avisar o Bruno do bug do Funil
  (card de núcleo não abre com o mouse) e pedir a exceção de borda; seguir o
  roteiro (diagramas para o Rivas, gsap da aprovação, mascote, página de
  apresentação).
---
O front do ValidTech foi commitado em `validani-nucleos`, na branch `nucleo/ntec` (commit 255ef0d, só a pasta `apps/web/src/nucleos/ntec/`). O push ainda não foi feito.

O Caqui achou péssima a distribuição horizontal das telas. Ficou assim:
- **Quadro:** as 5 colunas dividem a largura da mesa. Antes ficavam presas em 268px e sobrava um quarto vazio à direita.
- **Fila, Minha fila e Arquivados:** a lista ocupa a largura toda, como as do ValidaNI. Cada linha mostra, em colunas alinhadas, as três respostas do cabeçalho do card: onde está, o que falta e o próximo prazo.
- **Base de conhecimento, Configurações e card:** usam duas colunas.

Conferido em 1768px, 1366px e no celular. Os 67 testes, o build e a conferência da pasta passaram. Os prints estão em `07 Attachments/ValidaTech - front V3 - *.jpg`.
