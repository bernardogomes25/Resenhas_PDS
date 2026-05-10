---
title: "Design by Contract"
date: 2026-05-10
author: Bertrand Meyer
source: https://github.com/joaopauloaramuni/projeto-de-software/blob/main/ARTIGOS/Design-by-Contract.pdf
---

## Resenha: Design by Contract

### Introdução

O artigo Design by Contract, de Bertrand Meyer, estabelece uma base teórica para a construção de softwares confiáveis fundamentada na metáfora do contrato. O autor apresenta o desenvolvimento de sistemas como uma sucessão de decisões documentadas entre partes que interagem, visando solucionar o problema da falta de robustez e correção no código. A analogia central, que utiliza as obrigações e benefícios mútuos de um contrato comercial, serve para ilustrar como a clareza nas responsabilidades pode transformar a prática da programação orientada a objetos.

---

### Principais Ideias

A teoria proposta por Meyer funciona como um mecanismo de organização rigorosa da construção de software. Suas ideias centrais giram em torno do seguinte:

* **O Acordo entre Rotinas (Assertivas):** O autor propõe que cada componente de software deve definir explicitamente suas condições de operação. Através de pré-condições, pós-condições e invariantes de classe, o sistema documenta o que um fornecedor exige para funcionar e o que ele garante entregar. Essa abordagem não serve apenas para documentação, mas como uma ferramenta de design que assegura que cada chamada de rotina ocorra em um estado válido, evitando a propagação de erros silenciosos.


* **A Rejeição à Programação Defensiva:** Meyer critica a prática comum de incluir verificações redundantes em todos os níveis do código, o que muitas vezes resulta em sistemas complexos e difíceis de manter. Ao aplicar o Design by Contract, a responsabilidade é atribuída a apenas uma das partes: ou o cliente garante a pré-condição, ou o fornecedor trata o caso. Isso permite que os desenvolvedores foquem na lógica útil do processamento, eliminando o excesso de código de tratamento de erros que prejudica a clareza da arquitetura.


* **Disciplina no Tratamento de Exceções:** O texto redefine o conceito de exceção como a incapacidade de uma rotina em cumprir seu contrato. Meyer estabelece leis rígidas para o tratamento dessas situações, sugerindo que uma rotina só pode reagir de duas formas: tentando uma nova estratégia para cumprir o acordo (resunção) ou admitindo a falha e notificando o chamador (pânico organizado). Esse modelo evita que o sistema "finja" que uma operação foi bem-sucedida quando, na verdade, os objetivos não foram alcançados.


* **Subcontratação e Herança:** Um ponto fundamental é a interpretação da herança e do polimorfismo sob a ótica contratual. Meyer introduz a ideia de que uma classe descendente é um subcontratante. Para manter a integridade do sistema, o subcontratante pode ser mais eficiente ou oferecer resultados melhores, mas nunca pode exigir mais do cliente do que o contrato original previa. Essa lógica é formalizada na regra de que redefinições podem enfraquecer pré-condições e fortalecer pós-condições, garantindo a segurança do dynamic binding.



---

### Crítica e Reflexão

Uma reflexão importante extraída do conteúdo é o equilíbrio entre a simplicidade do design e a segurança na execução. O Design by Contract promove um rigor que beneficia a confiabilidade, mas Meyer reconhece o desafio de integrar essas técnicas formais na prática comum, que muitas vezes prioriza a flexibilidade em detrimento da correção. O autor alerta que o uso indevido de mecanismos de exceção sem uma base metodológica clara pode tornar o software tão perigoso quanto um sistema sem qualquer proteção.

Além disso, é interessante notar como o autor posiciona o monitoramento de assertivas. Embora funcionem como ferramentas de depuração e garantia de qualidade, as assertivas pertencem ao mundo descritivo das especificações. A distinção entre o que o software faz e o que ele deve ser é o que permite, segundo Meyer, que a complexidade seja gerenciada de forma que os componentes individuais permaneçam simples e focados em tarefas bem definidas.

---

### Conclusão

O Design by Contract é um exercício de transparência e responsabilidade na engenharia de software. Ele reconhece que, para criar sistemas sofisticados e robustos, não se deve buscar componentes que funcionem em qualquer circunstância mágica, mas sim componentes que declarem com precisão o que farão e o que exigem para tal.

Ao adotar essa postura contratual, o desenvolvimento torna-se mais previsível e a manutenção menos custosa. O custo dessa abordagem é a necessidade de uma análise mais profunda das interfaces e dos estados do sistema, mas esse é um investimento necessário para superar o caos das dependências implícitas e dos erros não documentados. No fim, o trabalho de Meyer demonstra que a confiabilidade do software não nasce da quantidade de verificações manuais, mas da solidez dos acordos estabelecidos entre suas partes.