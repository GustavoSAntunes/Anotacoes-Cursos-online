
Para fazer um site, é importante seguir um procedimento para não confundir as coisas:


# Primeiro passo: Planejar a estrutura para o site

Para layouts, podemos usar o [Figma](https://www.figma.com/pt-br/) como opção viável.

Escolher a paleta de cores usando o [Adobe Color](https://color.adobe.com)

Escolher as fontes usando o [Google Fonts](https://fonts.google.com/)

Crie pastas para: **Fontes**, **imagens** e **estilo**.

Coloque suas cores e fontes em *variáveis*.

Use o [:root] para isso ([[Variáveis]])

use uma tag universal [*]* para fazer com que as margens e os paddings fiquem zerados, para evitar problemas principalmente com o header e barras estranhas entre o nav e o main.

Use o @font-face com [font-family] e [url] para adicionar fontes externas.




# Segundo passo: Coloque o conteúdo no site

As tags são organizadas em:
	O [header] é o cabeçalho, normalmente lá ficam o Banner, logo, formulário de pesquisa, ícones e menu de navegação.
	-
	[nav] Agrupa o conjunto de links de navegação do site.
	-
	[main] É onde fica o conjunto principal da página.
	-
	[aside] Ficam informações relacionadas ao link principal.
	-
	[footer] É o rodapé do site, ele pode conter informações de autoria, direitos autorais, contato, mapa do site, links e documentos relacionados.
	-
	PS: Não faz merda, nav fica fora do header.
	-
	É possível ter mais de um [h1] em um site, por exemplo o título principal de um site no header e o título principal da matéria no main, ambos são aptos a usar o h1.

Adicione o ícone e todo o conteúdo que você quer naquela página, colocando-os em [articles], com [p] e [h1, 2, 3, etc..].




# Terceiro passo: Organizar o site


Além dos parágrafos e títulos, coloque as mídias: imagens [img src=""] e vídeos (incorporar do youtube)

Organize os itens que estarão em tags especiais (listas [ol, ul]e abreviações [abbr] por exemplo)

Adicione os links [a], externos ou internos

Formatar o texto usando [b], [strong], etc... () [[Tags#Formatação de Texto]]




# Quarto passo: As margens

Caso as margens estejam incomodando (provavelmente estão), podemos mudar as definições globais de todas as caixas para remover suas margens, removendo esses espaços estranhos no site.

Para isso, usa-se o seletor global [*]*, ela seleciona todos os elementos do arquivo. Agora, podemos mudar a *margin* e o *padding* para 0.




# Quinto passo: Responsividade


Agora temos que avaliar o tamanho mínimo e o tamanho máximo ideal para o site, podemos fazer isso usando a ferramenta inspecionar. Ex:

Se uma tela for menor que [400px], ele irá parar de apertar o conteúdo.
Se for maior que [800px], ele irá manter o conteúdo em 800 e a tela aumentar o restante.

Podemos usar a extensão [windows-resizer] para alterar entre vários dispositivos afim de testar a responsividade.

Para as imagens não ficarem tão grandes no site, podemos usar o [max-width] em 100% e o [min-width] em 10%, assim a imagem também se adapta dependendo da tela.

Algumas imagens e principalmente videos terão problemas para se encaixar ao meio, transforme suas caixas em caixas flex usando [display: flex] e então adicione a margem auto.

Para textos responsivos use o [text-size] como xvh.

[[Como criar Responsividade]]




**Sexto passo: O header**

Podemos usar o [min-height] e o [max-height] para definirmos a altura mínima e máxima do cabeçalho.

Use o [padding-top] (ou margin, o que der certo) no header para aumentar o espaço entre a parte de cima do cabeçalho e o h1.

Use o [max-width] para conseguir controlar melhor como o texto irá aparecer (quanto espaço ele pode ocupar antes de pular a linha, por exemplo).

Use os [padding-left] e [padding-right] para definir melhor como o bloco ocupará o espaço em telas menores.

Use o [text-shadow] para dar um destaque maior para o título ou qualquer outra coisa.

Use o [background-image: linear gradient] para criar um degradê.

Use [background-clip: text] e [-webkit-text-fill-color: transparent] para criar títulos com degradê.

Podemos usar o [box-shadow] embaixo do [nav] para criar uma sombrinha embaixo dele.

Use o [a:hover] para criar um estilo de um botão para os menus, faça o padding do link ser o mesmo do nav para evitar problemas na hora de mudar o [background-color].

Veja outras animações no [[Animação para menus]]




**Sétimo passo: Ajeitar o conteúdo**

Agora organize os parágrafos e o espaçamento entre textos e títulos.

use [margin] -> para separar melhor os blocos
[text-align justify] -> para textos
[text-indent] -> para indentação em parágrafos
[text-weight] -> para colocar destaque em um texto
[padding] -> para engordar termos que estão destacados e possuem um background color
[text-decoration] -> para colocar algo a mais nos textos




**Oitavo passo: Ajeitar o Rodapé e o aside**

Podemos ajeitar o footer sem colocar muitos detalhes, ele não precisa ser extravagante.


Para o aside, podemos mudar sua [background-color] e sua [padding] e [border-radius].

Se houver listas, podemos usar alguns comandos:

[list-style-position] -> Mudar a posição da lista, normalmente ela fica pra fora então usamos esse comando para ela ficar dentro, se ainda assim ficar meio pra fora aumente o padding do aside.

[columns] -> Aumente a quantidade de colunas que uma lista irá ocupar no espaço, vale notar que ao colocar mais de 2, normalmente cria-se problemas de Responsividade.

[list-style-type] -> Podemos mudar a bolinha do item de uma [ul] por outro símbolo, como emojis.
Para colocar emojis, procure o código dela na [Emojipedia](https://emojipedia.org) e, entre aspas simples, coloque primeiro uma barra invertida (\) e coloque o código.

Se o emoji ficar muito perto do item da lista, pode-se usar o [00A0] para colocar um espaço entre a decoração e o texto. ex:

list-style-type:'\2714\00A0\00A0';

**PS: O uso de list-style-type não é compatível em todos os navegadores.**

Se estiver com dificuldades de encaixar uma caixa de um h3 no topo do aside por exemplo, podemos usar **margens negativas**.

Se um aside tiver um padding de 10px e quisermos que um h1 se encaixe no topo dele, podemos colocar margens negativas no topo dessa caixa, fazendo com que ela ocupe o topo, como desejado.

::before e ::after são pseudo-elementos se quiser decorar algo como um link, interessante para links externos