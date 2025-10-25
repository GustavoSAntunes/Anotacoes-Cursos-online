
Todo formulário começa com a tag [form].

Para fazer aquela "caixinha" para preencher os dados, podemos usar o [input: text].
Todo input possui um **nome** e um **id**.

Para enviar os dados, podemos criar um [input: submit].

Para desligar o preenchimento automático de dados, vá até o [form] e coloque o elemento [autocomplete:="off"].

Com isso, já podemos fazer um formulário básico:

```formulario
<form action="">

	<p>Nome: <input type="text" name="nome" id="nome"></p>

	<p>Sobrenome: <input type="text" name="Sobrenome" id="sobrenome"></p>

	<p><input type="submit" value="Enviar"></p>

</form>
```

Porém isso ainda é bem incompleto, a primeira coisa que falta é: **Para onde vai os dados?**
A segunda coisa, bem importante, é que a palavra "**Nome**" não possui ligação com a **caixa de inserção de dados**. Essa ligação é bem importante para os mecanismos de buscas do google ou o próprio navegador saiba que essas duas coisas estão **relacionadas**.

Os dados do formulário são mandados para outra linguagem: Java, Java servidor, php, etc...

O [action=""] do form significa que, ao apertar o botão de submit, ele irá executar algo.

Para conectar uma caixa de input com o texto logo atrás dela, usaremos as **[labels]** (ou etiquetas).

### Diferença entre name e id

**name:** Para linguagens HTML e php, é preciso **que todo [input] (objeto de entrada) tenha um [name] (nome)**

**id:** Para linguagens como JavaScript, o **[id]** é mais utilizado.

PS: No [label], sempre coloque o [id] do [input] no [for].

Para **ids**, toda vez que um deles for definido, colocaremos um **i** no começo. Faremos isso principalmente para diferenciar o nome e o id. Ex:

```exemplo
<p><label for="inome">Nome:</label> 
	<input type="text" name="nome" id="inome"></p>
```

### GET e POST

dentro da tag [form] podemos usar o atributo [method], com ele temos:

GET -> Padrão, ao preencher os dados do formulário, esses dados irão aparecer lá em cima na URL.
Quando usar? -> Quando os dados não forem sensíveis: Nome, peso, etc...
**PS**: Formulários GET são compartilháveis (via URLs) e possuem um limite de 3 mil bytes.

POST -> Faz os dados não aparecem na URL.
Quando usar? -> Envio de arquivos e dados sensíveis: CPF, endereço, senha, etc...

### Caixas de texto e Senhas

Para senhas, use o [input:password]
Para limpar o formulário, temos [input:reset]

Para inserção de números, use [input:number]

Para inserção de mês e ano, use [input:month]
Para inserção de dia, mês e ano, use [input:date]
Para definir horário, use [input:time]

[input:email] para email.
[input:tel] para telefones (estudar RegEx - expressões regulares).

#### Alguns atributos do input
Para que seja obrigatório o preenchimento de uma das caixas, use o atributo [required] dentro da [input] desejada.

Se quisermos que a caixa tenha um requisito mínimo e máximo de caracteres, podemos usar, respectivamente, os atributos [minlength] e [maxlength].
[max] e [min] é a versão **numérica** dos requisitos.

Ao usar números com o input number, por padrão só será aceito números inteiros, podemos mudar isso com o atributo [step], e a quantidade. No caso de uma média por exemplo, [0.5] iria bastar na maioria dos casos. Entretanto, caso seja necessário usar do 0.1 até o 1, usa-se [0.1].

Podemos usar o atributo [value] para definir o valor padrão que irá aparecer de primeira dos inputs. Vale lembrar porém que, no caso de data por exemplo, o JavaScript pode resolver pegando a data atual que o cliente se encontra.

Podemos alterar o tamanho da caixa com o atributo [size]

[placeholder] para por um texto dentro da caixa, ele pode ser usado para dar "dicas" do que o usuário pode ou deve fazer nela.

Se deixarmos o [autocomplete] do [form] ligado, podemos colocar esse mesmo atributo no [input], vale notar que há varias opções de auto preenchimento.

Alguns exemplos de preenchimento importante são
[username] -> Nome de usuário.
[name] -> Nome, normalmente é o nome real.
[new-password] -> Senha **nova**, usada em cadastro.
[current-password] -> Senha **atual**, usada em login.


### Pattern, legend e fieldset
[pattern] -> Atributo usado no input de telefone, usado para definir padrões de telefones. Todo pattern começa com **^** e termina com $. Ex:

```pattern
pattern="^\d{4,5}-[0-9]{4}$"
```

