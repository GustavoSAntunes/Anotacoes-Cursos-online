[background-image: url()] - Muda o fundo para uma imagem, pode usar o caminho dos arquivos ou um link direto para a imagem de algum site por exemplo, tendo em vista que a mesma está refém da hospedagem desse site.

Por padrão, o uso dessa propriedade em qualquer caixa irá replicar a mesma imagem varias vezes até encher o local definido. Possuem também um tamanho fixo, independente do tamanho da janela.

Por padrão, as repetições sempre começam do lado superior esquerdo.


[background-repeat] - Modifica a repetição das imagens:
no-repeat: A imagem irá aparecer uma única vez.

repeat-x: Replica a imagem da esquerda pra direita.
repeat-y: Replica a imagem de cima para baixo.

[background-position] - Em que posição da tela vai ficar a imagem de fundo. seus elementos são:
Center / top / bottom / right / left.

Normalmente usa-se dois elementos para definir com mais precisão onde será a "âncora", ou seja, onde a imagem vai começar a se expandir. Ex:

| top left    |               |              |
| ----------- | ------------- | ------------ |
| center left | center center |              |
|             |               | bottom right |


**PS:** Quando for usar imagens de fundo, escolha uma cor de fundo, visto que caso a conexão do cliente ou o servidor em sí estiver lento, o texto vai carregar primeiro que a imagem, pois o conteúdo tem prioridade sobre esse estilo.


[background-size] - Respectivamente: Largura e Altura.

Podemos definir manualmente com pixels.

Podemos usar o height de 100vh e alterar o background-size para 100%, ela resolve o problema mas é *péssima* devido a distorção da imagem.


[contain] - Faz com que a imagem sempre seja mostrada 100%, mas com varias "picotadas" ao redor da tela, semelhante a cena de um filme com bordas em volta.


[cover] - Ele não exibe 100% da imagem, mas sempre ocupa 100% da viewport (da tela).


[background-attachment] - Ela irá fixar o background na viewport, ou seja, vai resolver o problema daquelas barras pretas ao usar o [cover].


Ao usar o [background-size] e [background-attachment] temos uma imagem de fundo que é responsiva e que não  quebra a renderização da mesma.



## Background shorthand
A ordem do shorthand de [background] é, respectivamente:
background

                color > image > position > / > size > repeat > attachment

a "/" é importante para separar o position e o size, pois sem eles o css considera como uso incorreto da propriedade e sumir com a imagem de fundo.


