Este projeto faz parte do [[Rank1]] dentro do [[Common-core]] da [[42]].
O objetive desse projeto é criar uma maquina virtual [[Linux]], mas sem usar nenhum "facilitador", como utilizar a instalação simplificada, instalar um [[Window System]] ou um [[GUI]] ao entrar no sistema. Dessa maneira, eu devo configurar tudo do zero - desde os acessos, até configurações de [[SSH]] e [[firewall]].

# Instalação
A instalação da máquina virtual segue um passo a passo básico, só se deve ter maior cuidado com o [[LVM]].

# Instalação do sudo
Para instalar o [[sudo]], precisamos estar no root user. 

Para isso devemos digitar o comando *su* no terminal. 

```bash
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

```bash
sudo vim /etc/ssh/sshd_config
```

Depois, encontre a linha `#PORT 22` e substitua por `PORT 4242` para mudar a porta de acesso da porta padrão para a 4242. O `#` deve ser apagado, por que é a anotação de comentário.

Agora, encontre a linha `#PermitRootLogin prohibit-password` e substitua por `PermitRootLogin no` para não permitir o acesso como root a partir de uma conexão SSH. O `#` também deve ser apagado.

Depois dessas modificações, salve o arquivo.

## ssh_config
Acesse:

```bash
sudo vim /etc/ssh/ssh_config
```

E faça a mesma coisa que fizemos no arquivo `sshd_config`.

# Instalação e configuração do [[firewall]]
Devemos instalar e configurar o firewall através do [[UFW]].

# Configuração do sudo
Crie o seguinte arquivo nesse caminho:

```bash
/etc/sudoers.d/sudo_config
```

Também devemos criar uma pasta para armazenar os logs de cada comando sudo que executarmos:

```bash
mkdir /var/log/sudo
```

Agora devemos editar o arquivo `sudo_config`e introduzir os seguintes comando para adicionar todos os requisitos do subject.

```bash
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

```bash
/etc/login.defs
```

Devemos modificar os seguintes parâmetros:

`PASS_MAX_DAYS 99999` para `PASS_MAX_DAYS 30`
`PASS_MIN_DAYS 0` para `PASS_MIN_DAYSmm 2`

- `PASS_MAX_DAYS` - Tempo em dias para senha expirar.
- `PASS_MIN_DAYS` - Tempo mínimo em dias para que a senha possa ser alterada.
- `PASS_WARN_AGE` - Avisa que falta x tempo para a senha expirar.

## Instalação e configuração do [[libpam-pwquality]]
Depois de instalar o `libpam-pwquality`, iremos editar o arquivo `common-password` no caminho `/etc/pam.d/common-password`.
Após `retry=3` devemos acrescentar os seguintes comandos:

```bash
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

```bash
sudo chage -l username
```

Se verificarmos que o usuário não cumpre com a política, devemos modificar o número mínimo e máximo para alterações entre senhas, com o seguinte comando:

```bash
sudo chage -m 2 username #Modifica o mínimo de dias para trocar a senha.
sudo chage -M 30 username #Modifica o máximo de dias.
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
Linux eteofilo42 6.1.0-27-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.115-1 (2024-11-01) x86_64 GNU/Linux
```

- **Linux**: Indica que o sistema operacional é baseado no núcleo Linux.
- **eteofilo42**: Nome do host (ou computador) que está executando o sistema.
- **6.1.0-26-amd64**: Versão do kernel Linux (versão 6.1.0, com o patch 26) e a arquitetura do processador (amd64, ou seja, 64 bits).
- **#1**: Número de compilação do kernel.
- **SMP**: Indica que o kernel suporta multiprocessamento simétrico (uso de múltiplos processadores).
- **PREEMPT_DYNAMIC**: Refere-se ao agendador do kernel, que pode alterar o comportamento de pré-empção de processos de maneira dinâmica.
- **Debian 6.1.112-1 (2024-09-30)**: Versão do pacote do kernel fornecido pela distribuição Debian, junto com a data de lançamento do pacote (30 de setembro de 2024).
- **x86_64**: Arquitetura do processador (64 bits).
- **GNU/Linux**: Indica que o sistema operacional está baseado no núcleo Linux e utiliza componentes do sistema GNU.

## 2. Núcleos físicos
Para exibir os núcleos físicos usaremos o comando `grep "physical id" /proc/cpuinfo | wc -l` 

- [[grep]]
- [[wc]]

## 3. Memória RAM
Para exibir a memória RAM, usaremos o comando [[free]] com a flag --mega. Esse é o retorno esperado:

