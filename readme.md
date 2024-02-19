# ARCHITECTURE

Este projeto é um exemplo de arquitetura utilizando novas tecnologias e melhores práticas.

O objetivo é aprender e compartilhar conhecimento e utilizá-lo como referência para novos projetos.

## PRINCÍPIOS e PADRÕES

* Arquitetura Limpa
* Código Limpo
* Princípios SÓLIDOS
* Princípio KISS
* Princípio SECO
* Princípio do fracasso rápido
* Princípio Comum de Fechamento
* Princípio Comum de Reutilização
* Princípio das Dependências Acíclicas
* Padrão Mediador
* Padrão de resultado
* Estrutura de pasta por recurso
* Separação de preocupações

## BENEFÍCIOS

* Arquitetura simples e evolutiva.
* Fluxo padronizado e centralizado para validação, log, segurança, retorno, etc.
* Evite referências cíclicas.
* Evite injeção de dependência desnecessária.
* Segregação por recurso em vez de tipo técnico.
* Responsabilidade única por cada solicitação e resposta.
* Simplicidade de testes unitários.

## TECNOLOGIAS

* [.NET](https://dotnet.microsoft.com/download)
* [ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core)
* [Núcleo do Entity Framework](https://docs.microsoft.com/en-us/ef/core)
* [C#](https://docs.microsoft.com/en-us/dotnet/csharp)
* [Angular](https://angular.io/docs)
* [UIkit](https://getuikit.com/docs/introduction)
## RUN

<detalhes>
<summary>Linha de comando</summary>

#### Pré-requisitos

* [SDK do .NET](https://dotnet.microsoft.com/download/dotnet)
* [SQL Server](https://go.microsoft.com/fwlink/?linkid=866662)
* [Nó](https://nodejs.org)
* [CLI Angular](https://cli.angular.io)

#### Passos

1. Abra o diretório **source\Web\Frontend** na linha de comando e execute **npm i**.
2. Abra o diretório **source\Web** na linha de comando e execute **dotnet run**.
3. Abra <https://localhost:8090>.

</detalhes>

<detalhes>
<summary>Código do Visual Studio</summary>

#### Pré-requisitos

* [SDK do .NET](https://dotnet.microsoft.com/download/dotnet)
* [SQL Server](https://go.microsoft.com/fwlink/?linkid=866662)
* [Nó](https://nodejs.org)
* [CLI Angular](https://cli.angular.io)
* [Código do Visual Studio](https://code.visualstudio.com)
* [Extensão C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)
* 
#### Passos

1. Abra o diretório **source\Web\Frontend** na linha de comando e execute **npm i**.
2. Abra o diretório **source** no Visual Studio Code.
3. Pressione **F5**.

</detalhes>

<detalhes>
<summary>Visual Studio</summary>

#### Pré-requisitos

* [Visual Studio](https://visualstudio.microsoft.com)
* [Nó](https://nodejs.org)
* [CLI Angular](https://cli.angular.io)

#### Passos

1. Abra o diretório **source\Web\Frontend** na linha de comando e execute **npm i**.
2. Abra **source\Architecture.sln** no Visual Studio.
3. Defina **Architecture.Web** como projeto de inicialização.
4. Pressione **F5**.

</detalhes>

<detalhes>
<summary>Docker</summary>

#### Pré-requisitos

* [Docker](https://www.docker.com/get-started)

#### Passos

1. Execute **docker compose up --build -d** no diretório docker.
2. Abra <http://localhost:8090>.

</detalhes>

## CAMADAS

**Web:** Frontend e Backend.

**Aplicação:** Controle de fluxo.

**Domínio:** regras de negócios e lógica de domínio.

**Modelo:** Objetos de transferência de dados.

**Banco de dados:** Persistência de dados.

## REDE

### FRONT-END

### Serviço

## LAYERS
**Web:** Frontend e Backend.

**Aplicação:** Controle de fluxo.

**Domínio:** regras de negócios e lógica de domínio.

**Modelo:** Objetos de transferência de dados.

**Banco de dados:** Persistência de dados.

## REDE

### FRONT-END

### Serviço

É a interface entre frontend e backend e possui uma lógica que não pertence aos componentes.

### Guarda

Valida se uma rota pode ser ativada.

### Manipulador de erros

Ele fornece um gancho para tratamento centralizado de exceções.

###HttpInterceptor

Ele intercepta e trata um HttpRequest ou HttpResponse.

### PROCESSO INTERNO

### Controlador

Não possui nenhuma lógica, regras de negócios ou dependências além do mediador.

## APLICATIVO

Possui apenas fluxo de negócios, não regras de negócios.

### Solicitar

Possui propriedades que representam a solicitação.

### Validador de solicitação

Possui regras para validação da solicitação.

### Resposta

Possui propriedades que representam a resposta.

### Manipulador

Ele é responsável pelo fluxo de negócios e pelo processamento de uma solicitação para retornar uma resposta.

Chama-se fábricas, repositórios, unidade de trabalho, serviços ou mediador, mas não possui regras de negócio.

### Fábrica

Ele cria um objeto complexo.

Qualquer alteração no objeto afeta o tempo de compilação e não o tempo de execução.

## DOMÍNIO
Não tem nenhuma referência a nenhuma camada.

Possui agregados, entidades, objetos de valor e serviços.

### Agregado

Define um limite de consistência em torno de uma ou mais entidades.

O objetivo é modelar invariantes transacionais.

Uma entidade em um agregado é a raiz, quaisquer outras entidades no agregado são filhas da raiz.

### Entidade

Tem identidade única. A identidade pode abranger múltiplos contextos limitados e durar além da vida.

A alteração de propriedades só é permitida através de métodos de negócio internos da entidade e não através de acesso direto às propriedades.

### Objeto de valor

Não tem identidade e é imutável.

É definido apenas pelos valores de suas propriedades.

Para atualizar um objeto de valor, você deve criar uma nova instância para substituir a antiga.

Pode ter métodos que encapsulam a lógica do domínio, mas esses métodos não devem ter efeitos colaterais no estado.

### Serviços

Ele executa operações de domínio e regras de negócios.

Não tem estado e não possui operações que não façam parte de uma entidade ou objeto de valor.

## MODELO

Possui propriedades para transportar e retornar dados.

## BASE DE DADOS

Ele encapsula a persistência de dados.

### Contexto

Ele configura a conexão e representa o banco de dados.

### Configuração da Entidade

Configura a entidade e suas propriedades no banco de dados.

### Repositório

Ele herda do repositório genérico e implementa apenas métodos específicos.