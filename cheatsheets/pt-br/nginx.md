# Comandos Essenciais do Nginx

Este documento contém uma lista de comandos essenciais para gerenciar o servidor Nginx de forma eficiente.

---

## 📌 1. Gerenciamento do Serviço Nginx

### Iniciar o Nginx

Para iniciar o serviço do Nginx:

```bash
sudo systemctl start nginx
```

### Parar o Nginx

Para parar o serviço do Nginx:

```bash
sudo systemctl stop nginx
```

### Reiniciar o Nginx

Para reiniciar o serviço do Nginx (útil após alterações na configuração):

```bash
sudo systemctl restart nginx
```

### Recarregar a configuração do Nginx

Para recarregar a configuração sem interromper as conexões ativas:

```bash
sudo systemctl reload nginx
```

### Verificar o status do Nginx

Para verificar se o Nginx está rodando:

```bash
sudo systemctl status nginx
```

---

## ⚙ 2. Configuração do Nginx

### Testar a configuração antes de aplicar

Antes de reiniciar o Nginx, verifique se a configuração está correta:

```bash
sudo nginx -t
```

### Localização do arquivo de configuração

O arquivo principal de configuração do Nginx geralmente está localizado em:

```bash
/etc/nginx/nginx.conf
```

Outras configurações podem estar em:

```bash
/etc/nginx/sites-available/
/etc/nginx/sites-enabled/
```

---

## 🔥 3. Gerenciamento de Logs

### Acessar logs de acesso

Para visualizar os logs de acesso:

```bash
tail -f /var/log/nginx/access.log
```

### Acessar logs de erros

Para visualizar os logs de erro:

```bash
tail -f /var/log/nginx/error.log
```

---

## 🌐 4. Trabalhando com Hosts Virtuais

### Criar um novo host virtual

1. Criar um novo arquivo de configuração:

```bash
sudo nano /etc/nginx/sites-available/meusite
```

2. Adicionar a configuração básica:

```nginx
server {
    listen 80;
    server_name meusite.com;
    root /var/www/meusite;
    index index.html;
}
```

3. Criar um link simbólico para ativar o site:

```bash
sudo ln -s /etc/nginx/sites-available/meusite /etc/nginx/sites-enabled/
```

4. Testar a configuração e reiniciar o Nginx:

```bash
sudo nginx -t
sudo systemctl restart nginx
```

---

## 🧹 5. Limpeza e Manutenção

### Remover pacotes desnecessários do Nginx

```bash
sudo apt autoremove nginx
```

### Parar e desativar o Nginx no boot

```bash
sudo systemctl disable nginx
```
