# Introdução a criação de websites com HTML5 e CSS3 (Lucas Vilaboim - https://www.linkedin.com/in/vilaboim)
- O elemento é a base do html.
- Cada elemento começa com uma tag de abertura, que pode possuir um atributo, conteúdo e a tag de fechamento.
- A estrutura básica do html seria:
```html
<!DOCTYPE html>
<html>
    <head>
        <meta>
        <title></title>
    </head>
    <body>
    </body>
</html>

```
- DOCTYPE não é 1 elemento html.
- O head possui informações que o navegador necessita, exemplo <meta charset=utf-8>
- Body é onde estará o conteúdo da página

## Semântica
- Por muito tempo os sites eram feitos usando <div> e classes.
- Com o Html5 novos elementos foram criados, como  
```html
<section>, <header> ,<article>, <aside>, <footer>, <h1>-<h6>
```
- A única regra sobre os elementos h1~h6 é que só pode haver 1 `<h1>` por página

## Textos e links em HTML
- Além dos <h1~h6>, usamos o `<p>`, para parágrafos e que não aceita apenas texto.
- O elemento `<a>` é uma âncora, entre elementos há o href, para um link na página ou externo e até mesmo e-mails ou telefones.
- Outro elemento do `<a>` é o target para dizer como o link será aberto. "target = '_blank' " diz para abrir em uma nova página.

## Imagens
- É um elemento sem tag de fechamento e possui apenas 2 elementos, `<src>`, que é obrigatório e o alt que é a descrição da imagem caso ela não seja carregada e leitores de imagem também a utilizam..

## Listas
- Servem para agrupar coleção de itens.
- No elemento `<ul>` a ordem dos itens não é impoortante, no `<ol>` sim.
- `<li>` são itens nessas listas.

## Introdução ao Css3
- Serve para criar regras de estilo para elementos ou grupo de elementos.
- Uma regra é formada por seletores(elementos html) e a declaração formada por um par de chaves. Exemplo:
```css
a, p, h1, h3 {
    color: blue;
    font-size: 14px;
}
```
- Podemos alterar toda a classe/elemento html ou id.
- Uma class é precedida por um **.** e uma id por **#**.
- Cada elemento html é um box model, com o css conseguesse alterar a aparência das áreas dessa caixa (margin, border, padding e content)
- Elementos que sofrem alterações após a interação do usuário são chamados subclasses, exemplo a:hover ao passar o mouse em cima do hyperlink
- algumas palavras-chave de estilização do border são solid, dotted, dashed que alteram o estilo da linha.
- Border-radius permite arredondar os cantos
- Para estilizar textos, temos font-family, font-size e font-style(itálico, negrito, etc)
- Ao alterar todas as margens é topo>direita>inferior>esquerda, pode-se alterar especificamente também.
- As propriedades de borda podem ter 3 valores: largura (pixels, centrimetros, milimetros...), cor(nome em inglês ou hexadecimal) e estilo (sólido, pontilhado, tracejado, etc)
```css
.post {
    border-top: 2px dotted green;
    border-right: 4px dashed pink;
    border-bottom: 1px solid purple;
    border-left: 4px dotted cyan;
}
/* São iguais: */ 
.post {
    border: 3px solid #505050;
}
.post {
    border-width: 3px;
    border-color: #505050;
    border-style: solid;
```
- Pode-se usar pixel, mas o mais comum para `border-radius` é  com porcentagem. Com `border-radius: 50%` é possível transformar um elemento quadrado em um círculo.
- Uma boa prática é colocar margem só acima ou só abaixo
- Fontes presentes na maioria dos dispositivos são chamadas de web safe fonts.
- É possível adicionar multiplas fontes ao `font-family` como backup;
- Entre propriedades há font-family, font-style, font-size, font-weight (peso, normal/bold), text-transform (uppercazse, lowercase, capitalize)
- text-decoration (underline, overline, line-through)
- Sobre listas há várias decorações. ul>list-style-type: square, ol>list-style-type: upper-romman, ul> list-style-type: "\1F44D", list-style-image: url-magem
- Algumas propriedades de alinhamento são:
    - width, height
    - max-width, max-height
    - margin
    - text align