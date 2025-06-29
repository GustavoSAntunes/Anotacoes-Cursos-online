
**IMPORTANTE**: Tabelas são importantes, PORÉM: **NÃO USE ELA PARA FAZER A ESTRUTURA DO SITE.** É ultrapassado e só vai dar problema, vai ficar tudo uma merda.

### HIERARQUIA DE TABELAS (simples)
TABLE - tabela
	TABLE ROW - linha de tabela
		TABLE HEADER - Cabeçalho de tabela
		TABLE DATA - Dado de tabela


Na criação de tabela, usamos os seguintes comandos:
[table] - O comando para criar tabelas.
[tr] - Representa uma linha na tabela.
[td] - Representa um dado da tabela.
[th] - Representa o cabeçalho da tabela
[border-collapse] - Esse é pra tabela, com ela escolhemos se as bordas de cada dado vão ter um "espacinho entre si" (vem assim por padrão) ou se eles vão ficar colados (igual no excel).
Exemplo:
```
<table>

	<tr> <!-- Primeira linha -->

		<td>A1</td>

		<td>B1</td>

		<td>C1</td>

	</tr>



	<tr class="linha">

		<td>A2</td>

		<td>B2</td>

		<td>C2</td>

	</tr>



	<tr>

		<td>A3</td>

		<td>B3</td>

		<td>C3</td>

	</tr>



	<tr>

		<td>A4</td>

		<td>B4</td>

		<td>C4</td>

	</tr>
</table>        
```
Vale lembrar que, como qualquer outro elemento em HTML, é possível de editar os mesmos da tabela usando CSS.

PS: No HTML moderno, o fechamento das tags [TR] e [TD] com o </tr> e o </td> é completamente OPCIONAL. Entretanto, é recomendado fechar eles para não dar chance ao erro. O Visual Studio já faz isso pra você então não muda muito tua vida.

PS.2: Se a hierarquia das tabelas (hierarquia acima) NÃO for obedecida, os elementos podem aparecer antes ou depois da tabela, ficando uma bagunça.

Normalmente, usa-se o [td] para DADOS dentro da tabela, enquanto o [th] usa-se para o resto, o título da tabela, nome de uma coluna, etc...

Podemos também mudar a forma em que o texto fica alinhado na célula:

[text-align] -> Alinhamento HORIZONTAL do texto.
[vertical-align] -> Alinhamento VERTICAL do texto.

No padrão do EXCEL, todo texto é alinhado pra esquerda e números para a direita.

para fazermos a parte dos números por HTML, teremos que criar uma classe numero e mudar o alinhamento para a direita, colocando-a em todas as células na qual for posta números.


### TRABALHANDO COM TABELAS GRANDES

ANATOMIA DAS TABELAS GRANDES

TABLE
	CAPTION
	THEAD
		TR, TD, TH
	TBODY
		TR, TD, TH
	TFOOT
		TR, TD, TH

[CAPTION] É o título da tabela
[THEAD] É o cabeçalho da tabela
[TBODY] Onde vai ficar os dados da tabela
[TFOOT] Rodapé

Vale notar que não é obrigatório a adição de um head (cabeçalho da tabela) e de um foot (rodapé) para a tabela.

Para mudar o tamanho de uma coluna, podemos colocar um style pontual na coluna selecionada e definir um width para a mesma.

Ex: 
```
<thead>

	<tr>

		<th></th>

		<th scope="col">Estado</th>

		<th scope="col" style="width: 50px;">População</th>

	</tr>

</thead>
```

PS: Independente de como você organizar o seu código, como por exemplo, colocar o THEAD por último e o TBODY em primeiro, o navegador entende onde que cada parte da tabela se localiza.

A [Pseudoclasse] de CSS [nth-child] é especificamente útil em tabelas, permitindo a alteração de estilo em lugares especificos de uma tabela, usando comandos-chaves como [even] e [odd], ou mesmo usando equações. ([[Pseudoclasses]]).

Podemos fixar o header da tabela no topo da tela seguindo os passos de [[Cabeçalhos e menus fixos]].
### ESCOPO

Não muda nada graficamente, mas ela é importante para a semântica do html e para ajudar os mecanismos de busca.

