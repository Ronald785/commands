# Comandos

## Nginx

```
sudo systemctl stop nginx
```

```
sudo systemctl start nginx
```

```
sudo systemctl restart nginx
```

## Excluir as pastas node_modules em todos os subdiretórios.

```
find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
```

## kill Process

```
sudo lsof -i :Port
```

```
sudo kill -9 port
```
