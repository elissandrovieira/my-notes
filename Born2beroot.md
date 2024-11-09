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

depois disso, instalar usando [[apt]].

```
apt install sudo
```

para que as alterações surtam efeito, precisamos reiniciar a vm.

```
sudo reboot
```

## Verificação do sudo
Para verificar se o sudo foi realmente instalado, digite o comando `sudo -V `. O resultado é como esse abaixo:

```
Sudo version 1.9.13p3
Sudoers policy plugin version 1.9.13p3
Sudoers file grammar version 50
Sudoers I/O plugin version 1.9.13p3
Sudoers audit plugin version 1.9.13p3
```

