# APIs e Web Services

Este projeto consiste em uma aplicação de gestão de academia chamada DEV Fitness, desenvolvida utilizando o framework C# no back-end, hospedado no IIS (Internet Information Services), com um front-end dinâmico e interativo. A aplicação oferece funcionalidades para a administração de membros, pagamentos e planos de treino, com autenticação robusta via tokens API (JWT) e proteção por autenticação baseada em tokens. O sistema é integrado com uma API que facilita o acesso seguro a dados de membros, pagamentos e planos, garantindo a eficiência na gestão de uma academia e oferecendo uma experiência segura e escalável para os usuários.

## Objetivos da API

- Facilitar a integração e troca de informações entre as aplicações Web e Mobile, possibilitando uma gestão eficiente da academia através da comunicação com o banco de dados.
- Permitir que diferentes tipos de usuários, como administradores e recepcionistas, acessem e utilizem o sistema de forma segura e organizada.
- Oferecer aos recepcionistas a capacidade de realizar operações de cadastro, edição e exclusão de dados referentes a membros, planos e pagamentos, garantindo a eficiência no atendimento.
- Proporcionar aos administradores acesso completo ao sistema, permitindo não só o cadastro, alteração e exclusão de dados, mas também a realização de pesquisas e consultas detalhadas para fins de gerenciamento e controle de operações.
- Garantir a continuidade do aprimoramento das funcionalidades da API para atender às necessidades futuras da gestão da academia.

## Arquitetura

### Principais Componentes:

#### Padrão MVC

- Controllers: Gerenciam as requisições recebidas, executam a lógica de negócio necessária e enviam as respostas apropriadas.

- Views: Estabelecem os pontos de acesso (endpoints) da API e direcionam as requisições HTTP para os respectivos controladores.

- Models: São responsáveis pela representação dos dados e realizam a comunicação direta com o banco de dados, permitindo manipulações como criação, leitura, atualização e exclusão (CRUD).

### Interações entre os Componentes:

- As requisições HTTP enviadas pelos clientes são recebidas pelas views, que as encaminham para os controladores adequados.

- Os controladores tratam as requisições, utilizando os modelos para acessar ou modificar dados no banco, e em seguida retornam a resposta apropriada aos clientes, como confirmações, dados ou erros.

## Modelagem da Aplicação

### Entidades Principais:

- Usuários: Armazena informações dos usuários do sistema, como nome, e-mail, senha (criptografada), tipo de usuário (administrador, recepcionista), permissões de acesso e dados de contato.
- Membros: Armazena os dados dos alunos da academia, incluindo nome, CPF, data de nascimento, telefone, endereço, e status do cadastro.
- Planos: Armazena informações sobre os diferentes tipos de planos que os membros podem ter, como tipo de plano (silver, gold, master), data de início, data de término, e status do plano (ativo, inativo).
- Pagamentos: Registra os pagamentos realizados pelos membros, incluindo data do pagamento, status (pago ou não pago), método de pagamento (cartão, boleto), e referência ao membro.
- Acess_token: Registra as sessões dos usuários logados, garantindo o controle de acesso e permissões dos mesmos.

### Funcionamento básico de uma API

