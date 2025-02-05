O *sudo* (**superuser do - fazer como super usuário**) é um pacote utilizado para dar privilégios root temporários a um usuário em sistemas baseados em [[Unix]], como o [[Linux]]. Quando se usa o comando *sudo* no terminal, o sistema solicita a senha de usuário e verifica se o usuário tem permissão para executar aquele comando com privilégios elevados, e, caso tenha, executa o comando.

# Exemplos de uso

```
sudo apt install package-name
```

Usar *sudo* é considerado uma boa prática porque ele evita que os usuários fiquem logados como root o tempo todo, minimizando o risco de erros acidentais ou ataques.

# Instalar

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
