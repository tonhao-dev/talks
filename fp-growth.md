---
theme: "solarized"
transition: "slide"
title: "FP Growth"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### FP Growth

_Luís Antônio_

---

### Antes do Growth

---

### Frequent pattern discovery
A tarefa de encontrar os padrões mais frequentes e relevantes em grandes conjuntos de dados. (Wikipedia)

---

### Autores
- J. Han
- Jian Pei
- Yiwen Yin

---

#### Vamos tentar entender na prática
![-](https://miro.medium.com/max/640/1*oHbYbRk8CbYNdGxQyXOxxA.webp)

---

### Ordenando
![-](https://miro.medium.com/max/434/1*IUO0iDzIJuSUbE2BiuQMig.webp){width=50%}

---

### Suporte
O suporte indica o quão frequente um conjunto de itens ocorre na base de dados. Se o suporte desse conjunto é muito pequeno significa que não temos informações suficiente para tirar conclusões.

---

### Suporte 
![-](https://miro.medium.com/max/640/1*fvZ6PJfgheY2crOwRXbUFw.webp)

---

### Considerando um SP mínino de 50%
![-](https://miro.medium.com/max/456/1*tbTqvEvph563-PF8f_vB2Q.webp)

---

### Certo, agora vamos para o 2° passo
Árvore se sufixos

---

### O que é isso?
![-](https://media.discordapp.net/attachments/839151579416363048/1044331966155194409/unknown.png?width=1303&height=686)

---

### Ordenando os itens para cada transação
![-](https://miro.medium.com/max/640/1*79jStEdWjTCQYF17H4pkrA.webp)

---

### Agora, é só inserir

---

### T1 (Manteiga, Pão, Leite)
![-](https://miro.medium.com/max/184/1*nbFQVNqKXqg4oKJXLSFzJg.webp)

---

### T2 (Manteiga, Leite, Café)
![-](https://miro.medium.com/max/184/1*nbFQVNqKXqg4oKJXLSFzJg.webp)

---

### T3 (Café)
![-](https://miro.medium.com/max/368/1*se1OUSUWoTw2x7R2BQTQsw.webp)

---

### T4 (Manteiga, Pão, Café)
![-](https://miro.medium.com/max/576/1*_YTDDQAMorClcvOKF38Thg.webp)

---

### T5 (Manteiga, Pão, Leite)
![-](https://miro.medium.com/max/568/1*EQ4PF69DOFY_yPsxUzQSiQ.webp)

---

### T6 (Manteiga, Pão, Leite, Café)
![-](https://miro.medium.com/max/542/1*F5wJ2Exuey2Do7ivmeTqPw.webp)

---

### Conjuntos intermediários

![-](https://miro.medium.com/max/640/1*WQe9AAgNfX5xWUyx12OUuw.webp)

Baseado nessa árvore construiremos os conjuntos intermediários conditional pattern base e conditional FP tree, para depois gerar os conjuntos frequentes.

---

### Conditional Pattern
Para achar o conditional pattern base precisamos iterar sobre cada item da coluna de frequência inversa, e guardar o caminho da raiz até o nó em questão. Exemplo: podemos encontrar um nó Café, pelos caminhos: { Manteiga, Pão, Leite }, {Manteiga, Leite}, {Manteiga, Pão}. Observe na Árvore que o caminho direto da raiz ao Café não é contado.

---

### Conditional FP tree
A partir do conditional pattern base, criamos o conditional FP tree que são os itens dos conjuntos de conditional pattern base que estão acima do suporte mínimo.

![-](https://miro.medium.com/max/640/1*EOSTfIctwdOp_YQluNXJiA.webp)

---

### Conjuntos frequentes

Agora finalmente podemos encontrar nossos conjuntos frequentes.

![-](https://miro.medium.com/max/640/1*g57TN_g4Tpgx53ii5JJFDw.webp)

---

### Obrigado

