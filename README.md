# TAD: pgweb

[pgweb](https://github.com/sosedoff/pgweb) é um cliente multi-plataforma para bancos de dados PostgreSQL.

É escrito em Go o que significa que você pode instalar usando `go get`:

```console
go get github.com/sosedoff/pgweb
```

Aqui vamos usar a imagem [docker com o postgres na versão 9.6](https://github.com/docker-library/postgres) com o docker-compose mas se você tiver uma instância local do PostgreSQL já serve.

Colocando o banco no ar:

```console
cd tadpgweb
docker-compose up tad
```

## Preparando o banco

Num outro terminal vamos copiar os arquivos de migração para dentro da pasta do postgres:

```console
sudo cp migrations/*up.sql data/postgres/
```

E depois para aplicar as migrações no banco:
```console
docker-compose exec tad psql -U postgres -d tadpgweb -1 -f /var/lib/postgresql/data/001_create_table_up.sql
docker-compose exec tad psql -U postgres -d tadpgweb -1 -f /var/lib/postgresql/data/002_alter_table_up.sql
docker-compose exec tad psql -U postgres -d tadpgweb -1 -f /var/lib/postgresql/data/003_alter_table_up.sql
docker-compose exec tad psql -U postgres -d tadpgweb -1 -f /var/lib/postgresql/data/004_data_migration_up.sql
```

E finalmente rode o `pgweb`:

```console
pgweb
```
