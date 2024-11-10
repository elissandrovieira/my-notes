O *apt* (Advanced Package Tool) é um [[Package Manager]] usado em distros [[Linux]] baseadas em Debian, como Ubuntu e Linux Mint.

o apt utiliza repositórios de pacotes para baixar e instalar o software pedido. Ele lida com o download, instalação e atualização dos pacotes.

Para utilizar o *apt*, é necessário ter privilégios de super usuário ([[sudo]]).

# Comandos principais do APT

1. **Instalar pacotes:** Para instalar um novo pacote, usamos o comando `apt install`. Por exemplo, para instalar o pacote **curl**:

```
sudo apt install curl
```

2. **Atualizar a lista de pacotes:** Antes de instalar ou atualizar pacotes, é uma boa prática atualizar a lista de pacotes disponíveis nos repositórios. Isso garante que você esteja baixando a versão mais recente de cada pacote:

```
sudo apt update
```

3. **Atualizar pacotes instalados:** O comando `apt upgrade` serve para atualizar os pacotes que já estão instalados no sistema, se houver novas versões disponíveis:

```
sudo apt upgrade
```

4. **Remover pacotes:** Para remover um pacote instalado, você pode usar o comando `apt remove`:

```
sudo apt remove package-name
```

5. Limpar pacotes não necessários: Após instalar e remover pacotes, o sistema pode deixar pacotes ou dependências não mais utilizados. O comando `apt autoremove` remove esses pacotes desnecessários:

```
sudo apt autoremove
```

6. **Pesquisar pacotes:** Para procurar pacotes disponíveis nos repositórios, você pode usar o comando `apt search`:

```
apt search package-name
```

7. Exibir informações sobre um pacote: Para obter detalhes sobre um pacote (como descrição, versão, dependências, etc.), você pode usar o comando apt show:

```
apt show package-name
```

# Diferença entre `apt` e outros comandos de pacotes

- **APT vs `dpkg`:** O **dpkg** é a ferramenta de baixo nível usada para gerenciar pacotes Debian, enquanto o **APT** é uma camada mais alta que usa `dpkg` e outros utilitários para resolver dependências automaticamente. Ou seja, o APT facilita a #### **Obsidian Sync + GitHub**instalação e a atualização de pacotes, enquanto o dpkg lida com a instalação de pacotes individuais sem resolver dependências.

- **APT vs `apt-get`:** O comando `apt-get` é a versão mais antiga e um pouco mais complexa do APT. Embora ambos cumpram funções similares, o **apt** foi introduzido para tornar os comandos mais simples e amigáveis, combinando funcionalidades dos comandos `apt-get` e `apt-cache`. Por exemplo:

	- `sudo apt-get update` -> `sudo apt update`
	- `sudo apt-get upgrade` -> `sudo apt upgrade`
	- `sudo apt-get install` -> `sudo apt install`

Ambos, `apt-get` e `apt`, ainda estão disponíveis, mas a recomendação atual é usar o **apt** para operações cotidianas, já que ele fornece uma interface mais moderna e amigável.