# 🪣 Baldino (MinIO com Docker Compose)

Este projeto utiliza o [MinIO](https://min.io/) — um servidor de armazenamento de objetos compatível com Amazon S3 — configurado via Docker Compose, com persistência de dados e interface web ativada.

## 🚀 Como iniciar

### 1. Crie o arquivo `.env`

Crie um arquivo `.env` na raiz do projeto com as credenciais de acesso:

```env
MINIO_ROOT_USER=admin
MINIO_ROOT_PASSWORD=admin123
MINIO_SERVER_URL=http://localhost:9000/
MINIO_BROWSER_REDIRECT_URL=http://localhost:9001/console

```

### 2. Suba o serviço

```bash
docker compose up -d
```

### 3. Acesse a interface

* Console Admin: [http://localhost:9001](http://localhost:9001)
* API S3: [http://localhost:9000](http://localhost:9000)

Use as credenciais do `.env` para login.

## 📦 Estrutura dos volumes

Os dados são persistidos no volume Docker chamado `baldino`. Isso garante que os dados não sejam perdidos entre reinicializações do contêiner.

## 🧼 Parar e limpar

```bash
docker compose down -v
```

## 📚 Referências

* [MinIO Docs](https://min.io/docs/minio/)
* [MinIO Console GitHub](https://github.com/minio/console)
* [MinIO Client (mc)](https://min.io/docs/minio/linux/reference/minio-mc.html)