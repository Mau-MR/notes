
# Explanation

# List links
```sh
ls  -l
```
# Create simbolic links

^dba451

> Code example to map vim command to nvim

```sh
sudo ln -s <path from> <path to>
# example
sudo ln -s $(which nvim) /usr/bin/vim
```

# Remove simbolic links
```sh
sudo unlink /<path>/<to>/<link>
# Example
sudo unlink /usr/bin/vim
```