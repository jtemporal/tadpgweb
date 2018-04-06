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

e num outro terminal rode o `pgweb`:

```console
pgweb
```
