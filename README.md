# Postgres Image

Este repositório contém os arquivos necessários para criar e configurar uma imagem Docker personalizada do PostgreSQL.

## Pré-requisitos

- Docker instalado ([Guia de instalação do Docker](https://docs.docker.com/get-docker/))
- Docker Compose instalado ([Guia de instalação do Docker Compose](https://docs.docker.com/compose/install/))

## Estrutura do Projeto

- `Dockerfile`: Define a imagem personalizada do PostgreSQL.
- `docker-compose.yaml`: Configura o serviço PostgreSQL.
- `init.sql`: Script SQL para inicializar o banco de dados.
- `README.md`: Documentação do projeto.

## Como criar a imagem e iniciar o container

1. Clone este repositório:

   ```bash
   git clone <url-do-repositorio>
   cd postgres
   ```

2. Construa a imagem e inicie o container:

   ```bash
   docker-compose up --build -d
   ```

3. Verifique se o container está em execução:

   ```bash
   docker ps
   ```

   Você verá um container chamado `microservice` em execução.

## Configuração do Banco de Dados

- Banco de Dados: `postgres`
- Usuário: `postgres`
- Senha: `postgres`

O script init.sql será executado automaticamente ao iniciar o container, criando o banco de dados `microservice`.

## Acessando o Banco de Dados

Você pode acessar o banco de dados usando qualquer cliente PostgreSQL, como o `psql` ou ferramentas gráficas como DBeaver ou pgAdmin.

Exemplo de conexão usando `psql`:

```bash
psql -h localhost -U postgres -d microservice
```

## Portas

O PostgreSQL estará disponível na porta `5432` do host.

## Observações

- O arquivo init.sql pode ser modificado para incluir mais comandos SQL de inicialização.
- Certifique-se de que a porta `5432` não esteja sendo usada por outro serviço no host.

