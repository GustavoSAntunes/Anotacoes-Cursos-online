#css #alinhamento

Um Grid Layout é semelhante ao Flexbox, porém ele é **Multidimensional**.

O Grid Layout é criado e otimizado para a criação de **interfaces de usuário**.

De forma similar ao flexbox, temos conceitos de **container** e **elementos-filho**.

E ao organizar esses elementos, podemos trabalhar tanto com medidas **flexíveis** ou **fixas**.

As vezes o flexbox pode atrapalhar, então usar o grid layout pode ser uma solução melhor, ele pode ser usado principalmente para **desenvolver o site inteiro**.


## Anatomia de um Grid


### Grid-container

Todo Grid irá possuir um **grid-container**, de forma similar ao flexbox, é o **elemento-pai**.


|     |     |     |     |
| --- | --- | --- | --- |
|     |     |     |     |
|     |     |     |     |
|     |     |     |     |

É basicamente o grid todo.

Cada "quadradinho" dentro de um grid container é chamado de **grid-item**.

| grid-item |
| --------- |

Quando temos items que vão do começo ao fim de uma coluna ou de uma linha, ele recebe o nome de **grid-track**.


|      |      |      | item |      |
| ---- | ---- | ---- | ---- | ---- |
| item | item | item | item | item |
|      |      |      | item |      |
|      |      |      | item |      |

Quando essa **track** é deitada (em linha), chamamos de **row track**.
Quando essa **track** é em pé (coluna), chamamos de **column track**.


Quando um grupo de grid-items é definido, ele é chamado de **grid area**.

É possível por um espaço entre os grid-items, e esse pequeno "respiro" entre eles é chamado de **grid gap**.
Podemos também mudar o tamanho desse **grid gap** sem mudar o tamanho dos **grid items**.
### Grid-lines

**Grid lines** (não confundir com **row track**) são as linhas que separam os **items**.

| 1   | 2   | 3   | 4   |
| --- | --- | --- | --- |
As linhas horizontais são divididas da esquerda para a direita.
Elas também são numeradas, de forma que a linha mais a esquerda é a 1.

Vale lembrar que, mesmo que tenha apenas 4 items acima, nós temos na verdade 5 **grid lines**.

| 1   |
| --- |
| 2   |
| 3   |
| 4   |

Elas são tanto as linhas verticais quanto as horizontais.

Na forma vertical, elas são contadas de cima para baixo.

E, assim como anteriormente, aqui também temos 5 **grid lines**.


A enumeração das grid-lines podem ser **negativas**;

Isso faz com que inverta o começo e o fim das grid-lines, EX:

Vertical:

| -4  |
| --- |
| -3  |
| -2  |
| -1  |

Horizontal:

| -4  | -3  | -2  | -1  |
| --- | --- | --- | --- |



## Propriedades para Grid

``display: grid;`` -> É o que transforma um container em Grid.

Ao usar o display grid, a princípio não haverá nenhuma diferença.
Isso acontece pois o padrão do Grid é de **uma coluna** e **múltiplas linhas**.

