Este projeto faz parte do [[Rank1]] dentro do [[Common-core]] da [[42]].
O objetive desse projeto é criar uma maquina virtual [[Linux]], mas sem usar nenhum "facilitador", como utilizar a instalação simplificada, instalar um [[Window System]] ou um [[GUI]] ao entrar no sistema. Dessa maneira, eu devo configurar tudo do zero - desde os acessos, até configurações de [[SSH]] e [[firewall]].

# Instalação
A instalação da máquina virtual segue um passo a passo básico, só se deve ter maior cuidado com o [[LVM]].

# Instalação do sudo
Para instalar o [[sudo]], precisamos estar no root user. Para isso devemos digitar o comando *su* no terminal. depois disso, instalar usando [[apt]].

```
apt install sudo
```