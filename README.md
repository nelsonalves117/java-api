# Sistema de Reserva de Tickets

## Descrição
Este projeto é uma API desenvolvida com Java Spring Boot que se destaca pela robustez e segurança na gestão de dados. Além das operações básicas de criação, leitura, atualização e exclusão, o sistema implementa diversas práticas avançadas
de segurança para proteger as informações dos usuários. Entre os diferenciais do projeto, destacam-se:

- Criptografia de Senha: Todas as senhas são criptografadas utilizando algoritmos de hashing seguros, garantindo que as informações sensíveis não sejam armazenadas em texto simples.
- Autenticação JWT: A API utiliza JSON Web Tokens (JWT) para autenticação, permitindo um sistema de login seguro e eficiente. Os tokens são gerados durante o login e devem ser incluídos em cada requisição subsequente para verificar a identidade
  do usuário.
- Middleware: O sistema implementa um middleware para filtrar requisições, tornando-o ainda mais seguro.

## Tecnologias Utilizadas
- Java
- Java Spring Boot
- Spring Security
- Maven
- JWT
- BCrypt
- MySQL

## Pré-requisitos
- Docker
- Docker Compose

## Instalação e Execução
### Passos Gerais
1. Para criar a imagem Docker, digite no terminal:
   
       docker build -t java_app .
   
2. Em seguida, para subir os containers:
   
       docker compose up
   

Antes de conseguir utilizar o programa para excluir, atualizar e ver os cadastros do banco, é necessário se autenticar:

3. Utilizando uma ferramente como o Postman ou o Insomnia, faça uma requisição POST para a URL ```http://localhost:8080/users```, com o seguinte body JSON na requisição:
   
```
{
  "name": "John Doe",
  "username": "johndoe",
  "email": "johndoe@example.com",
  "password": "password123",
  "telephone": "+1234567890"
}

```
4. E uma requisição POST para ```http://localhost:8080/users/login``` (com o mesmo JSON acima)

5. Será retornado um Token JWT como esse: ```Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJKb2huIERvZSIsImlzcyI6InRlc3RfaXNzdWVyIiwiZXhwIjoxNzIyNDEzMTg0fQ.MuEDcmH45kFa-dMGS70G4JTMp62EZshwY0MB5NvrtMk```, copie-o.

6. Em seguida, faça um GET para ```http://localhost:8080/users```

7. Pronto! Agora que você esta autenticado, é possível realizar todas as operações livremente nas seguintes rotas:

#### Get All
- GET para ```http://localhost:8080/users```

#### Get by ID
- GET para ```http://localhost:8080/users/:id```

#### Delete
- DELETE para ```http://localhost:8080/users/:id```

#### Create
- POST para ```http://localhost:8080/users``` (junto de um body seguindo o modelo citado na etapa 2)

#### Update
- POST para ```http://localhost:8080/users``` (junto do Body atualizado do usuário)
