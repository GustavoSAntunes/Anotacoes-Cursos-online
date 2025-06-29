
São as várias tags usadas para dar algum valor especial para um texto:

[mark] -> Marcar uma parte do texto, como se fosse um marca texto.

[small] -> Letras miúdas de um contrato.

[del] -> Marca um texto como excluído, ele pode ser lido mas não é mais considerado.

[ins] -> Um texto com ênfase e indica que ele foi adicionado depois.

[sup] -> "subir" o texto, ex: x²

[sub] -> "descer" o texto, um exemplo seria elementos da tabela periódica, como o H<sub>2</sub>O

[code] -> Fonte "mono-espaçada", ela é ótima para ler códigos.

[pre] -> Considera as tabulações e quebras de linha de um texto, muito bom ao combinar com a tag [code].
ex:
	<pre>

			<code>
		num = int(input("Digite um número"))
	
		if num % 2 == 0:
	
			print(f'O número {num} é 'PAR')
	
		else:
	
			print(f'O número {num} é IMPAR')
		print('fim do programa')

		</code>

	</pre>


[q] -> semântica usadas para citações SIMPLES, de uma única linha.

[blockquote cite=""] -> É usado para citações com quebra de linha, além do comando "cite", que permite o uso de um link para o livro ou algo do tipo que direciona ao que estamos falando, mesmo que não mude nada visualmente, a parte interna do site vai saber quem está sendo referenciado.

[abbr] title="" -> Abreviações, em title, coloque o significado de sua abreviação, ex: HTML (HyperText Markup Language).

[bdo] -> Inversão de texto.