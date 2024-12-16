O **`awk`** é uma poderosa linguagem de processamento de texto e análise de dados, especialmente útil para manipular e filtrar texto em arquivos e saídas de comandos no Linux. O nome **`awk`** vem das iniciais dos seus criadores: **A**lho, **W**einberger e **K**ernighan.

O `awk` funciona de forma muito eficiente para trabalhar com dados estruturados em linhas e colunas (como arquivos CSV, logs e tabelas). Ele permite que você execute operações de filtragem, transformação e formatação de maneira flexível e rápida.

## Sintaxe básica:

```shell
awk 'padrão {ação}' arquivo
```

- **padrão:** Uma condição ou expressão a ser verificada para cada linha do arquivo.
- **ação:** O que fazer quando o padrão for encontrado.