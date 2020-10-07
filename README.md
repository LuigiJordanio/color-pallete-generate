# Gerador de Paleta de Cores

[![N|Solid](https://uploaddeimagens.com.br/images/002/869/762/original/DesenvolvidoPor.png)](https://8pixel.com.br)

Essa biblioteca [Sass] tem como presente objetivo gerar arquivos css, mixins e functions sass que vão possuir formas e funcionalidades que vão colorir a sua aplicação.
O desenvolvedor seta inicialmente as cores base de sua paleta de cores e a partir dessas cores base e script gera uma paleta de cores com níves de cor mais claros e escuros.
Além disso, outras classes css/mixins sass vão permitir que o desenvolvedor consiga facilmente atribuir estilos padrão de cor para os seus componentes web.

<!-- 
### Demo
Para ver em funcionamento [visite nossa página demo] -->

## Instalação
### 1. Clonar o projeto 
Clone o projeto para obter os arquivos sass  
```console
git clone https://github.com/LuigiJordanio/gerador-paleta-sass.git
```
### 2. Importar biblioteca
Importe no início de sua folha de estilo:
```scss
@import "your-path/pallete";
```

### 3. Configurar variavies (_variables.scss)
#### 3.1.1 Colocar cores principais 
Coloque todas as suas cores padrão no objeto de cores, você pode colocar quantas cores quiser:
```scss
 $colors: (
    color-name: #ff00ff,
    color-name-2: #00ff99
);
```

#### 3.1.2 Coloque o grau de constraste entre as cores 
Por padrão ele vem com a numeração de 8, quanto maior o número maior vai ser a diferença entra as cores geradas:
```scss
$color_scale:8;
```
#### 3.1.3 Coloque o número de variações desejada
Por padrão ele vem com a numeração de 3,o script vai gerar o número desejado de variações mais claras e mais escuras:
```scss
$color_number:3;
```


## 4. Funcionalidades

### 4.1 Principais Helpers css
#### 4.1.1 Background
É gerado automaticamente um classe css que é composta por ``.bg-{nome-da-color}-{tipo}-{nivel}`` e um apelido que contém as 3 primeiras letras da cor, primeira letra do tipo e o numeral. ``.bg-{nom}-{tipo}{nivel}``
|         Cores        | Helper Css com o nome completo | Helper Css apelido |
|:--------------------:|:------------------------------:|:------------------:|
|       Darker 1       |     ``.bg-primary-darker-1``     |   ``.bg-pry-d1``   |
|       Darker 2       |     ``.bg-primary-darker-2``     |   ``.bg-pry-d2``   |
|       Darker 3       |     ``.bg-primary-darker-3``     |   ``.bg-pry-d3``   |
| Standard (Primary) |          ``.bg-primary``         |     ``.bg-pry``    |
|       Lighter 1      |     ``.bg-primary-lighter-1``    |   ``.bg-pry-l1``   |
|       Lighter 2      |     ``.bg-primary-lighter-2``    |   ``.bg-pry-l2``   |
|       Lighter 3      |     ``.bg-primary-lighter-3``    |   ``.bg-pry-l3``   |

<br/>

#### 4.1.2 Helper de Texto
É gerado automaticamente um classe css que é composta por ``.tx-{nome-da-color}-{tipo}-{nivel}`` e um apelido que contém as 3 primeiras letras da cor, primeira letra do tipo e o numeral. ``.tx-{nom}-{tipo}{nivel}``
|         Cores        | Helper Css com o nome completo | Helper Css apelido |
|:--------------------:|:------------------------------:|:------------------:|
|       Darker 1       |    ``.tx-primary-darker-1``    |   ``.tx-pry-d1``   |
|       Darker 2       |    ``.tx-primary-darker-1``    |   ``.tx-pry-d2``   |
|       Darker 3       |    ``.tx-primary-darker-3``    |   ``.tx-pry-d3``   |
| Standard (Principal) |         ``.tx-primary``        |     ``.tx-pry``    |
|       Lighter 1      |    ``.tx-primary-lighter-1``   |   ``.tx-pry-l1``   |
|       Lighter 2      |    ``.tx-primary-lighter-2``   |   ``.tx-pry-l2``   |
|       Lighter 3      |    ``.tx-primary-lighter-3``   |   ``.tx-pry-l3``   |


<br/>

#### 4.1.3 Helper de Borda
Para atribuir borda em todos os cantos do elemento é gerado automaticamente um classe css que é composta por ``.border-{nome-da-color}-{tipo}-{nivel}`` 
|         Cores        |             Helper            |      Alias     |
|:--------------------:|:-----------------------------:|:--------------:|
|       Darker 1       |  ``.border-primary-darker-1`` | ``.br-pri-d1`` |
|       Darker 2       |  ``.border-primary-darker-1`` | ``.br-pri-d2`` |
|       Darker 3       |  ``.border-primary-darker-3`` | ``.br-pri-d3`` |
| Standard (Principal) |      ``.border-primary``      |   ``.br-pri``  |
|       Lighter 1      | ``.border-primary-lighter-1`` | ``.br-pri-l1`` |
|       Lighter 2      | ``.border-primary-lighter-2`` | ``.br-pri-l2`` |
|       Lighter 3      | ``.border-primary-lighter-3`` | ``.br-pri-l3`` |


<br/>

#### 4.1.3.1 Helper de Borda no Canto Específico
Para atribuir borda em cantos específicos do elemento é gerado automaticamente um classe css que é composta por ``.border-{canto}-{nome-da-color}-{tipo}-{nivel}`` e também um apelido que é composto por ``.br-{canto}-{nome-da-color}-{tipo}{nivel}``
|  Canto |         Classe Css         |     Alias     |
|:------:|:--------------------------:|:-------------:|
|   Top  |   ``.border-top-primary``  | ``.br-t-pri`` |
| Bottom | ``.border-bottom-primary`` | ``.br-b-pri`` |
|  Todos |     ``.border-primary``    |  ``.br-pri``  |
|  Right |  ``.border-right-primary`` | ``.br-r-pri`` |
|  Left  |  ``.border-left-primary``  | ``.br-l-pri`` |


<br/>


### 4.1.2 Função para retornar cor
Para selecionar e utilizar a cor desejada, você pode utilizar a função que recebe 3 parametros e retorna a cor desejada.

```scss
  get-color('color','style','level');
```

```css
 .custom-primary-darker-1{
   background-color: get-color('primary','darker-1');
   color:get-color('primary','darker-1');
 }
```
Saída no css

```css
 .custom-primary-darker-1{
   background-color: #000000;
   color:#000000;
 }
```



### 4.2 Principais mixins sass
Afim de trazer mais comodidade para o desenvolvedor front-end, foram anexados mixins que permitem a atribuição de propriedades css diretamente na sua classe customizada.São eles:

#### 4.2.1 Background Mixins
Para atribuir uma cor de fundo para o seu elemento basta inserir a seguinte linha no seu arquivo sass. Os parametros de tipo e level são opcionais, quando não passados, o valor padrão é a cor standard.
```scss
 .custom-class{
   @include background-color('color','type-level')
 }
```
Exemplo:
```scss
 .custom-class{
   @include background-color('primary','darker-1')
 }
```
Saida
```css
 .custom-class{
   background-color: #000000;
 }
```

### 4.2 Principais mixins sass
Afim de trazer mais comodidade para o desenvolvedor front-end, foram anexados mixins que permitem a atribuição de propriedades css diretamente na sua classe customizada.São eles:

#### 4.2.1 Background Mixins
Para atribuir uma cor de fundo para o seu elemento basta inserir a seguinte linha no seu arquivo sass. Os parametros de tipo e level são opcionais, quando não passados, o valor padrão é a cor standard. Ainda existe um terceiro parametro para a passagem de uma cor com opacidade
```scss
 .custom-class{
   @include background-color('color','type-level');
 }
```
Exemplos:
```scss
 .custom-class-darker{
   @include background-color('primary','darker-1');
 }
 .custom-class{
   @include background-color('primary');
 }
 .custom-class-darker-opacity{
   @include background-color('primary','darker-1', 0.5);
 }
```
Saida
```css
  .custom-class-darker{
   background-color: #000000;
 }
 .custom-class{
   background-color: #00FF00;
 }
 .custom-class-darker-opacity{
   background-color: rgba(0,0,0,.5);
 }
```


#### 4.2.1 Border Colors Mixins
Para atribuir uma border com uma cor específica  para o seu elemento basta inserir a seguinte linha no seu arquivo sass. Os parametros de tipo e level são opcionais, quando não passados, o valor padrão é a cor standard. Ainda existe um terceiro parametro para a passagem de uma cor com opacidade. Quando o parametro de direção não for passado, ele implementara a cor da borda em todos os cantos.
```scss
 .custom-class{
   @include border-color('color','type','opacity','direction');
 }
```

Exemplos:
```scss
 .custom-border-darker{
   @include border-color('primary','darker-1');
 }
 .custom-class{
   @include border-color('primary');
 }
 .custom-class-darker-opacity-top{
   @include border-color('primary','darker-1', 0.5,'top');
 }
```
Saída no css:
```css
 .custom-border-darker{
   border-color:#00f000;
 }
 .custom-class{
   border-color:#00f000;
 }
 .custom-class-darker-opacity-top{
   border-top-color:rgba(0,0,0,.5);
 }
```

#### 4.2.1 Color text Mixins
Para atribuir uma cor de texto para o seu texto basta inserir a seguinte linha no seu arquivo sass. Os parametros de tipo e level são opcionais, quando não passados, o valor padrão é a cor standard. Ainda existe um terceiro parametro para a passagem de uma cor com opacidade
```scss
  @include color('color','type-level');
```
Exemplos:
```scss
 .custom-class-darker{
   @include color('primary','darker-1');
 }
 .custom-class{
   @include color('primary');
 }
 .custom-class-darker-opacity{
   @include color('primary','darker-1', 0.5);
 }
```

#### 4.2.1 Background Gradient Mixins
Para atribuir uma cor de fundo em gradient para o seu elemento basta inserir a seguinte linha no seu arquivo sass. São recebido como parametro dois valores de em hexadecimal, pode ser utilizado com a função ``get-color()``
```scss
   @include background-gradient(get-color('color'),get-color('color-2'));
```
Exemplos:
```scss
 .custom-class-gradient{
   @include background-gradient(get-color('color'),get-color('color-2'));
 }

 .custom-class-hex{
   @include background-gradient('#FFFFFF','#000000');
 }
```


#### 4.2.3 Text Color Gradient Mixins
Para atribuir uma cor de fundo em gradient para o seu elemento basta inserir a seguinte linha no seu arquivo sass. São recebido como parametro dois valores de em hexadecimal, pode ser utilizado com a função ``get-color()``
```scss
   @include color-gradient(get-color('color'),get-color('color-2'));
```
Exemplos:
```scss
 .custom-class-gradient{
   @include color-gradient(get-color('color'),get-color('color-2'));
 }

 .custom-class-hex{
   @include color-gradient('#FFFFFF','#000000');
 }
```


<!-- ### Contribua

Torne-se um [contribuidor] e ajuda essa iniciativa. -->

### TODOS

 - Automatizar teste de constraste de cor
 - Criar snippet codes Vs Studio e outros editores de texto
 - Criar biblioteca de cores para softwares de prototipação, ex: Figma, Sketch, Adobe XD, etc.
 - Criar webpack npm para gerar palleta de cores a partir de comandos.
 - Criar página de demo.

License
----

MIT

** Software livre**

  [Sass]: http://sass-lang.com

   [ visite nossa página demo]: <https://demowebpage.8pixel.com.br>
   [Teachable Machine]: <https://teachablemachine.withgoogle.com/>