# 🛠️ Setup Django com Docker e PostgreSQL

Este repositório fornece um setup básico e funcional para iniciar projetos Django utilizando Docker e PostgreSQL. Ideal para desenvolvimento local com ambiente isolado e reprodutível.

---

## 📦 Requisitos

- Python 3.10+
- Docker e Docker Compose
- Git

---

## 🚀 Primeiros Passos

1. **Criar um ambiente virtual:**

```bash
python -m venv .venv
```

Não é necessário ativar o ambiente virtual para este projeto, já que tudo está no Docker. O ambiente é necessário para outras funções

2. **Copiar/renomear o arquivo `.env-example` de exemplo:**

```bash
cp dotenv_files/.env-example dotenv_files/.env
```

Edite o `.env` com suas configurações reais de ambiente (nome do projeto, credenciais de banco etc).
**POSTGRES_HOST** de `.env` deve coincidir com **container_name** de `docker-compose.yml`

3. **Subir os containers Docker:**

Sempre que alterar o `Dockerfile` ou `docker-compose.yml`, use (certifique-se de estar com o Docker aberto):

```bash
docker-compose up --build
```

Caso contrário, apenas:

```bash
docker-compose up -d
```

---

## 🐘 Banco de Dados

Este setup já configura um container com PostgreSQL. Certifique-se de que as variáveis no `.env` estejam corretas para conexão com o banco.

---

## 📝 Configurações adicionais

- No `Dockerfile`, altere a linha `maintainer` para o seu nome ou email.

---

## 📂 Estrutura de pastas

```
/
├── .venv/               # Ambiente virtual local (não incluído no Docker)
├── .vscode/             # Configurações do VS Code
├── data/                # Diretórios para static e media
├── djangoapp/           # Código do projeto Django
├── dotenv_files/        # Variáveis de ambiente (.env)
├── scripts/             # Scripts utilitários (ex: setup, inicialização)
├── .dockerignore        # Arquivos ignorados pelo Docker
├── .gitignore           # Arquivos/pastas ignorados pelo Git
├── docker-compose.yml   # Orquestração dos containers
├── Dockerfile           # Ambiente Docker do Django
└── README.md            # Este arquivo
```

---

## ✅ Pronto para desenvolvimento!

Acesse o app via `http://127.0.0.0:8000` (ou conforme definido no `.env`).