Os números entre chaves são as quantidades aceitas, nesse caso na primeira ele aceita entre 4 e 5  números, na segunda aceita somente 4.
Das duas formas estamos aceitando dígitos em geral, mas na segunda estamos aceitando números de 0 a 9.
Se quisermos por o DD (o número entre parênteses no começo), temos:
```pattern
pattern="^\(\d{2}\)\d{4,5}-[0-9]{4}$"
```

Para abrir parênteses, use [\(] e para fechar use [\)]. O [\d] e o [{2}] é a quantidade de números necessárias dentro do parêntese, nesse caso o navegador não irá escrever os parênteses, porém caso não haja os parênteses nos exatos lugares propostos no pattern, ele será rejeitado.

**PS**: Isso é apenas caso esteja limitado ao html, pois outras línguas como **Javascript** ou **php** nos permite manusear esses dados de forma bem mais eficiente e menos limitada.

O comando [fieldset] é um agrupamento de elementos, podemos envelopar todas as caixas de formulário e formar uma "caixa" só, com todos esses elementos agrupados.
Dentro do fieldset ainda, podemos por o título dessa caixa, usando o [legend]. Ex:
```
<form action="cadastro.php" method="get" autocomplete="on">

	<fieldset> <!-- Fica dentro do form, envelopando todos os inputs-->
		<legend>Dados Pessoais</legend>
		<p>
			<label for="inome">Nome</label>
			<input type="text" name="nome" id="inome" minlength="5" maxlength="20" required>
		</p>

		<p>
			<label for="iemail">E-mail</label>
			<input type="email" name="email" id="iemail" autocomplete="email" required>
		</p>
		
		<p>
			<label for="itel">Telefone</label>
			<input type="tel" name="tel" id="itel" autocomplete="tel" pattern="^\(\d{2}\)\d{4,5}-[0-9]{4}$" required placeholder="(xx) xxxx-xxxx">
		</p>
		
		<p>
			<input type="submit" value="Enviar">
			<input type="reset" value="Limpar">
		</p>
	</fieldset>
	
</form>
```

O fieldset pode ser usado principalmente para agrupar diferentes grupos de dados semelhantes, no qual cada um tem um assunto diferente. Ex: Uma caixa para dados pessoais, dados de família, dados financeiros, dados escolares, etc.


### Checkbox e Radio button

[input:checkbox] para fazer formulários do tipo de marcação **MÚLTIPLO** (podendo marcar mais de uma opção). Ex: Em um formulário de cursos, marcar quais cursos dispostos foram concluídos.
Vale lembrar que é necessário vincular cada alternativa com o label correto. Ex:

```label
<input type="checkbox" name="esbas" id="iesbas"> <label for="iesbas">Basquete</label>
```

Se quiser organizar em colunas ao invés de linhas, coloque um [br] em cada input que for posto.

No caso do [input:radio] são formulários de **ALTERNATIVAS** (uma opção). Ex: Masculino ou feminino.
É necessário por um atributo [value] para indicar a opção selecionada na hora da extração dos dados.

Nesse tipo de input, é **obrigatório** que todas as alternativas de cada "questão" possuam o mesmo [name], caso contrário o navegador permitirá você assinalar mais de um deles. Ex:

```radio
<!-- NOMES IGUAIS -->
<input type="radio" name="sexo" id="isxmas"><label for="isxmas">Masculino</label> <br>

            <input type="radio" name="sexo" id="isxfem"><label for="isxfem">Feminino</label>
```

Para ambos radio e checkbox temos o atributo [checked], ele só deixa o input marcado automaticamente.


### Color, range e file

[input:color] basicamente permite o usuário escolher uma cor, e o dado recebido será o código hexadecimal dessa cor.

Podemos colocar o atributo [value] para mudar a cor padrão.

[input:range] é um formulário de nível, ou seja, o cliente será dado uma barra que, por padrão, vai de 0 a 100, e ele pode selecionar o nível com base na pergunta.

Use os atributos [min] e [max] para definir o número de níveis.
Use [value] para mudar o número padrão.

[input:file] é um formulário com inserção de arquivo.

**PS:** Ao usar esse tipo de input, é **mandatório** mudar o [method] para [post]. O motivo é devido ao que já foi citado anteriormente acerca do limite de dados, no qual o método [get] não pode ultrapassar 3000 bytes.


### Select, datalist e textarea

[select] -> Select é um tipo de formulário que lhe da uma série de opções pré-definidas para serem escolhidas.
[option] -> As opções que estarão disponíveis na lista.
Para deixar uma opção já selecionada, use o atributo [selected] na option desejada.

Dentro do [select], podemos envelopar quantas [options] quisermos dentro de uma [optgroup].
ao usar o atributo [label], podemos dar um nome para essa optgroup.

