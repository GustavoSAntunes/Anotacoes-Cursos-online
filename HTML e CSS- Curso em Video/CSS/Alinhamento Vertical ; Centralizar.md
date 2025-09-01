

Para fazer o alinhamento vertical, primeiramente precisaremos da presença de duas divs: Uma "container" e outra com o "conteudo".

Para alinhar um elemento horizontalmente, basta usar o [margin: auto] e já resolve, mas para alinhar verticalmente é um pouco mais complicado.

Uma das formas é usando o display, com apenas 4 linhas:


```vertical
.container {
	display: flex;
	justify-content: center;
	align-items: center;
	height: 100vh;
}
 ```


``display: flex;``  Possui diversas funções (procurem pela documentação), uma delas é habilitar o manejamento do conteúdo 

``justify-content: center;``  Alinhamento horizontal, ou seja, dispensa margin: auto; 

``align-items: center;``  Alinhamento vertical

`height: 100vh;` Ocupa toda a altura da tela

**PS:** Essas propriedades sempre são colocadas no elemento-pai (container), não se esqueçam desse importante detalhe.

As vezes centralizar com o flexbox pode dar problemas se o site não estiver configurado, caso esteja dificil de centralizar algo podemos mudar as margens universais e as alturas do site:

``` padrao
* {
	margin: 0;
	padding: 0;
}

html, body {
	height: 100vh;
	width: 100vw;
	background-color: black;
}
```

Podemos também usar os comandos: [top], [right], [left] e [top] para maior precisão na centralização

Outra opção também é usar o display grid:
```grid
display: grid;
place-items: center;
height: 100vh;
```

E a ultima opção, é usando o translate do [absolute]:

Primeiro, o container precisa ter um [position] relativo, mas por padrão do html, todo bloco já vem em posição relativa, então só mude caso você tenha mudado os padrões universais ou algo do tipo.


Segundo, o conteúdo precisa ter um [position] absoluto. Ou seja, o que tá de fora contendo o conteúdo (container) fica em [relative], e tudo que fica dentro desse container (conteudo) fica em [absolute].

Agora podemos usar alguns elementos como [left] e [top] da div conteudo.

Por exemplo, tanto o [left] quanto o [top] é a distância entre os respectivos nomes (left começa da esquerda e top começa do topo) até o **CANTO SUPERIOR ESQUERDO DO BLOCO**.
![[Pasted image 20250226130903.png]]
Ao tentarmos centralizar usando [top] e [left] nos 50% nós conseguimos "centralizar" o conteúdo no container, porém, por padrão,  **a centralização considera o canto superior esquerdo ao invés do centro da caixa**.

Podemos mudar isso usando o comando [transform], fazendo com que o alvo do conteudo fique junto com o alvo do container e movendo o target usando pixels em porcentagem (-50% -50%).