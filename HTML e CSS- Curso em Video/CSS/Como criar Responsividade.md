
A forma mais fácil de criar um site responsivo é usando os comando [max-width] e [min-width]

Usando o Inspecionar ou a extensão [Windows Resizer] podemos achar as medidas do site em forma de [px].

Dessa forma iremos procurar as larguras ideias para o site, ou seja:

No max-width-width, iremos definir o **tamanho máximo em que ela se expande**.
no min-width, iremos definir o tamanho mínimo para que ela **pare de diminuir**.

Ou seja, o site vai se expandir até o **max-width**, a partir desse número ele não cresce mais e fica no meio se por a margem auto, se for menor do que isso, ele se adapta a tela até alcançar o valor mínimo, onde ele irá parar de diminuir.

Para **Textos responsivos**, basta definir o [text-size] como um **x**[vh], em que **vh** é a viewport, ou seja, o tamanho da tela e **x** é uma porcentagem, então o tamanho do texto vai depender do tamanho da tela, e esse tamanho pode ser aumentado ou diminuido com o x. 

Para **imagens responsivas**, podemos simplesmente definir o width de um *seletor*  de uma [img] como 100%.

Para centralizar imagens, podemos transformar o bloco delas em um bloco **flex** usando o [display: flex], assim poderemos alterar a sua margem (auto) e colocando-os no meio do site.

Mas ao fazer isso, em telas menores a imagem pode potencialmente aumentar muito de tamanho, virando um problema.

Para isso, podemos usar o [min-width]:10% e o [max-width]:100%, assim a imagem ira diminuir para se encaixar em uma tela de um celular por exemplo.

além disso, podemos envelopar um [picture] dentro de um [img], assim podemos, por exemplo, escolher uma imagem de um tamanho diferente caso o usuário esteja com uma tela menor (celular).

Para **centralizar imagens**, podemos transformar o bloco delas em um bloco **flex** usando o [display: flex], assim poderemos alterar a sua margem (auto) e colocando-os no meio do site.

Um padrão para tamanhos: 320 mínimo e 800 máximo ou 300px mínimo e 1000px máximos.

**PS:** Podemos usar o [height: nvh], em que "n" é a porcentagem do vh, isso seria o "viewport height", ou seja, a porcentagem que o bloco vai ocupar em relação ao tamanho da parte branca (a tela do navegador). Outra opção viável para Responsividade, fica bem interessante em textos.