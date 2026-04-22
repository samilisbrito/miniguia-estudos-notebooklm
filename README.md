# miniguia-estudos-notebooklm
O desafio propõe a criação de um caderno temático no NotebookLM, reunindo de três a cinco fontes abertas em texto ou PDF sobre boas práticas no frontend

## OBJETIVO:
Criar um segundo cérebro baseado sobre o essencial de conhecimento de frontend.

## FRONTES DE VÍDEO:
https://youtu.be/9-r0RuX0pqk
https://www.youtube.com/playlist?list=PLdDT54c2vNM4NW8wXHcdfQPOzVxyvMWpI
https://www.youtube.com/watch?v=ppYfFT9gEbY
https://www.youtube.com/watch?v=Ie1tXvrSu18
https://youtu.be/GI8zxLviMog
https://youtu.be/J-lHpiu-Twk
https://www.youtube.com/watch?v=VStSGMkR0v0
https://youtu.be/6SfrO3D4dHM

## FONTES DE TEXTO:
https://www.alura.com.br/artigos/o-que-e-clean-code?srsltid=AfmBOooJ1U7Eiv5tlnEmYivHySVuPBFNJypYP44O2051yj-D2TxlmGV1
https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html
https://dev.to/nlapointe/clean-architecture-infrastructure-vs-core-492k
https://dev.to/nlapointe/clean-architecture-infrastructure-vs-core-492k

# Arquitetura moderna do frontend
As fontes exploradas abordam os fundamentos e a evolução da arquitetura de software, focando especialmente em práticas para o desenvolvimento de sistemas robustos e escaláveis. O conteúdo detalha princípios de Clean Code, enfatizando a importância de nomes significativos e a redução de complexidade técnica para garantir a legibilidade do código. Além disso, os textos explicam o modelo de Clean Architecture, destacando a separação de preocupações e a regra de dependência para criar aplicações independentes de frameworks. Por fim, há uma análise histórica da arquitetura front-end, discutindo a transição de páginas estáticas para SPAs e micro front-ends. Essas perspectivas combinadas oferecem um guia sobre como tomar decisões arquitetônicas estratégicas que agregam valor ao produto final.

# Principais conceitos:

### Arquitetura e Estrutura de Software
*   **Arquitetura de Software**: Refere-se às decisões estruturais de como dividir as camadas do sistema, como elas irão se comunicar e como o design de código será organizado.
*   **Clean Architecture (Arquitetura Limpa)**: Padrão que organiza o código em camadas independentes, separando o domínio de negócios (*Core*) das partes técnicas (*Infrastructure*). Ela engloba:
    *   **Entities (Entidades)**: Regras de negócio puras e independentes.
    *   **Use Cases (Casos de Uso)**: Lógica específica da aplicação que orquestra as entidades.
    *   **Controllers/Adapters**: Convertem dados entre o formato interno e o formato externo de frameworks.
    *   **Frameworks & Drivers**: Camada mais externa com detalhes de implementação, como banco de dados e bibliotecas web.
*   **Arquitetura Hexagonal (Ports and Adapters)**: Design de código voltado para inversão de dependências e isolamento da aplicação.
    *   **Ports (Portas)**: Interfaces de entrada (*Inbound*) ou saída (*Outbound*) do núcleo da aplicação.
    *   **Adapters (Adaptadores)**: Implementam as portas (ex: adaptadores HTTP ou banco de dados), garantindo que o domínio principal (*Core*) não conheça as tecnologias externas.
*   **MVVM (Model-View-ViewModel)**: Arquitetura muito usada em interfaces ricas, focada na separação do domínio e da lógica de apresentação.
    *   **Model**: Contém as entidades, regras de negócios e acesso a dados.
    *   **View**: A interface com o usuário, idealmente "burra" e com o mínimo de lógica, de comportamento declarativo.
    *   **ViewModel**: Intermediário que prepara, gerencia os dados da interface e os estados lógicos, comunicando-se com a *View* através de *Data Binding*.
*   **Data Binding (Ligação de Dados)**: Mecanismo central do MVVM onde a interface (View) observa as propriedades do ViewModel e se atualiza automaticamente em caso de mudanças.

