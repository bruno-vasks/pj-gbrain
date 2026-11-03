---
title: 'ValidaTech (NTec): front V2, cards clicáveis e telas completas'
type: status
tags:
  - validatech
  - ntec
  - front-end
author: Caqui
date: '2026-11-03'
ts: '2026-11-03T17:22:01.221Z'
related: []
nextStep: >-
  Caqui revisar no navegador. Depois: commit e push na nucleo/ntec; avisar o
  Bruno do bug do Funil e pedir a exceção de borda; seguir o roteiro de skills
  (diagramas para o Rivas, gsap da aprovação, mascote e página de apresentação).
---
Refiz o front do ValidTech em `validani-nucleos/apps/web/src/nucleos/ntec` (branch `nucleo/ntec`, ainda sem commit).

**Causa do card que não abria:** o `comum/Funil.tsx`, que é do Bruno, desenha o link da ficha com `pointer-events: none` e não põe `onClick` no card. Com isso, nenhuma ficha de núcleo abre com o mouse. O NTec agora tem um quadro próprio.

**O que entrou:**
- O card no formato do dossiê do NI: laje com três respostas (onde está, o que falta, próximo prazo), etapas e 8 abas.
- Configurações do NTec, cobrindo o Perfil e o Admin do Lovable: chave do Fathom e papéis do time.
- Downloads de PRD, protótipo, proposta técnica e pacote.
- Estados do PRD (na fila, em execução, concluído) com carregamento visível.
- Aba Validação por deferência: seletor de veredito deslizante e campo que abre a linha.
- Aviso de cada ação no canto da tela.
- Passada de texto com o humanizer.

**Verificação:** 67 testes passando, 7 deles clicando os fluxos de ponta a ponta; build e `conferir-nucleo` ok. Prints em `07 Attachments/ValidaTech - front V2`.
