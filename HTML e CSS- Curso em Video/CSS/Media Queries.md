
Media Queries são as várias formas que um site pode ser apresentado dependendo do seu estado: Computador, Tablet, Smartphone, para impressão, etc.

**Media queries** são a mesma coisa que **Media types** junto com **Media features**.

Media types são os tipos de mídia
Media features são as características da mídia.
[media=screen] é um tipo de mídia, as diferentes telas que serão configuradas (pc, celular, tablet) são as características da mídia.

## Media types

As 3 types mais usadas são:
[screen] -> tela
[print] -> impressão
[all] -> genérico, tudo

Para criarmos uma **media type**, temos que criar um arquivo css para essa media query:

```chamadas-queries
<link rel="stylesheet" href="estilos/style.css" media="screen">
<link rel="stylesheet" href="impressora/style.css" media="print">
```

Nesse exemplo, estamos fazendo uma media query para uma tela (**screen**) e outra para impressão (**print**). 

Se quisermos criar um estilo para todas, é só mudar o [media] para [media="all"].
Ele é útil quando temos configurações que são iguais para ambas [screen] e [print].

No media query de [print], podemos alterar o estilo de forma que ao imprimir, as alterações necessárias sejam feitas. 

Alguns exemplos de mudanças para **impressão** são:
- remover os menus usando o seletor [menu {}] e usando o elemento [display: none].
- Inserir, ao final da página, a origem desse artigo / site / etc.
``` creditos
 article::after {

    content: "Esse artigo foi impresso através do site www.cursoemvideo.com";

}
```

- Manter a [width] (largura) no 100%. Em um site de notícias por exemplo, normalmente o desenvolvedor não irá querer deixar a largura 100%, pois dependendo do tamanho da tela isso irá cansar o cliente, mas isso não ocorre no papel, então podemos deixar no 100%.


## Media features

São as características de uma [media].

O caso mais importante são as features de **tela**.
Celular, Tablet, PC, etc.

Um exemplo disso:

```media-features
<link rel="stylesheet" href="estilos/style.css" media="all">

    <link rel="stylesheet" href="estilos/retrato.css" media="screen and (orientation: portrait)">

    <link rel="stylesheet" href="estilos/paisagem.css" media="screen and (orientation: landscape)">
```

O **media type** é o primeiro, e é escrito normalmente após o "=" e as aspas.
Porém, após o type podemos usar as features, primeiro temos que colocar o "and" para indicar que estamos adicionando características a essa mídia.
Vale lembrar que, caso for usar mais de uma feature em uma única media, cada uma terá seu próprio parênteses.

E então o **media feature** é escrito entre parênteses, e no exemplo acima, estamos fazendo **telas**, no qual suas características são:
orientation é a forma que a tela se encontra.
Os computadores escolhem a orientação baseada na resolução da tela.

**orientation: portrait** -> Se a **altura** for maior que a largura, ele está em portrait (retrato)
**orientation: landscape** -> Se a **largura** for maior que a altura, ele está em landscape (paisagem)

Caso o projeto não seja muito grande, podemos juntar todas as CSS em uma só, ex:

```
/* Declarações retrato */

@media screen and (orientation: portrait) {

	body {

		background-image: url(../imagens/cev-portrait.jpg);

		background-position: bottom center;

	}

}



/* Declarações paisagens */

@media screen and (orientation: landscape) {

	body {

		background-image: url(../imagens/cev-landscape.jpg);

		background-position: bottom left;

	}

}
```

O and separa cada uma das características do [media]

É possível colocar todas as queries em um único arquivo dessa forma, isso vale tanto para arquivos externos (link: style) tanto internos (dentro do style).
Porém vale lembrar que é somente recomendável para projetos pequenos, e mesmo em projetos pequenos as coisas podem ficar confusas.

### Paisagem (landscape) e Retrato (portrait)

Normalmente são feitas apenas pequenas mudanças, tenha a certeza que a responsividade foi feita corretamente.