```shell
               total        used        free      shared  buff/cache   available
Mem:            1007         252         628           0         268         755
Swap:           1023           0        1023
```

Uma vez que executamos esse comando, devemos filtrar nossa pesquisa com [[awk]].

1. Para printar a memória usada:
	- `free --mega | awk '$1 == "Mem:" {print $3}'`
2. Para printar a memória total:
	- `free --mega | awk '$1 == "Mem:" {print $2}'
3. Para calcular e printar a % de memória usada:
	- `free --mega | awk '$1 == "Mem:" {printf("(%.2f%%)\n", $3/$2*100)}'

## 4. Memória em Disco
Para ver a memória de disco ocupada e disponível, usaremos o comando [[df]].

```shell
df -m
-------------------------------------------------------------------------
Filesystem                      1M-blocks  Used Available Use% Mounted on
udev                                  457     0       457   0% /dev
tmpfs                                  97     1        96   1% /run
/dev/mapper/eteofilo42--vg-root      2751  1098      1494  43% /
tmpfs                                 481     0       481   0% /dev/shm
tmpfs                                   5     0         5   0% /run/lock
/dev/sda1                             455    60       371  14% /boot
/dev/mapper/eteofilo42--vg-home      3701     1      3493   1% /home
tmpfs                                  97     0        97   0% /run/user/1000
```

```shell
df -m | grep "/dev" | grep -v "/boot"
-------------------------------------------------------------------------
udev                                  457     0       457   0% /dev
/dev/mapper/eteofilo42--vg-root      2751  1098      1494  43% /
tmpfs                                 481     0       481   0% /dev/shm
/dev/mapper/eteofilo42--vg-home      3701     1      3493   1% /home
```

- Memória em uso:

```shell
df -m | grep "/dev" | grep -v "/boot" |
awk '{memory_use +=$3} END {print memory_use}'
-------------------------------------------------------------------------
1099
```

- Espaço total:

```shell
df -m | grep "/dev" | grep -v "/boot" |
awk '{memory_result +=$2} END {printf ("%.0fGb\n") memory_result/1024}'
-------------------------------------------------------------------------
7Gb
```

- Porcentagem de memória usada:

```shell
df -m | grep "/dev/" | grep -v "/boot" |
awk '{use += $3} {total += $2} END {printf("(%d%%)\n"), use/total*100}'
-------------------------------------------------------------------------
(15%)
```

## 5. Porcentagem de uso de CPU
Para ver a porcentagem de CPU devemos usar o comando [[vmstat]].

```shell
vmstat 1 4 | tail -1 | awk '{print $15}'
```

- **vmstat:** Exibe informações sobre o uso de recursos do sistema, como memória, swap, CPU e I/O.
- **1:** Define o intervalo (em segundos) entre as atualizações das estatísticas.
- **4:** Especifica o número de vezes que as estatísticas deve ser atualizadas.

```shell
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 612908  10060 253924    0    0     8     3  282   26  0  0 100  0  0
 1  0      0 612908  10060 253924    0    0     0     0  257   33  0  0 100  0  0
 1  0      0 612908  10060 253924    0    0     0     0  263   35  0  0 100  0  0
 1  0      0 612908  10060 253924    0    0     0     0  293   36  0  0 100  0  0
```

- **tail -1:** Pega somente a última linha da saída fornecida.

```shell
 1  0      0 612908  10060 253924    0    0     0     0  271   29  0  0 99  1  0
```

- **awk '{print $15}':** pega apenas a palavra 15, que é a utilização de memória disponível.

```shell
100
```

## 6. Último reinício
Para ver a data e hora o último reinício do sistema usamos o comando `quem` com a flag `-b`. 

```shell
system boot  2024-11-15 00:13

```

Nesse caso também temos que filtrar o resultado com o awk.

```shell
who -b | awk '$1 == "system" {print $3 " " $4}'`
-------------------------------------------------------------------------

