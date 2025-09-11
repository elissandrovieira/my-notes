# Me ajude me indicando para o programa Github Stars

[Nominate a GitHub Star | GitHub Stars](https://stars.github.com/nominate/)

# Links úteis

[https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FJbHAcivlz9PqqnWfzoZU8W%2FPortfolio---LIVE-Angular%3Ftype%3Ddesign%26node-id%3D2265%3A58%26mode%3Ddesign%26t%3D6T5KMYqtOpX6rQQs-1](https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FJbHAcivlz9PqqnWfzoZU8W%2FPortfolio---LIVE-Angular%3Ftype%3Ddesign%26node-id%3D2265%3A58%26mode%3Ddesign%26t%3D6T5KMYqtOpX6rQQs-1)

[Introducing Angular v17](https://blog.angular.io/introducing-angular-v17-4d7033312e4b)

[Angular](https://angular.dev/)

# Criando projeto

Instalando o angular global

```java
npm i @angular/cli@17 -g
```

Criando um novo projeto angular

_Server Side Rendering_

```java
ng new PROJECT_NAME
// angular routing? y
// Stylesheet? SCSS
// Enable SSR and SSG? y
```

OU

```java
 ng new --ssr
```

# Primeiros componentes

1. Criando um novo componente

```java
ng g c COMPONENT_NAME
```

![Screenshot 2024-01-19 at 12.57.23.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/fd644d7d-aa56-49ba-a20f-e069811d4f0a/Screenshot_2024-01-19_at_12.57.23.png)

**selector:** Seletor desse componente, usado para referência-lo nos outros componentes

**standalone:** Indica se esse componente irá possuir um módulo ou não

**imports:** Imports necessários para seu componente como outros components, services…

**templateUrl:** path para o HTML do componente

**styleUrl:** path para o CSS do componente

# Lidando com imagens

A diretiva `NgOptimizedImage` foi introduzida no Angular 14.

Essa diretiva facilitar lidar com o carregamento de imagens e implementação de estratégias para melhorar o carregamento.

```java
import { NgOptimizedImage } from '@angular/common'

...
imports: [NgOptimizedImage]
```

> Não é necessário um carregador de imagens (Image Loader) para usar o NgOptimizedImage, mas usar um com um CDN de imagem permite uma melhora poderosa de desempenho, incluindo srcsets automáticos para suas imagens.

### Propriedades

- `priority = boolean`

Essa propriedade define a imagem como uma prioridade na ordem de carregamento dos demais recursos da página

- `width="400" height="200”`

Para evitar mudanças de layout relacionadas à imagem, NgOptimizedImage exige que você especifique uma altura e largura para sua imagem.

- `fill = boolean`

Nos casos em que você deseja que uma imagem preencha o tamanho do elemento que a contém (elemento pai), você pode usar o atributo fill. Isso geralmente é útil quando você deseja obter um comportamento de "background image".

- `srcset=”…”`

Definir o atributo `srcset` garante que o navegador solicite a imagem no tamanho certo para o viewport do usuário, para que não perca tempo baixando uma imagem muito grande. `NgOptimizedImage` gera um srcset apropriado para a imagem, com base na presença e no valor do atributo tamanhos na tag da imagem.

- `loading=”...”`

Por padrão, `NgOptimizedImage` define loading=lazy para todas as imagens que não estão marcadas como `priority`. Você pode desativar esse comportamento para imagens não prioritárias definindo o atributo de carregamento.

Este atributo aceita valores: `eager`, `auto`, and `lazy`.

`eager` O comportamento padrão do HTML, diz ao navegador para carregar a imagem assim que o elemento <img> for processado.

`lazy` Diz ao navegador para adiar o carregamento da imagem até que o navegador estime que ela será necessária em breve. Por exemplo, se o usuário estiver rolando pelo documento, um valor lento fará com que a imagem seja carregada pouco antes de aparecer na janela de visualização visual da janela.

# Formulários

Para criar formulários reativos no Angular 17, podemos usar o módulo `ReactiveFormsModule`

```tsx
@Component({
  selector: 'app-component',
  standalone: true,
  imports: [
    **ReactiveFormsModule**
  ],
  templateUrl: './app.component.html',
  styleUrl: './app.component.scss'
})
```

Com esse módulo importado pelo nosso componente, podemos criar nossos `FormControl` e `FormGroup`

- **`FormControl` = Rastreia o valor e o status de validação de um input do formulário individual.**
- **`FormGroup` = Rastreia os mesmos valores e status para uma coleção de `FormControl`, ou seja, formulário com vários inputs.**

## Criando nosso forms

Para criar nosso `FormGroup` devemos declarar uma propriedade na classe que representará a instância do nosso formulário, e iniciamos esse objeto `FormGroup` no construtor da classe, passando como parâmetro todos `FormControl` que pertencem ao formulário.

```tsx
meuForms!: FormGroup;

  constructor() {
    this.meuForms = new FormGroup({
      nome: new FormControl('', Validators.required),
    });
  }
```

E agora precisamos associar o Forms e os Inputs ao elementos HTML correspondentes

```html
<form **[formGroup]="meuForms"**>
    <label for="nome">Nome</label>
    <input id="nome" **formControlName="nome"**/>
</form>
```

# Signals

> Um signal é um wrapper em torno de um valor que notifica os consumidores interessados quando esse valor muda. Os signals podem conter qualquer valor, desde primitivos simples até estruturas de dados complexas.

Então o signals é uma forma nativa do Angular para a gente criar valores que podem ser alterados, e manter o rastreio desses valores

## Como usar

Declarando um signal:

```tsx
export class HomeComponent {
	count = signal(0);
	
	...
}

const isValid = signal(false);
```

Alterando o valor

```tsx
this.count.set(1);

isValid.set(true);
```

Para ler o valor de um signal, é só chamar sua função getter, **ela permite ao Angular rastrear onde o sinal é usado.**

Então todos locais que consumirem o valor de um signal através do seu getter, avisam pro Angular que estão “ouvindo” as mudanças desse valor, e quando ele for alterado o Angular notificará esses consumidores

```tsx
count()

isValid()
```

### Recomendo essa leitura para entender mais

[Angular](https://angular.dev/guide/signals#writable-signals)

# Clientes HTTP

Para criar clientes HTTP no Angular 17 com SSR, **não iremos mais importar o módulo** `HttpClientModule`

Devemos configurar o provider no arquivos `app.config.ts`

```tsx
export const appConfig: ApplicationConfig = {
  providers: [
    provideRouter(routes), 
    provideClientHydration(), 
    **provideHttpClient(withFetch())**
  ]
};
```

E agora conseguimos injetar o serviço HttpClient como uma dependência dos nossos componentes, serviços ou outras classes:

```tsx
@Injectable({
  providedIn: 'root'
})
export class NewsletterService {

  private endpointUrl = '<https://faed47pcwb7biktidlecuafuty0aegep.lambda-url.us-east-1.on.aws/>';

  constructor(**private http: HttpClient**) { }

  sendData(name: string, email: string): Observable<NewsletterResponse> {
    const body = { name, email };
    return this.http.post<NewsletterResponse>(this.endpointUrl, body);
  }
}
```

# Usando services

Para usar services nos nossos standalone components, devemos adicionar o array de `providers` no nosso componente

```tsx
@Component({
  selector: 'app-component',
  standalone: true,
  imports: [
    ...
  ],
  providers: [
    **seuService**
  ],
  templateUrl: './app.component.html',
  styleUrl: './app.component.scss'
})
```