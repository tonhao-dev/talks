---
theme: "black"
transition: "slide"
title: "Componentes Agnósticos"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### Agnostic Components

_Luís Antônio_

---

### Agnóstico

"Que é adepto ou se pode referir ao agnosticismo."
_Dicio_

---

### Por definição
Não depende de nenhuma estrutura.

---

### Idealmente
JavaScript, Java, C#, Python e etc.

---

### Como nem tudo são flores
![-](https://gerarmemes.s3.us-east-2.amazonaws.com/memes/thumb/a5725031.jpg)

---

### Web Components (W3C)
Web Components is a suite of different technologies allowing you to create reusable custom elements

![-](https://www.webcomponents.org/assets/logo-192x192.png)

---

### Technologies
- Custom elements
- Shadow DOM
- HTML templates

---

### Custom Elements 
```html
<ds-button variant="primary">Login</ds-button>
```

---

### Custom Elements Rules
```html
<my-element>
<open-234>
<html5-🤟>
<input-ðŸ¥ž></input-ðŸ¥ž>
```

---

### Shadow DOM
![-](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM/shadowdom.svg)

---

### Template
```html
<button onclick="showContent()">Show hidden content</button>

<template>
  <h2>Flower</h2>
  <img src="img_white_flower.jpg" width="214" height="204">
</template>

<script>
function showContent() {
  var temp = document.getElementsByTagName("template")[0];
  var clon = temp.content.cloneNode(true);
  document.body.appendChild(clon);
}
</script>
```

---

### Pause Break

---

### Lets go

---

### Create a Class for the WC

```js
export class Button extends HTMLElement {
  constructor() {
    super();
  }
}
```

---

### Define the WC name

```js
customElements.define("ds-button", Button);
```

---

### Display innerText

```js
export class Button extends HTMLElement {
  constructor() {
    super();
    this.innerHTML = `<h3>${this.innerText}</h3>`
  }
}
```

```html
<ds-button>Tonhão</ds-button>
```

---

### Qual o problema disso?

---

### Estilo
```css
h3 {
  color: red;
  background-color: blue;
}
```

---

### Shadow DOM

---

### Tip
Preferences > Elements > Show user agent shadow 

---

### HTML under the hood
![-](https://cdn.discordapp.com/attachments/839151579416363048/1103808379685699595/image.png)
![-](https://media.discordapp.net/attachments/839151579416363048/1103808422119493704/image.png)

---

### Button JS


```js
const template = document.createElement("template");
template.innerHTML = `<h3><slot></slot></h3>`

export class Button extends HTMLElement {
  constructor() {
    super();
      const shadow = this.attachShadow({ mode: "open" });
      shadow.append(template.content.cloneNode(true));
  }
}
```

---

### Na prática
![-](https://media.discordapp.net/attachments/839151579416363048/1103815674947706960/image.png)
![-](https://media.discordapp.net/attachments/839151579416363048/1103815824764059648/image.png)