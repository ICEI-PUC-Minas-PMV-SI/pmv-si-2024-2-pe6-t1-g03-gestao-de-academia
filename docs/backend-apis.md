# APIs e Web Services

Este projeto consiste em uma aplicação de gestão de academia chamada DEV Fitness, desenvolvida utilizando o framework Laravel no back-end e React no front-end. A aplicação oferece funcionalidades para a administração de membros, pagamentos e planos de treino, com autenticação robusta via tokens API (Sanctum) e proteção por autenticação baseada em tokens. O sistema é integrado com uma API que facilita o acesso seguro a dados de membros, pagamentos e planos, garantindo a eficiência na gestão de uma academia e oferecendo uma experiência segura e escalável para os usuários.

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
    
![image](https://github.com/user-attachments/assets/db87fd84-c1df-44b6-aac7-4b082da71481)
![image](https://github.com/user-attachments/assets/4384cdd3-ca71-4c6f-bfe1-f2c7ba7bed1f)


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
|RNF-001| O sistema deve ser responsivo, garantindo que a interface funcione adequadamente em dispositivos móveis e web | ALTA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA |
|RNF-003| O sistema deve ser escalável para suportar o crescimento da academia, incluindo mais alunos e novos serviços |  ALTA |
|RNF-004| O sistema deve garantir a segurança e confidencialidade dos dados dos alunos |  BAIXA |

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

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
