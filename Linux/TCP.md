**TCP** (Transmission Control Protocol) é um dos protocolos principais da **camada de transporte** do modelo OSI (Open Systems Interconnection) e da pilha de protocolos TCP/IP, usado para estabelecer uma comunicação confiável entre sistemas em redes de computadores, como a internet.

### Função principal do TCP:

O TCP garante que os dados enviados de um computador para outro cheguem de forma confiável, ordenada e sem erros. Ele é usado principalmente para aplicações que exigem alta confiabilidade na entrega de dados, como navegadores web, transferência de arquivos e e-mails.

### Características do TCP:

1. **Conexão Orientada**:
    
    - O TCP é um protocolo **orientado a conexão**, o que significa que antes de qualquer dado ser enviado, uma **conexão** é estabelecida entre o cliente e o servidor.
    - Isso é feito por meio de um processo chamado **three-way handshake** (aperto de mão de 3 etapas), que envolve a troca de pacotes de controle para garantir que ambos os lados da comunicação estão prontos para enviar e receber dados.
2. **Confiabilidade**:
    
    - O TCP garante que os dados cheguem **completos** e **na ordem correta**. Caso algum pacote se perca ou chegue com erro, ele será retransmitido.
    - Ele usa **números de sequência** para organizar os pacotes de dados e garantir que a sequência correta seja restaurada, mesmo que os pacotes cheguem fora de ordem.
3. **Controle de Fluxo**:
    
    - O TCP controla a quantidade de dados que um remetente pode enviar antes de precisar de uma confirmação do destinatário, evitando que o receptor seja sobrecarregado.
    - Isso é feito com o **controle de fluxo**, utilizando o conceito de **janela deslizante** (sliding window).
4. **Controle de Congestionamento**:
    
    - O TCP também monitora as condições da rede e ajusta a taxa de envio de dados com o objetivo de evitar **congestionamento** na rede.
    - Se a rede estiver congestionada, o TCP pode reduzir a velocidade de envio, evitando sobrecarregar a infraestrutura da rede.
5. **Controle de Erros**:
    
    - O TCP usa **somatórios de verificação (checksums)** para detectar erros em pacotes de dados. Se um erro for detectado, o pacote será descartado e retransmitido.
6. **Atrasos e Retransmissões**:
    
    - Como o TCP garante a entrega confiável dos dados, ele pode introduzir **atrasos** nas comunicações, já que cada pacote precisa ser confirmado e pode ser retransmitido em caso de falha.

### Como o TCP funciona? (Exemplo simplificado)

Aqui está o processo básico de como o TCP funciona durante uma comunicação entre dois sistemas:

#### 1. **Estabelecimento da Conexão (Three-Way Handshake)**:

- **Step 1**: O cliente envia um pacote **SYN** para o servidor, solicitando uma conexão.
- **Step 2**: O servidor responde com um pacote **SYN-ACK**, confirmando a solicitação e enviando um próprio.
- **Step 3**: O cliente envia um pacote **ACK**, confirmando a resposta do servidor.

Após esse processo, a conexão é estabelecida e os dados podem ser trocados.

#### 2. **Envio de Dados**:

- Os dados são segmentados em pacotes pelo TCP. Cada pacote tem um número de sequência para garantir que os pacotes sejam reorganizados corretamente, caso cheguem fora de ordem.
- O destinatário envia **acknowledgments (ACKs)** para confirmar a recepção dos pacotes. Se o remetente não receber um ACK dentro de um tempo limite, ele retransmitirá o pacote.

#### 3. **Fechamento da Conexão**:

- Quando a comunicação termina, o TCP realiza o processo de **four-way handshake** para fechar a conexão de forma segura:
    - Um dos lados envia um pacote **FIN**, indicando que terminou de enviar dados.
    - O outro lado responde com um **ACK**.
    - O lado que recebeu o **FIN** envia um **FIN** de volta para concluir o fechamento da comunicação.
    - O outro lado então envia um último **ACK**.

### Exemplos de protocolos que usam TCP:

- **HTTP** (HyperText Transfer Protocol) — para navegação web.
- **FTP** (File Transfer Protocol) — para transferência de arquivos.
- **SMTP** (Simple Mail Transfer Protocol) — para envio de e-mails.
- **Telnet** — para comunicação interativa com servidores.
- **SSH** (Secure Shell) — para comunicação segura entre sistemas.

### Diferença entre TCP e UDP:

- O **UDP** (User Datagram Protocol) também é um protocolo de transporte, mas ele não é orientado a conexão, não garante confiabilidade, não controla fluxo e não faz retransmissão de pacotes perdidos.
- O **TCP**, por outro lado, fornece uma comunicação confiável, com garantias de entrega e correção de erros, o que o torna mais lento em comparação com o UDP, mas ideal para aplicações onde a confiabilidade é crucial (como em navegadores web, emails e transferências de arquivos).

### Vantagens do TCP:

1. **Confiabilidade**: Garante a entrega dos pacotes sem erros.
2. **Controle de Congestionamento e Fluxo**: Evita sobrecarregar a rede e o receptor.
3. **Entrega Ordenada**: Garante que os pacotes cheguem na ordem correta.

### Desvantagens do TCP:

1. **Overhead**: O processo de verificação e controle dos pacotes gera **overhead** (sobrecarga), o que pode tornar o TCP mais lento em comparação com o UDP, especialmente para aplicações que não exigem a confiabilidade do TCP.
2. **Tempo de Estabelecimento de Conexão**: O processo de **handshake** inicial pode introduzir latência.