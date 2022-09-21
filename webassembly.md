---
theme: "league"
transition: "slide"
title: "WebAssembly"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### WebAssembly

_Como o WebAssembly permitiu Flutter e Python na Web_

---

### Níveis de Abstração

- Átomos
- Código de maquina (0 e 1)
- Assembly

---

### Grace Hopper

- Flow-Matic → COBOL
- Nascem as linguagens de baixo nível

---

### Javascript

- Foi feito para aplicações pequenas
- É interpretado
- Não é performático

---

### Compilação

- Tem um tempo maior para iniciar
- Análise léxica do código
- otimizações

---

### JIT

- Just in time compiler
- Compilação com JS
- Engine V8

---

![-](https://static.tildacdn.com/tild3533-6537-4639-b961-393433393837/1_GuWInZljjvtDpdeT6O.png)

---

### Quente e Frio

- “Temperatura do código”
- Partes muito executadas → Quentes
- Partes pouco executadas → Frias
- Partes quentes → Candidatas a compilação

---

### Show, entendi o JS, agora e esse tal de WASM?

---

### O que é o WASM

> Um novo tipo de código que pode ser executado em navegadores modernos e oferece novos recursos e grandes ganhos de desempenho.Ele não se destina principalmente a ser escrito à mão, mas foi projetado para ser um destino de compilação eficaz para linguagens de origem como C, C++, Rust, etc.

MDN

---

### Quais problemas o WASM resolve

- Melhor compatibilidade;
- Mais segurança;
- Maior desempenho em aplicações web;
- Melhor acesso a recursos nativos.

---

### Casos de uso

- Edição de vídeo/imagem
- Jogos
- Reconhecimento de imagem
- Aplicações CAD

---

### Como funciona o processo

![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/79f3a0cb-b49f-47b8-9609-6b411bdbaa05/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220727%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220727T232634Z&X-Amz-Expires=86400&X-Amz-Signature=9983eec4f5e73cdb7a41eedf7c43ee1300a94e0b564caa9aa3cd76136c933af0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

---

### Exemplo (C++)

![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/9619e35c-2404-4134-927e-ca08fd968e8f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220727%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220727T232713Z&X-Amz-Expires=86400&X-Amz-Signature=4126d0b08fb2f9dadd424fbc19e1f5d1839eff51dfc29542c79fe3ea383b31cf&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

---

### Exemplo (C++)

![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a8b36214-c839-4767-b642-8717f3dff0ed/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220727%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220727T232715Z&X-Amz-Expires=86400&X-Amz-Signature=3036f7af4d6cce870794bd6f8aecda13efa6b51a3e8e5521275b896a16a84f27&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

---

### Vamos caminhar para nosso objetivo

---

### Python na Web

---

### PyScript
- Houveram outras tentativas antes
- transcrypt e Brython 
- Pyodide

---

### Python é interpretado

Python é uma linguagem interpretada, que não vem com um compilador padrão que possa direcionar o WebAssembly. Então, como esse processo ocorre?

---

### Resposta 
![-](https://files.tecnoblog.net/wp-content/uploads/2022/05/pyscript-pyodide.jpg)

---

### E no caso do Flutter?

---

### Flutter na web

- DOM + Canvas + CSS → DomCanvas
- Compila código Dart em JS → dart2js
- Skia (O Skia é uma biblioteca de gráficos 2D)
- Flutter 1.17 → CanvasKit → WebAssembly e WebGl.

---

### Por que o Flutter não usa WebAssembly ao invés do dart2js?

---

### WASM não pode acessar o DOM


---

### Como assim?

- Wasm é mais rápido que Js para coisas complexas
- Mas o JS pode manipular o DOM

---

### Outro problema

- WASM não possui um garbage collector
- WASM originalmente foi pensado como um target para C/C++

---

### Luís Antônio (Tonhão)
- Linkedin: Luís Santiago
- GitHub: luis-antonio-dev
- Instagram: dev__luis

---

### Créditos
- [WebAssembly - web compilada | #devAdev com Larissa Gaulia](https://www.youtube.com/watch?v=puc-0FdT4QM&t=755s&ab_channel=PagarmeTalks)
- [WebAssembly, o futuro do desenvolvimento web e um pouco de amadorismo](https://www.youtube.com/watch?v=Ed8qQfopffU&ab_channel=Zero%261)