**OpenSSH** (Open Secure Shell) é uma implementação **de código aberto** do protocolo SSH (Secure Shell). Ele fornece um conjunto de ferramentas para criar conexões seguras entre computadores em redes não seguras, como a internet. O OpenSSH foi projetado para ser robusto, seguro e flexível.

# Instalação
Para instalar o OpenSSH, execute o seguinte comando no terminal:

```
sudo apt install openssh-server
```

Na mensagem de confirmação, digite `Y` e aperte `Enter`.

## Verificação da instalação
para verificar se foi instalado corretamente, execute:

```
sudo service ssh status
```

# Componentes
O pacote **OpenSSH** inclui diversos componentes, dos quais os mais importantes são:

- **`ssh`** (cliente SSH): Usado para se conectar a servidores SSH remotos e executar comandos de forma segura.
- **`sshd`** (servidor SSH): O daemon que roda no servidor e aguarda conexões SSH de clientes.
- **`scp`** (Secure Copy Protocol): Usado para transferir arquivos entre máquinas de forma segura via SSH.
- **`sftp`** (SSH File Transfer Protocol): Protocolo para transferência de arquivos sobre uma conexão SSH segura, similar ao FTP, mas criptografado.
- **`ssh-keygen`**: Utilitário para gerar chaves SSH públicas e privadas.
- **`ssh-agent`**: Ferramenta que gerencia as chaves privadas de autenticação SSH, permitindo o uso sem a necessidade de inserir senhas repetidamente.