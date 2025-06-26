
# 🛍️ Loja API - AV2 Spring Boot

API RESTful para gerenciamento de produtos e categorias com autenticação JWT, documentação via Swagger, testes com JUnit, monitoramento com Actuator + Prometheus + Grafana, e deploy com Docker.

---

## 📦 Tecnologias Utilizadas

- Java 17
- Spring Boot 3.x
- Spring Security + JWT
- Spring Data JPA + H2
- Springdoc OpenAPI (Swagger)
- JUnit 5 + Mockito
- Spring Actuator + Prometheus + Grafana
- Docker

---

## 🚀 Instalação e Execução Local

1. Clone o projeto:

```bash
git clone https://github.com/seu-usuario/loja-api.git
cd loja-api
```

2. Compile o projeto:

```bash
./mvnw clean install
```

3. Execute o projeto:

```bash
./mvnw spring-boot:run
```

🔗 Endpoints disponíveis:

- Swagger UI: http://localhost:8080/swagger-ui.html
- Login: POST http://localhost:8080/auth/login
- Registro: POST http://localhost:8080/auth/register
- Categorias e Produtos: protegidos por JWT

---

## 🔐 Autenticação JWT

1. Registre um usuário com:
```json
POST /auth/register
{
  "username": "admin",
  "password": "123456"
}
```

2. Faça login e receba o token:
```json
POST /auth/login
{
  "username": "admin",
  "password": "123456"
}
```

3. Use o token como Bearer:
```
Authorization: Bearer SEU_TOKEN_JWT
```

---

## ✅ Testes Automatizados

Execute os testes com:

```bash
./mvnw test
```

Os testes utilizam JUnit e Mockito para validar autenticação e regras de negócio.

---

## 📈 Testes de Carga com JMeter

1. Baixe e abra o Apache JMeter: https://jmeter.apache.org/download_jmeter.cgi
2. Crie um Thread Group e um HTTP Request simulando o endpoint POST /auth/login
3. Configure e execute o teste para medir:
   - Throughput
   - Tempo Médio de Resposta
   - Porcentagem de Erros

---

## 📖 Documentação Swagger

Após rodar o projeto, acesse:

🔗 http://localhost:8080/swagger-ui.html

---

## 🩺 Monitoramento com Actuator + Prometheus + Grafana

- Acesse:
  - http://localhost:8080/actuator/health
  - http://localhost:8080/actuator/metrics
  - http://localhost:8080/actuator/prometheus

📊 Configure o Prometheus com o seguinte alvo:
```yaml
static_configs:
  - targets: ['localhost:8080']
```

📈 Use Grafana para criar dashboards baseados nos dados do Prometheus.

---

## 🐳 Deploy com Docker

1. Gere o JAR:
```bash
./mvnw clean package -DskipTests
```

2. Construa a imagem:
```bash
docker build -t loja-api .
```

3. Execute o container:
```bash
docker run -p 8080:8080 loja-api
```

---

## ☁️ Deploy na Nuvem

Você pode usar serviços como:

- 🔧 Railway (https://railway.app)
- 🚀 Render (https://render.com)

Basta importar o repositório com suporte a Docker e definir a porta 8080.

---

## 📬 Contato

Kaique Batista - kaiquebatista38@gmail.com  
Curso: Análise e Desenvolvimento de Sistemas - Newton Paiva
