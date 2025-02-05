É uma [[API]] que permite que os sistemas operacionais [[Unix]] e [[Linux]] tratem a autenticação de maneira modular. Isso significa que métodos de autenticação, como senhas, podem ser configurados ou alterados sem afetar o funcionamento dos programas que dependem dela, como `login`, `sudo`, `ssh`  e etc.

### Como funciona o PAM?

O PAM funciona como uma camada de abstração entre os serviços de autenticação (como login, sudo, SSH, etc.) e os métodos reais de autenticação. Ao invés de ter código específico de autenticação incorporado em cada serviço, o PAM permite que cada serviço utilize um ou mais módulos para verificar a identidade do usuário.

O processo de autenticação é dividido em várias **etapas** ou **fases**, e os módulos PAM são responsáveis por realizar tarefas específicas durante cada uma dessas fases. Essas fases incluem:

1. **Autenticação (auth)**: Verificar se o usuário forneceu credenciais válidas (por exemplo, senha ou chave).
2. **Conta (account)**: Verificar se a conta do usuário está ativa, não expirada, e se ele tem permissões para realizar a operação.
3. **Senha (password)**: Alterar ou validar a senha do usuário.
4. **Sessão (session)**: Estabelecer ou encerrar sessões para o usuário, aplicando configurações de ambiente ou gerenciando registros de logs.

Cada uma dessas fases pode ter diferentes módulos PAM configurados, dependendo das necessidades do sistema.