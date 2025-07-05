
**Iframe** (inline frame, ou "quadros em linhas"), o [iframe] permite que você carregue outra página html dentro de sua própria página, é como se fosse uma nova aba só que dentro de seu site. 

Você pode, por exemplo, carregar uma localização do google maps dentro de seu site usando esse quadro.

Ele é **inline**, logo, ele vai se posicionar na mesma linha em que foi posto.

A primeira propriedade é a de [frameborder], por padrão ela é 0, ou seja, não adiciona borda. Se colocar o valor como 1, adiciona uma borda 3d em volta do iframe.

PS: É possível editar o estilo dessa borda.

Ele possui a propriedade [scrolling], ela altera as opções de ROLAGEM da página.

[auto] -> O padrão, se tiver muito grande vai adicionar a barra.

[yes] -> Sendo grande ou não, vai adicionar a barra de rolagem.

[no] -> Não adiciona o a barra de rolagem. (vale lembrar que, dependendo do navegador, pode não funcionar).

Alguns exemplos de usos de iframe incluem:

- mapas do google e do waze
- videos
- google documens (tabela, powerpoint, word, etc.)

PS: Vale lembrar que carregar um outro site dentro do seu vai diminuir a performance, é possível por vários sites mas tome cuidado.

PS 2: Tome MUITO cuidado com o uso de iframes em relação a **SEGURANÇA**, ao permitir sites de terceiros em seu próprio site, você pode permitir também todo tipo de riscos que afeta não só o site indexado, mas ao seu próprio!


### Indexando sites locais

Também há como colocar seus próprios sites locais dentro do iframe:

``` site_local
<iframe src="pag001.html" frameborder="0" height="500" width="500"></iframe>
```
De forma similar ao de escolher uma imagem, dentro do [src=""] podemos apertar *CTRL + Space* para escolher entre as páginas disponiveis.

Ressaltando, podemos usar o [../] para navegar entre arquivos, ele serve para voltar um arquivo.

```voltando
iframe src="../../../Módulo 3/ex023/tabela006.html"
```





### Compatibilidade

Podemos inserir algo entre a tag [iframe] no caso dela não funcionar, exemplo:

```compatibilidade
    <p>

        Acessando o site do

  

        <!-- Tamanho padrão 300x150 -->

        <iframe src="https://www.cursoemvideo.com" frameborder="1">

            <a href="http://cursoemvideo.com" target="_blank" rel="noopener noreferrer">Curso em Video</a>

        </iframe>

        para aprender a programar.

    </p>
```

Desse jeito, caso o comando iframe não funcione (algo mais comum em celulares), o que o cliente vai ver é o que estiver dentro dessa tag iframe.

### Tabelas: Overflow ou iframes?

Ambas opções são interessantes:

Se a sua tabela for relacionada com o restante do site, e seja necessário uma associação entre esses conteúdos, é melhor usar o [overflow], pois com o iframe os mecanismos de buscas não conseguem fazer o relacionamento corretamente.

Uma das vantagens de se usar o [iframe] é que as configurações de estilo são **separadas do arquivo primário**, já que com iframe toda essa configuração está posta em outro site.

Se a **tabela for importante** para essa página, use o [overflow].

Se for inserido outros conteúdos que **não são relacionados** a essa tabela, a opção de usar [iframes] pode ser considerada.

### Estilo

Dentro das tags de iframe, podemos alterar sua [height] e [width] (altura e largura), mas também podemos alterar isso no CSS.

Caso seja posto 2 valores diferentes no estilo e na tag, quem tem mais prioridade é o **CSS**. Se não houver alteração em nenhum dos dois, ela fica no tamanho padrão de 300x150.


### Navegação

É possível **navegar entre múltiplos links com um único iframe**. Para isso, temos que:

1 - Selecionar o iframe desejado, é nele que vai mostrar o resultado de abrir os links

2 - Colocar os links que deseja que seja mostrado no iframe em algum lugar do site

3 - no iframe escolhido, use a propriedade [name], escolha um nome para ele.

4 - Nos links que irão abrir a página nessa "tela", altere o seu [target] -> [target="nome do iframe"]

Dessa forma, ao clicar nos links com o target no iframe, ao invés dele abrir na mesma página ou em uma nova aba em branco, ele irá abrir no iframe.

Nota-se que se nenhum link for clicado, o iframe ficará vazio. Pare resolver isso basta colocar algum arquivo no [src] desse iframe.


### srcdoc

Podemos também editar o que estiver dentro do iframe quando não tiver escrito nada, fazemos isso substituindo o [src] por [srcdoc], desse jeito, dentro das aspas, podemos escrever um código em html para preencher a tela inicial do **iframe interativo.**

Entretanto, ele é simples demais devido a limitação de somente usar html simples, então o recomendado é criar um arquivo separado e colocá-lo dentro da página primária.


### Desvantagens do iframe

- Dificuldade de acesso - O bot do google pode ter problemas para indexar um iframe, tendo dificuldades de acesso ao conteúdo. Se o conteúdo for muito importante para a indexação de seu site, evite o iframe nesse caso.

- Baixa acessibilidade - Pessoas cegas que usam leitores de tela podem ter dificuldades em acessar páginas com os iframes.

- Se o site de terceiro não for responsivo, ele possivelmente ficará todo quebrado em seu iframe.

- Segurança - Cuidado com quais sites usar no iframe dentro do teu site. Se o site usado no iframe estiver capturando informações de usuário, o mesmo sistema de captura será aplicado em seu site também. Isso deixa o seu site aberto a alguns ataques como **cross-site scripting** e **ataques xss**.


### Segurança

Para lidar principalmente com os problemas de segurança de um iframe, podemos usar a propriedade [sandbox=""].

Esse atributo controla as restrições de um iframe. Se o valor estiver vazio, todas as restrições serão aplicadas, e a palavra-chave que for usada dentro desse valor será a permissão que você vai dar para o site de terceiro em relação ao seu próprio. Alguns deles são:

[sandbox="allow-same-origin"] - Permite com que **páginas de nosso próprio servidor** (conteúdo local) funcione no iframe.

[sandbox="allow-forms"] - Faz com que a exceção seja dada exclusivamente a **formulários**, tanto os de página local, tanto o de terceiros.

[sandbox="allow-scripts] - Essa exceção faz com que seja permitido **scripts**, se você quiser que o iframe permita **formulários, é preciso também permitir o uso de scripts**, já que o html5 executa scripts ao usar formulários. 
Vale lembrar que permitir o uso de scripts para sites de terceiros é algo arriscado, então cuidado.

Além disso, é possível colocar todos eles de uma vez, é só colocar o valor e apertar espaço para o próximo. Ex:

``` sandbox
sandbox="allow-same-origin allow-forms allow-scripts"
```


Também temos o elemento [referrerpolicy], resumidamente, os sites sempre conseguem ver onde o visitante estava quando decidiu ir para o seu site com os **rastros de navegação**, esses são chamados de *Referer Header*. Ao usarmos a configuração [referrerpoliciy="no-referrer"], faz com que o iframe NÃO colete nenhum tipo de informação do usuário utilizando o iframe.