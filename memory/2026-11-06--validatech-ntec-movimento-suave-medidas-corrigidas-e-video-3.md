---
title: 'ValidaTech (NTec): movimento suave, medidas corrigidas e vídeo 360 v2'
type: status
tags:
  - validatech
  - ntec
  - front
  - motion
  - '360'
author: Caqui
date: '2026-11-06'
ts: '2026-11-06T19:29:02.365Z'
related: []
nextStep: >-
  Caqui assistir o vídeo v2 e decidir o push da nucleo/ntec. Depois: pedido de
  ícones na moldura para o Bruno e apresentar ao pessoal do Tech.
---
Segunda passada no front do ValidTech, commit dd6e1f3 na `nucleo/ntec` (push não feito). Usei os princípios do Fluid Interfaces da Apple e do Emil Kowalski.

**Movimento:**
- Nada surge de repente: os blocos abrem a altura ao entrar e fecham pelo mesmo caminho ao sair.
- O painel da IA fica logo acima da aba, com a barra contínua e "passo N de M".
- As abas têm uma pílula que desliza.
- As fichas do quadro entram em cascata, e o card criado ou movido acende.
- Listas e telas entram em esmaecer.

**Medidas corrigidas:** abas alinhadas, botões com 40px ao lado dos campos, botão desabilitado com forma, cantos alinhados pelo topo e data da proposta sem corte.

**Vídeo v2 (6min51s):** capítulos por passo do Miro, rolagem suave, anel de destaque e gravação a 30fps constantes pelo screencast do DevTools com o ffmpeg. Os 71 testes passam. A nota é `03 Em Desenvolvimento/(C) ValidaTech - 360 e lacunas.md`.