Um exemplo de uso seria ao pedir o estado de um usuário, podemos organizar as options por regiões, uma optgroup seria o Sudeste, outra o Sul, outra o Norte, etc...

Logo acima do [optgroup] podemos colocar outra [option], essa terá o valor vazio ([value=""]) e caso o cliente possa enviar um formulário com essa opção sendo escolhida, use o atributo [disabled]. Não esqueça de defini-la como padrão usando o [selected].


[datalist] -> Quando quisermos ter uma lista de opção mas também a possibilidade de escrever uma possibilidade manualmente, podemos criar uma [datalist], para isso faremos os seguintes passos:
- Colocaremos o [input] de texto
- Logo abaixo, faremos uma [datalist], coloque todas as [options] desejadas dentro dela
- Dê um [id] para essa [datalist].
- No input que foi criado, adicione o atributo [list] e digite o id da [datalist] nele.

Caso não queira que apareça o código da option, remova o [value] da mesma.


[textarea] -> É o tipo de formulário que permite que o usuário mande textos. Com os atributos [rows] e [cols] podemos definir o tamanho da caixa, nota-se que isso altera apenas o tamanho da **CAIXA**, a quantidade de texto é infinita.

Podemos por um [placeholder] nessa área.

O Cliente pode manualmente aumentar ou diminuir o tamanho dessa caixa, caso isso não seja ideal podemos tirar essa permissão com o atributo [style="resize: none"]

**PS:** Caso use o [textarea], mude o [method] de sua [form] para [post]. Novamente pelo motivo de limite de 3000 bytes do get.


### Output

O [output] é um elemento de saída, ele é usado apenas para propósitos visuais.
É um elemento usado para injetar resultados de um cálculo ou o resultado de uma ação de um usuário.
Esse é um elemento de saída, ou seja, é necessário que ele esteja associado a um script

``` soma output
<form action="cadastro.php" method="get" autocomplete="on">

        <p>

            <label for="in1">Número 1</label>

            <input type="number" name="n1" id="in1" min="0" max="50" placeholder="0 a 50" required oninput="isoma.innerHTML = Number(in1.value) + Number(in2.value)">

        </p>

  

        <p>

            <label for="in2">Número 2</label>

            <input type="number" name="n2" id="in2" min="0" max="50" placeholder="0 a 50" required oninput="isoma.innerHTML = Number(in1.value) + Number(in2.value)">

        </p>

  

        <p>

            <label for="isoma">Soma:</label>

            <output name="soma" id="isoma">0</output>

        </p>

  

        <p>

            <input type="submit" value="Enviar">

            <input type="reset" value="Limpar">

        </p>

    </form>
```

Para usar o [output], primeiro precisamos da entrada de dados.

Nesse exemplo, usaremos a entrada de 2 números e mostrar o resultado da soma entre eles.

Com a tag [input:number] podemos pedir 2 números para um usuário. 

``` soma
oninput="isoma.innerHTML = Number(in1.value) + Number(in2.value)"
```

Dentro dos inputs, temos o [oninput], ele que executa as ações do script de JS, no qual o resultado é mostrado no [output].

o [in1] é o nome do id do primeiro input, o [in2] é o id do segundo input.
Ao colocar esse comando nos 2 [input] dos números, poderemos fazer a soma.

a tag [output] em sí ja é bem familiar: só colocar um nome e um id para essa operação. Nesse caso seria [isoma], como está descrito no comando acima.

Outro exemplo de uso de output é usando o formulário [range], faremos um output que visualize o número em que a barra se encontra:

```range
<form action="cadastro.php">



	<p>

		<label for="inum">Número: </label>

		<input type="range" name="num" id="inum" min="0" max="10" oninput="ival.innerHTML = Number(inum.value)">



		<output id="ival">5</output>

	</p>



	<p>

		<input type="submit" value="Enviar">

		<input type="reset" value="Limpar">

	</p>

</form>
```

O último exemplo vai ser de um formulário que irá pedir o ano em que o usuário nasceu, e devolver o número da sua idade:

```idade
<body>

    <h1>Exemplo de Formulário</h1>

  

    <form action="cadastro.php" method="get" autocomplete="on">

  

        <p>

            <label for="iano">Em que ano você nasceu?</label>

            <input type="number" name="ano" id="iano" min="1900" max="2025" value="2000" oninput="calcIdade()">

        </p>

  

        <p>

            <label for="iidade">Sua idade é: </label>

            <output id="iidade"></output>

        </p>

    </form>

  

    <script>

        function calcIdade() {

            let atual = new Date().getFullYear()

            iidade.innerHTML = Number(atual) - Number(iano.value)

        }

    </script>
```