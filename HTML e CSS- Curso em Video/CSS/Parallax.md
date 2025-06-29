
Para criar um efeito "**Parallax**", ou seja, um efeito em que o fundo da tela se mexe em uma velocidade diferente a do conteúdo enquanto "scrolla", é bem simples:


Primeiro, crie um container (uma div) para o conteúdo no qual deseja-se criar o efeito parallax.

Segundo, defina a imagem de fundo e, se quiser, uma altura específica com um [min-height] ou um [max-height].

Terceiro, use o elemento [background-attachment: fixed], ele que será responsável por criar o efeito parallax no site.

Quarto, use os outros elementos para alterar a escala e a centralização da imagem:

[background-position: center] centralizar
[background-size: cover] mudar a escala
[background-repeat: no-repeat] evitar repetições da mesma imagem na caixa