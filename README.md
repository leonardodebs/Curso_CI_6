# Curso de CI/CD com Go
![Linguagem Principal](https://img.shields.io/badge/Linguagem-Go-blue.svg)

## Sobre o Projeto

O Curso CI/CD com Go é uma aplicação de demonstração para o curso de Controle de Versão e Desenvolvimento Contínuo (CI/CD) em Go. A aplicação é uma API RESTful que fornece métodos para criar, atualizar e deletar registros em um banco de dados PostgreSQL.

## Funcionalidades Principais

* Criação de registros em banco de dados PostgreSQL
* Atualização de registros em banco de dados PostgreSQL
* Deleção de registros em banco de dados PostgreSQL
* Gerenciamento de conexão com banco de dados PostgreSQL

## Pré-requisitos

* Go Instalado na máquina 🚀
* Docker Instalado na máquina 🐳
* Docker Compose Instalado na máquina 🐳

## Instalação

### Passo 1: Clonar o Repositório

```bash
git clone https://github.com/guilhermeonrails/Curso_CI_6.git
```

### Passo 2: Criar arquivo `.env` com as variáveis de ambiente

```bash
DBPORT=5432
DBUSER=root
DBPASSWORD=root
DBNAME=root
```

### Passo 3: Rodar comandos para construir a imagem e subir o container do PostgreSQL

```bash
docker-compose build
docker-compose up -d
```

### Passo 4: Rodar o comando para construir a imagem e subir o container da aplicação

```bash
go build main.go
./main
```

## Exemplos de uso:

* Criar um novo registro:

```bash
curl -X POST \
  http://localhost:8000/registros \
  -H 'Content-Type: application/json' \
  -d '{"nome": "João", "idade": 20}'
```

* Atualizar um registro:

```bash
curl -X PUT \
  http://localhost:8000/registros/1 \
  -H 'Content-Type: application/json' \
  -d '{"nome": "Maria", "idade": 25}'
```

* Deletar um registro:

```bash
curl -X DELETE \
  http://localhost:8000/registros/1
```

## Estrutura Simplificada do Projeto

```markdown
.
├── main.go
├── main_test.go
├── controllers
│   ├── registrController.go
│   └── ...
├── database
│   ├── db.go
│   └── ...
├── models
│   ├── registro.go
│   └── ...
├── routes
│   ├── routes.go
│   └── ...
└── templates
    └── ...
```

## Licença

Este projeto é licenciado sob a Licença MIT. Você pode ver o texto da licença em [LICENSE.md](LICENSE.md). 💡