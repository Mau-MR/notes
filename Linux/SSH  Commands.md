# SSH Commands

## Generate SSH Key
```sh
ssh-keygen -t ed25519 -C "your_email@example.com"
```

## SSH Agent Commands
1.  Inicia el agente SSH en segundo plano.

```sh
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```

Dependiendo de tu ambiente, puede que necesites utilizar un comando diferente. Por ejemplo, puede que necesites utilizar acceso de raíz ejecutando `sudo -s -H` antes de iniciar el ssh-agent, o puede que necesites utilizar `exec ssh-agent bash` o `exec ssh-agent zsh` para ejecutar el ssh-agent.


2.  Add your SSH private key to the ssh-agent. Si creaste tu llave con un nombre diferente o si estás agregando una llave existente que tenga un nombre diferente, reemplaza a _id_ed25519_ en el comando con el nombre de tu archivo de llave privada.
  
```sh
$ ssh-add ~/.ssh/id_ed25519
```

