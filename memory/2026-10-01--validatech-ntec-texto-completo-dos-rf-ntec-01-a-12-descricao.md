---
title: >-
  ValidaTech (NTec): texto completo dos RF-NTec-01 a 12 (descrição + critério de
  aceitação)
type: fato
tags:
  - valida-ni
  - ntec
  - validatech
  - requisitos
  - prd
author: Caqui
date: '2026-10-01'
ts: '2026-10-01T19:58:49.378Z'
related:
  - 2026-10-01--validatech-ntec-secao-2-3-da-prd-reescrita-em-12-rfs-seguind
nextStep: ''
---
Versão detalhada da seção 2.3 (NTec) da PRD "Requisitos — Valida NI (por Núcleo)", de 2026-10-01. No Google Docs vai uma versão resumida em tabela; esta é a referência completa. O nome do produto é provisório, por isso o texto diz "a plataforma". Papéis: CN = Consultor de Negócios; AS = Analista Sênior (validador); CP = Gerente de Projetos.

## RF-NTec-01 — Abertura do card e registro dos insumos
**Descrição:** Quando a reunião de proposta com o cliente é marcada, o CN abre o card do projeto na plataforma e registra nele os três insumos da validação: a transcrição da reunião de AT com o cliente (e do aprofundamento, se houve), a descrição do protótipo feito no Lovable e a documentação das APIs e integrações do projeto. O escopo sai desses insumos. Não existe formulário de escopo para preencher à mão.
**Critério de aceitação:**
- O card fica vinculado a um cliente/deal identificado e registra a data da reunião de proposta.
- Transcrição da AT: entra sozinha quando a reunião foi gravada no Fathom. Se não foi, o CN cola ou anexa o texto. Se houve aprofundamento, a transcrição dele também entra.
- Link do protótipo: o CN informa o link do protótipo no Lovable (o front-end mockado), para o AS abrir e navegar pelas telas.
- Descrição do protótipo: o card mostra o prompt padrão de extração (RF-NTec-09), pronto para copiar. O CN roda esse prompt no chat do Lovable, que devolve uma descrição em texto do protótipo (telas, funcionalidades, dados exibidos, integrações), e cola essa descrição no card.
- A descrição traz só o que serve à validação. Estrutura de pastas, nomes de variáveis e parâmetros de código ficam de fora, porque são definidos pelo CP na Imersão.
- APIs e integrações: cada integração citada recebe documentação (arquivo ou link) com endpoints, formato e limites de dados, ou o CN marca "projeto sem integrações". Conseguir a documentação é responsabilidade do CN, mas qualquer membro do NTec pode anexar.
- Um insumo que não se aplica é marcado como "não se aplica", com uma linha de justificativa.
- O rascunho do PRD (RF-NTec-02) só é liberado quando os três insumos estão registrados ou marcados como "não se aplica".

## RF-NTec-02 — Rascunho do PRD gerado por IA
**Onde entra no fluxo:** na etapa 2, logo depois dos insumos. Substitui o passo "CN elabora o PRD": a IA escreve o rascunho, e o CN revisa, completa e submete.
**Descrição:** Com os insumos registrados (RF-NTec-01), a plataforma gera o rascunho do PRD no padrão ValeDOC, usando o prompt padrão do NTec. O CN revisa, completa e submete. Se preferir, o CN pode usar um prompt próprio, desde que o PRD siga a mesma estrutura.
**Critério de aceitação:**
- O rascunho é gerado a partir dos três insumos: transcrição da AT, descrição do protótipo e docs de API.
- A estrutura é obrigatória: Visão Geral; Notas e Abreviaturas (A(cli)D/SID); Requisitos Funcionais numerados por seção, com Regras de Negócio (RN-XX); Requisitos Não Funcionais; Exclusões Explícitas.
- Uma seção sem informação nos insumos aparece marcada como "não abordado na call". A IA nunca preenche com suposição.
- Cada requisito do rascunho indica de onde veio: um trecho da transcrição, uma tela do protótipo ou um doc de API.
- O CN pode editar tudo antes de submeter.
- Prompt próprio: o CN pode subir um PRD feito com outro prompt. A plataforma confere a estrutura obrigatória e registra que o PRD não usou o prompt padrão.
- Submeter o PRD dispara a pré-validação (RF-NTec-03).

