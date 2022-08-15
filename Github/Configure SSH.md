<h1>SSH Configuration</h1>

>Check the full reference on: https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-


<h2>SSH-KEY generator</h2>

```sh
ssh-keygen -t ed25519 -C "your_email@example.com"
```

## Adding your SSH key to the ssh-agent

Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for existing SSH keys and generated a new SSH key.

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
  
3.  Add the SSH key to your account on GitHub. For more information, see "[Adding a new SSH key to your GitHub account](https://docs.github.com/es/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)."

<h2>Probar la autenticacion</h2>
-   Abre la Terminal.

-   Ingresa lo siguiente:
  
    ```sh
    $ ssh -T git@github.com
    # Attempts to ssh to GitHub
    ```

Puedes ver una advertencia como la siguiente:

```sh
    > La autenticidad del host 'github.com (DIRECCIÓN IP)' no se puede establecer.
    > La clave de huella digital RSA es SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
    > ¿Estás seguro de que quieres continuar conectado (sí/no)?
```
    
-   Verifica que la huella dactilar en el mensaje que ves empate con [la huella dactilar de la llave pública de GitHub](https://docs.github.com/es/github/authenticating-to-github/githubs-ssh-key-fingerprints). Si lo hace, entonces teclea `yes`:

```sh
> Hi username! You've successfully authenticated, but GitHub does not
> provide shell access.
```

<h2>Use</h2>
Once  the authentication has been done correctly, add a remote origin to ssh like this

```sh
git remote set-url origin git@github.com:<Username>/<Project>.git
```

or clone it directly

```sh 
git clone git@github.com:<Username>/<Project>.git
```