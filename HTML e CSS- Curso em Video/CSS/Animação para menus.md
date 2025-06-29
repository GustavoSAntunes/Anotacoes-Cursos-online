
Use o [transition-duration] em um [a:hover] para criar uma pequena animação nos botões ou em qualquer outra caixa.

podemos usar [border-radius] para fazer as bordas ficarem em forma de círculo.

Coloque o tamanho máximo de um padding no [nav], então crie um [nav > a] com um padding um pouco menor, e então faça um [nav > a:hover] com o mesmo tamanho do [nav], se fizer isso junto com o [transition-duration], faz um efeito de animação muito massa.

Esse código abaixo permite a utilização de animações para os botões, fazendo com que ganhem uma sombra colorida por um breve momento.

```pulsate
@keyframes pulsate {

    0%{

        box-shadow:

        0 0 25px red,

        0 0 25px green;

    }

}
```

Coloque essa regra, e então, coloque esse comando dentro do [a:hover]

```animation
animation: pulsate 1s ease-in-out;
```

O [keyframe] é a regra que permite a animação, ela faz com que o estado atual do bloco se altere para o outro estilo que fora configurado.

Para que a animação funcione, é preciso conectá-la a um **elemento**, como mostrado acima. Ao lado da regra você seleciona o **nome** da animação, e depois você consegue usar ela em outros blocos do site como se fossem **variáveis**.

Antes de selecionar como será a animação, deve-se configurar em que parte dela ocorrerá, no exemplo acima ela começa (no 0%) vermelha e encaminha até o verde (que seria o 100%).

Com a animação criada, podemos usar o shorthand de animation, temos: [o nome da animação criada], [tempo de animação (segundos, minutos)]  e [no caso do de cima, um efeito].