# Front-end Web

Este projeto consiste em uma aplicação de gestão de academia chamada DEV Fitness, desenvolvida utilizando HTML, CSS e JavaScript no front-end para criar uma interface dinâmica e responsiva. O objetivo principal é oferecer uma experiência intuitiva para a administração de membros, pagamentos e planos de treino. A aplicação conta com funcionalidades interativas, como formulários de cadastro, tabelas de exibição de dados.

## Tecnologias Utilizadas

- HTML: Linguagem de marcação utilizada no front-end para estruturar as páginas da aplicação, facilitando a organização dos elementos visuais.
- CSS: Linguagem de estilo utilizada para definir o layout, cores, espaçamentos e outras características visuais da interface da aplicação, tornando-a atraente e responsiva.
- JavaScript: Linguagem de programação utilizada no front-end para adicionar interatividade e manipulação dinâmica dos dados exibidos na interface, como a busca de dados via API, validação de formulários e atualização de conteúdo sem recarregar a página.
- PHP/Laravel: Linguagem de programação utilizada no back-end para construção da lógica da aplicação.
- MySQL: Banco de dados relacional utilizado para armazenar informações sobre membros, pagamentos e planos.
- JWT (JSON Web Token): Utilizado para autenticação segura entre o cliente e a API.
- Apache: Servidor web para hospedar a aplicação.

## Arquitetura

Utilizado principalmente o padrão MVC.

- Model: Responsável pela interação com o banco de dados, representando as entidades do sistema (membros, pagamentos, planos) e realizando operações como consulta, inserção e atualização de dados.
- View: Representa a camada de interface com o usuário, onde são exibidos os dados e elementos visuais, permitindo que o usuário interaja com o sistema. Essa camada é construída com HTML, CSS e JavaScript.
- Controller: Atua como intermediário entre a visão e o modelo, recebendo as requisições do usuário, processando as regras de negócio e retornando as respostas adequadas.

## Modelagem da Aplicação
[Descreva a modelagem da aplicação, incluindo a estrutura de dados, diagramas de classes ou entidades, e outras representações visuais relevantes.]

## Projeto da Interface Web

### Interações do Usuário - Front Page da Academia

N cabeçalho da aplicação apresentamos um menu de navegação fixo e responsivo. Ele inclui links principais para as seções "Home", "Sobre", "Planos", "Professores", "Contato" e um link para o sistema administrativo (deve ser retirado, é apenas para teste). O logo da academia, "DEV Fitness", é destacado no lado esquerdo, e o menu se adapta perfeitamente a diferentes tamanhos de tela com um botão de alternância (toggle) para dispositivos móveis.

A interface inclui várias interações do usuário, como:

- Navegação Responsiva: O menu se adapta perfeitamente a dispositivos móveis e permite fácil acesso às seções principais.
- Botões de Ação: Botões visíveis e bem posicionados são utilizados para direcionar o usuário a explorar planos e conhecer mais sobre a academia.
- Formulários: O formulário de contato facilita a comunicação entre os usuários e a equipe da academia, garantindo uma experiência de suporte ágil.
- Carrossel de Depoimentos: O carrossel permite aos usuários visualizar depoimentos de outros alunos, o que pode influenciar positivamente na decisão de se matricular na academia.

### Outros Aspectos Relevantes

- Preloader: Um carregador animado é exibido durante o carregamento da página, melhorando a percepção de velocidade e a experiência do usuário.
- Design Responsivo: Todos os elementos da página foram projetados com uma abordagem mobile-first, garantindo uma navegação fluida em dispositivos móveis.
- Ícones e Imagens: Ícones FontAwesome e imagens de alta qualidade são usados em todo o site para reforçar o conteúdo visualmente e melhorar a comunicação da marca.

O layout foi pensado para ser simples e direto, facilitando o uso para diferentes perfis de usuários, desde jovens até o público adulto, que podem acessar as informações de forma rápida e sem complicações.

## Sistema de Gerenciamento

O acesso ao sistema é feito por meio da tela de login, apresentada abaixo.

