# TODO List

API para gerenciar tarefas (CRUD).

## Tecnologias

- Spring Boot
- Spring MVC
- Spring Data JPA
- SpringDoc OpenAPI 3
- Mysql

## Práticas adotadas

- API REST
- Consultas com Spring Data JPA
- Injeção de Dependências
- Geração automática do Swagger com a OpenAPI 3

## Como Executar

- Clonar repositório git
- Construir o projeto:

`./mvnw clean package`

- Executar a aplicação:

`java -jar target/todolist-0.0.1-SNAPSHOT.jar`

A API poderá ser acessada em `localhost:8080`.  
O Swagger poderá ser visualizado em `localhost:8080/swagger-ui/index.html`

## API Endpoints

Para fazer as requisições HTTP abaixo, foi utilizada a ferramenta httpie:

### Criar Tarefa

```
http POST :8080/todos name="To do 1" description="Description 1" priority=1

Resposta:

[
    {
        "description": "Description 1",
        "done": false,
        "id": 1,
        "name": "To do 1",
        "priority": 1
    }
]
```
### Listar Tarefas

```
http GET :8080/todos

Resposta:

[
    {
        "description": "Description 1",
        "done": false,
        "id": 1,
        "name": "To do 1",
        "priority": 1
    }
]
```

### Modificar Tarefa

```
http PUT :8080/todos id=1 name="To do 1" description="Description 1" done=true priority=2

Resposta:

[
    {
        "description": "Description 1",
        "done": true,
        "id": 1,
        "name": "To do 1",
        "priority": 2
    }
]
```

### Deletar Tarefa

```
http DELETE :8080/todos/1

Resposta:

[]
```