2024-11-15 00:13
```

## 7. Utilização de LVM

Para verificar se o LVM está ativado, usaremos o comando lsblk, que nos mostra todas as informações de todos os dispositivos de bloco. Vamos contar o número de linhas onde "lvm" aparece e se houver imprimimos Sim, senão Não.

```shell
if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi
```

 **if**:
- **`$(lsblk | grep "lvm" | wc -l)`**: Esse trecho executa o pipeline de comandos e retorna o número de linhas que contêm "lvm".
- **`-gt 0`**: A expressão **`-gt`** significa **"greater than"** (maior que). Portanto, o comando está verificando se o número de linhas que contém "lvm" é maior que 0.
- **Se a condição for verdadeira** (ou seja, se o número de linhas contendo "lvm" for maior que 0), então ele executa **`echo yes`**.
- **Se a condição for falsa** (ou seja, se não houver LVM no sistema), ele executa **`echo no`**.
- **fi:** Fecha o if.

## 8. Conexões [[TCP]]
Para ver o número de ligações estabelecidas, utilizaremos o comando `ss`.

```shell
ss -ta | grep ESTAB | wc -l
-------------------------------------------------------------------------
1
```

- **ss(Socket Statictcs):** Exibe informações sobre as conexões de rede no Linux.
- **-t:** Filtra para somente conexões TCP.
- **a:** Faz com que todas as conexões sejam mostradas.
- **grep ESTAB:** Filtra por conexões bem sucedidas (established).
- **wc -l:** Conta o número de linhas.
## 9. Número de utilizadores
Usaremos o comando `users`.

```shell
users | wc -w
-------------------------------------------------------------------------
2
```
## 10. Endereço de [[IP]] e [[MAC]]
**Endereço IP** e **endereço MAC** são dois tipos de identificadores usados em redes de computadores, mas eles servem para propósitos diferentes e operam em níveis diferentes do modelo de redes. Vamos ver o que são e como eles funcionam:

**Diferença entre Endereço IP e Endereço MAC**

| Característica     | **Endereço IP**                                                                             | **Endereço MAC**                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| **Função**         | Identifica dispositivos em uma rede e permite o roteamento de dados entre diferentes redes. | Identifica dispositivos dentro de uma rede local (LAN).                                           |
| **Formato**        | IPv4: `192.168.1.1`, IPv6: `fe80::1a2b:3c4d`                                                | `00:14:22:01:23:45` (12 caracteres hexadecimais).                                                 |
| **Nível OSI**      | Camada 3 (Rede)                                                                             | Camada 2 (Enlace de Dados)                                                                        |
| **Alterabilidade** | Pode ser alterado manualmente ou automaticamente (via DHCP).                                | Fixo, atribuído pelo fabricante da placa de rede.                                                 |
| **Visibilidade**   | Visível globalmente em redes públicas (como a Internet).                                    | Visível somente dentro de uma rede local (LAN).                                                   |
| **Escopo**         | Usado para roteamento e comunicação entre redes diferentes (como a Internet).               | Usado para comunicação dentro de uma rede local (LAN), entre dispositivos conectados diretamente. |
**1. IP**

```shell
hostname -I
```

**2. MAC**

```shell
ip link | grep "link/ether" | awk '{print $2}'
```


## 11.Número de comando executados com sudo

```shell
journalctl _COMM=sudo | grep COMMAND | wc -l)
```

- **journalctl:** Acessa e exibe os logs do sistema.
- **COMM=sudo:** É um filtro para ser usado com o journalctl. `_COMM`se refere ao nome do comando ou processo que gerou uma entrada no log. No nosso caso, o sudo.
- **grep COMMAND:** COMMAND, aparece na saída do comando sudo nos logs do journalctl. Assim, o grep filtra os logs sudo.
- **wc -l:** Retorna o numero de linhas.
# [[Crontab]]
Devemos configurar o crontab editando o arquivo com o seguinte comando:

```shell
sudo crontab -u root -e
```

No arquivo, devemos adicionar o seguinte comando para que o script seja executado de 10 em 10 minutos:

```shell
*/10 * * * * sh /caminho-do-script
```


# Avaliação

## 0. Assinatura
```shell
shasum Born2beroot.vdi
```

## 1. Explique o funcionamento básico de uma máquina virtual
Uma máquina virtual emula um hardware dedicado e roda um os nele.
Assim, podemos dedicar parte da memória, armazenamento e núcleos de cpu da maquina física para a máquina virtual.

## 2. Minha escolha de sistema operacional
Escolhi o Debian por ser mais simples de conseguir finalizar o projeto, visto que temos mais material sobre ele na internet e é mais conhecido do público em geral.

## 3. Diferenças entre Rocky e Debian
O Rocky é um fork do centOs, distribuição baseada no Red Hat, que é uma distro comercial com suporte pago e serviços empresariais. Isso aconteceu por que o centOs se tornou rolling-release ao em vez de lts. Ele é amplamente usado em servidores por seu suporte ao Red Hat e suporte de 10 anos.

O debian é uma distro muito popular e usada tanto em desktops como servidores. É menos usada em grandes servidores do que o Rocky, devido a sua característica de mesmo em sua versão lts, ter 5 anos de suporte no lugar de 10 anos do Rocky.

## 4. Benefícios de uma máquina virtual
Com uma máquina virtual, posso testar um sistema sem que eu comprometa o meu sistema atual. É mais seguro para testar sistemas instáveis.

Também me proporciona maior facilidade de backup e restauração por conta dos snapshots e clones.

## 5. Diferenças entre apt e aptitude
Ambos são gerenciadores de pacotes.

O apt é recomendado pela equipe do Debian por ser mais atual e direto, sem muitas opções ou configurações complexas.

o aptitude é uma ferramenta mais antiga que tem tanto um GUI como CLI.
Ele oferece várias opções para o gerenciamento de pacotes e mais detalhes sobre cada pacote.

## 6. O que é o AppArmor?
É um modulo de segurança do Kernel do Linux que fornece um sistema de controle que permite que o administrador do sistema defina restrições para os aplicativos, limitando suas permissões detalhadamente.

*Exemplo*
O navegador pode ser configurado para não acessar o diretório ~/.ssh ou outros arquivos sensíveis do usuário.

## 7. Verifique se o sistema é o Debian
```shell
cat /etc/os-release
```

## 8. Verifique se o UFW está rodando
```shell
sudo ufw status
```

## 9. Verifique se o SSH está rodando
```shell
sudo service ssh status
```

## 10. Verifique se o usuário eteofilo está dentro do grupo "sudo" e "user42"
```shell
getent group sudo
getent group user42
```
## 11. Caso precise verificar politicas de senha
```shell
chage -l username
```

## 12. Como eu modifiquei a política de senhas
Editei o arquivo `login.defs`

```bash
/etc/login.defs
```

Modificando os seguintes parâmetros:

`PASS_MAX_DAYS 99999` para `PASS_MAX_DAYS 30`
`PASS_MIN_DAYS 0` para `PASS_MIN_DAYS 2`

- `PASS_MAX_DAYS` - Tempo em dias para senha expirar.
- `PASS_MIN_DAYS` - Tempo mínimo em dias para que a senha possa ser alterada.
- `PASS_WARN_AGE` - Avisa que falta x tempo para a senha expirar.

Depois, instalei o `libpam-pwquality`, que ajuda a melhorar a qualidade das senhas, e editei o arquivo `common-password` no caminho `/etc/pam.d/common-password`.
Após `retry=3` devemos acrescentar os seguintes comandos:

```bash
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


