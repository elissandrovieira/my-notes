Grep (*global Regular Expression Print*) é um utilitário de terminal para sistemas [[Unix]] e [[Linux]]. Podemos usa-lo para pesquisar em arquivos e linhas de comando algo que seja especificado.

Essa é sintaxe básica para usar `grep`:

```shell
grep [options] pattern [file...]
```

- **pattern:** O texto ou expressão procurada.
- **file:** Um ou mais arquivos a serem pesquisados. Se não for introduzido, o `grep` pesquisará no input.

## Flags

- `-i`: Ignorar o case-sensitive.
- `-r` ou `-R`: Pesquisar recursivamente em diretórios.
- `-v`: Inverte a seleção(Mostra tudo que não foi selecionado no *pattern*).
- `-l`: Mostra o nome dos arquivos que contém o *pattern*.
- `-n`: Mostra o numero das linhas com o resultado correspondente.
- `-c`: Mostra o numero de linhas com o resultado correspondente.
- `-H`: Printa o arquivo com seu nome.