## RF-NTec-03 — Pré-validação automática por IA
**Descrição:** Quando o CN submete o PRD, a plataforma roda sozinha a pré-validação técnica, usando o prompt padrão do NTec e a base de features (RF-NTec-07). O CN vê o resultado, corrige o que for preciso e só então envia o card para a fila. O objetivo é o card chegar redondo para o AS. Substitui o chat no Claude com o prompt da Hillary.
**Critério de aceitação:**
- Roda automaticamente quando o CN submete o PRD, sem nenhuma ação dele.
- Para cada feature, entrega: a viabilidade (viável / viável com ressalva, dizendo qual / inviável como está, dizendo por quê e sugerindo reduzir o escopo, atacar só parte do problema ou aumentar o dimensionamento); as horas estimadas; e a referência, que é o item da base usado na estimativa ou o aviso "sem referência na base".
- Cada estimativa vem com uma confiança: alta quando há referência na base, baixa quando não há.
- Uma integração ou API que não está na base aparece destacada como risco.
- Aponta ambiguidades técnicas (por exemplo, "tempo real" sem dizer se é polling ou websocket) e seções obrigatórias que estão faltando.
- Calcula a carga do card: a soma das horas e o nível leve / médio / pesado, com faixas de horas definidas pelo NTec. Essa carga aparece na fila (RF-NTec-04).
- O CN vê o resultado antes de enviar o card para a fila. Ele pode corrigir o PRD e rodar a pré-validação de novo, ou enviar como está.
- Uma seção obrigatória faltando bloqueia o envio para a fila. Os outros alertas não bloqueiam e seguem junto para o AS.
- Fica registrada a versão do prompt usada (RF-NTec-09).
- O resultado é sempre um rascunho: nunca aparece como "validado" e nunca libera a proposta.

## RF-NTec-04 — Fila de validação com aceite
**Descrição:** Depois que o CN envia o PRD pré-validado, o card entra na fila de validação do NTec. Os AS veem a fila com um resumo de cada card e aceitam os que querem validar, escolhendo pela afinidade técnica e pela própria carga de trabalho. A fila é ordenada pelo prazo, contado para trás a partir da reunião de proposta.
**Critério de aceitação:**
- Todos os AS do NTec veem a fila e podem aceitar cards. Os demais membros do NTec só visualizam.
- Cada card na fila mostra: o cliente; a data da reunião de proposta e o prazo-limite da validação (RF-NTec-10); as APIs e integrações, com destaque para as que não estão na base; o número de features; a carga estimada (horas e leve / médio / pesado) e a confiança da estimativa; e os alertas da pré-validação que ficaram em aberto.
- A fila é ordenada pelo prazo-limite, com o que vence primeiro no topo. Um card cuja reunião de proposta está muito próxima aparece marcado como urgente.
- Há filtros por API/integração e por nível de carga.
- O AS vê a própria carga atual: quantos cards está validando e a soma das horas.
- Aceitar é um clique: o card sai da fila e fica atribuído àquele AS. Cada card tem um AS só; se dois aceitarem ao mesmo tempo, vale o primeiro.
- O AS pode devolver à fila um card que aceitou, com um motivo de uma linha.
- Se ninguém aceitar até o prazo de aceite, o gerente de projetos é avisado e pode atribuir um AS manualmente.
- Um card que o AS devolveu ao CN para correção (RF-NTec-05) volta para o mesmo AS, e não para a fila.

