# Estrutura de pastas recomendada

```css
phonebook/
 ├── src/
 │    └── com/
 │         └── phonebook/
 │              ├── Main.java
 │              ├── model/
 │              │    └── Contact.java
 │              ├── service/
 │              │    └── ContactService.java
 │              └── util/
 │                   └── CsvUtils.java
 └── resources/
      └── contacts.csv    (arquivo para salvar dados, se usar csv)

```

# Explicação

- **`src/com/phonebook`** — pacote raiz do seu projeto.
- **`model`** — classes que representam dados, por ex: `Contact` (contato).
- **`service`** — classes que têm a lógica de negócio, como manipular contatos (adicionar, remover, buscar).
- **`util`** — helpers, utilitários, por ex: salvar e carregar CSV.
- **`resources`** — arquivos de dados, configuração, como seu arquivo CSV com os contatos.