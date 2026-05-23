# 🔐 Auth Service com JWT + Refresh Token

Serviço de autenticação completo com JWT de curta duração e refresh token rotativo.

## 🛠 Tecnologias
- Kotlin + Spring Boot 3.2
- Spring Security
- JWT (jjwt 0.12)
- PostgreSQL
- BCrypt

## 📋 Funcionalidades
- Registro de usuário com senha hasheada (BCrypt)
- Login com geração de Access Token (15min) + Refresh Token (7 dias)
- Refresh de token com rotação automática (previne reuso)
- Logout com revogação de todas as sessões ativas

## 🚀 Como rodar

```bash
docker-compose up -d
./gradlew bootRun
```

## 📡 Endpoints

| Método | Rota | Descrição |
|--------|------|-----------|
| POST | `/api/auth/register` | Cria conta |
| POST | `/api/auth/login` | Login e retorna tokens |
| POST | `/api/auth/refresh` | Renova access token |
| POST | `/api/auth/logout/{userId}` | Revoga todas as sessões |

### Exemplo
```json
POST /api/auth/login
{ "email": "jhonata@dev.com", "password": "senha123" }

Response:
{ "accessToken": "eyJ...", "refreshToken": "uuid...", "userId": "..." }
```

---
> Projeto desenvolvido por **Jhonata Breno** — Estudante de ADS | Backend Developer
