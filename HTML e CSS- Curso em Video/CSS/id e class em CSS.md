São formas de organizar seus estilos.

**id = #  /  classe = .  /  pseudo-classe = :  /**

Um dos seus usos é identificar um componente do seu site, para que você possa mudar aquele componente em específico.

use [id=""] ao lado do que deseja especificar, dentro da tag.

coloque o nome do id nas aspas.

na parte de estilos, coloque a tag, seguida de uma hashtag e o nome da sua id.

```id
h1#principal {
	color: black;
	background-color: red;
}
```

**PS: REGRA do W3C: Você NÃO pode usar o mesmo id mais de uma vez.**

Funciona, mas tá errado.

Para aplicar a mesma configuração em várias tags, use o **class**.

Na nomenclatura de ids e classes, faça um nome baseado em sua **FUNÇÃO** e NÃO em sua **FORMA**.

Por exemplo, no subtítulo de um site, você pode por o nome baseado no que ele está falando sobre, mas não um nome baseado em sua cor ou se suas letras são grandes.

Para criar classes, use o [.] e o nome da classe a frente.

É possível por ids e classes ao mesmo tempo em uma mesma tag, não é preciso separar por vírgulas, apenas escreva uma classe ou id, use espaço e coloque a próxima.

Existe uma certa hierarquia na criação de estilos:
Primeiro as configurações genéricas (h1, h2, body, p, etc.)
Depois, vem os ids e classes
O que vai prevalecer é qual foi posta por último, e o que vem depois herda o que veio anteriormente.

Posso criar um h1 com fonte Arial, fundo verde, cor cinza.

Ao criar um id chamado principal e mudar sua cor, ele continuará com a fonte e o fundo.

**É possível interagir com partes "filhas" de uma tag usando [>]. EX:**
div > p -> esse estilo só vai afetar o **p** que estiver dentro de uma **div**.