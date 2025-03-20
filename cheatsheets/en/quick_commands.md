# Commands

## Delete node_modules folders in all subdirectories.

```
find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
```

## Kill Process

```
sudo lsof -i :Port
```

```
sudo kill -9 port
```

## Node Process

```
ps aux | grep node
```

## Compress Folder

```
tar -czvf folder.tar.gz folder
```

## Decompress Folder

```
tar -xzvf folder.tar.gz folder
```
