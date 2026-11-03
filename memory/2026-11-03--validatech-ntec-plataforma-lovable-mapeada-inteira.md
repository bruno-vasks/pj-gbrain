---
title: 'ValidaTech (NTec): plataforma Lovable mapeada inteira'
type: status
tags:
  - validatech
  - ntec
  - front-end
  - lovable
author: Caqui
date: '2026-11-03'
ts: '2026-11-03T15:35:15.589Z'
related: []
nextStep: >-
  Decidir com o Rivas se, quando os dois divergem, vale o Lovable ou os RFs (e o
  ponto brief × extração do protótipo). Depois, montar o plano de telas do NTec
  no repo e pedir OK antes de codar.
---
Mapeei o protótipo do NTec no Lovable a partir do código das rotas e da navegação pelos 4 perfis (CN, AS, Admin, Membro). A nota está em `02 Especificação/(C) ValidaTech - mapa da plataforma Lovable (NTec).md` e cobre: as 8 rotas, as 8 abas do card, a máquina de estados com 5 colunas, a matriz de permissões, o modelo de dados e o cruzamento com os RFs.

Clonei também o repositório `bruno-vasks/validani-nucleos`. O front do NTec vai em `apps/web/src/nucleos/ntec/`, que hoje só tem o Funil com dados falsos. Regras do repositório: trabalhar na branch `nucleo/ntec`, usar o design system Bruma (sem bordas, sem cor decorativa, no máximo dois destaques pretos por tela), mostrar o plano antes de editar e marcar com `ASSUMPTION:` toda regra inventada. A skill UI UX Pro Max está no próprio repositório, em `.agents/skills/ui-ux-pro-max`.
