### **1. O Problema que o Docker Veio Resolver**

Antes do Docker, o desenvolvimento e a implantação de software enfrentavam vários problemas:

- **Acoplamento de Recursos**: Várias aplicações (Java, Python, .NET) rodavam no mesmo servidor físico (hardware), compartilhando recursos (CPU, memória, disco). Isso causava conflitos e dificuldade de gerenciamento.
    
- **Escalabilidade Ineficiente**: Sem isolamento, era necessário adicionar novos servidores físicos para escalar, o que era caro e complexo.
    
- **Problemas de Compatibilidade**: Diferentes aplicações exigiam versões específicas de bibliotecas, o que gerava conflitos.
    

---

### **2. Evolução: Máquinas Virtuais (VMs)**

As VMs surgiram para melhorar o gerenciamento de recursos:

- **Hypervisor**: Software (como KVM) que divide o hardware físico em múltiplas VMs.
    
- **Isolamento**: Cada VM roda seu próprio sistema operacional e aplicações, isolando recursos.
    
- **Problemas das VMs**:
    
    - Consomem muitos recursos (cada VM precisa de um SO completo, bibliotecas, etc.).
        
    - São pesadas e lentas para inicializar.
        
    - Dificuldade de migração e versionamento.
        

---

### **3. Docker: A Solução Moderna**

O Docker foi criado para resolver os problemas das VMs:

- **Contêineres**: Isolam aplicações sem precisar de um SO completo por contêiner.
    
- **Economia de Recursos**: Os contêineres compartilham o kernel do SO host, usando apenas o necessário para rodar a aplicação.
    
- **Portabilidade**: Uma aplicação containerizada roda igual em qualquer ambiente (desenvolvimento, teste, produção).
    

---

### **4. Arquitetura do Docker**

#### **Componentes Principais**:

1. **Docker Daemon**: Servidor em segundo plano que gerencia contêineres, imagens, volumes, etc.
    
2. **Docker Client**: Interface de linha de comando (`docker`) ou GUI (Docker Desktop) para interagir com o Daemon.
    
3. **Imagens**: Modelos read-only usados para criar contêineres. Ex: `postgres`, `node`, `java`.
    
4. **Contêineres**: Instâncias executáveis de imagens.
    
5. **Docker Hub**: Registro público de imagens (como o GitHub para código).
    
6. **Volumes**: Mecanismo para persistir dados gerados por contêineres.
    

#### **Fluxo de Trabalho**:

1. Crie um `Dockerfile` com instruções para construir uma imagem.
    
2. Use `docker build` para criar a imagem.
    
3. Use `docker run` para executar a imagem em um contêiner.
    
4. Use `docker push` para enviar a imagem para o Docker Hub.
    

---

### **5. Dockerfile: Criando Imagens Personalizadas**

Exemplo de `Dockerfile` para uma aplicação Java:

dockerfile

# Define a imagem base
FROM eclipse-temurin:17

# Define o mantenedor da imagem
LABEL maintainer="contato@j10x.com"

# Define o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copia o arquivo JAR para o contêiner
COPY target/docker-aula-java10x-0.0.1-SNAPSHOT.jar /app/aula-docker.jar

# Define o comando para executar a aplicação
ENTRYPOINT ["java", "-jar", "aula-docker.jar"]

# Expõe a porta da aplicação
EXPOSE 8080

#### **Comandos para Construir e Executar**:

bash

# Build da imagem
docker build -t minha-imagem:0.0.1 .

# Executar o contêiner
docker run -p 8080:8080 minha-imagem:0.0.1

---

### **6. Persistência de Dados: Volumes**

- Contêineres são efêmeros: os dados são perdidos quando o contêiner é removido.
    
- **Volumes** permitem persistir dados:
    
    bash
    

- docker volume create meu-volume
    docker run -v meu-volume:/caminho/no/contêiner minha-imagem
    

---

### **7. Docker Hub: Compartilhando Imagens**

- **Push de Imagens**:
    
    bash
    

- docker tag minha-imagem:0.0.1 usuario-docker/minha-imagem:0.0.1
    docker push usuario-docker/minha-imagem:0.0.1
    
- **Pull de Imagens**:
    
    bash
    

- docker pull usuario-docker/minha-imagem:0.0.1
    

---

### **8. Docker vs. VMs: Comparação**

|Aspecto|Docker (Contêineres)|VMs|
|---|---|---|
|Isolamento|Processo|Hardware completo|
|Consumo de recursos|Baixo|Alto|
|Tempo de inicialização|Segundos|Minutos|
|Portabilidade|Alta (imagens leves)|Baixa (pesada)|

---

### **9. Limitações do Docker**

- **Produção**: Docker é ótimo para desenvolvimento, mas em produção exige ferramentas adicionais (Kubernetes, Swarm) para orquestração.
    
- **Persistência**: Volumes não substituem um banco de dados real em produção para casos críticos.
    

---

### **10. Próximos Passos**

1. Aprender sobre `docker-compose` para orquestrar múltiplos contêineres.
    
2. Explorar ferramentas de orquestração como Kubernetes.
    
3. Praticar a criação de imagens para diferentes linguagens (Node.js, Python, etc.).
    

---

### **📌 Resumo dos Comandos Principais**

|Comando|Descrição|
|---|---|
|`docker build -t nome:tag .`|Constrói uma imagem a partir do Dockerfile.|
|`docker run -p porta:porta imagem`|Executa um contêiner.|
|`docker ps`|Lista contêineres em execução.|
|`docker images`|Lista imagens locais.|
|`docker push usuario/imagem:tag`|Envia imagem para o Docker Hub.|
|`docker pull usuario/imagem:tag`|Baixa imagem do Docker Hub.|
|`docker volume create nome`|Cria um volume para persistência.|