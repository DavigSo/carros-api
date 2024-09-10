Mais um exemplo de fixação para SpringBoot do professor Wellington DE Oliveira

# Carro API

Esta é uma aplicação Spring Boot que gerencia uma entidade `Carro`. A aplicação expõe uma API REST para realizar operações CRUD (Criar, Ler, Atualizar e Deletar) sobre carros.

## Estrutura do Projeto

- **`app.entity.Carro`**: Representa a entidade `Carro` com atributos `id`, `nome` e `ano`.
- **`app.repository.CarroRepository`**: Interface que estende `JpaRepository` para operações CRUD.
- **`app.service.CarroService`**: Camada de serviço que contém a lógica de negócios para manipulação dos carros.
- **`app.controller.CarroController`**: Controlador REST que expõe os endpoints da API.
- **`app.app.AppApplication`**: Classe principal da aplicação Spring Boot.
- **`app.app.AppApplicationTests`**: Teste de integração básico da aplicação.

## Pré-requisitos

- Java 11 ou superior
- Maven ou Gradle (para gerenciamento de dependências)
- MySQL ou qualquer outro banco de dados compatível com JPA

## Configuração

1. **Clone o Repositório:**

   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd <NOME_DO_DIRETORIO>
   ```

2. **Configure o Banco de Dados:**

   Certifique-se de que você tenha um banco de dados configurado e acessível. Atualize as configurações do banco de dados no arquivo `application.properties` (ou `application.yml` se estiver usando YAML) na pasta `src/main/resources`:

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/nome_do_banco_de_dados
   spring.datasource.username=usuario
   spring.datasource.password=senha
   spring.jpa.hibernate.ddl-auto=update
   ```

3. **Construa o Projeto:**

   Para Maven:
   
   ```bash
   mvn clean install
   ```

   Para Gradle:
   
   ```bash
   gradle build
   ```

## Execução

Para iniciar a aplicação, execute o comando:

```bash
mvn spring-boot:run
```

ou, se estiver usando Gradle:

```bash
gradle bootRun
```

A aplicação estará disponível em `http://localhost:8080`.

## Endpoints da API

### Criar Carro

- **Método:** `POST`
- **URL:** `/api/carro/save`
- **Corpo da Requisição:**
  
  ```json
  {
    "nome": "Modelo X",
    "ano": 2024
  }
  ```

- **Resposta:** Mensagem de sucesso ou erro

### Atualizar Carro

- **Método:** `PUT`
- **URL:** `/api/carro/update/{id}`
- **Corpo da Requisição:**

  ```json
  {
    "nome": "Modelo Y",
    "ano": 2025
  }
  ```

- **Resposta:** Mensagem de sucesso ou erro

### Deletar Carro

- **Método:** `DELETE`
- **URL:** `/api/carro/delete/{id}`

- **Resposta:** Mensagem de sucesso ou erro

### Buscar Todos os Carros

- **Método:** `GET`
- **URL:** `/api/carro/findAll`

- **Resposta:**

  ```json
  [
    {
      "id": 1,
      "nome": "Modelo X",
      "ano": 2024
    }
  ]
  ```

### Buscar Carro por ID

- **Método:** `GET`
- **URL:** `/api/carro/findById/{id}`

- **Resposta:**

  ```json
  {
    "id": 1,
    "nome": "Modelo X",
    "ano": 2024
  }
  ```

## Testes

Para executar os testes, use:

```bash
mvn test
```

ou, se estiver usando Gradle:

```bash
gradle test
```

