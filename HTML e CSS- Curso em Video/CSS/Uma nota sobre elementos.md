
# A diferença entre (elemento elemento) e (elemento > elemento)

(elemento elemento) significa que o seletor vai afetar o **descendente**. Um elemento descendente é qualquer elemento declarado dentro de outro

(elemento > elemento) significa que o seletor vai afetar o **Filho direto** de tal elemento. Exemplos abaixo:

Quando você escreve `div span { ... }`, você está dizendo qualquer `span` descendente (dentro) do `div`, e atuando no `span` nos dois casos abaixo:

```xml
<div><span> bla bla </span></div>
<div><a><span> bla bla </span></a></div>
```

Agora, quando usa `div > span { ... }`, vai ter efeito em apenas filhos do `div`, como este:

```xml
<div><span> bla bla </span></div>
```

Os atributos **não vão ser aplicados** em outros níveis de descendência, como neste caso:

```xml
<div><a><span> bla bla </span></a></div>
```

Motivo: o `<span>` neste último caso é "neto" do `<div>`, ou seja, é descendente mas não é filho, pois o filho é o `<a>`.