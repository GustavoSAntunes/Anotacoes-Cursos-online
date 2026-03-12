#css #alinhamento

É um **container** (ou **elemento pai**), no qual dentro dele possuiremos **elementos filhos**.

A grande vantagem do flexbox é poder fazer com que os filhos dentro do container se adaptem ao tamanho da **tela**, ou do próprio **container**.

Um Flexbox é **Unidimensional**

Contêiner - Elemento pai, significa que ele é a "caixa" onde vai ficar os itens, sendo assim os limites serão definidos por ele.

O flexbox permite adaptar de varias maneiras os itens dentro de um contêiner. Alguns exemplos são: 
- Criar uma "responsividade" dentro do contêiner, permitindo que os itens dentro dele tanto se "amassem" quando o pai diminui, ou se estiquem caso o pai aumente;
- Fazer com que um dos elementos quebre linha, e ao quebrar fazer com que esse elemento se alargue ao tamanho do contêiner.
- Ou até mesmo mudar o eixo do contêiner para que ele seja vertical.

**IMPORTANTE: SE NÃO SOUBER COMO A CAIXA ESTÁ SE COMPORTANDO, COLOQUE UM PONTILHADO EM VOLTA DELA:** 

``` Pontilhado
border: 1px dotted black;
```


## Elemento pai e Elemento filho

Certas configurações geralmente devem ser aplicadas apenas ao **elemento pai** (container) e outras apenas ao **elemento filho** (itens).

