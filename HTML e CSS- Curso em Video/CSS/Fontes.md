

# Aplicando fontes

Use o comando [font-family]

Normalmente ao escolher uma fonte, encontra-se pelo menos 3 ou mais delas no mesmo 
comando, isso se chama "Safe-Fonts", semelhante as mídias, nem todo dispositivo vai ter a mesma fonte disponível, então escolhemos pelo menos 3 para se usar, se o site não conseguir encontrar a primeira, ele vai para a próxima, até a última.

Normalmente a última é um comando genérico, fazendo com que o site encontre a fonte padrão do que deseja, por exemplo sans-serif (sem serifa), cursive, serif, monospace, etc...


# Tamanho das fontes


## Medidas absolutas

cm, mm, in (polegada), px, pt (ponto), pc (picas)
pt e pc são de tipografias, não são recomendados para telas.


## Medidas Relativas
*em*, ex, rem, vw, vh, %

*em* - Relativo a altura do M maiúsculo de uma fonte.

16px é geralmente = 1em
*ex* - Relativo a altura do x de uma fonte.

*rem* - Tipo a em, só que está relacionado ao root, a fonte do body.

*vw* - Relacionado a largura da viewport, viewport é o tamanho da tela.

*vh* - Relacionado a altura da viewport.

**PS**: Para a [font-size], a W3C recomenda o uso do **px** e o **em**.

**em** geralmente trabalha com porcentagem da tela, então consegue ser efetivo tanto na tela de um pc, tanto na tela de um celular.


# Peso das fontes

Use o comando [font-weight]

Suas variações são: lighter, normal, bold, bolder

Poucas fontes possuem todas as variações, e mesmo as que possuem algumas das variações não sentem muita diferença.

Outro comando é o [font-style], assim como o anterior, são poucas fontes que realmente possuem essas diferenças de estilos.

Para fazer um sublinhado em seu texto, usa-se o comando [text-decoration], com o parâmetro underline. Também depende da fonte.

# Shorthand font
Ele resume todos os 4 comandos de fonte acima em um único comando.

A ordem da execução é:

*font-style* > *font-weight* > *font-size* > *font-family*

Exemplo:
[font: italic bolder 3em 'work sans', serif]


# Adicionando fontes

Para adicionar fontes no site, use o [Google Fonts](https://fonts.google.com/)

Normalmente usa-se o import, e como ele é uma regra, ele sempre fica dentro do style e fica nas primeiras linhas do Style.


```fonte
@import fonte // Isso é regra

body  // Isso é seletor{
código // aqui são declarações
}
```

**PS: Normalmente temos 3 ou 4 fontes para um site, um para título, um para destaque e outro normal.**


Para fontes externas, temos o [Dafont](dafont.com)

**PS: CUIDADO COM FONTES SEM ACENTO**

# Aplicando fontes externas
Depois de baixar uma fonte, temos que aplica-la no site.
Use o seletor especial @font-face

[font-family:] para nomear essa fonte no arquivo
Use o parâmetro [url=] para adicionar a fonte

Use o CTRL + SPACE para encontrar a fonte nos arquivos
Se estiver em outra página do site, pode usar o ../ para voltar nos arquivos.

Tipos de format()
- opentype (otf)
- truetype (ttf)
- embedded-opentype
- truetype-aat (Apple Advanced Typography)
- svg


## Pegando fontes que achou em sites por aí

Usaremos o Fonts Ninja, extensão do google.

Use a fonte e passe o mouse por cima da fonte que achou interessante
A extensão já mostra o nome da fonte, tamanho, espaçamento, cor, etc.


## Pegando fontes em Imagens

Os sites que podem ser usados são 3:

[Font Finder](https://www.whatfontis.com/)
[Squirrel font](https://www.fontsquirrel.com/)
[MyFonts](https://www.myfonts.com)