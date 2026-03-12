#html
# favicons
Na parte de head, acima do titulo, escreva:

"link", e então selecione a opção "favicon"

na parte " href="" ", entre as aspas, aperte CTRL + SPACE e selecione seu ícone.

para converter imagens para ícones, use o site [ícones](https://favicon.io/favicon-converter/)


# svg e xml

Há também um outro tipo de arquivo: Os arquivos **svg**.

Os arquivos **svg** se comportam de maneira similar ao tipo xml, que se comporta de maneira similar ao html.

Basicamente o svg utiliza o xml para criar uma imagem.

se tivermos um ícone svg, podemos substituir o ".svg" por ".xml". Ao fazer isso, teremos acesso ao código que foi usado na criação do mesmo.

Dentro dele, temos um ou mais caminhos (path) e, geralmente localizado abaixo do path, temos o **fill**, é lá que fica a cor desse ícone.

Já que ele trabalha de forma similar a um html, podemos criar uma tag style dentro dele, e mudar algumas configurações. Exemplo:

```svg
<style>

    path {

        fill: black;

        stroke: white;

        stroke-width: 3px;

    }

</style>
```

- **fill** é a cor do preenchimento
- **stroke** é a linha em volta do ícone
- **stroke-width** é a largura do stroke

Após terminada as estilizações, renomeie-o de volta para "nome.svg"