[[Grid Layout#Tamanho|Tamanho]] -> Contém `grid-column` e o `grid-row`, usados para mudar o tamanho do container do grid layout.

[[Grid Layout#Quebra automática|Quebra]] -> Contém o `grid-auto-flow`, usado na quebra automática dos items no container.

[[Grid Layout#gap|gap]] -> Usado para criar um espaço entre os items.

[[Grid Layout#Alinhamento|Alinhamento]] -> Contém as propriedades `align-content` e `align-items` para alinhamento vertical, além de `justify-items` para alinhamento horizontal.

[[Grid Layout#Propriedades para itens em Grid Layout|items]] -> Propriedades de items em grid-layout, usados para definir a *área* que ele vai ocupar em um grid, além do `order` que é usado para mudar a prioridade de um item.

[[Grid Layout#Short-hands|Short-hands]] -> As várias short-hands de grid-layout.

[[Grid Layout#Diferença entre o fr e o auto|fr]] -> usando frações ao invés de números exatos.

[[Grid Layout#Grid-view|Grid-view]] -> Usando o Grid-view do google para ver a grid no site.



## Propriedades para container
### Tamanho

``grid-template-columns`` -> É a propriedade usada para alterar a quantidade e o tamanho de colunas de um grid.
Um de seus usos é da seguinte forma: ``grid-template-columns: auto auto;``
Isso faz com que o grid tenha 2 colunas. Quanto mais ``auto`` colocarmos, mais colunas teremos. Significa que, ao usarmos: ``grid-template-columns: auto auto auto;`` teremos 3 colunas.

``grid-template-rows`` -> É a propriedade usada para alterar a quantidade e o tamanho de linhas de um grid.
Um exemplo de uso é: ``grid-template-rows: 100px 100px 100px;``, desse jeito podemos configurar cada linha do grid, nesse caso fazemos com que as primeiras 3 linhas tenham 100px (se houver espaço). Por padrão, os elementos vão se esticar, mas podemos mudar isso se quisermos.

Suas respectivas shorthands são:

`grid-column` -> start / end

`grid-row` -> start / end

[[Grid Layout#Propriedades para Grid|Return]]



### Quebra automática

``grid-auto-flow`` -> Altera a forma de como a quebra automática dos ``items`` se comporta, o seu valor padrão é o `row`, ou seja, toda vez que ``items`` novos quebrarem o container eles serão reposicionados abaixo do anterior.

Podemos mudar o valor para `column` e dessa forma, temos que:
- Os `items` são posicionados de cima pra baixo.
- Quando acontece a quebra do container, ele é reposicionado para o lado.


No mais, temos também o conceito de **Grids explícitas** vs **Grids implícitas**.

No exemplo anterior, configuramos até 3 linhas, fazendo-as terem 100px cada (explícito). Entretanto, ao colocar um item extra (implícito), ele não irá desaparecer ou quebrar o container, mas ele também não vai ficar igual os anteriores.

Ao fazer isso, ele irá ter o tamanho exato do conteúdo.

Vale lembrar que também podemos configurar o grid para crescer em forma de coluna (então ele iria crescer para a direita).

Para resolver isso, podemos usar as propriedades 
`grid-auto-row` e `grid-auto-column`. 

Isso faz com que seja possível configurar todo item novo que possa eventualmente se juntar a essa grid.

[[Grid Layout#Propriedades para Grid|Return]]


### gap

``gap`` -> O gap cria um pequeno espaço entre cada um dos items, pode-se pensar como se fosse um "margin" só que dentro de um grid container.

[[Grid Layout#Propriedades para Grid|Return]]



### Alinhamento

Uma dica para as próximas propriedades é:
Quando estiver lidando com **Grid**, toda vez que align for usado, significa que ele irá alinhar os items de forma vertical (cima pra baixo). 

E no caso de justify, ele irá alinhar os items de forma horizontal (esquerda pra direita).

E também, todas as 4 propriedades possuem o valor `normal`, que é o valor padrão de todos eles, no caso o `stretch`.




``align-items`` -> Propriedade usada para alinhar os items verticalmente (cada quadrado do grid é um item).
As propriedades envolvendo ``items`` irão alinhar a forma que cada objeto se posiciona dentro de um **item** (quadradinho).

O seu valor padrão é o `stretch`, onde ele estica o item até colar nas grid lines **DO ITEM**.
   `start` -> fica grudado no inicio do item. (align é vertical, então fica em cima)
   `center` -> Meio do item.
   `end` -> Fim do item.

``justify-items`` -> Propriedade que alinha os **items** horizontalmente (esquerda pra direita), o padrão também é `stretch`.
Também possui os valores `start`, `center` e end. O `start` vai ficar na esquerda por ser um alinhamento horizontal.


``align-content`` -> Propriedade usada para alinhar **verticalmente** (cima pra baixo) o **CONTENT** no container.
O content é basicamente a área toda em que seus **items** estão. É preciso ter espaço o bastante no tamanho do container para usar ambos os contents.

Além dos valores `start`, `center` e `end` temos:

   `space-between` -> Cola a primeira linha no topo, a última linha no fim, e coloca espaço em branco igualmente para as **tracks** (linha de items) no meio.

   `space-evenly` -> Faz com que o espaço acima e abaixo de cada track seja exatamente igual do começo ao fim.

   `space-around` -> É bem similar ao `space-evenly`, mas ele possui o mesmo espaço **ao redor**, então a diferença notável fica no começo e no fim, onde as tracks estão mais próximas da borda.
Isso acontece pois com as tracks no meio terá o espaço de duas tracks ao mesmo tempo, enquanto no topo ou no fim haverá o espaço apenas de uma.
Portanto, podemos dizer que **os items próximos a borda recebem metade do espaço em branco das tracks ao meio.**

   `stretch` -> padrão, vai puxar até o fim do container.


``justify-content`` -> Faz a mesma coisa do align-content, mas ao invés de ser na vertical ele faz na **horizontal** (esquerda pra direita).
Ele também possui os valores `start`, `center`, `end` e `stretch`. Os outros são:

`space-between` -> Cola a primeira `column-track` (track de coluna) na esquerda, a última coluna na direita, e então distribui o espaço igualmente para as do meio.

`space-evenly` -> Espaço igual para todas as tracks.

`space-around` -> Mesmo espaço **ao redor** das tracks. Principal mudança é a proximidade nas bordas.

[[Grid Layout#Propriedades para Grid|Return]]


## Propriedades para itens em Grid Layout

São as propriedades usadas nos **items**, sendo usadas para a criação de **grid areas**.

Porém, se quiser definir as áreas de um ou mais items no elemento-pai (container), podemos usar o `grid-template-areas`

`grid-template-areas` -> Especifica áreas no grid com nomes, separando a célula que cada um vai receber. 

É semelhante ao excel, colocamos da esquerda pra direita as colunas e se precisarmos pular uma linha, fazemos outro `" "`. Como podemos ver no exemplo abaixo é possível separar as linhas para não ficar confuso.

Usamos o nome mais de uma vez se quisermos que ele ocupe uma área maior e usamos o "`.`" se quisermos que aquela célula fique vazia. Exemplo:
```template-area-ex
#grid-container {
	grid-template-columns: auto 300px 1fr auto;
	grid-template-areas:
	". ficha apresentacao ."
	". ficha skills ."
	". . formacao ."
	". . projetos .";
}

section#ficha {
	grid-area: ficha;
}

#apresentacao {
	grid-area: apresentacao;
}

#skills {
	grid-area: skills;
}

#formacao {
	grid-area: formacao;
}

#projeto-container {
	grid-area: projetos;
}
```
Conforme vemos no exemplo, podemos dar o nome que quisermos no `grid-template-areas` como se fosse uma variável, depois só precisamos pegar as divs que desejamos separar e usar o `grid-area` para designar o espaço.


Com as propriedades abaixo, podemos definir o tamanho de uma `area` em um grid layout.

Vale lembrar que o cálculo da área é com  **`grid-lines`** e não com **``grid-tracks``**

``grid-row-start`` -> O começo da linha da área (cima pra baixo).

`grid-row-end` -> Fim da linha.

`grid-column-start` -> O começo da coluna (esquerda pra direita)

`grid-column-end` -> Fim da coluna.

`span` -> "expansão", ele é usado nas propriedades com `end`, basicamente, ao invés de termos um começo e um fim de uma `grid-area`, temos um começo e a quantidade de vezes que **desejamos expandir esse começo**. Exemplos:

Exemplo normal:
```Ex
grid-row-start: 1;
grid-row-end: 4;
```

Abaixo temos o exemplo com span, onde ao invés de dizermos em qual linha ele acaba, dizemos pra ele que queremos **expandir 3 linhas**:
```Ex-span
grid-row-start: 1;
grid-row-end: span 3;
```

Exemplo de um `grid-area` que possui um tamanho de 3x2:
``` Ex
grid-row-start: 1;
grid-row-end: 3;
grid-column-start: 1;
grid-column-start: 2;
```

E assim como em flexbox, podemos usar o `order` para mudar a prioridade de um item em um container.

[[Grid Layout#Propriedades para Grid|Return]]

## Short-hands

As propriedades abaixo são **shorthands** usadas para as propriedades anteriores, temos:

`place-items` -> Aplica, respectivamente, `align-items` (cima pra baixo) e `justify-items` (esquerda pra direita)

`place-content` -> `align-content` (cima pra baixo) e `justify-content` (esquerda pra direita)

`grid-template` -> `grid-template-rows` e `grid-template-columns`


`grid-row` -> Aplica, respectivamente, `grid-row-start` e `grid-row-end`

Além disso, caso `grid-row` ou `grid-column` sejam encontrados com apenas um número, significa que eles começam nesse número e o seu próximo valor é `auto`, ou seja, ele termina no número imediatamente posterior a ele.

`grid-column` -> `grid-column-start` e `grid-column-end`

`grid-area` -> Unifica as duas últimas propriedades na ordem de **começo / começo / fim / fim**.
- `grid-row-start`
- `grid-column-start`
- `grid-row-end`
- `grid-column-end`

```Ex-area
grid-area: 1 / 5 / 1 / 2;
```

Pequeno exemplo:
``` Ex
place-items: stretch center;
place-content: start end;
grid-template: 100px 100px 100px (linha) / auto auto auto (coluna)
```

Para não ter que escrever a mesma coisa 3 ou mais vezes, podemos usar uma função chamada ``repeat()``.

Os parâmetros dela são: Quantas vezes vai repetir; Qual valor vai repetir. Ex:

``` Ex1
grid-template-columns: repeat(3, auto);
grid-template-rows: repeat(3, 100opx);
```

E claro, podemos usar o short-hand junto com essa função:

```Ex2
grid-template: repeat(3, 100px), repeat(3, auto);
```

[[Grid Layout#Propriedades para Grid|Return]]


## Unidade fracional

Usamos muito fração por serem muito mais precisas do que as divisões automáticas.

Por exemplo, suponhamos que nós temos um Grid de 1500px, e queremos dividi-lo da seguinte forma:
``` Ex1
grid-template-columns: auto auto auto;
```

Dessa forma, o grid vai dividir os elementos em 3 colunas diferentes, tendo 500px cada.

Podemos mudar o comando acima por:
``` Ex2
grid-template-columns: 1fr 1fr 1fr;
```

Ao utilizar o fr (fração), faremos com que o template (tanto em row quanto em column) pega a largura inteira do container, e divide entre as frações. No exemplo Ex2, o número de frações é 3, gerando o mesmo resultado do Ex1.

### Diferença entre o fr e o auto

A forma de uso é simples:
- Quando for usar Grid, usa ``fr`` (fraction).
- Se não, usa ``auto``.

Um exemplo de uso é:

No Exemplo anterior, se eu quiser que, por exemplo, o segundo bloco tenha o dobro do tamanho dos outros, podemos fazer isso simplesmente usando o `fr`:
``` Ex3
grid-template-columns: 1fr 2fr 1fr;
```

Estamos dividindo esse container em 3 **colunas**, porém estamos dividindo em 4 **frações**. Para descobrir o número de fractions podemos simplesmente somar o número dos ``fr``.
É importante visualizar isso, pois significa que não dividiremos o container por 3, mas sim por **4**.

E claro, também podemos usar o `repeat()` com o `fr`, exemplo:

```
grid-template-columns: repeat(3, 1fr);
```

Lembrando que caso queira colocar números diferentes em cada fraction, será inviável o uso do ``repeat()``.

[[Grid Layout#Propriedades para Grid|Return]]


## Calculando com unidades mistas

No primeiro exemplo, teremos os seguintes valores:
``` Ex1
grid-template-columns: 100px 20% 1fr 1fr;
```
O grid irá medir 1500px.

Começamos com o número absoluto: 100px.

Após isso temos a porcentagem: 20%. A porcentagem significa que ele vai sempre herdar do elemento-pai, ou seja, ele vai sempre herdar 20% do **tamanho total** do **container**, esse calculo **NÃO** inclui os 100 pixels a menos do item anterior.
Ou seja: 20% dos 1500px vai ser 300px.

Depois disso, temos as duas frações (1fr 1fr).
As frações irão fazer o cálculo **baseado no que sobrou**.
Ou seja, depois dos primeiros 2 items ocuparem 400px, sobrou 1100px para serem usados. O `fr` vai dividir esse número baseado em quantas frações forem usadas e quanta área do container sobrou.
No exemplo ele irá dividir a área por 2 e distribuir igualmente entre os 2 items. Poderia ser distribuído de forma desigual se houvesse ``2fr 1fr`` por exemplo.




## Grid-view

Um recurso muito útil para ajudar a visualizar as grids é o **grid-view**.

Podemos acessa-la usando as DevTools (o inspecionar do site).

Procure o seu container grid nos **Elements** e lá terá o botão **grid**.
Com esse botão podemos ver onde está localizado as suas **grid-lines** e as suas **enumerações**, tanto as positivas quanto as negativas.

Além das mudanças visuais, ainda nas DevTools, localizado no **Styles**, procure pelo ``display: grid;`` de seu container. Do lado dele, terá um botão de grade.

Com esse botão podemos mudar para vários tipos de **alinhamentos** diferentes.

[[Grid Layout#Propriedades para Grid|Return]]