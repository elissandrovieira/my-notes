Este projeto faz parte do [[Rank1]] dentro do [[Common-core]] da [[42]].
O objetive desse projeto é criar uma maquina virtual [[Linux]], mas sem usar nenhum "facilitador", como utilizar a instalação simplificada, instalar um [[Window System]] ou um [[GUI]] ao entrar no sistema. Dessa maneira, eu devo configurar tudo do zero - desde os acessos, até configurações de [[SSH]] e [[firewall]].

# Instalação
A instalação da máquina virtual segue um passo a passo básico, só se deve ter maior cuidado com o [[LVM]].

# Instalação do sudo
Para instalar o [[sudo]], precisamos estar no root user. 

Para isso devemos digitar o comando *su* no terminal. 

```
su
```

# Configuração de usuários e grupos

## [[Grupos]]
Precisamos criar um grupo chamado `user42`.

## Usuários
Iremos incluir nosso usuário `eteofilo` dentro dos grupos `sudo` e `user42`. Veja [[Grupos]] para saber como fazer.

# Instalação e configuração do [[SSH]]
Agora, iremos instalar o [[OpenSSH]], uma ferramenta que inclui um servidor e um cliente SSH.

Após a instalação do OpenSSH, alguns arquivos vão ter sido criados e nós temos que configura-los.

## sshd_config
Acesse:

```
sudo vim /etc/ssh/sshd_config
```

Depois, encontre a linha `#PORT 22` e substitua por `PORT 4242` para mudar a porta de acesso da porta padrão para a 4242. O `#` deve ser apagado, por que é a anotação de comentário.

Agora, encontre a linha `#PermitRootLogin prohibit-password` e substitua por `PermitRootLogin no` para não permitir o acesso como root a partir de uma conexão SSH. O `#` também deve ser apagado.

Depois dessas modificações, salve o arquivo.

## ssh_config
Acesse:

```
sudo vim /etc/ssh/ssh_config
```

E faça a mesma coisa que fizemos no arquivo `sshd_config`.

# Instalação e configuração do firewall
Devemos instalar e configurar o firewall através do [[UFW]].

# Configuração do sudo
Crie o seguinte arquivo nesse caminho:

```
/etc/sudoers.d/sudo_config
```

Também devemos criar uma pasta para armazenar os logs de cada comando sudo que executarmos:

```
mkdir /var/log/sudo
```

Agora devemos editar o arquivo `sudo_config`e introduzir os seguintes comando para adicionar todos os requisitos do subject.

```
Defaults  passwd_tries=3
Defaults  badpass_message="Mensagem de erro"
Defaults  logfile="/var/log/sudo/sudo_config"
Defaults  log_input, log_output
Defaults  iolog_dir="/var/log/sudo"
Defaults  requiretty
Defaults  secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
```

## O que cada comando faz?
- passwd_tries - Número de tentativas de inserir uma senha errada.
- badpass_message - Mensagem de erro.
- logfile - Arquivo que ficarão registrados todos os logs do sudo.
- log_input, log_output & iolog_dir - Para que cada comando, tanto input como output, fique arquivado na pasta específica selecionada.
- requiretty - Para que o sudo só possa ser usado em terminais interativos. Isso significa que **não será permitido** o uso de sudo em ambientes como scripts ou conexões remostas sem um terminal interativo.
- secure_path - Para restringir o acesso do sudo apenas a caminhos confiáveis.

# Configurações de política de senhas fortes
Precisamos editar o arquivo `login.defs`

```
/etc/login.defs
```

Devemos modificar os seguintes parâmetros:

`PASS_MAX_DAYS 99999` para `PASS_MAX_DAYS 30`
`PASS_MIN_DAYS 0` para `PASS_MIN_DAYS 2`

- `PASS_MAX_DAYS` - Tempo em dias para senha expirar.
- `PASS_MIN_DAYS` - Tempo mínimo em dias para que a senha possa ser alterada.
- `PASS_WARN_AGE` - Avisa que falta x tempo para a senha expirar.

## Instalação e configuração do [[libpam-pwquality]]
Depois de instalar o `libpam-pwquality`, iremos editar o arquivo `common-password`.
Após `retry=3` devemos acrescentar os seguintes comandos:

```
minlen=10 #O número mínimo de caracteres que a senha deve ter.

ucredit=-1      #Deve conter pelo menos uma letra maiúscula. Usamos `-`,
				se fosse `+` estaríamos dizendo que seria no máximo uma
				letra maiúscula.
			
dcredit=-1      #Deve conter pelo menos 1 dígito.

lcredit=-1      #Deve conter pelo menos 1 letra minúscula.

maxrepeat=3     #Máximo de vezes em que um caracter pode ser repetido
				seguido.

reject_username #Não é permitido conter o nome do usuário

difok=7         #Deve conter pelo menos 7 caracteres que não fazem parte
				da senha antiga.
		
enforce_for_root #Essa política será aplicada ao root.
```

Ficará assim:

![[Screenshot from 2024-11-12 18-01-30.png]]

## Verificação de usuário
Essas políticas só serão aplicadas a novos usuários. Para ver se um usuário está em conformidade com as novas políticas, digite o comando:

```
sudo change -l username
```

Se verificarmos que o usuário não cumpre com a política, devemos modificar o número mínimo e máximo para alterações entre senhas, com o seguinte comando:

```
sudo change -m 2 username #Modifica o mínimo de dias para trocar a senha.
sudo change -M 30 username #Modifica o máximo de dias.
```


# Conectar via SSH
Com todas essas configurações feitas, podemos conectar nossa maquina virtual a física via SSH, seguindo esses passos:

![[Pasted image 20241112182644.png]]![[Pasted image 20241112182700.png]]
![[Pasted image 20241112182710.png]]
![[Pasted image 20241112182721.png]]

Depois disso basta se conectar com o comando `ssh username@localhost -p 4242`.

# Script
Na avaliação posso precisar explicar cada comando.

## 1. Arquitetura
Para ver a arquitetura do OS e a sua versão do kernel, usamos o comando `uname -a` (`-a` == `--all`).

```
eteofilo@eteofilo42:~$ uname -a
Linux eteofilo42 6.1.0-26-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.112-1 (2024-09-30) x86_64 GNU/Linux
```