em background-images principalmente, é necessário verificar algum possível erro ou problema na tela. normalmente o [contain] funciona melhor para retrato (tela em pé) e o [cover] fica melhor em portrait (tela deitada).


## Mobile First

Normalmente, ao fazer sites, fazemos ele bonitinho pelo computador, ajustando a posição das coisas, animações, cores, imagens, etc. Depois de todo o trabalho, para ajustar para os celulares, nós vamos removendo coisas e ajustando a posição das coisas. 

Ele é muito aceito e majoritariamente usado em geral. Seu uso é fortemente recomendado.

O **Mobile First** consiste em fazer o inverso: Construir o site inteiro primeiro para celulares, e depois ajustaremos as outras queries adicionando elementos, ao invés de remove-los. Algumas vantagens de Mobile First são:
- Sites Mobile First são **favorecidos pelo algoritmo de buscas** do google e outras ferramentas de busca. Fica mais fácil de ficar no topo do resultado de buscas.
- **Melhoria na experiência do usuário**. Menos peso para dispositivos mais lentos.
- **Aumento de credibilidade**. O seu site soa mais "profissional" ao rodar com performance em um celular e sem problemas.
- **Performance**, pois muita gente acessa celular em áreas com internet limitada ou mesmo com infraestruturas limitadas.



### Typical Device Breakpoints

São os números que definem qual resolução é de uma tv, de um celular, de um tablet, etc...

Os padrões são voláteis, então o ideal é sempre pesquisar o padrão mais recente.

```celular-ex
@media screen and (min-width: 768px) and (max-width: 992px) {

}
```

Vale lembrar que não é possível usar [background-image] em queries de impressão ([print]).

Entretanto, ainda é possível usar outros recursos como font-family, font-size, shadow, border, etc. Outro recurso interessante para impressão é o pseudo-elemento [::after]
```
main::after {
        content: "Essa impressão foi feita através do site www.cursoemvideo.com";
}
```


## Menu Hamburguer

Usaremos o site [Google Fonts](https://fonts.google.com), selecione a opção de "Icons" e procure pelo ícone chamado "**Menu**".
Ao clicar nela teremos duas opções: Uma de usar diretamente do servidor do google e a segunda opção é baixar e hostear pelo seu próprio site. Usaremos a primeira opção.

Exemplo de ícone hosteado pelo google:
```
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0&icon_names=menu" />
```

Exemplo de ícone sendo usado no site:
```
<span class="material-symbols-outlined">menu</span>
```

Para editar esse ícone, dê um `id` para o mesmo, ex:

```
<span id="burguer" class="material-symbols-outlined" onclick="clickMenu()">menu</span>
```

Função de `Javascript` para a criação de um menu hamburguer:

```
function clickMenu() {

	var itens = document.getElementById("itens");

	if (itens.style.display == 'block') {

		itens.style.display = "none";

	} else {

		itens.style.display = 'block';

	}

}
```
PS: `itens` é o nome do id que se refere ao MENU, altere esta parte pelo nome do seu menu e tenha certeza de que o menu foi feito corretamente (dentro de um `nav` em uma lista `ul`) e tudo irá funcionar.

Para esconder o menu, podemos usar media query:

```
@media screen and (min-width: 768px) {

	span#burguer {
	
		display: none;
	
	}
	
	
	
	nav#itens {
	
		display: block;
	
	}
	
	
	
	#itens > ul > li {
	
		display: inline-block;
	
	}

}
```

Ao usarmos esse menu, haverá um pequeno bug: Ao abrir e minimizar o hamburguer, e depois mudar o tamanho da tela para 768 pixels ou mais, o `nav` simplesmente desaparece. Para arrumar isso, criaremos uma função que será ativada ao mudar o tamanho do navegador:

Adicione o `onresize` no `body` e coloque o nome da função, nesse caso será `mudouTamanho()`
```
<body onresize="mudouTamanho()">
```

Script
```
function mudouTamanho() {

	if (window.innerWidth >= 768) {

		itens.style.display = 'block'

	} else {

		itens.style.display = "none"

	}

}
```

