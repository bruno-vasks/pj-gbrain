---
title: 'ValidaTech (NTec): prompt do 360 e da auditoria pronto'
type: status
tags:
  - validatech
  - ntec
  - front
  - mascote
author: Caqui
date: '2026-11-06'
ts: '2026-11-06T17:54:31.178Z'
related: []
nextStep: >-
  Rodar o prompt do 360: auditoria nos 4 perfis, correções, mascote do NTec e
  gravação. Push da nucleo/ntec continua pendente de decisão do Caqui.
---
Montei o prompt para o próximo passo do ValidaTech. A tarefa é auditar o front V3 contra o Lovable, os RFs e o Miro; corrigir as lacunas; gerar o mascote do NTec; e gravar o 360 (prints por fluxo + vídeo) para mostrar ao pessoal do Tech. O prompt aponta as fontes no vault: o mapa do Lovable, os RFs, a seção NTEC do Miro e o plano de telas.

O gerador de pixel art do Lampião fica em `validani-nucleos/apps/web/scripts/gen-mascote.py` e lê `mascote.sprite.txt` (31x48). Ele escreve em `src/components/mascote.desenho.ts`, fora da pasta `ntec/`, então o mascote do NTec (macaco azul hacker) precisa de um sprite e de uma saída novos dentro de `ntec/`.
