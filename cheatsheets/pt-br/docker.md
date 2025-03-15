# Comandos Docker Essenciais

Este documento contém uma lista de comandos essenciais do Docker que todo programador deve conhecer para trabalhar de forma eficiente com contêineres e imagens.

---

## 📌 1. Informações sobre o Docker

### Verificar a versão do Docker

Para verificar a versão do Docker instalada:

```bash
docker --version
```

### Listar imagens do Docker

Para listar todas as imagens baixadas no seu sistema:

```bash
docker images
```

### Buscar uma imagem no Docker Hub

Para procurar por uma imagem no Docker Hub:

```bash
docker search <nome-da-imagem>
```

---

## 🛠 2. Gerenciamento de Contêineres

### Listar contêineres em execução

Para listar todos os contêineres que estão em execução:

```bash
docker ps
```

Para listar todos os contêineres, incluindo os que estão parados:

```bash
docker ps -a
```

### Executar um contêiner

Para rodar um contêiner a partir de uma imagem (exemplo com a imagem `nginx`):

```bash
docker run -d -p 80:80 --name meu-nginx nginx
```

**Explicação**:

-   `-d`: Rodar em modo "detached" (em segundo plano).
-   `-p 80:80`: Mapeia a porta 80 do contêiner para a porta 80 do host.
-   `--name`: Define um nome para o contêiner.

### Parar e iniciar um contêiner

Para parar um contêiner que está em execução:

```bash
docker stop <nome-ou-id-do-container>
```

Para iniciar um contêiner que já foi criado, mas está parado:

```bash
docker start <nome-ou-id-do-container>
```

### Remover um contêiner

Para remover um contêiner parado:

```bash
docker rm <nome-ou-id-do-container>
```

Para forçar a remoção de um contêiner em execução:

```bash
docker rm -f <nome-ou-id-do-container>
```

---

## 🖼 3. Gerenciamento de Imagens

### Criar uma imagem Docker

Para criar uma imagem a partir de um Dockerfile:

```bash
docker build -t nome-da-imagem .
```

O `.` refere-se ao diretório atual onde o Dockerfile está localizado.

### Remover uma imagem

Para remover uma imagem Docker:

```bash
docker rmi <nome-ou-id-da-imagem>
```

### Atualizar imagens

Para atualizar uma imagem para a versão mais recente:

```bash
docker pull <nome-da-imagem>
```

---

## 🗄 4. Gerenciamento de Volumes

### Listar volumes

Para listar os volumes Docker:

```bash
docker volume ls
```

### Criar e remover volumes

Para criar um volume:

```bash
docker volume create <nome-do-volume>
```

Para remover um volume:

```bash
docker volume rm <nome-do-volume>
```

---

## 📡 5. Redes no Docker

### Criar uma rede Docker personalizada

```bash
docker network create <nome-da-rede>
```

### Listar redes existentes

```bash
docker network ls
```

---

## 📂 6. Logs e Diagnóstico

### Ver logs de um contêiner

Para visualizar os logs de um contêiner em execução:

```bash
docker logs <nome-ou-id-do-container>
```

### Inspecionar um contêiner ou imagem

Para obter detalhes sobre um contêiner ou imagem:

```bash
docker inspect <nome-ou-id-do-container-ou-imagem>
```

### Acessar um contêiner em execução

Para acessar o terminal de um contêiner em execução (usando `bash` ou `sh`):

```bash
docker exec -it <nome-ou-id-do-container> bash
```

Se o contêiner não tiver `bash`, você pode tentar `sh`:

```bash
docker exec -it <nome-ou-id-do-container> sh
```

---

## 🧹 7. Limpeza e Otimização

### Limpar contêineres, imagens e volumes não utilizados

Para remover todos os contêineres parados, imagens não usadas e volumes não utilizados:

```bash
docker system prune
```

---

## ⚙ 8. Docker Compose

### Executar o Docker Compose

O Docker Compose é uma ferramenta para definir e rodar aplicações multi-contêineres. Para rodar a aplicação definida no `docker-compose.yml`:

```bash
docker-compose up
```

Para rodar em segundo plano (modo detached):

```bash
docker-compose up -d
```

Para parar e remover os contêineres, redes e volumes criados pelo `docker-compose`:

```bash
docker-compose down
```