## RF-NTec-05 — Validação técnica pelo AS
**Descrição:** O AS que aceitou o card (RF-NTec-04) faz a validação técnica humana. Ele revisa o PRD e a pré-validação, decide feature a feature, ajusta horas, registra ressalvas e premissas e, se precisar, edita o PRD. A validação termina com um feedback obrigatório ao CN e com o aceite explícito "Revisei o conteúdo gerado", que muda o status do card para "Validado". Sem esse status, nada segue para a proposta.
**Critério de aceitação:**
- Para cada feature, o AS escolhe entre: aprovada; aprovada com ressalva/premissa (texto obrigatório); ou fora do escopo (motivo obrigatório). O que fica fora do escopo entra sozinho nas Exclusões Explícitas do PRD.
- O AS confirma ou ajusta as horas de cada feature. Se mudar o valor da pré-validação, escreve um motivo de uma linha.
- O AS pode editar o PRD, e o histórico mostra o que mudou, quem mudou e quando.
- Se faltar informação, o AS devolve o card ao CN dizendo o que falta. Depois da correção, o card volta para o mesmo AS.
- O feedback ao CN é obrigatório, mesmo que seja "tudo certo, pode elaborar a proposta". Ele fica registrado no card, nunca no privado.
- Para virar "Validado", o AS precisa marcar "Revisei o conteúdo gerado". A plataforma registra quem validou e quando.
- Enquanto o card não está "Validado": o CN não recebe o pacote validado nem o prompt da proposta (RF-NTec-08), o card não avança para "Elaboração da proposta" e o PRD não pode ser exportado nem compartilhado fora da plataforma.
- Limite: a plataforma não impede o CN de mandar uma proposta ao cliente por fora, por exemplo por e-mail. O que ela faz é tornar isso inútil, porque sem validação ele não tem o pacote nem o prompt, e visível: se o deal no Pipedrive for para "proposta enviada" com o card ainda não validado, o gerente é avisado (desde que o NTec use o Pipedrive). Isso também deve virar regra de processo do núcleo.

## RF-NTec-06 — Feedback visível e consulta ao CP
**Descrição:** Toda a validação de um card (pré-validação, vereditos por feature, ressalvas e feedback do AS) fica registrada no card e visível para todo o NTec. Quando o AS precisa de alguém mais experiente, ele chama essa pessoa para dentro do card, sem repassar documentos nem criar grupo de WhatsApp.
**Critério de aceitação:**
- Qualquer membro do NTec abre qualquer card e lê o PRD, a pré-validação, os vereditos, as ressalvas e o feedback. Só quem está no card (CN, AS e convidados) escreve.
- O AS convida o CP ou outro AS com uma @menção. O convidado é notificado e vê todo o contexto do card.
- A conversa da consulta fica no card (no chat do card ou na thread do requisito), nunca no privado.
- O convidado comenta e sugere, mas o veredito e o "Validado" continuam sendo do AS do card.
- Os cards validados continuam disponíveis para consulta depois de fechados, com busca por cliente, feature e API.

## RF-NTec-07 — Base de features e integrações
**Descrição:** A plataforma mantém a base do NTec com as features e integrações já validadas e quanto elas custaram. A base é alimentada de forma semiautomática a partir dos cards validados e usada pela pré-validação, pelo AS e por qualquer membro que queira consultar.
**Critério de aceitação:**
- Cada item da base tem: nome; tipo (feature ou integração/API); horas de referência; ressalvas e premissas típicas; documentação e endpoints (no caso de integrações); os cards em que apareceu; e as horas reais, quando houver. ⚠️ É preciso confirmar com o NTec se os projetos registram horas por feature.
- Quando um card vira "Validado", as features e integrações dele viram candidatas à base.
- O gerente de projetos ou o AS que validou aprova cada candidata com um clique, edita antes de aprovar ou junta a candidata a um item que já existe. Antes da aprovação, a plataforma mostra os itens parecidos que já estão na base.
- Quando o AS ajusta as horas de uma feature que veio da base (RF-NTec-05), a plataforma sugere atualizar o item. Essa atualização também é aprovada com um clique.
- Qualquer membro do NTec consulta a base, com busca por nome e filtro por tipo.
- A pré-validação (RF-NTec-03) e a fila (RF-NTec-04) consultam a base automaticamente.

## RF-NTec-08 — Prompt da proposta
**Descrição:** Depois que o card vira "Validado", a plataforma monta o prompt para o CN elaborar a proposta numa ferramenta externa (por exemplo, o Claude Design). A plataforma não gera a proposta: ela entrega o pacote validado e o prompt pronto para copiar.
**Critério de aceitação:**
- O prompt só fica disponível quando o card está "Validado" (RF-NTec-05).
- O prompt leva as features aprovadas com as horas, as ressalvas e premissas, as exclusões explícitas, o total de horas e o modelo de proposta do NTec.
- O modelo de proposta da biblioteca (RF-NTec-09) define um nível mínimo de detalhe, igual para todos os CNs.
- Quando o design system da PJ existir, o prompt inclui as instruções dele. Enquanto não existir, o prompt funciona sem ele.
- O CN copia o prompt com um clique. Se o card for validado de novo, o prompt é refeito com o conteúdo novo.
- A plataforma registra quem copiou o prompt e quando.

