[ol] -> Listas ordenadas.
	[li] para identificar cada item da lista.
	Parâmetro type: Mudar o tipo de contagem. (1, A, a, I, i)
	Parâmetro start: Mudar onde que começa a contagem. 
	**PS: NÃO IMPORTA O TIPO, O START SEMPRE É NUMÉRICO.**
	-
	**PS 2**: Se for necessário envelopar múltiplos itens (li), envelope todos eles de uma vez, escreva o [li] e depois use o *[*] (fica assim li*).
	-
	Ex: <.ol type="A" start="3">

[ul] -> Listas não ordenadas, ou seja, não são numeradas.
	[type=""] -> Mudar a forma da lista (circle, disc, square)


[list-style-position] -> Mudar a posição da lista, normalmente ela fica pra fora então usamos esse comando para ela ficar dentro, se ainda assim ficar meio pra fora aumente o padding do aside.

[columns] -> Aumente a quantidade de colunas que uma lista irá ocupar no espaço, vale notar que ao colocar mais de 2, normalmente cria-se problemas de Responsividade.

[list-style-type] -> Podemos mudar a bolinha do item de uma [ul] por outro símbolo, como emojis.
Para colocar emojis, procure o código dela na [Emojipedia](https://emojipedia.org) e, entre aspas simples, coloque primeiro uma barra invertida (\) e coloque o código.

Se quiser editar mais de um comando ao mesmo tempo, você pode segurar ALT e clicar onde deseja fazer as mudanças.


[dl] -> Lista de Definições. É como se fosse um dicionário:
	Primeiro você coloca o termo: <.dt> (Definition Term)
	E depois a definição de tal termo: <.dd> (Definition Description)