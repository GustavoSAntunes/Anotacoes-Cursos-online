#css #imagens 

Use `divs` para agrupar uma ou mais imagens, imagens com texto, imagens com outros elementos, etc.
Altere o `width` e o `height`, ao usarmos div podemos colocar como 100% para fazer com que ele ocupe apenas a caixa.
Podemos ajustar o tamanho mínimo e máximo com `min-height` e `max-height` (ou `min-width` e `max-width` para alterar a largura).

`aspect-ratio` para mudar a proporção de uma imagem. (Um exemplo é a proporção 16/9 para imagens com uma largura maior).
Podemos também usar `fit-content` se necessário.

`object-fit` altera como o conteúdo de um elemento se ajusta em uma caixa, sendo suas propriedades:
- `fill` -> O conteúdo se foca apenas em preencher a caixa inteira;
- `contain` -> Foca em ajustar a imagem para que ela toda seja visível, mesmo que deixe áreas vazias (bordas da cor do fundo) em volta da imagem ou da caixa dela.
- `cover` -> Foca em ajustar a imagem para cobrir a caixa toda, ela mantém a proporção da imagem, mas partes dela podem não ser visíveis.
- `scale-down` -> Se o container for especificado, resulta em um tamanho menor que ele.