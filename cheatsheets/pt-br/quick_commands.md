# Comandos

## Excluir as pastas node_modules em todos os subdiretórios.

```
find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
```

## kill process

```
sudo lsof -i :Port
```

```
sudo kill -9 port
```

## Node process

```
ps aux | grep node
```

## Compactar pasta

```
tar -czvf folder.tar.gz folder
```

## Descompactar pasta

```
tar -xzvf folder.tar.gz folder
```
