O comando **`vmstat`** (virtual memory statistics) no Linux é utilizado para relatar estatísticas sobre o **uso de memória virtual**, **processos**, **swap**, **entrada/saída** (I/O), **interrupções**, **CPU** e outros parâmetros do sistema. Ele fornece uma visão geral da saúde e desempenho do sistema, sendo muito útil para administradores de sistemas monitorarem a utilização de recursos do computador em tempo real.

## Sintaxe Básica:

```shell
vmstat [opções] [intervalo] [contagem]
```

- **intervalo:** O número de segundos entre as atualizações da saída.
- **contagem:** O número de vezes que as estatísticas devem ser atualizadas. Se omitido, o vmstat continuará exibindo as estatísticas até que você o interrompa (geralmente com Ctrl+C).