---
title: "Entre Releases — 2026-10-28"
authors: [ALVR]
tags: [entre-releases]
date: 2026-10-28
---

<!--
Modelo de entrada do diário de bordo. Duplique este arquivo uma vez por fase
(5 no semestre todo), renomeando para algo como
blog/2027-03-10-formacao-de-equipe.md, e preencha:

- title: nome da fase + data
- authors: seu pseudônimo (o MESMO em todas as entradas)
- tags: o slug da fase:
    formacao-equipe | pre-release-1 | entre-releases | pre-release-2 | pos-entrega
- date: data da entrada (YYYY-MM-DD)

O bloco entre "---" acima (front matter) não aparece na tela — ele existe só
para scripts/export-entries.mjs conseguir montar o pacote de dados no fim do
semestre. Não apague nem renomeie essas chaves.

Depois de criar o arquivo, adicione um link para ele em _sidebar.md, na
seção "Minhas entradas", para ele aparecer na navegação do site.

NÃO coloque nome real, matrícula, e-mail ou usuário do GitHub real em nenhum
campo ou no corpo do texto. As perguntas completas de cada fase estão em
docs/perguntas.md.
-->

## Como o feedback recebido (de colegas, professora, monitoria) tem influenciado o que vocês estão fazendo agora?

_Nas três semanas depois da R1, praticamente todo o trabalho da equipe foi guiado pelo feedback que recebemos. O ponto mais visível foi a gamificação: a professora e os monitores sugeriram que pensássemos em formas de fazer o usuário voltar ao site todos os dias, e isso virou um bloco inteiro de requisitos novos para a Release 2 envolvendo pontos, sequência semanal, patente, ranking e a Bandeja de Ouro, um ícone que irá funcionar como uma conquista dentro do PWA, para os primeiros colocados de cada campus. Outro feedback que mudou bastante o projeto veio de uma orientação da professora: perguntar ao usuário, algum tempo depois do check-in, se ele já saiu da fila. Isso criou um dado que não tínhamos pensado, o tempo de espera, e fez a gente repensar como a previsão de pico é mostrada. Também seguimos a crítica de que os requisitos funcionais estavam parecidos com histórias de usuário e com critérios de aceite grandes demais: uma colega fez uma revisão grande no documento de requisitos para enxugar os RFs e os critérios._

## Descreva como as decisões técnicas estão sendo tomadas na sua equipe nesta fase — quem decide, como se chega a um consenso.

_Nesta fase, as decisões técnicas passaram a ser registradas em ADRs. Eu escrevi duas delas logo depois da R1, baseadas no feedback dado pela professora: a ADR 0009, sobre fazer a detecção do campus no próprio aparelho (para que as coordenadas do usuário não precisem ir para o servidor só para abrir o cardápio), e a ADR 0010, sobre como usar o tempo de espera na previsão de pico. Na ADR 0010 tínhamos três opções: usar o tempo de espera só como informação extra, calcular o nível da fila inteiramente por ele, ou um modelo híbrido. Escolhemos a primeira, porque as respostas à pergunta de saída da fila provavelmente serão bem menos frequentes que os check-ins, e não queríamos que a previsão ficasse instável. Escrever as opções lado a lado, com os prós e contras, deixou a discussão no grupo mais objetiva. Em vez de cada um defender uma ideia, a conversa girava em torno de requisitos concretos. Um exemplo de decisão que mudou no meio do caminho foi o ranking da gamificação: ele começou mensal e, alguns dias depois, foi revisado para semestral e por campus, o que também mudou a ADR 0011.  Em geral, quem está mais próximo do assunto escreve a proposta e o restante revisa no Pull Request antes do merge. A conclusão que tiro é que registrar a decisão por escrito obriga a gente a justificar a escolha, e isso evita voltar à mesma discussão depois. Creio que a única coisa diferente que eu faria é tentar envolver mais o grupo nessas decisões, mas por questões de horário e logística, nem sempre todos conseguem participar das em reuniões que tomamos essas decisões._

## Que lacunas técnicas ainda te incomodam, e o que você tem feito, ou pretende fazer, a respeito?

_A lacuna que mais me incomoda agora é a implementação do backend, pois o planejamento inicial era que tivéssemos começado a implementação há 10 dias, mas durante todo esse tempo nós ficamos trabalhando na documentação do projeto que mudou consideravelmente com a gamificação (principalmente os diagramas de arquitetura do backend). Isso foi necessário, porque as mudanças da R2 (GPS, pergunta de saída da fila, gamificação) mexem diretamente no modelo de dados e na API, mas faz com que eu ainda não me sinta seguro com o Django REST Framework na prática: estudei a teoria, mas ainda não construí um endpoint real do projeto. Uma lição que já apareceu na review da Sprint 4 é que a documentação consumiu mais tempo do que o estimado e comprimiu o tempo de desenvolvimento, e está se repetindo agora. Apesar de ter menos tempo para implementar o projeto, creio que tudo ainda ocorrerá dentro do esperado e não haverá nenhum atraso em relação à entrega completa._