![login_sistema](https://github.com/user-attachments/assets/c3299b28-ca36-4e5c-b616-cb208feb201b)
<br>*Tela de Login*

O Dashboard do sistema administrativo da DEV Fitness apresenta uma visão geral da academia, com informações resumidas em cartões coloridos que destacam o total de alunos matriculados e a quantidade de alunos em cada plano (Silver, Gold e Black). Abaixo, uma tabela detalhada lista os alunos com suas principais informações, como nome, email, CPF, telefone e data de nascimento, além de botões de ações para visualizar, editar ou excluir cada aluno. A interface é organizada e intuitiva, com navegação fácil pela sidebar à esquerda e paginação clara para gerenciar grandes volumes de dados. O design é funcional, oferecendo ao administrador uma visão completa e o controle total das operações da academia.

![sistema_administrativo](https://github.com/user-attachments/assets/2281a9f9-5919-40e1-9c5c-ce4763dc5769)
*Dashboard principal*

### Wireframes
[Inclua os wireframes das páginas principais da interface, mostrando a disposição dos elementos na página.]

### Design Visual
[Descreva o estilo visual da interface, incluindo paleta de cores, tipografia, ícones e outros elementos gráficos.]

### Layout Responsivo

Em relação a responsividade do módulo Web do sistema administrativo, o grupo utlizou os seguintes recursos:

- 1 Meta Viewport Tag

`<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Isso garante que o layout seja exibido corretamente em diferentes dispositivos, como smartphones, tablets e desktops, ajustando a largura do conteúdo com base no tamanho da tela.

- 2 Uso do Bootstrap

Bootstrap é um framework CSS responsivo que adapta automaticamente o layout para diferentes tamanhos de tela. Ele divide a interface em colunas que são reorganizadas ou ajustadas conforme o tamanho da tela. Botões e tabelas têm classes do Bootstrap que adaptam seu tamanho e espaçamento, melhorando a experiência do usuário em dispositivos menores.

![ver_membro_cell_phone](https://github.com/user-attachments/assets/8430f74b-fc5e-420a-91a1-18d8d8620b0a)
<br>*Ver um aluno específico no Celular*

- 3 Menu de Navegação

O menu de navegação utiliza o Bootstrap para colapsar em dispositivos móveis (ou seja, transforma-se em um menu hamburguer): 
`navbar-expand-lg`: O menu será exibido expandido em telas grandes, mas colapsado (com o botão de menu) em telas menores.
`d-none d-md-block`: Utilizado para esconder itens da barra de navegação em dispositivos móveis e exibi-los apenas em telas de tamanho médio e grande.

### Interações do Usuário
[Descreva as interações do usuário na interface, como animações, transições entre páginas e outras interações.]

## Fluxo de Dados

- Requisições HTTP: Os usuários interagem com o sistema por meio de requisições HTTP (GET, POST, PUT, DELETE), enviadas do front-end (navegador) para a API.
Controladores: As requisições são capturadas pelos controladores no Laravel, que processam a lógica da aplicação e validam os dados.
- Modelos: Os controladores acionam os modelos, que interagem com o banco de dados para consultar, inserir, atualizar ou deletar informações.
- Respostas JSON: Os dados processados são retornados como respostas JSON, enviadas de volta para o front-end, onde o JavaScript é responsável por atualizar dinamicamente a interface.
- Persistência de Dados: As informações como pagamentos, planos e membros são armazenadas de forma persistente no banco de dados MySQL, garantindo que todas as operações realizadas no sistema sejam refletidas e mantidas.

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito | Responsável |
|------|------------------------|-------------|
|RF-001| O sistema deve fazer a gestão das informações dos alunos | Rodrigo, Vinícius |
|RF-002| O sistema deve fazer a gestão de pagamentos | Fernando, Leandro |
|RF-003| O sistema deve permitir a atualização e o gerenciamento de planos de treinamento dos alunos | Laryssa, Douglas |
|RF-004| O sistema deve prover relatórios de gestão | Cada desenvolvedor |

### Requisitos não Funcionais

|ID     | Descrição do Requisito | Prioridade |
|-------|------------------------|------------|
|RNF-001| O sistema deve ser responsivo, garantindo que a interface funcione adequadamente em dispositivos móveis e web | ALTA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA |
|RNF-003| O sistema deve ser escalável para suportar o crescimento da academia, incluindo mais alunos e novos serviços |  ALTA |
|RNF-004| O sistema deve garantir a segurança e confidencialidade dos dados dos alunos |  BAIXA |

## Considerações de Segurança

### Autenticação

A autenticação garante que apenas usuários e sistemas confiáveis possam acessar a aplicação. Em um ambiente distribuído, a autenticação deve ser robusta e escalável, garantindo que cada requisição seja proveniente de uma fonte autenticada.

Na nossa aplicação, a autenticação é feita através de tokens de autenticação que são passados no cabeçalho da requisição (header) usando o método Bearer Token. Quando um usuário realiza login, um token é gerado e retornado. Esse token deve ser incluído em todas as requisições subsequentes, permitindo acesso aos recursos protegidos da API.

### Proteção contra ataques

Para garantir a segurança da aplicação contra ataques de injeção, como SQL e NoSQL, utilizamos consultas parametrizadas e mapeamento objeto-relacional (ORM). Essas práticas evitam que entradas maliciosas sejam executadas diretamente nos bancos de dados, protegendo o sistema contra a execução de comandos não autorizados e garantindo a integridade das informações. A validação rigorosa das entradas de dados e o uso de práticas seguras de codificação minimizam os riscos de injeção de código malicioso.

## Implantação

[Instruções para implantar a aplicação distribuída em um ambiente de produção.]

1. Defina os requisitos de hardware e software necessários para implantar a aplicação em um ambiente de produção.
2. Escolha uma plataforma de hospedagem adequada, como um provedor de nuvem ou um servidor dedicado.
3. Configure o ambiente de implantação, incluindo a instalação de dependências e configuração de variáveis de ambiente.
4. Faça o deploy da aplicação no ambiente escolhido, seguindo as instruções específicas da plataforma de hospedagem.
5. Realize testes para garantir que a aplicação esteja funcionando corretamente no ambiente de produção.

## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
