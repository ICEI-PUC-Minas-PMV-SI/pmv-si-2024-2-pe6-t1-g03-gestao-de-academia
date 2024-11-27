# Front-end Móvel

Este projeto consiste em uma aplicação de gestão de academia chamada DEV Fitness, desenvolvida utilizando React Native no front-end mobile para criar uma interface intuitiva e responsiva. O objetivo principal é oferecer uma experiência prática para a administração de membros, pagamentos e planos de treino diretamente em dispositivos móveis. A aplicação conta com funcionalidades interativas, como formulários de cadastro, listas dinâmicas de dados e navegação fluida, garantindo acessibilidade e facilidade de uso para os administradores e usuários.

## Tecnologias Utilizadas
[Lista das tecnologias principais que serão utilizadas no projeto.]

## Arquitetura

Utilizado principalmente o padrão MVC.

- Model: Responsável pela interação com o banco de dados, representando as entidades do sistema (membros, pagamentos, planos) e realizando operações como consulta, inserção e atualização de dados.
- View: Representa a camada de interface com o usuário, onde são exibidos os dados e elementos visuais, permitindo que o usuário interaja com o sistema. Essa camada é construída com HTML, CSS e JavaScript.
- Controller: Atua como intermediário entre a visão e o modelo, recebendo as requisições do usuário, processando as regras de negócio e retornando as respostas adequadas.

## Modelagem da Aplicação

Entidades Principais:

- Usuários: Armazena informações dos usuários do sistema, como nome, e-mail, senha (criptografada), tipo de usuário (administrador, recepcionista), permissões de acesso e dados de contato.-
- Membros: Armazena os dados dos alunos da academia, incluindo nome, CPF, data de nascimento, telefone, endereço, e status do cadastro.
- Planos: Armazena informações sobre os diferentes tipos de planos que os membros podem ter, como tipo de plano (silver, gold, master), data de início, data de término, e status do plano (ativo, inativo).
- Pagamentos: Registra os pagamentos realizados pelos membros, incluindo data do pagamento, status (pago ou não pago), método de pagamento (cartão, boleto), e referência ao membro.
Acess_token: Registra as sessões dos usuários logados, garantindo o controle de acesso e permissões dos mesmos.

## Projeto da Interface
O projeto da interface do aplicativo móvel foi desenvolvido para simplificar a gestão administrativa de academias, com foco no acompanhamento do fluxo de pagamentos e status dos planos dos alunos. A interface é clara e objetiva, proporcionando uma experiência funcional e prática para consultas e ajustes rápidos.

### Wireframes
O wireframe foi projetado para priorizar a organização lógica dos elementos e garantir uma experiência de uso intuitiva. As páginas principais são:
  1. <b>Página Inicial:</b> Tela com informações introdutórias e botão de avançar;
  2. <b>Tela de Login:</b> Entrada para o sistema por meio de credenciais (email e senha);
  3. <b>Painel de Gestão:</b> Mostra estatísticas importantes, como o total de alunos matriculados e a quantidade distribuída entre os planos Silver, Gold e Black.
  4. <b>Detalhes do Aluno:</b> Apresenta informações completas do aluno, incluindo dados pessoais, status de pagamento e detalhes do plano.
     
### Design Visual
O design visual utiliza uma paleta de cores vibrante para melhorar a usabilidade e a clareza das informações:
  - <b>Azul:</b> Representa informações gerais e planos padrão.
  - <b>Verde:</b> Indica ações positivas, como confirmações ou atualizações bem-sucedidas.
  - <b>Vermelho:</b> Destaca alertas ou pendências, como pagamentos atrasados.

A tipografia foi escolhida para garantir leitura fácil em dispositivos móveis, com um estilo moderno e limpo. Ícones visuais foram adicionados para facilitar a identificação das ações disponíveis.  

### Layout Responsivo
A interface foi projetada para ser responsiva, adaptando-se a diferentes tamanhos de tela e dispositivos móveis. Em telas menores, os elementos são reorganizados em pilhas verticais para manter a usabilidade e evitar sobrecarga visual. O design responsivo garante que o aplicativo funcione de forma eficiente em celulares de variados modelos e tamanhos.

### Interações do Usuário
[Descreva as interações do usuário na interface, como animações, transições entre páginas e outras interações.]

## Fluxo de Dados

- Requisições HTTP: Os usuários interagem com o sistema por meio de requisições HTTP (GET, POST, PUT, DELETE), enviadas do front-end (navegador) para a API.
Controladores: As requisições são capturadas pelos controladores no Laravel, que processam a lógica da aplicação e validam os dados.
- Modelos: Os controladores acionam os modelos, que interagem com o banco de dados para consultar, inserir, atualizar ou deletar informações.
- Respostas JSON: Os dados processados são retornados como respostas JSON, enviadas de volta para o front-end, onde o JavaScript é responsável por atualizar dinamicamente a interface.
- Persistência de Dados: As informações como pagamentos, planos e membros são armazenadas de forma persistente no banco de dados MySQL, garantindo que todas as operações realizadas no sistema sejam refletidas e mantidas.

## Requisitos Funcionais

|ID    | Descrição do Requisito | Responsável |
|------|------------------------|-------------|
|RF-001| O sistema deve fazer a gestão das informações dos alunos | Rodrigo, Vinícius |
|RF-002| O sistema deve fazer a gestão de pagamentos | Fernando, Leandro |
|RF-003| O sistema deve permitir a atualização e o gerenciamento de planos de treinamento dos alunos | Laryssa, Douglas |
|RF-004| O sistema deve prover relatórios de gestão | Cada desenvolvedor |

## Requisitos Não Funcionais

|ID     | Descrição do Requisito | Prioridade |
|-------|------------------------|------------|
|RNF-001| O sistema deve ser responsivo, garantindo que a interface funcione adequadamente em dispositivos móveis e web | ALTA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA |
|RNF-003| O sistema deve ser escalável para suportar o crescimento da academia, incluindo mais alunos e novos serviços |  ALTA |
|RNF-004| O sistema deve garantir a segurança e confidencialidade dos dados dos alunos |  BAIXA |


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
