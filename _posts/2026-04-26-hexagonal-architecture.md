---
title: "Hexagonal Architecture"
date: 2026-04-26
author: Alistair Cockburn
source: https://alistair.cockburn.us/hexagonal-architecture
---

## Resenha: Hexagonal Architecture

### Introdução

A Arquitetura Hexagonal, idealizada por Alistair Cockburn, propõe uma mudança estrutural na forma como pensamos o isolamento de um software em relação ao seu ambiente externo. A ideia central é que uma aplicação deve ser capaz de operar de forma imparcial às tecnologias de interface ou de armazenamento, comunicando-se com o mundo fora de suas fronteiras através de "portas" que definem protocolos de conversa e "adaptadores" que traduzem esses protocolos para ferramentas específicas. Ao tratar usuários, bancos de dados e testes automatizados de forma simétrica, o padrão busca evitar que a lógica de negócio seja contaminada por detalhes técnicos, garantindo que o núcleo do sistema permaneça testável e funcional mesmo que os componentes externos ao redor do hexágono sejam completamente substituídos.

---

### Principais Ideias

O objetivo central do padrão é permitir que uma aplicação seja desenvolvida, testada e operada de forma isolada de seus dispositivos de tempo de execução e bancos de dados. O artigo propõe uma mudança de perspectiva ao substituir as tradicionais visões de camadas assimétricas por uma visão de simetria entre o dentro e o fora da aplicação. Essa abordagem visa combater problemas históricos do desenvolvimento de software, como a infiltração de lógica de negócio na interface do usuário ou o acoplamento excessivo com serviços externos.

* **Sincronia e Simetria**: O padrão estabelece que tanto o lado do usuário quanto o lado do servidor causam problemas similares de design quando há o entrelaçamento entre a lógica de negócio e entidades externas.
* **Portas e Adaptadores**: Uma "porta" define um protocolo de conversa com o mundo externo através de uma API. Para cada dispositivo externo, existe um "adaptador" que converte essa definição de API nos sinais específicos exigidos pela tecnologia, seja ela uma interface gráfica (GUI), um script de teste automatizado ou um banco de dados SQL.
* **Independência de Tecnologia**: A aplicação deve ser capaz de funcionar sem uma interface de usuário ou banco de dados real. Isso permite a execução de testes de regressão automatizados contra a aplicação em modo isolado, utilizando mocks de memória para substituir bancos de dados reais.
* **Assimetria Interna vs. Externa**: A figura do hexágono é utilizada para destacar visualmente que não importa se a interação vem da esquerda ou da direita, mas sim se ela está dentro ou fora da fronteira da aplicação.
* **Atores Primários e Secundários**: Na implementação, as portas são divididas entre primárias (que dirigem a aplicação, como usuários ou testes) e secundárias (que são dirigidas pela aplicação, como bancos de dados ou sistemas de notificação).

---

### Crítica e Reflexão

A maior contribuição reflexiva de Cockburn é a desconstrução da "mentira" das arquiteturas em camadas tradicionais. Ele argumenta que, embora as organizações prometam manter a lógica de negócio separada, a falta de um mecanismo físico que impeça vazamentos acaba resultando em sistemas onde a interface e o banco de dados dominam o comportamento do software. O hexágono não é uma regra matemática sobre o número seis, mas um símbolo de liberdade criativa; ele existe para que o arquiteto tenha espaço para desenhar quantas conexões forem necessárias sem se sentir preso a uma pilha vertical.

Uma reflexão profunda presente no texto é sobre a natureza humana no desenvolvimento: o autor aponta que o acoplamento excessivo gera custos de atraso e sentimentos negativos entre os membros da equipe quando o trabalho de um depende da disponibilidade tecnológica de outro. Ao adotar as portas e adaptadores, o desenvolvimento deixa de ser um processo sequencial e dependente para se tornar uma atividade paralela, onde a lógica de negócio pode ser finalizada antes mesmo de se decidir qual banco de dados ou interface será usada. Além disso, Cockburn propõe que os casos de uso devem ser escritos focando na fronteira da aplicação, o que os torna mais curtos, legíveis e imunes às mudanças constantes de tecnologias externas.

---

### Conclusão

A Arquitetura Hexagonal resolve o pesadelo de manutenção e testes ao transformar as interfaces do sistema em componentes substituíveis. Ao tornar a aplicação executável em modo isolado e através de APIs visíveis, o padrão permite que suítes de software complexas sejam desmembradas e reconectadas sob demanda. Cockburn conclui que o benefício fundamental de Portas e Adaptadores é a capacidade de isolar a lógica central de negócio das mudanças tecnológicas externas, garantindo que o software permaneça testável e funcional mesmo diante da instabilidade de interfaces ou serviços de back-end. O padrão se consolida como uma aplicação estratégica do padrão Adapter, focada na criação de sistemas simétricos, robustos e preparados para o futuro.