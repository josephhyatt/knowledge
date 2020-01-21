# Backup System \(rsync\)

Save `/home` directory excluding `.cache` and `station` directories 

```text
sudo rsync -aAXv --delete --exclude={/home/joe/.cache/,/home/joe/station/} /home /run/media/joe/backup
```

