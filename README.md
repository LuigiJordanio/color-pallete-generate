# Gerador de Paleta de Cores

[![N|Solid](https://uploaddeimagens.com.br/images/002/869/762/original/DesenvolvidoPor.png)](https://8pixel.com.br)

Essa biblioteca [Sass] tem como presente objetivo gerar arquivos css, mixins e functions sass que vão possuir formas e funcionalidades que vão colorir a sua aplicação.
O desenvolvedor seta inicialmente as cores base de sua paleta de cores e a partir dessas cores base e script gera uma paleta de cores com níves de cor mais claros e escuros.
Além disso, outras classes css/mixins sass vão permitir que o desenvolvedor consiga facilmente atribuir estilos padrão de cor para os seus componentes web.

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
### 4.1 Helpers css
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

#### 4.1.1 Helper de Texto
|         Cores        | Helper Css com o nome completo | Helper Css apelido |
|:--------------------:|:------------------------------:|:------------------:|
|       Darker 1       |    ``.tx-primary-darker-1``    |   ``.tx-pry-d1``   |
|       Darker 2       |    ``.tx-primary-darker-1``    |   ``.tx-pry-d2``   |
|       Darker 3       |    ``.tx-primary-darker-3``    |   ``.tx-pry-d3``   |
| Standard (Principal) |         ``.tx-primary``        |     ``.tx-pry``    |
|       Lighter 1      |    ``.tx-primary-lighter-1``   |   ``.tx-pry-l1``   |
|       Lighter 2      |    ``.tx-primary-lighter-2``   |   ``.tx-pry-l2``   |
|       Lighter 3      |    ``.tx-primary-lighter-3``   |   ``.tx-pry-l3``   |

### Demo
Para ver em funcionamento [visite nossa página demo]

### Contribua

Torne-se um [contribuidor] e ajuda essa iniciativa.

### Todos

 - Automatizar teste de constraste de cor
 - Gerar snippet codes Vs Studio e outros editores de texto
 - Gerar biblioteca de cores para softwares de prototipação, ex: Figma, Sketch, Adobe XD, etc.
 - Criar webpack npm para gerar palleta de cores a partir de comandos.
 - Criar página de demo.

License
----

MIT

** Software livre**

  [Sass]: http://sass-lang.com

   [ visite nossa página demo]: <https://demowebpage.8pixel.com.br>
   [Teachable Machine]: <https://teachablemachine.withgoogle.com/>