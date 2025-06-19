# 📖 Meu Livro de Receitas

<div align="center">

[![.NET][badge-dot-net]][link-dotnet]
[![CSharp](https://img.shields.io/badge/C%23-13.0-239120?logo=c-sharp&logoColor=white&style=for-the-badge)](https://learn.microsoft.com/pt-br/dotnet/csharp/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)


</div>

<p align="center">
  <a href="#🚀-sobre-o-projeto">Sobre</a> •
  <a href="#✨-funcionalidades">Funcionalidades</a> •
  <a href="#🛠️-tecnologias-e-padrões">Tecnologias</a> •
  <a href="#🏛️-arquitetura">Arquitetura</a> •
  <a href="#🏁-começando">Começando</a> •
  <a href="#👨‍💻-autor">Autor</a>
</p>

---

## 🚀 Sobre o Projeto

O **Meu Livro de Receitas** é uma API RESTful completa, desenvolvida em **.NET 9**, projetada para ser a solução definitiva para amantes da culinária que desejam organizar e compartilhar suas criações. A aplicação permite o gerenciamento completo de receitas, desde o cadastro de usuários até a criação, edição e busca detalhada de pratos, incluindo ingredientes, modo de preparo, tempo, dificuldade e imagens.

Construído com base em princípios de arquitetura robusta como **Domain-Driven Design (DDD)** e **SOLID**, o projeto demonstra a aplicação de boas práticas de desenvolvimento de software em um cenário real. A qualidade do código é assegurada por uma suíte completa de **testes de unidade e integração**, além de uma pipeline de **CI/CD com GitHub Actions** e análise estática contínua com **SonarCloud**.

## ✨ Funcionalidades

-   👤 **Gerenciamento de Usuários**: Cadastro, login e autenticação segura.
-   🔐 **Autenticação Segura**: Implementação de **Tokens JWT** com política de **Refresh Token**.
-   🔗 **Login Social**: Integração para autenticação via **conta Google (OAuth 2.0)**.
-   🍲 **CRUD de Receitas**: Criação, leitura, atualização, exclusão e filtragem de receitas.
-   📸 **Upload de Imagens**: Permite o envio de imagens para ilustrar as receitas.
-   🤖 **Integração com IA**: Uso do **ChatGPT (OpenAI)** para sugerir receitas a partir de ingredientes.
-   📩 **Mensageria Assíncrona**: Gerenciamento de processos em background, como a exclusão de contas, utilizando **filas (Queues)** para garantir resiliência.
-   🧪 **Cobertura de Testes**: Testes de unidade e integração para garantir a estabilidade e a qualidade da aplicação.

## 🛠️ Tecnologias e Padrões

O projeto foi construído utilizando as seguintes tecnologias e padrões de mercado:

#### **Backend & Frameworks**

![badge-dot-net] ![badge-visual-studio] ![badge-swagger]

-   **.NET 9** e **C# 13**
-   **ASP.NET Core**: Para a construção da API.
-   **Entity Framework Core**: ORM para comunicação com o banco de dados.

#### **Bancos de Dados**

![badge-mysql] ![badge-sqlserver]

-   Suporte para **MySQL** e **SQL Server**.
-   **EF Core Migrations**: Para versionamento do schema do banco de dados.

#### **Arquitetura e Boas Práticas**

-   **Domain-Driven Design (DDD)**: Foco no domínio do negócio para uma arquitetura mais limpa e manutenível.
-   **Princípios SOLID**: Para um código mais coeso, desacoplado e extensível.
-   **CQRS (Command Query Responsibility Segregation)**: Separação de responsabilidades de leitura e escrita.
-   **Injeção de Dependência (DI)**: Utilizando o contêiner nativo do .NET.
-   **FluentValidation**: Para validações de dados de forma declarativa e robusta.

#### **Autenticação e Segurança**

![badge-google] ![badge-openai]

-   **JWT (JSON Web Tokens)** & **Refresh Tokens**.
-   **Autenticação OAuth 2.0** com Google.
-   Integração segura com a API da **OpenAI**.

#### **Testes**

-   **xUnit**: Framework de testes.
-   **FluentAssertions**: Para asserções mais legíveis.
-   **Moq**: Para criação de mocks.
-   **Respawn**: Para resetar o estado do banco de dados em testes de integração.

#### **DevOps & Infraestrutura**

![badge-docker] ![badge-azure] ![badge-azure-pipelines] ![badge-sonarcloud]

-   **GitHub Actions**: Para automação de CI/CD (Build, Teste e Análise de Código).
-   **SonarCloud**: Para análise contínua de qualidade e segurança do código.
-   **Docker**: Suporte para containerização da aplicação.
-   **Azure Service Bus**: Como opção para o serviço de mensageria.

## 🏛️ Arquitetura

A solução segue os princípios da **Arquitetura Limpa (Clean Architecture)** e **Domain-Driven Design (DDD)**, dividindo o projeto em camadas com responsabilidades bem definidas:

-   `src/API`: Camada de apresentação. Responsável por expor os endpoints da API, receber as requisições e retornar as respostas.
-   `src/Application`: Camada de aplicação. Orquestra os casos de uso, processa as requisições e coordena a comunicação entre o domínio e a infraestrutura.
-   `src/Domain`: O coração do software. Contém as entidades de negócio, regras de domínio e a lógica principal da aplicação.
-   `src/Infrastructure`: Camada de infraestrutura. Implementa os detalhes técnicos, como acesso ao banco de dados, comunicação com APIs externas e serviços de mensageria.
-   `tests/`: Contém os projetos de testes de unidade e integração, garantindo a qualidade e o comportamento esperado da aplicação.

## 🏁 Começando

Para executar o projeto localmente, siga os passos abaixo.

### Pré-requisitos

-   [.NET 9 SDK][link-dotnet] ou superior.
-   Visual Studio 2022 ou Visual Studio Code.
-   Um cliente Git.
-   SQL Server ou MySQL instalado e rodando.
-   Docker (Opcional, para rodar em container).

### Instalação e Configuração

1.  **Clone o repositório:**
    ```sh
    git clone https://github.com/edielsonsilva/MeuLivroReceitas
    cd MeuLivroReceitas
    ```

2.  **Restaure as dependências do projeto:**
    ```sh
    dotnet restore
    ```

3.  **Configure as variáveis de ambiente:**
    Renomeie o arquivo `appsettings.Development.sample.json` na pasta `src/API` para `appsettings.Development.json` e preencha as informações necessárias, como a string de conexão do banco de dados e as chaves de API.

    **Exemplo (`appsettings.Development.json`):**
    ``` json
        {
        "ConnectionStrings": {
          "DatabaseType": "1",
          "ConnectionMySQLServer": "Server=localhost;Database=MyRecipeBookDB;Uid=root;Pwd=sua_senha_mysql;",
          "ConnectionSQLServer": "Server=localhost;Database=MyRecipeBookDB;User Id=sa;Password=sua_senha_sqlserver;TrustServerCertificate=True"
        },
        "Settings": {
          "Jwt": {
            "SigningKey": "sua_chave_secreta_super_longa_para_jwt_aqui",
            "ExpirationTimeMinutes": 1000
          },
          "IdCryptographyAlphabet": "achIugtW19s7vA4ldomHjULNFYbery0EpTMxkBiQ6qJ2SKXZG35Cz8RDfnPOVw",
          "OpenAI": {
            "ApiKey": "sua_api_key_do_openai"
          },
          "ServiceBus": {
            "DeleteUserAccount": "nome_da_fila_de_exclusao_de_usuario"
          },
          "BlobStorage": {
            "Azure": "sua_connection_string_do_azure_blob_storage"
          },
          "Google": {
            "ClientId": "seu_client_id_do_google.apps.googleusercontent.com",
            "ClientSecret": "seu_client_secret_do_google"
          }
        }
      }
 
### Executando a Aplicação

-   **Via linha de comando:**
    ```sh
    dotnet run --project src/API
    ```
-   **Via Visual Studio:**
    Pressione `F5` ou o botão de play "▶️" para iniciar o projeto.

A API estará disponível em `https://localhost:7068` e a documentação do Swagger UI pode ser acessada em `https://localhost:7068/swagger`.

### Executando os Testes

Para rodar todos os testes de unidade e integração, execute o seguinte comando na raiz do projeto:

```sh
dotnet test
```



## 👨‍💻 Autor

Feito com ❤️ por **Edielson Silverio**.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/edielson-silverio-b27078b5/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/edielsonsilva)

---

<!-- Links -->
[link-dotnet]: https://dotnet.microsoft.com/en-us/download/dotnet/9.0


<!-- Badges -->
[badge-sqlserver]: https://img.shields.io/badge/Microsoft%20SQL%20Server-CC2927?logo=microsoftsqlserver&logoColor=fff&style=for-the-badge
[badge-mysql]: https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=fff&style=for-the-badge
[badge-dot-net]: https://img.shields.io/badge/.NET-9-512BD4?logo=dotnet&logoColor=fff&style=for-the-badge
[badge-visual-studio]: https://img.shields.io/badge/Visual%20Studio-5C2D91?logo=visualstudio&logoColor=fff&style=for-the-badge
[badge-swagger]: https://img.shields.io/badge/Swagger-85EA2D?logo=swagger&logoColor=000&style=for-the-badge
[badge-docker]: https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=fff&style=for-the-badge
[badge-azure]: https://img.shields.io/badge/Microsoft%20Azure-0078D4?logo=microsoftazure&logoColor=fff&style=for-the-badge
[badge-azure-pipelines]: https://img.shields.io/badge/Azure%20Pipelines-2560E0?logo=azurepipelines&logoColor=fff&style=for-the-badge
[badge-google]: https://img.shields.io/badge/Google%20OAuth-4285F4?logo=google&logoColor=fff&style=for-the-badge
[badge-openai]: https://img.shields.io/badge/OpenAI-412991?logo=openai&logoColor=fff&style=for-the-badge
[badge-sonarcloud-quality]: https://img.shields.io/sonar/quality_gate/