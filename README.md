# API de Cadastro de Usuários

Este projeto consiste em uma API REST desenvolvida com FastAPI para cadastro de usuários e um script Python para enviar dados de usuários a partir de um arquivo CSV.

## Requisitos

- Python 3.8+
- Dependências listadas em `requirements.txt`

## Instalação

1. Clone o repositório
2. Instale as dependências:
```bash
pip install -r requirements.txt
```

## Estrutura do Projeto

- `main.py`: API FastAPI com endpoints para cadastro de usuários
- `send_users.py`: Script para enviar dados de usuários do CSV para a API
- `usuarios.csv`: Arquivo CSV com dados de exemplo dos usuários
- `requirements.txt`: Lista de dependências do projeto

## Como Usar

1. Inicie a API:
```bash
python main.py
```

2. Em outro terminal, execute o script para enviar os dados:
```bash
python send_users.py
```

## Endpoints da API

### POST /token
- Autenticação JWT
- Credenciais padrão:
  - Username: admin
  - Password: admin

### POST /usuarios
- Cadastro de usuários
- Requer autenticação JWT
- Campos necessários:
  - nome (string)
  - email (formato válido de email)
  - cpf (formato XXX.XXX.XXX-XX)
  - data_nascimento (formato YYYY-MM-DD)

## Validações

- Nome não pode ser vazio
- Email deve ser válido
- CPF deve seguir o formato correto
- Data de nascimento deve ser válida e não pode ser no futuro

## Respostas

- 201: Usuário cadastrado com sucesso
- 400: Dados inválidos
- 401: Não autorizado (token inválido ou ausente)