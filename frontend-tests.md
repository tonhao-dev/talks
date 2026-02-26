---
theme: "white"
transition: "slide"
title: "Testes automatizados no frontend: muito além de telas"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### Testes automatizados no frontend
*Muito além de telas*

---

### Quem sou eu?

- Luís Santiago (Tonhão)
- Desenvolvedor Frontend há 6+ anos
- Techbiz Forense Digital
- Capoeirista & enxadrista

---

### Contato

luis.developer.ac@gmail.com
https://www.linkedin.com/in/tonhao-dev/

---

### O que veremos hoje?

Indo além dos testes visuais: abordando estratégias, boas práticas e o papel dos testes de unidade, integração, end-to-end e regressão visual.

---

### O Elefante da Sala

![-](https://www.institutobrasilisrael.org/wp-content/uploads/2023/03/A77D157C-9748-4102-BA89-A63169120C2D.jpeg)

---

### O que você ganha participando?

- Downtime é dinheiro perdido.
- Case: como os testes me salvaram diversas vezes.

---

### O Preço de um Bug

> "Código é barato mas software continua caro, o preço de um bug não mudou."

---

### O que é frontend?

- Vamos nos limitar ao frontend web.
- Aplicações com SSR, SSG e ISR podem ganhar muito com [k6.io](https://k6.io/).

---

### Conceitos Iniciais

O que é um teste?

---

### Conceitos Iniciais

Como vocês testam hoje?

---

### Testes automatizados

Basicamente: código que testa código.

---

### Pirâmide de Testes
![-](https://miro.medium.com/v2/1*NQ7s8qic4dz2-zGcTpFxfA.png)

---

### Testes de Unidade

- **Ferramentas:** Jest.
- **O que testar:** Funções, métodos e hooks.
- **Dica:** Utilizar `react-hooks-testing-library`.

---

### Testes de Componente

- **Ferramenta principal:** Storybook.

---

### Testes de Integração

- **Ferramentas:** React Testing Library ou Angular Testing Library.
- **Foco:** Containers da aplicação.

---

### Testes de Regressão Visual

- Foco exclusivo na validação da Interface de Usuário (UI).
- **Ferramenta:** Playwright.

---

### Testes End-to-End (E2E)

- **Como funciona:** Playwright rodando em conjunto com a aplicação real.

---

### Boas Práticas de Teste

- O teste só deve falhar por um motivo.
- Testes devem ser independentes (isso ajuda muito no paralelismo).
- Cuidado com falsos positivos: garanta o *red* primeiro.

---

### Indo além

- [Melhores práticas em testes de software.](https://esr.rnp.br/desenvolvimento-de-sistemas/melhores-praticas-em-testes-de-software/)
- [Como evitar que sua automação vire código morto (Artigo no Medium).](https://medium.com/@lilianborbadeoliveira/%EF%B8%8F-testes-que-envelhecem-como-evitar-que-sua-automa%C3%A7%C3%A3o-vire-c%C3%B3digo-morto-c681c95c1218)

---

### Hands on!

Vamos sujar as mãos.

---

### Hands On: Regressão Visual e E2E

- Escrever testes de regressão visual validando o site da SASI usando o Playwright.
- Escrever testes de E2E para testar o site da SASI com Playwright.

---

### Hands On: Unidade e Componente

- Escrever um teste de unidade para a classe `URL` (e propor que vocês escrevam os demais).
- Escrever os testes de componente de um `button`.

---

### Hands On: Integração

Escrever dois testes de integração:
1. Deve exibir o título da página quando ela for carregada.
2. Deve exibir o botão de salvar a coleção.

---

### Referências

- [Intro to Storybook](https://storybook.js.org/tutorials/intro-to-storybook/angular/en/get-started/)
- [JavaScript Assertivo](https://javascriptassertivo.com.br/)
- [Os sete princípios do teste (Smarapd)](https://www.smarapd.com.br/os-sete-principios-do-teste)