Usa-se o escopo nos Headers, na definição das colunas:
Esse título pode ser referente a uma COLUNA ou ao uma LINHA.

[scope="col"] -> É o escopo de coluna, Indica que esse th é relativo aos dados que estão na mesma COLUNA. (abaixo)
[scope="row"] -> Indica que o th está relativo aos dados que estão na mesma LINHA. (do lado)

Com grupos de Colunas ou Linhas usa-se: [scope="colgroup"] e [scope="rowgroup"].


### MESCLAGEM DE CÉLULAS

Ao fazer tabelas, as vezes temos que remover uma de suas células. Ao fazer isso, teremos um buraco na tabela. Podemos resolver isso "extendendo" a célula até esse buraco, "mesclando" ela e removendo o buraco da tabela.

PS: COLUNA é em pé
LINHA é deitado

COLUNA:

|     |
| --- |
|     |
|     |

LINHA:

|     |     |     |
| --- | --- | --- |

Se você apagar uma COLUNA, então você quer EXPANDIR A COLUNA. Mesmo que pareça fazer sentido querer expandir em linha (já que os dois estão deitados), a lógica é EXPANDIR A COLUNA e não ADICIONAR UMA LINHA.
Assim como se for necessário expandir uma LINHA, você vai querer expandir a LINHA. Não confundir.

Se for necessário expandir a COLUNA (expandir para a direita), use [colspan], em seguida coloque o número de células que deseja expandir.

Se for necessário expandir a LINHA (expandir para baixo), use [rowspan]


Ao usar mesclagem de linhas e colunas, podemos ter uma coluna abrangendo varias linhas, ou uma linha envolvendo várias colunas, nesses casos usaremos o [rowgroup] e o [colgroup]. 
Se usarmos somente [row] em uma linha que mescla 3 colunas, o escopo vai considerar apenas a primeira coluna e ignorar as outras 2. Nesses momentos usaremos a versão **group** desse comando.

PS: Nem toda mesclagem vai envolver o uso de um [rowgroup] e [colgroup], as vezes esse titulo mesclado refere-se somente a um valor.

Um exemplo disso seria o total de uma tabela, ela pode mesclar 3 ou mais colunas dependendo do tamanho, mas ela refere-se somente a uma célula, que normalmente fica ao lado.

### COLGROUP

Quando queremos alterar o estilo de uma das colunas, nós normalmente iremos colocar uma classe em cada linha, e então finalmente mudaremos o estilo... Isso funciona quando temos apenas 10 linhas ou menos, mas e no caso de termos 500 linhas? Para isso temos o [colgroup].

O [colgroup] vai ficar dentro da [table], o lugar não importa, mas recomenda-se deixá-la no topo, acima da [caption]. 
Dentro da colgroup podemos usar o seletor [col], cada col vai representar uma coluna.
Dentro de cada [col], podemos indicar o nome dessa classe. Ex:

Temos 4 colunas, então criaremos um [colgroup] com 4 [col];

```colgroup
<colgroup>
	<col class="cNome">
	<col class="cSexo">
	<col class="cIdade">
	<col class="cProf">
</colgroup>
```

Além disso, de forma semelhante a mesclagem de células, podemos mesclar o estilo de duas colunas em uma só classe.
Suponhamos que o cliente agora quer que a coluna "Sexo" e "Idade" tenham o mesmo estilo, com o uso de [span] podemos fazer a seguinte alteração:

```colgroup_mesclado
<colgroup>
	<col class="cNome">
	<col class="cSexoeIdade" span="2">
	<col class="cProf">
</colgroup>
```


### RESPONSIVIDADE EM TABELAS

1 - Envelope toda sua tabela em uma [div], o id pode ser qualquer um, no exemplo será chamado *container*.

2 - Crie um estilo para essa div container, usando a propriedade [overflow: auto]

Essa propriedade fará com que ao invés de uma tabela larga coloque uma barra de rolagem para a página inteira, essa rolagem seja aplicada APENAS a tabela.

Ao usar a propriedade [overflow-x], será aplicada apenas rolagem LATERAL.

Com a propriedade [overflow-y], apenas rolagem VERTICAL.