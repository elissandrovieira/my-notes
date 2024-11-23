 crontab é uma ferramenta de agendamento de tarefas em sistemas Unix e Linux. A palavra "crontab" vem de "cron", que é o daemon responsável por executar tarefas agendadas, e "tab", que se refere a uma tabela. Com o crontab, você pode agendar comandos ou scripts para serem executados automaticamente em intervalos de tempo específicos, como diariamente, semanalmente, mensalmente, ou em horários específicos.

Como funciona o crontab?
O crontab usa um arquivo de configuração onde as tarefas agendadas são definidas, e o cron daemon fica em execução no plano de fundo, verificando esse arquivo para saber quando executar os comandos. A configuração do crontab é baseada em uma sintaxe específica de tempo.

Sintaxe do crontab
A sintaxe para definir as tarefas no crontab tem a seguinte estrutura:

```scss
* * * * * comando a ser executado
| | | | |
| | | | +--- Dia da semana (0 - 6) (Domingo=0)
| | | +----- Mês (1 - 12)
| | +------- Dia do mês (1 - 31)
| +--------- Hora (0 - 23)
+----------- Minuto (0 - 59)
```
