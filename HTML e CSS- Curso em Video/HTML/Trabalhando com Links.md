[a] -> são chamados de âncoras, são usados na criação de hyperlinks.

O principal parâmetro é o "href" (referência a hipertexto), que é onde fica o link.

Outros parâmetros importantes são:

[hreflang=""] -> Indica o principal idioma do site que está sendo referenciado. Isso permite que o navegador e os softwares lidem com a tradução automática por exemplo.


[target=""] -> Altera onde o site indicado vai abrir, o mesmo contém os seguintes valores:

blank -> abre o link em uma nova janela em branco

self -> Abre o link na janela atual (padrão)

top -> desfaz os frames e abre o destino no navegador completo

parent -> similar ao top, referência à janela mãe 


[rel=""] -> (relativo a) -> Indica qual "caminho" o link irá seguir

external: link externo.

next: Próxima página de um link interno.

prev: Página anterior de um link interno.


Como navegar entre links internos em pastas diferentes? 

href="./" -> própria pasta

href="../" -> pasta anterior

Para entrar em pastas é só usar CTRL + SPACE no href.


Como fazer links com download?

Mesma coisa que o link normal, aperta CTRL + SPACE e seleciona o arquivo.

O atributo "type" especifica o tipo do documento

Para saber todos os types: [Types](https://www.iana.org/assignments/media-types/media-types.xhtml)

O "download" especifica que o "target" será baixado quando clicado, e possui a opção de mudar o nome do download.


[title=""] -> Ele aparece quando você passa o mouse em cima do link