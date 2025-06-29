

# Estilo CSS Inline

É basicamente fazer um estilo para cada linha específica de um html.

**ex:** <.h1 style color: darkred;> titulo <./h1>

Ele é útil caso seja necessário alterar uma linha em específico, mas há maneiras melhores de organizar os estilos de um site.


# Estilo CSS Interno
O estilo é colocado dentro do head

Normalmente em baixo do title, mas pode ser em qualquer lugar.

Use uma tag style

e então, coloque a tag da parte do texto que deseja mudar, ex:

```xml
<style>
	body{ (isto é chamado de seletor)
		background-color: blue;
	}
	h1{
		color: darkred;
	}
</style>
```


# Estilo CSS Externo
## Como fazer?

O estilo é colocado em outro ARQUIVO

Dentro do index, abaixo do title, use a tag [link] com CSS

Segure CTRL e clique em "style.css"

Agora é só colocar todos os estilos que desejar dentro desse arquivo.

## Regras

Tudo que começar com @ é uma REGRA.

A primeira regra importante que terá em todos os arquivos será a de permitir acentuações
@charset "UTF-8";

## Observações

**É POSSÍVEL UTILIZAR MAIS DE UM LINK EM UMA MESMA PÁGINA**

É possível usar os 3 estilos de uma vez na mesma página

**EVITE** AO MÁXIMO usar o estilo inline, use somente para casos muito específicos e pontuais.

Use o estilo interno somente para pequenos estilos, se o número de páginas crescer já é hora de usar o externo.

Use o externo principalmente se o site tiver mais de uma página, tendo em mente que você pode usar vários links em uma página tranquilamente.