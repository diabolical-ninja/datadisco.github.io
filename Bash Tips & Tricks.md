# Handy Tricks for Bash

## File Sizes
Size of all files in a directory
```bash
du -h
```

Size of current directory
```bash
du -h -s
```

Size of top-level directories within current directory
```bash
du -h -d 1
```


## Find files
### List Files & directories
```bash
ls
```

### Filter on name
```bash
ls | grep "<file/directory name>"
```

