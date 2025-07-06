## 02 -
Faz uma tratativa entre as planilhas extraídas do FileZilla e do K2 de valores de exames. 

## 03 - 
Faz o cruzamento de dados entre as planilhas extraídas do FileZilla e do K2 com parâmetros de perfil codificado e perfil.

## 05 - 
Faz o calculo da variação dos preços de exames dos alfas convênios de acordo a sua marca.

## 02, 03 e 05 - 
A execução dessas três automações depende da área usuária atualizar os arquivos no Sharepoint. 

## 07 -
A automação tem um alto nível de importância por conta da área de cadastro e da sua periodicidade.
Extrai informações dos chamados via API e cadastra novos convênios no sistema K2(Que é direcionado a área de negócios) e o SAP(que é direcionada para a área financeira).

## 09 -
A automação tem um alto nível de importância por conta da área de cadastro, seu volume de itens e da sua periodicidade.
Extrai informações dos chamados via API, identifica o tipo de solicitação e resumo e faz o cadastro de parceiro de negócio no SAP. 

## 10 -
A automação tem um alto nível de importância por que ele atualiza o banco de dados do Progress.
Utiliza um arquivo de rotina extraído do Sharepoint para fazer a atualização no banco de dados das marcas no K2. 

## 16 - 
A automação tem um alto nível de importância por conta do seu alto volume diário de processamento, sua função e sua periodicidade.
Acessa o DISA, extrai as planilhas, extrai os dados das planilhas e realiza a abertura, fechamento e bloqueio de agendas no Progress. 

## 17 - 
Extrai o demonstrativo e notas fiscais no Hygia, realiza leitura dos pdfs via Google Vision e preenche a planilha para consumo da automação 37.

## 25 - 
Extrai o relatório de chamados no Maker, acessa o site da Siemens e Roche e abre os chamados, retorna no Maker e sinaliza a abertura e por fim coloca o número da ordem de serviço no Arkmeds. 

## 26 - 
Extrai o relatório de chamados no Maker, acessa o site da Simens e Roche e verifica se os chamados estão abertos e por fim verifica no Arkmeds se consta o número da ordem de serviço.

## 27 - 
Acessa o e-mail da área de Engenharia, filtra os e-mails do Siemens e Roche, extrai os anexos e a descrição dos serviços feitos e por fim ele registra no Maker e insere o anexo. Em resumo ele realiza o fechamento do chamado.

## 28 - 
Extrai a planilha de reajustes no Sharepoint, realiza filtros e tratativas e envia o relatório por e-mail.
A execução da automação depende da área usuária atualizar o arquivo no Sharepoint. 

## 29 -
Acessa o SAP, extrai relatórios de pagamentos e envia por e-mail para cada fornecedor. 

## 30 - 
Extrai informações no SAP, gera planilha de carga massiva e envia a planilha por e-mail aos responsáveis.

## 35 -
Extrai planilha da base do Gliese no SharePoint, faz filtros e tratativas, extrai os dados e envia por e-mail aos responsáveis.

## 36 - 
Acessa o MXM extrai os relatórios de erros, filtra as mensagem de erro do grupo de pagamento, acessa o Arquivei e busca pelas notas, extrai os dados e por fim realiza a parametrização, reprocessamento e homologação no MXM.

## 37 -
Extrai planilhas de depara no Sharepoint, a automação 17 enviará os dados para a fila do 37, com esses dados será gerada uma planilha e será emitido pedidos em lote no SAP.
A automação não está funcionando por que a área precisa fazer uma alteração no flag da data de execução. Esse flag uma checagem se a automação está autorizada a executar naquele dia. 

## 39 - 
Extrai via API os logs de erro e sucesso das filas de cada automação, gera um relatório para cada uma delas e salva no SharePoint.
Após, gera um relatório final e envia por e-mail aos responsáveis.

## 43 - 
A automação tem um alto nível de importância por conta do seu alto volume diário de processamento, sua função e sua periodicidade.
Extrai planilha de chamados no Sharepoint, consume os dados e realiza abertura de agendas no Progress.

## 50 -
Acessa o orchestrador via API e extrai os seguintes dados das automações:
“Key”, “Machine”, “Account”, “RobotName”, “Type”, “StartTime”, “EndTime” e “State”.
Após isso, gera uma planilha e disponibiliza na pasta de saída do robô. 


## 54 -
A automação tem um alto nível de importância por conta do seu alto volume diário de processamento, sua função e sua periodicidade.
Acessa o sistema Coupa via API, extrai os pedidos de compra de diagnósticos e vacinas, extrai os dados de cada pedido no SAP e realiza filtro para itens não expandidos, por fim reprocessa os itens no SAP e gera o relatório dos itens expandidos e relatório de erro dos itens não expandidos.
Itens não expandidos são itens que deveriam estar adicionados/atualizados em algum Centro de Destino.

## 55 - 
O objetivo é extrair informações do site GNDI e alimentar uma planilha para controle de glosa(Quando um operador de plano de saúde se recusa a pagar um procesimento).

Acessa o Sharepoint e extrai a planilha de processamento, acessa o GNDI, extrai o PDF, realiza leitura do PDF por OCR, preenche a planilha de processamento com os dados extraídos e envia a planilha por e-mail. 
A execução da automação depende da área usuária atualizar o arquivo no Sharepoint. 

