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

![dev_front_full_page](https://github.com/user-attachments/assets/26717444-a94a-468d-93ab-7336678bc73a)


### Wireframes
[Inclua os wireframes das páginas principais da interface, mostrando a disposição dos elementos na página.]

### Design Visual
[Descreva o estilo visual da interface, incluindo paleta de cores, tipografia, ícones e outros elementos gráficos.]

### Layout Responsivo
[Discuta como a interface será adaptada para diferentes tamanhos de tela e dispositivos.]

### Interações do Usuário
[Descreva as interações do usuário na interface, como animações, transições entre páginas e outras interações.]

## Fluxo de Dados

- Requisições HTTP: Os usuários interagem com o sistema por meio de requisições HTTP (GET, POST, PUT, DELETE), enviadas do front-end (navegador) para a API.
Controladores: As requisições são capturadas pelos controladores no Laravel, que processam a lógica da aplicação e validam os dados.
- Modelos: Os controladores acionam os modelos, que interagem com o banco de dados para consultar, inserir, atualizar ou deletar informações.
- Respostas JSON: Os dados processados são retornados como respostas JSON, enviadas de volta para o front-end, onde o JavaScript é responsável por atualizar dinamicamente a interface.
- Persistência de Dados: As informações como pagamentos, planos e membros são armazenadas de forma persistente no banco de dados MySQL, garantindo que todas as operações realizadas no sistema sejam refletidas e mantidas.

## Requisitos Funcionais

[Liste os principais requisitos funcionais da aplicação.]

## Requisitos Não Funcionais

[Liste os principais requisitos não funcionais da aplicação, como desempenho, segurança, escalabilidade, etc.]


## Considerações de Segurança

[Discuta as considerações de segurança relevantes para a aplicação distribuída, como autenticação, autorização, proteção contra ataques, etc.]

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
