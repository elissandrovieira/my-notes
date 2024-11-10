SSH (Secure Shell) é um protocolo de rede que permite a comunicação segura entre computadores, especialmente para acesso remoto e execução de comando em sistemas.

### Principais características do SSH:

1. **Segurança**:

- O SSH fornece uma **conexão criptografada** entre o cliente e o servidor. Isso significa que os dados transmitidos são protegidos contra interceptação (ataques man-in-the-middle).
- Ele autentica tanto o cliente quanto o servidor para garantir que as partes envolvidas na comunicação são quem dizem ser.
2. **Autenticação**:

- O SSH oferece autenticação através de **senhas** ou **chaves públicas/privadas**.
- A autenticação por **chave pública/privada** é mais segura, pois utiliza criptografia assimétrica. O servidor tem a **chave pública** e o cliente possui a **chave privada** correspondente, garantindo que a comunicação seja segura sem a necessidade de enviar senhas pela rede.
3. **Execução Remota de Comandos**:

- Com o SSH, você pode **executar comandos remotamente** em um servidor como se estivesse fisicamente presente no terminal. Isso é útil para administradores de sistemas que precisam gerenciar servidores sem estar no local físico.
4. **Túnel SSH**:

- O SSH também permite a criação de **túneis seguros**, que podem ser usados para **encapsular outros protocolos** de rede (como HTTP, FTP) e enviá-los de forma segura por meio da conexão SSH. Isso pode ser útil para acessar serviços de forma segura, mesmo em redes inseguras.

### Componentes do SSH:

- **Cliente SSH**: O programa no lado do usuário que se conecta a um servidor SSH remoto. Em sistemas Linux e macOS, o cliente SSH já vem instalado por padrão. No Windows, você pode usar ferramentas como o **PuTTY** ou o cliente SSH integrado no Windows 10 e versões posteriores.

- **Servidor SSH**: O serviço que roda no computador remoto, geralmente na porta 22, esperando conexões de clientes SSH. No lado do servidor, o software mais comum para SSH é o [[OpenSSH]].