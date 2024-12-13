# Front-end Móvel

Este projeto consiste em uma aplicação de gestão de academia chamada DEV Fitness, desenvolvida utilizando React Native no front-end mobile para criar uma interface intuitiva e responsiva. O objetivo principal é oferecer uma experiência prática para a administração de membros, pagamentos e planos de treino diretamente em dispositivos móveis. A aplicação conta com funcionalidades interativas, como formulários de cadastro, listas dinâmicas de dados e navegação fluida, garantindo acessibilidade e facilidade de uso para os administradores e usuários.

## Tecnologias Utilizadas

Para o desenvolvimento da aplicação móvel DEV Fitness, utilizamos um conjunto de tecnologias modernas e eficientes que garantem a criação de uma interface responsiva e intuitiva para dispositivos móveis. As principais tecnologias incluem:

- **React Native**: Framework escolhido para o desenvolvimento do front-end móvel, permitindo o uso de JavaScript para criar aplicativos nativos para Android e iOS.
- **Expo**: Plataforma usada para facilitar o desenvolvimento e teste do aplicativo. Expo proporciona um ambiente de desenvolvimento que inclui diversas bibliotecas prontas e ferramentas úteis, como visualização em tempo real e acesso a APIs nativas sem necessidade de configuração adicional.
- **Node.js**: Ambiente de execução JavaScript usado para rodar o Expo CLI, além de gerenciar pacotes e dependências do projeto.
- **JavaScript (ES6+)**: Linguagem de programação utilizada para escrever a lógica da aplicação, aproveitando os recursos modernos do JavaScript para melhorar a legibilidade e a manutenção do código.

### Ferramentas de Desenvolvimento
- **Android Studio**: Utilizado para configurar e executar o emulador Android, permitindo testar e ajustar a aplicação em um ambiente controlado.
- **Xcode**: Utilizado para configuração e execução no simulador iOS, disponível apenas para macOS, proporcionando um ambiente de teste integrado para dispositivos Apple.
- **Visual Studio Code**: Editor de código recomendado para desenvolvimento, oferecendo suporte robusto para JavaScript e React Native através de extensões.

### Gestão de Pacotes e Dependências
- **npm (Node Package Manager)**: Ferramenta utilizada para gerenciar as bibliotecas e módulos necessários para o projeto.


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

1. **Página Inicial:** Tela com informações introdutórias e botão de avançar;
2. **Tela de Login:** Entrada para o sistema por meio de credenciais (email e senha);
3. **Painel de Gestão:** Mostra estatísticas importantes, como o total de alunos matriculados e a quantidade distribuída entre os planos Silver, Gold e Black;
4. **Detalhes do Aluno:** Apresenta informações completas do aluno, incluindo dados pessoais, status de pagamento e detalhes do plano.

<div align="center">
  <img src="https://github.com/user-attachments/assets/88259a9e-1423-4f08-bb66-0b6ae48b06b3" alt="Wireframe Página Inicial" style="height:450px; width:auto;">
  <p><i>Wireframe da Página Inicial, Tela de Login e Totais do Painel de Gestão</i></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/c964ea55-3b3d-45fb-bfe0-b795c3fd087f" alt="Wireframe Tela de Login" style="height:450px; width:auto;">
  <p><i>Planos dos Paineis de Gestão</i></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/d0beab49-14a1-42d9-aa91-da15500b2a01" alt="Wireframe Detalhes do Aluno" style="height:450px; width:auto;">
  <p><i>Detalhes do Aluno</i></p>
</div>


     
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
Foram elaborados os seguintes casos de teste para a aplicação mobile:

### Caso de teste 1
**Resumo:** Login na aplicação – Dados corretos  
**Prioridade:** Alta  
**Pré-condição:** Estar cadastrado no sistema, dados de login corretos  

**Passos:**  
1. Acessar o app;  
2. Preencher com os dados de email e senha;  
3. Clique no botão “Acessar”.  

**Resultado Esperado:**  
Exibir modal com a mensagem “Login realizado com sucesso!” e redirecionamento para Página Inicial.

<div align="center">
  <img src="https://github.com/user-attachments/assets/3934c051-68da-47ec-832b-1c1342450cc6" alt="Teste de Login bem-sucedido" style="height:350px; width:auto;">
  <p><i>Teste de Login bem-sucedido</i></p>
