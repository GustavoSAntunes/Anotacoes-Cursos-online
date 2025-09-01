
`width` -> O quanto de *largura* o conteúdo ocupará.
`height` -> O quanto de *altura* o conteúdo ocupará.
`padding` -> Engordar um pouco o conteúdo, para não ficar estranho.
`margin` -> Deixe no auto para que o conteúdo sempre fique no meio
`top`, `bottom`, `right`, `left` -> Muda, com bastante precisão, a posição de uma caixa (talvez só funcione com `position: relative` (?))

`border-radius` -> Serve para alterar as pontas do conteúdo, deixa redondo.

`box-shadow` -> Altera as sombras, os parâmetros são, respectivamente: O quanto a sombra vai andar para o lado, quanto vai andar para baixo, o quanto ela se espalha e o último é a transparência, cor. PS: QUANDO FOR COLOCAR O PARÂMETRO NÃO PONHA VÍRGULA

`text-indent` -> Indentação para textos.
`text-shadow` -> Sombras para textos.
`text-align` -> Alinhamento de textos.
`line-height` -> A altura criada entre linhas.

`border` -> Cria bordas no conteúdo, possui 3 parâmetros respectivamente: Tamanho, tipo e cor.

`display` -> Como o conteúdo será mostrado. Ex: `Inline` ou `Inline-block` (tudo na mesma linha)
`content` -> Usado para adicionar conteúdo no style.
`font-variants` -> Bom para títulos, pois tem o mesmo destaque de um texto maiúsculo, mas sem a sensação de "escrever gritando".

`nth-child`-> Esse pseudo-elemento não precisa de uma ação, ele basicamente escolhe os vários elementos dentro de um grupo baseado em uma equação ou numero, muito útil em tabelas por exemplo. Ele possui 2 elementos chave: 

`odd` -> Representa os valores em posição ímpar

`even` -> Representa os valores em posição par

Centralizar itens na tela:
``` center
display: flex;  

    justify-content: center;

    align-items: center;
```

Mudar a ordenação de linha para colunas (úteis para botões que ficam de um lado da página)
``` column
display:  flex;

flex-direction:  column;
```

Para esconder a barra de scroll
```no-scroll
::-webkit-scrollbar {

	height: 0;

	width: 0;

}
```

`currentcolor` é a cor atual, e pode ser usada em outras propriedades.
``` currentcolor
foo {
  color: red;
  bar {
    box-shadow: 2px 2px currentcolor;
  }
}
```

Função `clamp()`: O primeiro valor é o mínimo, o segundo é o de preferência ("ideal") e o terceiro é o valor máximo.
``` clamp()
font-size: clamp(2rem, 3vw, 3rem)
```

## Ajustando o texto
Só usar o Style do CSS
	Use `margin` para ajustar o espaçamento entre o texto e os outros conteúdos
	`Text-align` -> Alinhar textos.
	`Text-indent` -> Espaço de parágrafo, indentação.
	`text-align justify` -> para deixar o texto justificado.
	`line-height` -> Altera a **altura** entre **linhas**.