# MySql---Como-Modelar-um-Banco-de-Controle-de-S-ries-Assistidas

A modelagem de dados é uma etapa fundamental no desenvolvimento de sistemas baseados em bancos de dados. No contexto do controle de séries assistidas pelo usuário, a modelagem visa representar, de forma eficiente e flexível, as informações relacionadas às séries assistidas. Vamos explorar como modelar um banco de controle de séries assistidas utilizando o SGBD MySQL.

## Objetivo do Projeto
O objetivo deste projeto prático hands-on é permitir aos participantes adquirir habilidades na modelagem de dados utilizando o MySQL para a criação de um banco de controle de séries assistidas pelo usuário. Através da prática, os participantes serão capazes de compreender os conceitos de modelagem de dados e aplicá-los em um contexto real.

## Passos para Modelagem do Banco de Controle de Séries Assistidas
1. **Entendimento do Cenário:**
   - Antes de iniciar a modelagem, é importante entender o cenário. Quais informações precisam ser armazenadas? Quais entidades estão envolvidas (por exemplo, séries, usuários, episódios)?
   - No nosso caso, teremos entidades como "Usuário", "Série", "Episódio" e "Assistido".

2. **Identificação das Entidades e Relacionamentos:**
   - Liste as entidades e seus atributos. Por exemplo:
     - **Usuário**: ID, Nome, E-mail, Senha.
     - **Série**: ID, Título, Gênero, Temporadas.
     - **Episódio**: ID, Título, Número da Temporada, Número do Episódio.
     - **Assistido**: Relacionamento entre Usuário e Episódio (pode conter informações como data de visualização).

3. **Modelagem Conceitual (Diagrama Entidade-Relacionamento - DER):**
   - Crie um DER que represente as entidades e seus relacionamentos. Por exemplo:
     - Um usuário pode assistir a vários episódios.
     - Um episódio pertence a uma série.
     - Um episódio pode ser assistido por vários usuários.

4. **Modelagem Lógica (Tabelas e Relacionamentos):**
   - Transforme o DER em tabelas. Por exemplo:
     - Tabela **Usuário**: ID (PK), Nome, E-mail, Senha.
     - Tabela **Série**: ID (PK), Título, Gênero, Temporadas.
     - Tabela **Episódio**: ID (PK), Título, Número da Temporada, Número do Episódio, ID da Série (FK).
     - Tabela **Assistido**: ID do Usuário (FK), ID do Episódio (FK), Data de Visualização.

5. **Criação do Banco de Dados:**
   - Utilize a linguagem SQL para criar as tabelas no MySQL.
   - Execute os comandos para criar o banco de dados e as tabelas.

6. **Considerações Finais:**
   - Pense na escalabilidade do banco. Como ele se comportará com muitos usuários e séries?
   - Considere índices para otimizar consultas.
   - Teste o banco com dados de exemplo para verificar se atende aos requisitos.

## Exemplo Prático
Suponhamos que temos um usuário chamado "João" que assistiu ao episódio 5 da série "Breaking Bad". O banco de dados armazenaria essas informações nas tabelas correspondentes.

Lembre-se de adaptar esse exemplo às suas necessidades específicas e expandir conforme necessário. 

Vamos explorar alguns exemplos de relacionamentos em modelagem de banco de dados:

1. **Relacionamento Um-Para-Um (1:1):**
   - Nesse tipo de relacionamento, uma instância da entidade A está relacionada a **apenas uma** instância da entidade B, e vice-versa.
   - Exemplo: Imagine um sistema de cadastro de funcionários. Cada funcionário está associado a **apenas um** departamento, e cada departamento tem **apenas um** gerente.

2. **Relacionamento Um-Para-Vários (1:N):**
   - Aqui, uma instância da entidade A está relacionada a **várias** instâncias da entidade B, mas cada instância da entidade B está associada a **apenas uma** instância da entidade A.
   - Exemplo: Em um sistema de biblioteca, um autor pode ter escrito **vários** livros, mas cada livro tem **apenas um** autor.

3. **Relacionamento Vários-Para-Vários (N:M):**
   - Nesse tipo de relacionamento, várias instâncias da entidade A estão relacionadas a várias instâncias da entidade B, e vice-versa.
   - Exemplo: Em um sistema de matrícula de alunos, um aluno pode se inscrever em **várias** disciplinas, e cada disciplina tem **vários** alunos matriculados.

4. **Cardinalidade Mínima:**
   - Além das cardinalidades máximas, podemos especificar a cardinalidade mínima. Por exemplo:
     - Relacionamento Um-Para-Vários com cardinalidade mínima: **Usuário - Empréstimo (1,1:0,N)**
       - Um usuário pode estar relacionado a **nenhum ou vários** empréstimos. Um empréstimo deve estar relacionado a **apenas um** usuário.
     - Relacionamento Vários-Para-Vários com cardinalidade mínima: **Empréstimo - Livro (0,N:1,N)**
       - Um empréstimo pode estar relacionado a **um ou vários** livros. Um livro pode estar relacionado a **nenhum ou vários** empréstimos.

Lembre-se de adaptar esses exemplos à sua modelagem específica. A clareza dos relacionamentos é essencial para um banco de dados bem projetado.
