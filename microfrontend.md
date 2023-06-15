---
theme: "blood"
transition: "slide"
title: "Micro Frontend"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### Micro Frontend

_Luís Antônio (tonhao.dev)_

---

![-](https://cdn.discordapp.com/attachments/839151579416363048/1119037687723204728/FyslugYWAAARIpI.png)

---

### Objetivo
- O que é
- Como funciona
- Exemplo


---

### Um pouco de história

---

### Monolito
![-](https://wac-cdn.atlassian.com/dam/jcr:95b9a276-c524-42b1-8d06-ded56d589858/Monolithic%20architecture@2x.png?cdnVersion=1056){width=70%}

---

### Monolito - Características

1. Sistema único
2. Não dividido
3. Vários componentes ligados a uma plataforma


---

### Monolito - Vantagens

1. Mais simples de desenvolver
2. Simples de testar
3. Simples de fazer o deploy

---

### Monolito - Desvantagens

1. Manutenção
2. Alterações vs Deploy
3. Não há flexibilidade quanto a linguagem

---

### Em resumo: acoplamento

---

### Front & Back

![-](https://cdn.discordapp.com/attachments/839151579416363048/1119019615209664632/PI2zu0k3yIgAAAABJRU5ErkJggg.png)

---

### A medida que o problema cresceu

---

###  Micro serviços 
![-](https://miro.medium.com/v2/resize:fit:1308/0*hootD597dp9Pg56T.png)

_(mas só no backend)_

---

### O que são os micro serviços

<p>
<q cite="http://www.wwf.org">é um estilo de arquitetura que estrutura um aplicativo como uma coleção de serviços</q>

microservices.io
</p>

---

### Características

1. Deploy independente
2. Baixo acoplamento
3. Reflete as necessidades de negócio
4. Responsabilidade de um time pequeno

---

### Recaptulando 

![-](https://media.discordapp.net/attachments/839151579416363048/1119018869445644348/Untitled.png?width=569&height=541)

---

### Próximo passo natural?

---

### Integração Frontend para Sistemas Verticalizados

---

### Ou então

---

### Microfrontend

![-](https://media.discordapp.net/attachments/839151579416363048/1119021566387302440/Untitled.png?width=829&height=475)

---

### Core Ideas

<section data-auto-animate>
  <ul>
    <li>Be Technology Agnostic</li>
  </ul>
</section>
<section data-auto-animate>
  <ul>
    <li>Be Technology Agnostic</li>
    <li>Isolate Team Code</li>
  </ul>
</section>
<section data-auto-animate>
  <ul>
    <li>Be Technology Agnostic</li>
    <li>Isolate Team Code</li>
    <li>Establish Team Prefixes</li>
  </ul>
</section>
<section data-auto-animate>
  <ul>
    <li>Be Technology Agnostic</li>
    <li>Isolate Team Code</li>
    <li>Establish Team Prefixes</li>
    <li>Favor Native Browser Features over Custom APIs</li>
  </ul>
</section>
<section data-auto-animate>
  <ul>
    <li>Be Technology Agnostic</li>
    <li>Isolate Team Code</li>
    <li>Establish Team Prefixes</li>
    <li>Favor Native Browser Features over Custom APIs</li>
    <li>Build a Resilient Site</li>
  </ul>
</section>

---

### Uma aplicação de exemplo

![-](https://micro-frontends.org/ressources/video/model-store-0.gif){width=100%}

---

### Mas antes

---

### Problemas

1. Cargas úteis aumentadas
2. Baixo desempenho
3. Coding e Deploy mais complexo
4. Dependências redundantes
5. Risco de falta de comunicação (teams)

---

### Como dividir?
![-](https://micro-frontends.org/ressources/screen/three-teams.png)

---

### Botão de comprar - Web Components
```js
class BlueBuy extends HTMLElement {
  connectedCallback() {
    this.innerHTML = `<button type="button">buy for 66,00 €</button>`;
  }

  disconnectedCallback() { ... }
}
window.customElements.define('blue-buy', BlueBuy);
```

---

### Botão de comprar
![-](https://micro-frontends.org/ressources/video/custom-element.gif){width=100%}

---

### Usuário escolhe algum trator

![-](https://micro-frontends.org/ressources/video/custom-element-attribute.gif){width=100%}

---

```js
const prices = {
  t_porsche: '66,00 €',
  t_fendt: '54,00 €',
  t_eicher: '58,00 €',
};

class BlueBuy extends HTMLElement {
  static get observedAttributes() {
    return ['sku'];
  }
  connectedCallback() {
    this.render();
  }
  render() {
    const sku = this.getAttribute('sku');
    const price = prices[sku];
    this.innerHTML = `<button type="button">buy for ${price}</button>`;
  }
  attributeChangedCallback(attr, oldValue, newValue) {
    this.render();
  }
  disconnectedCallback() {...}
}
window.customElements.define('blue-buy', BlueBuy);
```

---

### Comunicação via props
Funciona bem para pai-filho, mas e no nosso exemplo?

---

### Usuário clicou para comprar

![-](https://micro-frontends.org/ressources/screen/three-teams.png)

---

### Problema
Como fazer para que os componentes do time azul se comuniquem?

---

### Resposta
Favor Native Browser Features over Custom APIs

---

### O botão de comprar

```js
class BlueBuy extends HTMLElement {
  [...]
  connectedCallback() {
    [...]
    this.render();
    this.firstChild.addEventListener('click', this.addToCart);
  }
  addToCart() {
    // maybe talk to an api
    this.dispatchEvent(new CustomEvent('blue:basket:changed', {
      bubbles: true,
    }));
  }
  render() {
    this.innerHTML = `<button type="button">buy</button>`;
  }
  disconnectedCallback() {
    this.firstChild.removeEventListener('click', this.addToCart);
  }
}
```

---

### O carrinho de compras

```js
class BlueBasket extends HTMLElement {
  connectedCallback() {
    [...]
    window.addEventListener('blue:basket:changed', this.refresh);
  }
  refresh() {
    // fetch new data and render it
  }
  disconnectedCallback() {
    window.removeEventListener('blue:basket:changed', this.refresh);
  }
}
```

---

### Vamos olhar on the fly

https://micro-frontends.org/1-composition-client-only/

---

### Microfrontend architecture

_Luis Antonio (tonhao.dev)_ 

---

### Referências

1. https://www.youtube.com/watch?v=KZpSghOWOnE&t=1418s&ab_channel=FullCycle
2. https://www.youtube.com/watch?v=SC1QkRfFccE&t=359s&ab_channel=Codeminer42
3. https://dev.to/jpbrab0/o-que-e-micro-front-end-4kci#:~:text=Micro%20Front-end%20%C3%A9%20um,dessas%20funcionalidades%20de%20forma%20independente
4. https://micro-frontends.org/