[[Flexbox#flex-direction|flex-direction]] -> Muda a direção entre linha ou coluna.

[[Flexbox#Flex-wrap|flex-wrap]] -> Desativa ou ativa a quebra automática, além de permitir a sua configuração.

[[Flexbox#Flex-flow|flex-flow]] -> Junta, respectivamente, o `flex-direction` e `flex-wrap`.


[[Flexbox#justify-content|justify-content]] -> Alinha os itens em relação ao main-axis (eixo principal).

[[Flexbox#align-items|align-items]] -> Alinha os itens em relação ao cross-axis (eixo transversal).

[[Flexbox#Align-content|align-content]] -> Alinha o conteúdo em relação ao cross-axis, usado quando há espaço em branco.


[[Flexbox#align-self|align-self]] -> Alinha o item em relação ao eixo transversal (cross-axis), pode ser usado individualmente em cada item ou em vários de uma vez.

[[Flexbox#order|order]] -> Muda a prioridade de um item.


[[Flexbox#flex-basis|flex-basis]] -> Muda a largura do container.

[[Flexbox#flex-grow e flex-shrink|flex-grow e flex-shrink]] -> Mexe na proporção, tanto ao aumentar quanto ao diminuir.

[[Flexbox#flex|flex]] -> Shorthand que incorpora o `flex-basis`, `flex-grow` e `flex-shrink`.




## Elemento-pai:
### Eixos

Esses são aplicados ao elemento pai, neste primeiro exemplo está sendo aplicado o 
``flex-direction: row;`` 

`main-axis` -> Eixo principal, já criado por padrão, gerando 2 pontos:
- `main-start` e `main-ending`, respectivamente o começo e o fim, **esquerda pra direita**.

MAIN

|  -  |  -  |  >  |
| :-: | :-: | :-: |

- `cross-axis` -> Eixo transversal, gerando 2 pontos:
  - `cross-start` e `cross-ending`, começo e fim, **de cima pra baixo**.
  
CROSS

| \|  |
| :-: |
| \|  |
|  V  |


Vale lembrar que a direção do main se inverte ao usar o `flex-direction: row-reverse`:
- `main-axis` vai da **direita para a esquerda**.

MAIN

|  <  |  -  |  -  |
| :-: | :-: | :-: |

- `cross-axis` continua de **cima para baixo**.

Os eixos mencionadas acimas são válidas **APENAS** para o `flex-direction: row;`, visto que quando usamos o `flex-direction: column;`, os eixos e suas direções mudam. 

Usando o `flex-direction: column;`, Temos que:
- `main-axis` vai de **cima para baixo**.

MAIN

| \|  |
| :-: |
| \|  |
|  V  |

- `cross-axis` vai da **esquerda para a direita**.

CROSS

|  -  |  -  |  >  |
| :-: | :-: | :-: |


E claro, a direção da main se inverte com o `flex-direction: column-reverse`:
- `main-axis` vai de **baixo para cima**.

MAIN

|  ^  |
| :-: |
| \|  |
| \|  |

- `cross-axis` continua da **esquerda para a direita**.

É importante saber os eixos, visto que eles são necessários para justificar ou alinhar o posicionamento de um item.









### flex-direction

`flex-direction` -> Por padrão sua direção é a `row`, ou seja, direção de **linha**, da esquerda pra direita.
`flex-direction: row-reverse;` -> Inverte a direção da linha, indo da direita para a esquerda.

`flex-direction: column;` -> Direção de coluna, vai de cima para baixo.
`flex-direction: column-reverse;` -> Inverte a direção da coluna, vai de baixo pra cima.

[[Flexbox#Elemento pai e Elemento filho|Return]]

### Flex-wrap

Flex-wrap (empacotamento ou encapsulamento), ela controla o comportamento da capsula (ou seja, o elemento pai)

Por padrão, ele está definido como:

```
flex-wrap: nowrap;
```

Isso significa que, ao diminuir o seu tamanho ao ponto de não ter espaço nem para os itens, ele irá "encolher" tudo que estiver dentro.
Ele não irá quebrar a sequência que foi ordenada.
**PS:** O encolhimento dos itens dentro de um flex-box irá depender de seu conteúdo.

A outra opção é:

```
flex-wrap: wrap;
```

Ele funciona igual o no-wrap, mas quando faltar espaço para algum item, ele irá quebrar **na direção do EIXO TRANSVERSAL (o CROSS).**
Ou seja, se eu tiver um ``flex-direction: row;``, quando acabar o espaço ele irá quebrar em seu eixo transversal (cross), nesse caso ele irá para baixo.

Há também o inverso do wrap:

```
flex-wrap: wrap-reverse;
```

Isso faz com que a quebra dos itens seja na direção **OPOSTA** do **EIXO TRANSVERSAL (cross)**.
Usando o mesmo exemplo de cima, quando acontecer a quebra de itens em um row, a quebra será feito PARA CIMA.

Nota-se que ao usar um ``flex-direction: row-reverse`` ou o column-reverse, fará com que inverta-se a direção do main, incluindo a sua quebra.

[[Flexbox#Elemento pai e Elemento filho|Return]]

### Flex-flow
É a **SHORTHAND** que junta o ``flex-direction`` e o ``flex-wrap`` respectivamente. Exemplo:

```
flex-flow: row nowrap;
```

Ao usarmos o ``flex: auto;`` no elemento filho, faremos com que, caso o bloco quebre e o wrap esteja ligado, este bloco que foi quebrado irá ocupar a largura inteira do container.

[[Flexbox#Elemento pai e Elemento filho|Return]]

### justify-content

Ele é usado para alinhar os itens em relação ao **EIXO PRINCIPAL (main-axis)** 

``justify-content: start;`` -> O flex-start significa que o alinhamento irá começar no main-start, ou seja, **no começo do eixo principal**.

Por exemplo, se o seu flex-direction for um row, ele irá começar da esquerda (onde fica o main-start) e o espaço em branco ficará a direita (main-end).
Se ele tiver invertido, irá começar da direita (onde fica o start) e o espaço extra ficará na esquerda (main-end).

Portanto, se o direction for uma coluna, então começará a alinhar no topo e o espaço em branco ficará em baixo.

#### Alinhamento

``justify-content: end;`` -> É o inverso do flex-start, o alinhamento irá começar do final do eixo (main-end) e irá seguir até o começo (main-start).


``justify-content: center;`` -> Como o nome já diz, ele irá posicionar os itens no centro de um container. Nele, o espaço em branco fica distribuido igualmente entre o main-start e o main-end.

#### Espaçamento

``justify-content: space-between;`` -> Ele faz com que o primeiro item fique colado no main-start e que o último item fique colado no main-end, e os itens no meio ficarão espaçados igualmente.

``justify-content: space-evenly;`` -> Ele é bem similar ao anterior, a diferença é que o primeiro e o último item não ficarão colados no começo e no fim, todos os itens irão receber a mesma quantidade de espaçamento.

``justify-content: space-around;`` -> Este é um pouco diferente, o space-around faz com que cada item receba o seu próprio "quadrado" dentro do container, e após isso, ele centraliza os itens dentro desses quadrados.

![[Pasted image 20260109201736.png]]


[[Flexbox#Elemento pai e Elemento filho|Return]]

### align-items

O alinhamento de ``align-items`` é feito no sentido do **EIXO TRANSVERSAL (CROSS AXIS)**, diferente do ``justify-content``, que é feito no sentido do EIXO PRINCIPAL.

``align-items: stretch;`` -> É o padrão, ele faz com que os elementos se estiquem do cross-start até o cross-end.

``align-items: start;`` -> Faz com que o elemento fique colado no cross-start, fazendo com que o espaço em branco fique no cross-end.

``align-items: end;`` -> Inverso do flex-start, faz com que os elementos fiquem colados no cross-end, fazendo com que o espaço em branco fique no cross-start.

``align-items: center;`` -> Centraliza os elementos entre o cross-start e o cross-end.

[[Flexbox#Elemento pai e Elemento filho|Return]]


### Centralização absoluta

Faze-lo em flexbox é bem simples, é só colocar as propriedades ``justify-content: center;`` e o ``align-items: center;``, dessa forma fazemos com que os elementos fiquem perfeitamente no centro de seu elemento pai. 
Lembrando que essas propriedades ficam no elemento-pai (container) e não nos elementos-filhos (itens).

[[Flexbox#Elemento pai e Elemento filho|Return]]

### Align-content

Serve para alinhar os elementos no eixo transversal, porém com algumas especificações.
Ele só é aplicado quando:

- O container possui mais de uma linha de elementos.
- Ele só é aplicado quando há espaço vazio sobrando, visto que ele é usado para manipular em quais partes desse container vazio o seu grupo de elementos vai se alinhar.

``align-content: stretch;`` -> O padrão, Ele pega a dimensão inteira do eixo transversal do container e irá dividi-lo em quadrados, o número de quadrados é baseado no número de linhas (ou colunas), após isso ele irá esticar os elementos até o final desses quadrados.

``align-content: start;`` -> Essa propriedade faz com que os elementos fiquem colados no ``cross-start``, incluindo as suas quebras, reservando o espaço em branco pro ``cross-end``.

``align-content: end;`` -> Inverso do start, deixando os elementos no ``cross-end`` e deixando o espaço em branco no ``cross-start``.
PS: A quebra continua do mesmo jeito, ela não será invertida. Portanto, ela muda somente em que parte do container os elementos irão se alinhar.

``align-content: center;`` -> Ela alinha o grupo de elementos ao centro do container.

``align-content: space-between;`` -> Pega a primeira linha de elementos e coloca no ``cross-start``, pega a última linha de elementos e a posiciona no ``cross-end``, e os elementos no meio são divididos de forma igualmente no meio.

``align-content: space-evenly;`` -> É a mesma coisa que o space-between, mas o espaço em branco é posto também antes da primeira linha e depois da última linha, fazendo com que o espaço em branco seja igualmente distribuido.

``align-content: space-around;`` -> De forma similar ao ``stretch``, divide o espaço do container em quadrados (o número de quadrados depende do número de linhas), e após colocar os elementos nesses quadrados, ele centraliza os elementos em volta desse "quadrado".

[[Flexbox#Elemento pai e Elemento filho|Return]]

## Elemento-filho:
### order

É possível dar um número para cada um dos itens, fazendo com que seja possível ordenar eles baseado na ordem crescente desses números. Exemplo:

``<div class="item" style="order: -3">D</div>``

Se dois ou mais números forem iguais, eles simplesmente serão ordenados baseado em quem apareceu primeiro.

PS: Agora são os elementos-filhos, logo as propriedades devem ser aplicadas aos itens.

Todo item dentro de um container em flexbox terá o ``order: 0``. Logo, se um item tiver um ``order: 1``, ele irá ficar na frente de todos os outros, isso se não tiverem configurados.

[[Flexbox#Elemento pai e Elemento filho|Return]]

### align-self

Essa propriedade pode ser aplicada a **CADA** item de um container, se necessário.

o ``align-self`` é baseado no **CROSS-AXIS (eixo transversal)**.

Os **5 valores** do align-self são:

- ``auto`` -> padrão, ele vai herdar a propriedade  de alinhamento vertical do elemento-pai.
- ``flex-start`` -> Colado ao ``cross-start``.
- ``flex-end`` -> Colado ao ``cross-end``.
- ``center`` -> Centraliza em relação ao eixo transversal.
- ``stretch`` -> Estica do start até o end.

**PS: SE FOR USAR O ALIGN-SELF, LEMBRE-SE QUE O align-content SOBREPÕE O align-self. OU SEJA, AO APLICAR OS DOIS E OCORRER AS CONDIÇÕES PARA O ALIGN-CONTENT, QUALQUER ALTERAÇÃO FEITA USANDO O ALIGN-SELF SERÁ ANULADA EM PROL DO ALIGN-CONTENT.**

[[Flexbox#Elemento pai e Elemento filho|Return]]

### flex-basis

O ``flex-basis`` é a largura do **conteúdo** dentro de um **item**.

Por exemplo, a propriedade padrão é ``flex-basis: auto``, isso significa que o item vai ter o tamanho baseado no conteúdo que tiver dentro. Portanto, podemos ter um pequeno item que vai estar escrito apenas ``a``, mas se tivermos um item escrito ``bbbbbbbbbbbbbbbb``, esse item irá se esticar até que ele consiga mostrar todo o seu conteúdo.

Ao mudarmos essa propriedade auto para um número fixo, faremos com que os itens percam a sua "adaptação ao conteúdo", ou seja, todos os itens terão a mesma largura, mesmo que o seu conteúdo ocupe ou não todo esse espaço.

E claro, podemos também mudar o ``flex-basis`` de forma única para cada um dos itens em um container.

**PS: Estamos usando flexbox, isso significa que um item NÃO pode quebrar os limites de um container. Podemos colocar números grandes, mas o item vai se adaptar ENQUANTO DER. Caso não exista espaço o suficiente, todos irão diminuir igualmente.**

[[Flexbox#Elemento pai e Elemento filho|Return]]


### flex-grow e flex-shrink

Essas propriedades são as responsáveis por aumentar ou diminuir o tamanho dos itens **até o limite** de seus containers.
Temos dois valores básicos: 0 para desativar e 1 para ativar.

Por padrão, temos o ``flex-grow: 0;`` e o ``flex-shrink: 1;``

Isso significa que quando o container for maior que os itens, os itens apenas irão deixar espaço em branco. Mas quando o container for menor que os itens, os itens irão encolher até onde for possível para se encaixar ao container.

A propriedade ``flex-grow`` é melhor visualizada ao usarmos a propriedade ``flex-wrap: wrap;``, visto que ao acontecer a quebra do wrap, o item que recebeu a quebra irá **aumentar até o final do container**, sendo essa uma opção interessante de design.

Vale lembrar que já que essas propriedades são aplicadas aos itens, **podemos por um valor diferente para cada item.**

Essa propriedade não é binária, ela possui outros números.

[[Flexbox#Elemento pai e Elemento filho|Return]]


#### Proporção flex-grow

além do 0 e 1, podemos ter números maiores, por exemplo

|0| |1| |2|

Com números maiores do que 1 estamos mexendo com **PROPORÇÃO**, ou seja, no exemplo acima estamos comparando a diferença de proporção entre 1 e 2. 2 é o dobro de 1, logo, a proporção do item 2 vai ser o DOBRO do elemento 1. (2:1)

|0| |  1  | |    2    |

Vale notar que a comparação são entre os valores, e não simplesmente o dobro ou triplo. Por exemplo:

|0| |2| |2|

Aqui temos dois números iguais, ou seja, mesmo que ambos possuam o número 2, comparando esses valores eles são iguais e, portanto, eles terão **A MESMA PROPORÇÃO**. (2:2)

|0| |  2  | |  2  |


#### Proporção flex-shrink

Da mesma forma ao flex-grow, podemos colocar valores diferentes ao flex-shrink. Exemplo: (2:1)

|    2    | |    0    | |    1    |

Quanto maior o número, **MENOR** vai ser a proporção em comparação aos outros.

|2| |    0    | |  1  |

Logo, o número 2 vai diminuir o **DOBRO** do número 1, enquanto o 0 segue inalterado.

[[Flexbox#Elemento pai e Elemento filho|Return]]


### flex

É a **shorthand** que junta, respectivamente: ``flex-grow``, ``flex-shrink `` e ``flex-basis``. A escrita será da seguinte forma:

``` flex
flex: 0 1 150px;
```

Onde:
- O primeiro número é o ``flex-grow``
- O segundo número é o ``flex-shrink``
- O terceiro número é o ``flex-basis``


#### Valores mais utilizados

```padrao
flex: 0 1 auto;
```

Esse é o valor PADRÃO para as 3 propriedades desse shorthand.

O outro jeito de escrever isso é:

``` initial
flex: initial;
```



```
flex: 0 0 auto;
```

Os objetos não crescem e nem diminuem, além do tamanho de seus itens serem baseado em seus conteúdos. É a forma mais "rígida" do flexbox, pode-se dizer que é até mesmo "inflexível". Portanto, outro nome que ele recebe é:

``` none
flex: none;
```



```
flex: 1 1 auto;
```

É o inverso do anterior, isso faz com que os elementos filhos tenham a maior flexibilidade possível. Assim, ele recebe o nome:

``` auto
flex: auto;
```



```ex2
flex: 3;
```

As vezes encontramos uma flex que possui apenas 1 ou 2 valores, isso é devido ao jeito que as **shorthands** funcionam.

Isso significa que apenas a primeira propriedade (nesse caso, o ``flex-grow``) foi alterada. Enquanto as outras 2 permanecem padronizadas, sendo assim é a mesma coisa que escrever:

```ex3
flex: 3 1 auto;
```


[[Flexbox#Elemento pai e Elemento filho|Return]]