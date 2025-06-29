
Para isso, podemos usar o parâmetro [background-image] + [linear-gradient]
Pode colocar quantas cores quiser no degradê.

[background-attachment] para manter o degradê fixo na pagina.

A frente das cores, pode-se usar % para definir o quanto que a cor  ocupará da tela.

PS: Use o [height] em escala global  para que o degradê ocupe a  tela inteira.

Podemos fazer isso com **textos** também, com alguns passos:

Primeiro: Crie um degradê

Segundo: use [background-clip: text], isso vai fazer com que tudo que não esteja exatamente atrás do texto seja apagado.  Vale lembrar que alguns navegadores precisam do prefixo **-webkit** [-webkit-background-clip: text].

Terceiro: [webkit-text-fill-color: transparent], esse ai faz com que a cor do degradê afete o texto também, criando o efeito de degradê em texto desejado.