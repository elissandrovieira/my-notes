O comando `getent` é uma ferramenta usada em sistemas Unix e Linux para consultar informações de várias bases de dados do sistema, como usuários, grupos, serviços, hosts, entre outros. Ele funciona consultando as fontes configuradas no arquivo `/etc/nsswitch.conf` e retornando os dados relacionados às diferentes categorias.

## Sintaxe básica:
```
getent <tipo de banco de dados> [chave]
```

### Exemplos de tipos de banco de dados:

1. **passwd**: Consultar informações sobre usuários (equivalente a `/etc/passwd`).
    - Exemplo: `getent passwd <nome_do_usuario>`
2. **group**: Consultar informações sobre grupos (equivalente a `/etc/group`).
    - Exemplo: `getent group <nome_do_grupo>`
3. **hosts**: Consultar informações sobre hosts (equivalente a `/etc/hosts` ou DNS).
    - Exemplo: `getent hosts <nome_do_host>`
4. **services**: Consultar informações sobre serviços de rede (equivalente a `/etc/services`).
    - Exemplo: `getent services <nome_do_serviço>`
5. **shadow**: Consultar informações sobre senhas de usuários (equivalente a `/etc/shadow`).
    - Exemplo: `getent shadow <nome_do_usuario>`
6. **passwd**: Consultar os usuários do sistema.
    - Exemplo: `getent passwd`