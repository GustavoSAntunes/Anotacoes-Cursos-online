#css #menu

A princípio, a forma mais simples é:
- usar o `position: sticky`
- definir em que lugar do site ele ficará grudado
```Exemplo
position: sticky;
top: 0;
```
É preciso reajustar o número (`top`) até que a caixa se encaixe da maneira desejada ao rolar.

Se isso não funcionar, tente a opção abaixo:

1 -> Coloque a caixa com o menu / cabeçalho em posição RELATIVA

```position
position: relative;
```

2 -> Procure o menu específico que você deseja colar no topo, em seguida:

- Em uma tabela por exemplo, ela normalmente fica dentro de um th, dentro de um tr, dentro de um thead: [thead > tr > th].
- Defina a posição desse menu como **sticky** [position: sticky]
- Agora use a propriedade [top], se o header não ocupar o topo inteiro, defina-o como -1px.
- Mude o [background-color] para a mesma cor desse header.