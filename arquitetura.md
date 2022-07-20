---
theme: "white"
transition: "slide"
title: "Arquitetura backend"
enableMenu: false
enableSearch: false
enableChalkboard: true
---

### Arquitetura Backend - Indo além do MVC

_Henrique Schmitt_

---

### O que é arquitetura de software?

---

### Linha do tempo - Arquitetura

- 1950
  - Non-structured Programming
  - ~1951 – Assembly
- 1960 -**Structured Programming** -**Layering: 1 tier** with the UI, Business Logic and Data Storage
  - ~1958 – Algol
- 1970 -**Procedural / Functional Programming**
  - ~1970 – Pascal
  - ~1972 – C
  - 1979 – Model-View-Controller

---

### Linha do tempo - Arquitetura

- 1980
  - **Object Oriented Programming** (first thoughts were in the late 1960s, though)
  - **Layering: 2 tier**, the 1st tier with the UI, the 2nd tier with Business Logic and Data Storage
  - ~1980 – C++
  - **CORBA** – Common Object Request Broker Architecture (though the first stable version was only out in 1991, the first usages were during the 1980s)
  - ~1986 – Erlang

---

- ...1980
  - 1987 – PAC aka Hierarchical Model-View-Controller
  - 1988 – LSP (~SOLID)
- 1990
  - Layering: 3 tier, the 1st tier with the UI, the 2nd tier Business Logic (and the UI presentation logic in case of a browser as client), the 3rd tier with the Data Storage
  - ~1991 – Message Bus
  - ~1991 – Python

---

### Linha do tempo - Arquitetura

- ...1990
  - 1992 – Entity-Boundary-Interactor Architecture aka EBC aka EIC
  - ~1993 – Ruby
  - ~1995 – Delphi, Java, Javascript, PHP
  - 1996 – Model-View-Presenter
  - 1996 – OCP, ISP, DIP (~SOLID), REP, CRP, CCP, ADP
  - 1997 – SDP, SAP
  - ~1997 – Aspect Oriented Programming
  - ~1997 – Web Services
  - ~1997 – ESB – Enterprise Service Bus (although the book that coined the term was published in 2004, the concept was already used before)

---

### Linha do tempo - Arquitetura

- 2000
  - 2002 – SRP (~SOLID)
  - 2003 – Domain-Driven Design
  - 2005 – Model-View-ViewModel
  - 2005 – Ports & Adapters Architecture aka Hexagonal Architecture
  - 2006 – CQRS & ES (Command Query Responsibility Segregation & Event Sourcing)
  - 2008 – Onion Architecture
  - 2009 – Microservices (at Netflix)

---

### Linha do tempo - Arquitetura

- 2010
  - 2010 – Data-Context-Interaction Architecture
  - 2012 – Clean Architecture
  - 2014 – C4 Model

---

### Exemplos de arquiteturas

- P2P
- Quadro Negro
- Computação distribuída
- Criação implícita
- Dutos e filtros

---

### As mais conhecidas

- Client x Server
- Aplicação monolítica
- Modelo em três camadas

---

### As mais modernas

- Analise de sistema estruturada
- Arquitetura orientada a serviço
- Arquitetura orientada a busca

---

### Verdade ou mito ?

Arquitetura de software é cíclica, ou seja, os conceitos usados anos atrás tendem a reaparecer ou já reapareceram

---

### Conceito arquitetura x design de software

---

_"É difícil avaliar se um design está certo ou errado. Sua natureza é interpretativa. Depende do observador"_

B. Brito

---

### Qual a diferença de estilo arquitetural e arquitetura?

---

### Porque não fazermos um microservice primeiro?

![-](https://martinfowler.com/bliki/images/microservice-verdict/path.png){width=70%}

---

### Arquiteturas mais comuns em C#

---

### Arquiteturas mais comuns em C# - 3 Camadas

![-](https://media.discordapp.net/attachments/839151579416363048/908133510462717973/3LayeredArch.png?width=764&height=426)

---

### Arquiteturas mais comuns em C# - Clean

![-](https://media.discordapp.net/attachments/839151579416363048/908131800788922388/CleanArchitecture.png?width=580&height=426)

---

### Arquiteturas mais comuns em C# - Hexagonal

![-](https://media.discordapp.net/attachments/839151579416363048/908132128494088202/58020f00-9aa6-11ea-94d8-0155338f76a4.png?width=756&height=426)

---

### Estilos arquiteturais mais comuns em C#:

- REST
- CQRS
- RPC

---

### Arquitetura backend - Indo além do MVC
