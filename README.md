# API Usuário

API REST simples para cadastro e gerenciamento de usuários, desenvolvida com Spring Boot e MongoDB.

## 🚀 Tecnologias

- Java 25
- Spring Boot 4.1.1
- Spring Web (MVC)
- Spring Data MongoDB
- Maven

## 📁 Estrutura do projeto

src/main/java/com/yudipires/api_usuario/
├── ApiUsuarioApplication.java # Classe principal
├── business/
│ └── UsuarioService.java # Regras de negócio
├── controller/
│ └── UsuarioController.java # Endpoints REST
└── infrastructure/
├── entities/
│ └── Usuario.java # Entidade/documento MongoDB
└── repository/
└── UsuarioRepository.java # Repositório Mongo


## ⚙️ Configuração

O projeto usa o MongoDB como banco de dados. Copie o arquivo de exemplo e preencha com suas credenciais:

```bash
cp application.properties.example src/main/resources/application.properties
```

Edite `src/main/resources/application.properties` com a URI da sua instância MongoDB (Atlas ou local):

```properties
spring.application.name=api-usuario
spring.mongodb.uri=mongodb+srv://<usuario>:<senha>@<cluster>.mongodb.net/api_usuario?retryWrites=true&w=majority
```

> ⚠️ **Nunca** faça commit do `application.properties` com credenciais reais. Esse arquivo já está no `.gitignore`.

## ▶️ Como executar

Usando o Maven Wrapper (não precisa ter o Maven instalado):

```bash
./mvnw spring-boot:run
```

No Windows:

```bash
mvnw.cmd spring-boot:run
```

A aplicação sobe por padrão em `http://localhost:8080`.

### Rodar os testes

```bash
./mvnw test
```

## 📌 Endpoints

Base path: `/usuarios`

| Método | Rota                  | Descrição                    |
|--------|-----------------------|-------------------------------|
| POST   | `/usuarios`            | Cria um novo usuário          |
| GET    | `/usuarios`            | Lista todos os usuários       |
| PUT    | `/usuarios`            | Atualiza um usuário existente |
| DELETE | `/usuarios?id={id}`    | Remove um usuário pelo id     |

### Exemplo de corpo (POST/PUT)

```json
{
  "id": "opcional-na-criacao",
  "nome": "Yudi Pires",
  "email": "yudi@example.com"
}
```

## 📝 Licença

Projeto de estudo — sem licença definida.