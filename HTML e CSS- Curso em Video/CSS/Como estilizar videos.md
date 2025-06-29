Primeiro envelope o vídeo em uma div, e depois dê uma classe a ela (normalmente vídeo ou algo do tipo).

Podemos mudar a cor do fundo para ter uma noção do quanto de espaço está sendo ocupado 

Se quiser que o fundo ocupe a largura inteira, use margens negativas nos lados. Também pode-se usar o [padding] para engordar a caixa.

Depois iremos configurar o [iframe] dentro da classe.

Pode-se usar o [width] e [height] em 100%, para que o vídeo ocupe toda a caixa. Ao fazer isso, pode ser que o tamanho do vídeo fique minúsculo, ou bem torto. Para arrumar isso, mude a escala dele usando [aspect ratio: 16 / 9], ficando melhor de se assistir em dispositivos menores (também há a opção de 4 / 3 caso seja útil alguma hora).

Se não quiser que ele ocupe a caixa inteira, use um [display: flex] nele e então [margin: auto], deixando o vídeo no meio da caixa.