## RF-NTec-09 — Biblioteca de prompts do NTec
**Descrição:** Os prompts padrão do NTec ficam numa biblioteca dentro da plataforma: extração do Lovable, rascunho do PRD, pré-validação e proposta. Não há um dono único: mais de uma pessoa edita, e o controle vem do versionamento.
**Critério de aceitação:**
- Há um prompt padrão ativo para cada etapa: extração do Lovable, PRD, pré-validação e proposta.
- Qualquer membro do NTec pode editar os prompts. Membros de outros núcleos nunca editam.
- Cada edição gera uma versão nova, com autor, data e motivo. Dá para comparar duas versões e voltar a uma anterior.
- Cada PRD, pré-validação e prompt de proposta registra a versão do prompt que usou.
- Quando o CN usa um prompt próprio (RF-NTec-02), isso fica registrado no card.
- Editar um prompt nunca altera cards que já foram validados.

## RF-NTec-10 — Prazos e notificações
**Descrição:** Os prazos da validação são contados para trás a partir da data da reunião de proposta. A plataforma avisa cada pessoa quando há algo para ela fazer e quando um prazo está perto de vencer, e com isso substitui o grupo de validação no WhatsApp.
**Critério de aceitação:**
- A partir da data da reunião de proposta, a plataforma calcula três prazos: o envio do PRD para a fila, o aceite pelo AS e a validação. Quantos dias antes da reunião vence cada um, o NTec define.
- Se a data da reunião mudar, os prazos são recalculados.
- Notificações: o card entra na fila → todos os AS; o AS aceita → o CN; o AS devolve para correção → o CN; o CN corrige → o AS do card; convite para consulta → o convidado; o card é validado → o CN, junto com o feedback; uma candidata entra para a base → o gerente de projetos e o AS que validou.
- Prazo perto de vencer → o responsável pela etapa. Prazo vencido → o responsável e o gerente de projetos.
- Os canais são os mesmos do ValidaNI: no app, e-mail e push. O WhatsApp é tratado na seção comum aos 5 núcleos.

## RF-NTec-11 — Métricas
**Descrição:** A plataforma mede se a validação do NTec está melhorando, com foco no superdimensionamento, que é o principal problema declarado pelo núcleo. Também mede se a plataforma está de fato sendo usada.
**Critério de aceitação:**
- Ajuste do AS: a diferença, por feature, entre as horas da pré-validação e as horas validadas pelo AS. Mostra se a IA superdimensiona e já funciona desde o primeiro card.
- Precisão do dimensionamento: horas validadas × horas reais, por feature e por projeto. ⚠️ É preciso confirmar com o NTec: essa métrica só existe se os projetos registrarem as horas reais gastas por feature. Se não registrarem, fica só o "ajuste do AS" até isso ser resolvido.
- O tempo de cada etapa (insumos → PRD na fila → aceite → validado) e a % de cards validados dentro do prazo.
- Retrabalho: quantas vezes o card voltou do AS para o CN.
- Uso: cards abertos por mês; % das propostas do NTec que passaram pela plataforma; % de PRDs feitos com o prompt padrão × com prompt próprio; consultas à base.
- Base: o número de itens e a % das features da pré-validação que tiveram referência na base.
- A unidade é sempre hora. Acima de um dia, a tela mostra também em dias, e quantas horas valem um "dia" o NTec define.
- As métricas ficam visíveis para todo o NTec.

## RF-NTec-12 — Login e perfis
Mantido do template base (RF-05 original do NI).

## Perguntas pendentes para o NTec
1. A extração do Lovable é um prompt no chat do Lovable que devolve uma descrição em texto?
2. Os projetos registram as horas reais gastas por feature?
3. Quantos dias antes da reunião de proposta vencem o aceite e a validação?
4. Quais são as faixas de horas de leve, médio e pesado?
