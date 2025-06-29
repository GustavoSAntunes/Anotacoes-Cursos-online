

# O que são caixas?

É um conceito usado para organizar seu site.
Ela organiza seu site em forma de caixas.

Um exemplo de uma caixa seria o h1.
A altura dela é [height] e a sua largura é [width].

Borda é a linha que circula o seu conteúdo ([border]).

O espaço criado entre uma borda e o conteúdo é chamado de Preenchimento ([padding]). É 
como se você estivesse engordando o seu elemento para que a borda fique distante do seu conteúdo. Diferentes paddings podem ser formado em cada direção.

Margem [margin], é bem semelhante ao preenchimento, mas ao invés de ser entre a borda e o conteúdo, ele fica do lado externo da borda.

O traçado [outline] fica entre a borda e a margem.

Ou seja, temos o Conteúdo -> Padding -> Border -> outline -> Margin.

Nota: Essas características só irão aparecer se você configurá-las em seu código.

# Tipos de Caixa

Existem dois tipos de caixa: A caixa **box-level** e a **inline-level**.

Em uma caixa box-level, o elemento sempre vai iniciar em outra linha, ocupando a largura total da tela, e depois pular para a outra linha.

Exemplos: [div], [p], [main], [video], [h1]

Em uma caixa inline-level, o elemento não irá pular uma linha, mas sim "abrir uma caixa" exatamente onde foi posta, e logo em seguida vai deixar o conteúdo continuar, sem quebra de linha.

Exemplos: [a], [span], [code], [strong], [em].

# Caixas na prática

Abrindo a opção de inspecionar de um site, podemos achar um modelo de caixa já feito.

Tudo que foi feito pelo navegador é chamado de user agent. Normalmente são as configurações padrão para um site.

O sentido para configurar os paddings e margins é em sentido horário, começando de cima, indo para a direita até a esquerda.

Para fazer com que uma caixa fique centralizada, use [margin: auto].

Vale lembrar que o *outline* não aumenta os limites da margem, então mesmo se você deixá-lo enorme, ele pode extrapolar um pouco a margem, mas ela continuará igual.

Podemos usar [display: inline-block] para que a caixa ocupe somente o conteúdo. O comando


# Shorthand: border, padding, margin e outline

É a simplificação desses parâmetros

**border:** A ordem dos parâmetros, são, respectivamente: Largura, Estilo e Cor.
[border: 18px solid darkgray;]

**padding:** A ordem é feita em sentido horário, começando de cima, indo para a direita até a esquerda.

**PS: Se as quatro forem iguais, basta informar um único número, e ele deixará as quatro medidas iguais.**

**PS(2): Se você colocar apenas 2 números, o primeiro irá mudar o [top] e o [bottom], enquanto o segundo mudará o [right] e o [left].**

É possível centralizar as margens, usando [auto], contanto que você use nos lados corretos.
Ex: [20px auto 40px auto]

Os parâmetros do *outline*, são, respectivamente: Largura, Estilo e Cor.

É possível mudar como um bloco será exposto em seu site usando o [display], podemos por exemplo, transformar um [a], que é um inline-level (sem quebra de linha) em um box-level (que quebra linha e se isola).


# Sombras nas caixas

Usando o Shorthand [box-shadow]

Os parâmetros são:

-Deslocamento da sombra na horizontal
Positivo = direito
Negativo = esquerdo

-Deslocamento vertical
Positivo = baixo
Negativo = cima

-Espalhamento da Sombra

-Cor

Podemos por inset no começo também para ela ficar interna.

Ao invés de decorar tudo isso, temos a opção também de usar o inspecionar no site, procurar a box-shadow onde deseja-se por a sombra, configurar por lá e copiar para por no código.

# Sombras nos textos

Usando o shorthand [text-shadow], podemos criar sombras de maneira quase idêntica ao box (horizontal, vertical, espalhamento e cor), a diferença é que a sombra se localiza no texto ao invés de ser na caixa.


# Círculo das bordas

Usando o shorthand [border-radius]
A ordem dos parâmetros são:

Começa no [border-top-left] (esquerda superior)
Então ele vai para a direita (top-right)
Em seguida, desce (bottom-right)
E termina no bottom-left.

Ao colocar 2 números, o primeiro irá modificar a **esquerda superior** e a **direita inferior**
Enquanto o segundo irá modificar a **direita superior** e a **esquerda inferior.**


# Bordas personalizadas

Usando [border-image-source]
É preciso criar uma borda qualquer primeiro, para segurar a borda personalizada.
PS: É possível criar a borda transparente caso o navegador não seja compatível.

Use o [border-image-slice] para formar a borda com a imagem.
Use o [border-image-repeat] para personalizar melhor.

Shorthand:
[border-image:]	url:('imagem') (numero do slice) (repeat)