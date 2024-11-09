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