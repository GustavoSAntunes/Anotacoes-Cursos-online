**Pseudoclasses** são os *estados* de um *elemento*. Basicamente eles são ativados após uma certa ação ou condição for cumprida, dependendo da pseudoclasse usada.
Alguns exemplos de pseudoclasses:

[Hover] -> Ativa ao passar o mouse em cima do mesmo.

[Visited] -> Usado em links, ativa quando o link ja foi visitado.

[Active] -> Ativa ao ser clicado.

Ex:
```pseudoclass
a:hover{
	font-size: 3em;
}
```

[nth-child] -> Esse pseudo-elemento não precisa de uma ação, ele basicamente escolhe os vários elementos dentro de um grupo baseado em uma equação ou numero, muito útil em tabelas por exemplo. Ele possui 2 elementos chave: 

[odd] -> Representa os valores em posição ímpar

[even] -> Representa os valores em posição par.

Ex:

```nth-child
tbody > tr:nth-child(even) {

	background-color: lightgray;

}
```



## Pseudoelementos

**Pseudoelementos** são estilos que podem ser postos entre conteúdos, criando meio que um padrão para aquela tag.

```pseudoelement
a::before{
	content: '\1F517'
}
a::after {
	content: '<'
}
```

Isso faz com que essas setas sejam posicionadas, respectivamente, **ANTES** de um link e **DEPOIS** de um link. Elas podem parecer algo do html (conteúdo) mas ele é usado mais para decorar o conteúdo do que adicionar conteúdo em sí.