## 13. Crie um grupo com nome de "evaluating" e adicione o user do avaliador
```shell
sudo addgroup evaluating
sudo adduser user-name evaluating
getent group evaluating
```

## 14. Vantagens e desvantagens de politica de senhas
### *Vantages*
- Senhas mais seguras
	- O usuário deve mudar a senha a cada 30 dias
	- Requisitos fortes para a senha
### *Desvantagens*
- Pessoas que não conseguem se lembrar ou não guardam direito a senha nova, ou diferente do habitual.
## 15. Verificar hostname
```shell
hostnamectl
```

## 16. Mudar hostname com o avaliador
```shell
sudo hostnamectl set-hostname name
```

*Caso queira ver o hostname no terminal use* `exec bash`.

## 17. Mostrar as partições
```shell
lsblk
```

## 18. LVM
LVM é o gerenciador de volumes lógicos que dá mais flexibilidade na administração de discos e partições.

Os volumes físicos(HD's, SSD's) formam um unico volume chamado de **volume group** e os lv são criados dentro desse grupo.

Funciona como uma partição tradicional, mas pode ser redimensionado dinamicamente, sem necessidade de formatação.

## 19. Verificar a instalação do sudo ##
```shell
command -v sudo
```

## 20. Verificar os logs do sudo
```shell
ls /var/log/sudo/
cat -e /var/log/sudo/file
```

## 21. Verificar UFW
```shell
sudo ufw status
```

## 22. Adicionar e remover porta 8080 no UFW

### *Add*
```shell
sudo uffw allow 8080
```

### *remove*
```shell
sudo ufw status numbered
```

```shell
sudo ufw delete port-number
```

## 23. Verificar SSH
```shell
sudo service ssh status
```

## 24. O que é o cron
Um utilitário de agendamento de tarefas, que permite executar scripts automaticamente em horários e datas específicas.

```shell
sudo systemctl stop cron
```