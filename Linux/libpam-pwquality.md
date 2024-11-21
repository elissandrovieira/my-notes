É um [[módulo PAM]] usado em sistemas [[Linux]] para melhorar a qualidade das senhas dos usuários.

Define requisitos específicos para senhas dos usuários, como comprimento mínimo, complexidade (uso de caracteres especiais, números, letras maiúsculas e minúsculas), entre outras regras de segurança. Essas regras são configuradas no arquivo de configuração do PAM, geralmente localizado em `/etc/security/pwquality.conf`.

## Exemplo:

```
minlen = 12 #Define que a senha tenha no mínimo 12 caracteres.
minclass = 3 #Exige que a senha tenha pelo menos 3 tipos de caracteres.
maxrepeat = 3 #Limita o número de caracteres repetidos consecutivamente.
```


## Instalação

```
sudo apt install libpam-pwquality
```
