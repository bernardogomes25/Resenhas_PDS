---
title: "Criteria for Modularization"
date: 1972-12-01
author: D. L. Parnas
source: https://dl.acm.org/doi/epdf/10.1145/361598.361623
---

## Resenha: Criteria for Modularization

### Introdução
Essa é uma daquelas leituras que parecem antigas à primeira vista, mas que dão um "estalo" na nossa cabeça sobre como realmente construir um sistema. O artigo de Parnas, escrito lá em 1972, é o tipo de texto que define a base do que estudamos hoje em Engenharia de Software.

O texto começa com uma pergunta simples, mas profunda: como devemos dividir um sistema em partes menores (módulos)?. Parnas observa que todo mundo concorda que "modularizar" é bom para diminuir o tempo de desenvolvimento e facilitar o entendimento do código. Porém, o que quase ninguém discutia na época eram os critérios usados para fazer esse corte. Para ilustrar isso, ele usa um exemplo de um sistema que organiza índices de palavras (KWIC) e mostra duas formas completamente diferentes de resolvê-lo.

---

### Principais Ideias

O ponto central que o Parnas defende é que a forma como a gente "corta" o bolo do software muda tudo no futuro. Ele coloca duas modularizações frente a frente para provar isso:

* **A Abordagem do Fluxograma (O jeito "óbvio"):** Sabe quando a gente desenha o passo a passo de um algoritmo?. "Primeiro o sistema faz A, depois faz B, depois C". Na primeira modularização, cada caixa do desenho vira um módulo.
    * **O Problema Escondido:** Como cada módulo é apenas um "passo" do processo, todos eles acabam precisando conhecer os detalhes íntimos de como os dados estão organizados (formatos de tabelas, índices, endereços de memória) para conseguir passar o bastão para o próximo.
    * **O Efeito Dominó:** Se você descobrir que o jeito que guardou os dados ficou lento e precisar mudar, terá que abrir e alterar praticamente todos os módulos do sistema, porque todos "sabem demais" uns sobre os outros.

* **A Abordagem do Escondimento de Informações (O jeito "Engenheiro"):** Aqui, o critério muda completamente. Em vez de pensar no "tempo" (o que vem primeiro), você pensa em decisões de design.
    * **Cada módulo é um cofre:** O objetivo de cada parte do código é esconder um segredo (uma decisão técnica difícil ou que pode mudar). Por exemplo, existe um módulo só para "Armazenamento de Linhas". Se o texto está compactado ou não, se está na RAM ou no disco, só ele sabe.
    * **Interfaces como Contratos:** Os outros módulos não acessam os dados direto; eles pedem educadamente através de funções (como "me dê o caractere X da palavra Y"). Assim, se você mudar o "segredo" dentro do cofre, ninguém do lado de fora precisa ser avisado ou alterado.

Parnas resume que o segredo de uma boa arquitetura é fazer uma lista de todas as coisas que você não tem certeza ou que podem dar errado no futuro e garantir que cada uma dessas incertezas fique "presa" dentro de um único módulo. Isso permite que várias equipes trabalhem sozinhas sem precisar ficar conversando o tempo todo sobre detalhes técnicos chatos, já que as interfaces são simples e estáveis.

---

### Crítica e Reflexão

Lendo hoje, percebemos que o que Parnas defendia é o que chamamos modernamente de Encapsulamento e Baixo Acoplamento. É impressionante como, mesmo antes das linguagens modernas que facilitam isso (como Java ou TypeScript), ele já previa que a maior dificuldade de um software não é fazê-lo funcionar na primeira vez, mas sim conseguir alterá-lo depois de um ano.

Um ponto interessante é que ele admite que essa divisão "inteligente" pode ser um pouco mais lenta para o computador processar no início, devido à troca de mensagens entre os módulos. No entanto, ele defende que a facilidade de manutenção e a clareza para o programador valem muito mais a pena do que essa pequena perda de performance.

---

### Conclusão

O artigo é um soco no estômago da nossa intuição de "fazer um fluxograma e começar a codar". Ele nos ensina que o papel do engenheiro de software não é apenas escrever código que a máquina entenda, mas desenhar uma estrutura que humanos consigam evoluir sem medo. Se você quer criar algo que dure e que não se torne um pesadelo para dar manutenção, comece listando o que é mais provável que mude no seu projeto e "esconda" essas incertezas dentro de módulos bem definidos.