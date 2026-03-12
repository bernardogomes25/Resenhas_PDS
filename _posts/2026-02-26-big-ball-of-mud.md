---
title: "Big Ball of Mud"
date: 1997-08-26
author: Brian Foote and Joseph Yoder
source: https://www.researchgate.net/publication/2938621_Big_Ball_of_Mud
---

# Resenha: Big Ball of Mud

## Introdução

O artigo analisa por que o modelo de arquitetura de software mais comum na prática é o chamado "Big Ball of Mud", em vez de estruturas organizadas e elegantes. Uma "Big Ball of Mud" é um sistema estruturado de forma casual ou até descuidada, onde a organização é guiada mais pela conveniência do que pelo planejamento. Os autores exploram como pressões reais, como prazos e custos, levam bons programadores a criar sistemas desordenados, mas que mesmo assim se tornam o padrão da indústria por sua eficácia rápida.

---

## Principais Ideias

O texto detalha como forças externas e decisões internas direcionam a evolução de um sistema à desordem:

* **Forças Globais**: Tempo, custo, inexperiência e mudanças constantes de requisitos são os principais motores que direcionam o desenvolvimento para soluções rápidas e desorganizadas.
* **Código Descartável**: É o código escrito para ser usado apenas uma vez, mas que acaba sendo mantido e expandido por funcionar bem o suficiente para o momento.
* **Crescimento Fragmentado**: À medida que um sistema ganha novos requisitos, ele cresce aos poucos, muitas vezes de forma descontrolada, o que pode destruir qualquer estrutura original que existisse.
* **Mantenha Funcionando**: Esta estratégia prioriza a manutenção da vitalidade do sistema, selecionando apenas mudanças que não quebrem a operação atual, mesmo que isso signifique adiar melhorias arquiteturais.
* **Varrendo para Debaixo do Tapete**: Consiste em identificar partes confusas do código e isolá-los atrás de uma interface limpa ou "fachada", escondendo a bagunça para que o resto do sistema possa interagir com ela de forma mais simples.
* **Reconstrução**: Quando o código se torna incompreensível, a única alternativa é descartar a implementação antiga e começar uma nova do zero, aproveitando apenas a experiência acumulada.

---

## Crítica e Reflexão

Os autores fazem uma crítica provocativa à visão tradicional de que a bagunça é sempre um sinal de má vontade. Eles comparam o software a "favelas", que surgem para resolver necessidades imediatas de moradia usando materiais baratos e mão de obra disponível. Essa analogia mostra que, mesmo que a maioria prefira cidades planejadas, as favelas já cumprem um papel essencial de sobrevivência ao trazer recursos disponíveis para o problema.

A reflexão central é que uma arquitetura prematura pode se tornar uma "camisa de força", impedindo que o sistema aprenda e se adapte ao real problema. A "lama" inicial permite que a funcionalidade encontre seu lugar antes de ser engessada por regras rígidas. De qualquer forma, a negligência contínua faz o sistema se degradar como um bairro decadente, onde bons programadores se recusam a trabalhar e a manutenção se torna muito cara.

---

## Conclusão

A Grande Bola de Lama é, frequentemente, o caminho de menor resistência para entregar software funcional em mercados rápidos e competitivos. O artigo conclui que, embora a desordem inicial seja natural, a sobrevivência do software a longo prazo exige uma limpeza contínua através da refatoração. A ideia não é tentar evitar a bagunça completamente, mas entender as forças que a criam e saber o momento certo de consolidar as partes confusas em componentes robustos e reutilizáveis.

O artigo apresenta uma visão realista e quase empática sobre a desordem técnica, desafiando a afirmação de que o design perfeito deve existir antes da execução. A defesa de que a "lama" possui méritos práticos (como a facilidade de aprendizado e a resposta rápida ao mercado) é um choque de realidade necessário para profissionais da engenharia de software.

O perigo dessa abordagem é que ela pode "validar" a mediocridade, dependendo da interpretação do leitor. O texto acerta ao humanizar o processo de desenvolvimento e suas pressões financeiras, ele deixa claro que a "lama" só é aceitável como uma estação de transição. O maior valor desse artigo não é autorizar o código ruim, mas sim ensinar a reconhecer as variáveis que o produzem para que o arquiteto possa combatê-las no momento correto.