</div>

---

### Caso de teste 2
**Resumo:** Login de Paciente – Dados incorretos  
**Prioridade:** Alta  
**Pré-condição:** Usuário sem cadastro  

**Passos:**  
1. Acessar o app ConsulMed;  
2. Preencher com os dados de email e senha;  
3. Clique no botão “Acessar”.  

**Resultado Esperado:**  
Exibir modal com a mensagem “Email ou Senha inválidos”.

<div align="center">
  <img src="https://github.com/user-attachments/assets/ddf926b4-8ac8-4bc0-97a6-1b077b67be11" alt="Teste de Login inválido" style="height:350px; width:auto;">
  <p><i>Teste de Login inválido</i></p>
</div>

---

### Caso de teste 3
**Resumo:** Visualizar clientes em cada plano  
**Prioridade:** Alta  
**Pré-condição:** Cadastro no Sistema e Login  

**Passos:**  
1. Acessar o app;  
2. Realizar login;  
3. Página inicial rolar para lateral visualizando os totais;  
4. Rolar para lateral visualizando os planos específicos cadastrados.  

**Resultado Esperado:**  
Exibir as informações corretas armazenadas no banco.

<div align="center">
  <img src="https://github.com/user-attachments/assets/ae951ee1-b59d-47f4-b129-9145c1fffd49" alt="Teste de Visualização de Clientes" style="height:350px; width:auto;">
  <p><i>Teste de Visualização de Clientes</i></p>
</div>

---

### Caso de teste 4
**Resumo:** Visualizar como cliente o status do pagamento  
**Prioridade:** Alta  
**Pré-condição:** Cadastro no Sistema e Login  

**Passos:**  
1. Acessar o app;  
2. Realizar login;  
3. Navegar para a Página inicial e acessar como usuário.  

**Resultado Esperado:**  
Exibir as informações corretas armazenadas no banco.

<div align="center">
  <img src="https://github.com/user-attachments/assets/da04dbc1-91bb-4257-8439-eae96a6c637c" alt="Teste de Status de Pagamento" style="height:350px; width:auto;">
  <p><i>Teste de Status de Pagamento</i></p>
</div>

---

### Caso de teste 5
**Resumo:** Adição de pagamento  

<div align="center">
  <img src="https://github.com/user-attachments/assets/8989bbe8-d17d-4e89-a1c4-d29f5ae1f3c4" alt="Adição de Pagamento 1" style="height:350px; width:auto;">
  <p><i>Adição de Pagamento - Passo 1</i></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/f068bcf8-7060-4ffd-a1b7-2cefc821615e" alt="Adição de Pagamento 2" style="height:350px; width:auto;">
  <p><i>Adição de Pagamento - Passo 2</i></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/8e7f57b2-42af-4d09-b88b-ffab877cf3a1" alt="Adição de Pagamento 3" style="height:350px; width:auto;">
  <p><i>Adição de Pagamento - Passo 3</i></p>
</div>

---

### Caso de teste 6
**Resumo:** Deleção de pagamento  
**Prioridade:** Alta  
**Pré-condição:** Cadastro no Sistema, Login e presença de pagamentos registrados  

**Passos:**  
1. Acessar o app;  
2. Realizar login;  
3. Navegar até a lista de pagamentos;  
4. Selecionar um pagamento a ser excluído;  
5. Confirmar a escolha no modal apertando “Sim”;  
6. Exibir a tela atualizada sem o pagamento excluído.  

**Resultado Esperado:**  
O pagamento selecionado é removido da lista, e a tela é atualizada para refletir a exclusão.

<div align="center">
  <img src="https://github.com/user-attachments/assets/cb88c0b9-f71f-40a3-b3ca-2f5203cf75ae" alt="Deleção de Pagamento 1" style="height:350px; width:auto;">
  <p><i>Passo 1: Seleção do pagamento a ser excluído</i></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/75496aa5-3797-4a55-8d5c-a3ef509aaa29" alt="Deleção de Pagamento 2" style="height:350px; width:auto;">
  <p><i>Passo 2: Modal de confirmação exibido</i></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/00c59f49-7648-4d63-8893-dc7ec3d2744e" alt="Deleção de Pagamento 3" style="height:350px; width:auto;">
  <p><i>Passo 3: Tela atualizada sem o pagamento excluído</i></p>
</div>

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
