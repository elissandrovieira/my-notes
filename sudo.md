O *sudo* (**superuser do - fazer como super usuário**) é um pacote utilizado para dar privilégios root temporários a um usuário em sistemas baseados em [[Unix]], como o [[Linux]]. Quando se usa o comando *sudo* no terminal, o sistema solicita a senha de usuário e verifica se o usuário tem permissão para executar aquele comando com privilégios elevados, e, caso tenha, executa o comando.

# Exemplos de uso

```
sudo apt install package-name
```

Usar *sudo* é considerado uma boa prática porque ele evita que os usuários fiquem logados como root o tempo todo, minimizando o risco de erros acidentais ou ataques.