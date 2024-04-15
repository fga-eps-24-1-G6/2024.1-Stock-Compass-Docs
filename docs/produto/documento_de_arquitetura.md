# Documento de Arquitetura

## Histórico de versão

| Atividade                          | Responsável   | Data       |
|------------------------------------|---------------|------------|
| Criação do documento | João Victor | 14/04/2024 |
| Elaboração do diagrama de Microserviços| Lucas Felipe e Yan Andrade | 09/04/2024 |
| Elaboração do diagrama de Pacotes| Lucas Felipe e Yan Andrade| 10/04/2024 |
| Elaboração do Diagrama de classes | Lucas Felipe e Yan Andrade | 12/04/2024 |

## Diagrama de Classes

### Introdução

Exemplificar e restringir tudo aquilo que deve ou não estar contido dentro de um sistema de software nem sempre é uma atividade simples, com isso a linguagem de modelagem unificada (UML) auxilia esses profissionais a modelar como se darão esses processos e trilhar de maneira mais clara e lógica como vai se dar o processo de desenvolvimento deste software de maneira padronizada e estabelecida dentro da comunidade. O diagrama de classes, um dos mais populares diagramas da arquitetura de software, trata-se de um diagrama da estrutura de software devido sua capacidade de descrever tudo aquilo que estará dentro do sistema e como essas estruturas vão conversar entre si.

### Metodologia

O diagrama foi elaborado seguindo a documentação e padronização prevista pela linguagem de modelagem unificada(UML). Para elaboração do mesmo, os alunos Lucas Felipe e Yan Andrade utilizaram a ferramenta [Lucid Chart](https://www.lucidchart.com/pages/pt) para a modelagem do diagrama de classes. As principais discussões foram discutidas durante a finalização do lean inception, definição do backlog e a elaboração dos diagramas de microserviçoes e pacotes.

#### Discussões

Um diagrama de classes é um diagrama estático da UML que reúne os elementos mais importantes de um sistema orientado a objetos. Nele são exibidos um conjunto de classes, interfaces e seus relacionamentos. As classes especificam tanto as propriedades quanto os comportamentos dos objetos. O diagrama de classes surgiu com o objetivo de reunir as "melhores práticas de engenharia" que provaram ter sucesso em modelar sistemas complexos na época.

[Diagrama de classes](/2024.1-Stock-Compass-Docs/docs/produto/assets/diagramadeclasses.png)

## Diagrama de Pacotes

### Introdução

O Diagrama de Pacotes é uma das formas de modelagem estática usada para representar de forma geral as estruturas dos elementos dentro de um sistema. O pacote faz a representação de um conjunto de unidades UML, que são apresentados em pastas, e proporcionam uma melhor visualização da arquitetura do software. Essa modelagem traz uma série de vantagens para o desenvolvimento do projeto, como melhor visualização da estrutura hierárquica, simplificação de diagramas mais complexos e fácil atualização durante o andamento do projeto.

### Metodologia

Para esboçar o diagrama, os membros Lucas Felipe e Yan Andrade se reuniram e utilizaram como ferramenta o [Lucid Chart](https://www.lucidchart.com/pages/pt) e foram evoluindo ao longo da sprint, iniciada no dia 08/04/2024.

### Diagrama de Pacotes

Durante a execução de tal diagrama, optamos inicialmente por esboçar de maneira mais geral quais os serviços que estão sendo pensados de maneira inicial para o sistema. Posteriormente, conseguimos aprofundar com maior nível de detalhamento o que cada serviço deste terá como responsabilidade e como os mesmos se comunicarão entre si e com outros módulos da plataforma. Nas imagens a seguir,  iremos tratar cada um de maneira individual.

[Coleta de Dados](/2024.1-Stock-Compass-Docs/docs/produto/assets/coletaDados.png)

O serviço de coleta de dados, será o serviço que terá como responsabilidade coletar atualizar dados de uma API externa e alimentar nosso banco de dados com essas informações. ALém mais, tal serviço é primordial para a garantia de dados que serão útilizados para implementação das mais variadas regras de negócio que serão trabalhadas em outros serviços.

[Front-End](/2024.1-Stock-Compass-Docs/docs/produto/assets/pacoteFrontEnd.png.png)

O pacote de Front-End, representa a maneira geral como nossa camada de interface será implementada dentro do sistema. Basicamente sua principal responsabilidade será formar uma interface simplificada  para o consumo dos serviços. Uma particularidade deste pacote em questão, será a utilização do Framework "Next.js", com o mesmo teremos a simplificação do que se diz repeito a implantação de rotas pois a mesma utiliza a estrutura dos próprios arquivos para a mesma.

[Carteira](/2024.1-Stock-Compass-Docs/docs/produto/assets/servicoCarteira.png.png)

O pacote de Carteira, representa a lógica de negócio onde o usuário vai poder cadastrar seus dados financeiros dos quais ele deseja simular todo o processo de investimentos e com os mesmos o sistema vai trabalhar com todos os cálculos e conversões de dados de maneira que sirva os mesmos de maneira intuitiva para o Usuário.

[Acoes](/2024.1-Stock-Compass-Docs/docs/produto/assets/servicoAcoes.png.png)

O pacote de Ações, representa o serviço do qual vamos trabalhar com a manipulação dos dados recebidos da coleta de dados para que os mesmos agora sejam capazes de serem melhor trabalhados e calculados para outros serviços.

[User](/2024.1-Stock-Compass-Docs/docs/produto/assets/servicoUsuario.png.png)

O pacote de usuário, vai ser responsável por gerenciar o processo de autênticação e autorização do usuário no sistema. Basicamente esse serviço vai garantir a integridade dos dados do usuário e a garantia de que os dados trabalhados sejam do mesmo

## Diagrama de microserviços

De maneira similar ao diagrama de pacotes, trabalhamos também com o diagrama de microserviços onde os principais objetivos são descrever e ilustrar com mais detalhes quais serão os serviçõs utilizados no sistema e como os mesmos vão conversar entre si e com o sistema como um todo.

[Microservicos](/2024.1-Stock-Compass-Docs/docs/produto/assets/microServicos.png.png)