### Princípios SOLID
Acrônimo que consolida cinco princípios para o desenvolvimento orientado a objetos:
*   **SRP (Single Responsibility Principle - Princípio da Responsabilidade Única)**: Uma classe deve ter uma única responsabilidade ou razão para mudar, mantendo a coesão.
*   **OCP (Open/Closed Principle - Princípio do Aberto/Fechado)**: As entidades de software devem estar abertas para a extensão, mas fechadas para a modificação.
*   **LSP (Liskov Substitution Principle - Princípio da Substituição de Liskov)**: Subclasses devem ser substituíveis por suas classes base sem alterar a funcionalidade do programa.
*   **ISP (Interface Segregation Principle - Princípio da Segregação de Interfaces)**: Uma interface deve ter apenas os métodos que são estritamente relevantes e exigidos para as implementações que a utilizarão.
*   **DIP (Dependency Inversion Principle - Princípio da Inversão de Dependência)**: Módulos de alto e baixo nível devem depender de abstrações (interfaces), e não um do outro de maneira acoplada.

### Design Patterns (Padrões de Projeto)
Soluções reutilizáveis e testadas para problemas comuns de design de software. Dividem-se em três grupos:
*   **Padrões de Criação (Creational)**: Focados na construção de objetos. O **Builder**, por exemplo, ajuda na criação passo a passo de objetos complexos e dinâmicos.
*   **Padrões Estruturais (Structural)**: Tratam da relação e interação entre os objetos. O **Adapter** padroniza interfaces incompatíveis; o **Decorator** adiciona funcionalidades dinamicamente; e o **Flyweight** economiza espaço compartilhando partes de objetos.
*   **Padrões Comportamentais (Behavioral)**: Lidam com a comunicação e algoritmos. O **Strategy**, por exemplo, permite criar múltiplas variações de algoritmos (como calcular diferentes tipos de fretes) injetados a partir de uma interface comum.

### Frontend System Design
Padrões e estratégias para projetar interfaces de larga escala:
*   **Estratégias de Renderização**:
    *   **SSG (Static Site Generation)**: Geração de páginas no *build* e servidas como HTML estático via CDN.
    *   **ISR (Incremental Static Regeneration)**: Regeneração de páginas estáticas em *background* para atualizar o conteúdo sem um novo *build*.
    *   **SSR (Server-Side Rendering)**: Renderização feita no servidor a cada requisição, enviando a página pronta ao usuário.
    *   **CSR (Client-Side Rendering)**: Renderização no navegador usando JavaScript para montar a interface.
*   **Performance**:
    *   **Code Splitting**: Divisão do JavaScript em pacotes menores (*bundles*) para carregar só o que é necessário.
    *   **Lazy Loading**: Carregamento de recursos sob demanda, geralmente quando um elemento se torna visível na tela.
    *   **Service Workers & Caching**: Scripts no navegador para armazenar recursos, ajudando na funcionalidade *offline* e tempo de resposta.
    *   **CDN (Content Delivery Network)**: Distribuição de conteúdos em servidores geograficamente próximos aos usuários para redução de latência.
*   **Arquitetura e Organização**:
    *   **MFE (Micro Frontends) vs Monorepo**: Modelos de escalabilidade. Monorepo centraliza código para governança unificada; MFE foca em times desacoplados com *deploy* independente.
    *   **Design System**: Bibliotecas de padrões, módulos, e elementos estruturais criados para garantir consistência em interfaces gráficas.

### Engenharia de Código Limpo (Clean Code)
Técnicas essenciais para legibilidade do código, citadas no capítulo "Nomes Significativos":
*   **Autoexplicativo**: O nome da variável ou função deve revelar seu propósito de forma muito clara, eliminando a necessidade de comentários de explicação.
*   **Busca e Pronúncia**: É recomendado evitar abreviações confusas, adotando nomes fáceis de pronunciar e de serem pesquisados no código.
*   **Evite Informações Erradas ou Genéricas**: Crie nomes precisos e distintos que reflitam o comportamento real, não utilizando trocadilhos (engraçadinhos) ou palavras vagas que induzam o leitor ao erro (como `DataProcessor` em vez de algo específico como `UserProfileProcessor`).

# Prompts:

1. Qual o básico deste assunto que todo dev frontend deve saber?
2. Quais são as 10 dicas essenciais para um Clean Code?
3. como aplicar clean arquiteture no react?
