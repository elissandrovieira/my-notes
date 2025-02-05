Grupos são coleções de usuários que compartilham as mesmas permissões e acessos ao sistema.

# Criar grupo
Para criar um grupo, devemos usar o seguinte comando:

```
sudo addgroup group-name
```

Ao rodar esse comando, ele retorna o [[GID]] desse grupo:

```
Adding group 'user42' (GID 1001) ...
Done.
```

# Adicionar usuário
Para adicionar um usuário ao grupo, devemos usar o seguinte comando:

```
sudo adduser user-name group-name
```

# Verificando o grupo
Para verificar se o grupo foi criado corretamente e quais são seus usuários, podemos usar o comando [[Getent]]:

```
getent group group-name
```

Ou o comando:

```
cat /etc/group
```

