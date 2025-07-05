### Unidades Absolutas:

- **px (pixels):**
    
    A unidade mais comum e fundamental. Um pixel é a menor unidade de medida em um dispositivo digital e é frequentemente usada para definir tamanhos precisos.
    
- **cm (centímetros), mm (milímetros), in (polegadas), pt (pontos), pc (paicas):**
    
    Unidades de medida físicas. São mais adequadas para impressão do que para telas, onde o tamanho físico pode variar bastante. 
    

### Unidades Relativas:

- **% (porcentagem):** O tamanho é definido em relação ao elemento pai. Por exemplo, `width: 50%;` significa que o elemento terá metade da largura do seu contêiner. 
- **em:** O tamanho é relativo ao tamanho da fonte do próprio elemento. `2em` significa o dobro do tamanho da fonte definida para o elemento. 
- **rem (root em):** O tamanho é relativo ao tamanho da fonte do elemento raiz (`<html>`). Isso permite criar layouts mais consistentes, pois a escala é baseada no tamanho da fonte global. 
- **vw (viewport width):** 1% da largura da viewport (janela do navegador). `50vw` significa metade da largura da tela. 
- **vh (viewport height):** 1% da altura da viewport. `50vh` significa metade da altura da tela. 
- **vmin:** 1% da menor dimensão (largura ou altura) da viewport. 
- **vmax:** 1% da maior dimensão (largura ou altura) da viewport. 
- **ex:** Relativo à altura da letra "x" minúscula da fonte atual. 
- **ch:** Relativo à largura do caractere "0" (zero) da fonte atual. 

### Recomendações de uso:

- **Para layouts responsivos e flexíveis:** Utilize unidades relativas como `em`, `rem`, `vw`, e `vh` para criar designs que se adaptem a diferentes tamanhos de tela.
- **Para designs que precisam de precisão:** Use `px` para definir tamanhos específicos, especialmente quando a consistência é crucial.
- **Para impressão:** Considere o uso de unidades absolutas como `cm`, `mm`, `in`, `pt`, e `pc`.