![how-apis-work-2-303162022](https://github.com/user-attachments/assets/18639f79-b4e0-4c73-8ee1-e52775665a59)

### Tabelas do Banco de Dados

![er_diagram](https://github.com/user-attachments/assets/44edf58b-8553-417f-afe4-073bbbae5fb2)

## Fluxo de Dados

### Cadastro de Usuário (Aluno):

- O aluno acessa a página de cadastro e preenche suas informações pessoais como nome, e-mail, CPF, telefone, e data de nascimento.
- Após enviar o formulário, as informações são validadas e enviadas para a API, onde são armazenadas na tabela members do banco de dados.
- Se o cadastro for bem-sucedido, o sistema retorna uma confirmação ao aluno.

### Escolha de Plano:

- O aluno logado acessa a seção de planos e visualiza as opções disponíveis (Silver, Gold, Master).
- Ao escolher um plano, a API associa o aluno a um plano específico, criando um registro na tabela plans, vinculada ao membro através de member_id.
- A API registra informações como o tipo de plano, data de início, data de término e o status (ativo/inativo).

### Pagamentos:

- Com o plano escolhido, o aluno pode visualizar suas opções de pagamento.
- Ao efetuar um pagamento, a API registra esse pagamento na tabela payments, associando o pagamento ao aluno (via member_id).
- Detalhes do pagamento como método, data, valor e status (pago/não pago) são registrados.

### Consulta de Status:

- O aluno pode consultar o histórico de seus pagamentos e o status do plano atual, acessando informações como a validade do plano e eventuais pagamentos pendentes.

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
|RNF-001| Deve processar requisições do usuário em no máximo 3s |  BAIXA |
|RNF-002| O sistema deve ser escalável para suportar o crescimento da academia, incluindo mais alunos e novos serviços |  ALTA |
|RNF-003| O sistema deve garantir a segurança e confidencialidade dos dados dos alunos |  BAIXA |

## Tecnologias Utilizadas

### Back End

- **Linguagem de Programação:** C# (.NET)
- **Framework:** .NET 8/9
- **Banco de Dados:** MySQL
- **API:** ASP.NET Core Web API
 - **Documentação de API:** Swagger para documentação automática e interface de teste de APIs
- **IDE de Desenvolvimento:** Visual Studio 2019/2022
- **Ferramentas de Versionamento:** Git, usando GitHub
- **Ferramentas de Teste:** xUnit, se necessário.

### Front End

- **Framework:** 
  - **Para Web:** React
  - **Para Mobile:** React Native
- **Linguagens:** JavaScript (ou TypeScript)
- **IDE de Desenvolvimento:** Visual Studio Code ou outro de preferencia.

### Hospedagem

- AWS em um servidor com serviço de IIS

## API Endpoints

Esta documentação cobre os endpoints disponíveis para gerenciar os membros na aplicação de gestão da academia.

## Endpoints

### GET /Cliente

Retorna uma lista de todos os clientes da academia.

- **URL**: `https://localhost:7260/api/Clientes`
- **Método**: `GET`
- **Auth requerida**: Sim
- **Permissões requeridas**: Nenhuma

#### Respostas

- **200 OK**

  Retorna uma lista de estudantes. Exemplo:
```json
{
    "$id": "1",
    "items": {
        "$id": "2",
        "$values": [
            {
                "$id": "3",
                "nome": "DevSenior",
                "email": "DevSenior@dev.com",
                "cpf": "12345567899",
                "telefone": "3199998888",
                "planos": null,
                "pagamentos": null,
                "id": 2
            },
            {
                "$id": "4",
                "nome": "teste",
                "email": "teste@teste.com",
                "cpf": "12345567899",
                "telefone": "1399999999",
                "planos": null,
                "pagamentos": null,
                "id": 1
            }
        ]
    },
    "currentPage": 1,
    "pageSize": 10,
    "totalCount": 2
}
```

### GET /Cliente/{id}
Retorna os detalhes de um membro da academia específico.

- **URL**: `https://localhost:7260/api/Clientes/{id}`
- **Método**: `GET`
- **Auth requerida**: Sim
- **Permissões requeridas**: Nenhuma

#### Parâmetros

- **id** (int) - ID do membro a ser consultado

#### Respostas

- **200 OK**

Retorna os detalhes do membro. Exemplo:

```json
{
    "$id": "1",
    "nome": "teste",
    "email": "teste@teste.com",
    "cpf": "12345567899",
    "telefone": "1399999999",
    "planos": null,
    "pagamentos": null,
    "id": 1
}
```
**404 Not Found**

```json
{
    "$id": "1",
    "message": "Entidade do tipo Cliente com ID 3 não encontrada."
}
```

### POST /Cliente

Cria um novo membro da academia.

- **URL**: `https://localhost:7260/api/Clientes/ `
- **Método**: `POST`
- **Auth requerida**: Sim
- **Permissões requeridas**: Nenhuma

#### Corpo da Requisição

- **Content-Type**: `application/json`
- **Body**:
```json
{
  "nome": "Dev5 test",
  "email": "dev5test@mail.com",
  "cpf": "55223345677",
  "telefone": "3198883333"
}
```

#### Respostas

- **201 Created**
```json
{
    "$id": "1",
    "nome": "Dev5 test",
    "email": "dev5test@mail.com",
    "cpf": "55223345677",
    "telefone": "3198883333",
    "planos": null,
    "pagamentos": null,
    "id": 4
}
```
- **400 Bad Request**
```json
{
    "$id": "1",
    "type": "https://tools.ietf.org/html/rfc9110#section-15.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "errors": {
        "$id": "2",
        "Email": [
            "The Email field is required."
        ]
    },
    "traceId": "00-67dbc2dd59c4d1c35a0c959b091fa4ac-7023ce9e48be9723-00"
}
```

### PUT /Cliente/{id}

Atualiza os detalhes de um estudante existente.

- **URL**: `/members/{id}`
- **Método**: `PUT`
- **Auth requerida**: Sim
- **Permissões requeridas**: Nenhuma

{
    "id": 3,
    "nome": "Dev3 test3",
    "email": "dev3test@mail.com",
    "cpf": "11223345677",
    "telefone": "3198885555"
}
- **200 OK**
Resposta

```json

{
    "$id": "1",
    "nome": "Dev3 test3",
    "email": "dev3test@mail.com",
    "cpf": "11223345677",
    "telefone": "3198885555",
    "planos": null,
    "pagamentos": null,
    "id": 3
}
```

## Considerações de Segurança

### Autenticação

A autenticação garante que apenas usuários e sistemas confiáveis possam acessar a aplicação. Em um ambiente distribuído, a autenticação deve ser robusta e escalável, garantindo que cada requisição seja proveniente de uma fonte autenticada.

Na nossa aplicação, a autenticação é feita através de tokens de autenticação que são passados no cabeçalho da requisição (header) usando o método Bearer Token. Quando um usuário realiza login, um token é gerado e retornado. Esse token deve ser incluído em todas as requisições subsequentes, permitindo acesso aos recursos protegidos da API.

### Proteção contra ataques

Para garantir a segurança da aplicação contra ataques de injeção, como SQL e NoSQL, utilizamos consultas parametrizadas e mapeamento objeto-relacional (ORM). Essas práticas evitam que entradas maliciosas sejam executadas diretamente nos bancos de dados, protegendo o sistema contra a execução de comandos não autorizados e garantindo a integridade das informações. A validação rigorosa das entradas de dados e o uso de práticas seguras de codificação minimizam os riscos de injeção de código malicioso.

## Implantação

### Requisitos de Hardware:

- Servidor Web: Ainda não definido.
- Armazenamento: Banco de dados MySQL
- Memória RAM: 16GB de RAM para lidar com as operações da aplicação.
- Processador: Ainda não definido.
- Requisitos de Software:
- Sistema Operacional: Sistema Operacional Linux
- Servidor Web: Servidor IIS

## Testes

### Caso de teste: 1

- Resumo: Listar Clientes
- Requisito: RF-001
- Prioridade: Alta
- Pré-condição: O usuário deverá estar logado no sistema e com permissões adequadas.

Passos:

- Enviar uma requisição GET para o endpoint /api/Clientes.
- Verificar a resposta do servidor.

Resultado Esperado:

Exibir a lista de clientes cadastrados com código 200.

- Mensagem "Operação bem sucedida".
- Código 401 se o usuário não estiver autenticado.
- Código 500 para erro no servidor.
- Observações: Código 200 com lista de clientes, 401 se não autenticado.
- Comentários: O teste deve garantir que a lista de clientes seja retornada corretamente.

```json
{
    "$id": "1",
    "items": {
        "$id": "2",
        "$values": [
            {
                "$id": "3",
                "nome": "DevSenior",
                "email": "DevSenior@dev.com",
                "cpf": "12345567899",
                "telefone": "3199998888",
                "planos": null,
                "pagamentos": null,
                "id": 2
            },
            {
                "$id": "4",
                "nome": "teste",
                "email": "teste@teste.com",
                "cpf": "12345567899",
                "telefone": "1399999999",
                "planos": null,
                "pagamentos": null,
                "id": 1
            }
        ]
    },
    "currentPage": 1,
    "pageSize": 10,
    "totalCount": 2
}
```

### Caso de teste: 2

- Resumo: Detalhar Cliente
- Requisito: RF-002
- Prioridade: Média
- Pré-condição: O usuário deverá estar logado no sistema.

Passos:

- Enviar uma requisição GET para o endpoint /api/Clientes/{id}.
- Informar o ID de um cliente existente.
- Verificar a resposta do servidor.

Resultado Esperado:

Exibir os detalhes do cliente com código 200.

- Código 404 se o cliente não for encontrado.
- Código 401 se o usuário não estiver autenticado.
- Observações: Código 200 para cliente encontrado, 404 para cliente não encontrado, 401 se não autenticado.
- Comentários: O teste deve garantir que os detalhes corretos do cliente sejam retornados.

```json
{
    "$id": "1",
    "nome": "teste",
    "email": "teste@teste.com",
    "cpf": "12345567899",
    "telefone": "1399999999",
    "planos": null,
    "pagamentos": null,
    "id": 1
}
```

### Caso de teste: 3

- Resumo: Criar Cliente
- Requisito: RF-003
- Prioridade: Alta
- Pré-condição: O usuário deverá estar logado no sistema.

Passos:

- Enviar uma requisição POST para o endpoint /api/Clientes/.
- Preencher os campos nome, email, cpf, e telefone.
- Verificar a resposta do servidor.
- Resultado Esperado:

Exibir mensagem "Operação bem sucedida" com código 201.

- Código 400 se houver erro de validação nos dados fornecidos.
- Código 401 se o usuário não estiver autenticado.
- Observações: Código 201 para cliente criado, 400 para entrada inválida, 401 se não autenticado.
- Comentários: Teste deve verificar se o cliente é criado corretamente e se há validação dos dados de entrada.

```json
{
  "nome": "Dev5 test",
  "email": "dev5test@mail.com",
  "cpf": "55223345677",
  "telefone": "3198883333"
}
```

### Caso de teste: 4

- Resumo: Atualizar Cliente
- Requisito: RF-004
- Prioridade: Média
- Pré-condição: O usuário deverá estar logado no sistema.

Passos:

- Enviar uma requisição PUT para o endpoint /api/Clientes/{id}.
- Informar o ID do cliente a ser atualizado.
- Preencher os campos com os novos dados do cliente.
- Verificar a resposta do servidor.

Resultado Esperado:

Exibir mensagem "Operação bem sucedida" com código 200.

- Código 404 se o cliente não for encontrado.
- Código 400 se houver erro de validação.
- Código 401 se o usuário não estiver autenticado.
- Observações: Código 200 para atualização, 404 para cliente não encontrado, 400 para erro de validação, 401 se não autenticado.
- Comentários: Teste deve garantir que a atualização do cliente funcione e que os erros de validação sejam tratados corretamente.

{
    "id": 3,
    "nome": "Dev3 test3",
    "email": "dev3test@mail.com",
    "cpf": "11223345677",
    "telefone": "3198885555"
}
- **200 OK**
Resposta

```json

{
    "$id": "1",
    "nome": "Dev3 test3",
    "email": "dev3test@mail.com",
    "cpf": "11223345677",
    "telefone": "3198885555",
    "planos": null,
    "pagamentos": null,
    "id": 3
}
```

### Caso de teste: 5

- Resumo: Excluir Cliente
- Requisito: RF-005
- Prioridade: Alta
- Pré-condição: O usuário deverá estar logado no sistema.

Passos:

- Enviar uma requisição DELETE para o endpoint /api/Clientes/{id}.
- Informar o ID do cliente a ser excluído.
- Verificar a resposta do servidor.

Resultado Esperado:

Exibir mensagem "Operação bem sucedida" com código 200.

- Código 404 se o cliente não for encontrado.
- Código 401 se o usuário não estiver autenticado.
- Observações: Código 200 para cliente excluído, 404 para cliente não encontrado, 401 se não autenticado.
- Comentários: Teste deve garantir que o cliente seja excluído corretamente e que o sistema trate corretamente o caso de cliente inexistente.

```json
    Received response (200): 

{
    "status": true,
    "message": "Membro deletado com sucesso"
}
```

### Caso de teste: 6

- Resumo: Criar Cliente com Dados Inválidos
- Requisito: RF-006
- Prioridade: Alta
- Pré-condição: O usuário deverá estar logado no sistema.

Passos:

- Enviar uma requisição POST para o endpoint /api/Clientes/.
- Preencher os campos com dados inválidos (ex.: e-mail inválido).
- Verificar a resposta do servidor.

Resultado Esperado:

Código 400 para erro de validação dos dados.

- Exibir mensagem de erro adequada informando os campos inválidos.
- Código 401 se o usuário não estiver autenticado.
- Observações: Código 400 para erro de validação, 401 se não autenticado.
- Comentários: Teste deve garantir que o sistema retorne erros apropriados para dados inválidos.

```json
    Received response (422): 

{
    "status": false,
    "message": "Falha na validação dos dados",
    "errors": {
        "cpf": [
            "O campo CPF deve ter exatamente 11 dígitos."
        ],
        "phone": [
            "O campo telefone deve ter exatamente 11 dígitos."
        ],
        "date_of_birth": [
            "O campo data de nascimento deve ser uma data válida."
        ],
        "gender": [
            "O campo gênero deve ser um dos seguintes valores: male, female, other."
        ]
    }
}
```

# Painel Gerencial

O Dashboard com as informações gerenciais pode ser acessado aqui: https://rodrigozambon.com.br/dashboard/dataview/372d3171812500279ffcf92375722fe4

# Referências

- COULOURIS, George F. et al. Sistemas distribuídos: conceitos e projeto. 5. ed. Porto Alegre: Bookman, 2013.
- GOUGH, James; BRYANT, Daniel; AUBURN, Matthew. Mastering API Architecture. O'Reilly Media, Inc.. 2021. 
- LAURET, Arnaud. The Design of Web APIs. Manning Publications. 2019.
