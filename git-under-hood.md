---
theme: "serif"
transition: "slide"
title: "Git por debaixo dos panos"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### Git por debaixo dos panos

_Luís Antônio_

---

### Roteiro da apresentação
- Ponteiros
- Git do dia a dia
- 3 Áreas do git
- Objetos git
- Funcionamento interno
- Branch e merge
- Prática

---

### Ponteiros

> [...] um ponteiro ou apontador é um tipo de dado [...], cujo valor se refere diretamente a um outro valor alocado em outra área da memória.

Wikipedia

---

### Ponteiros

![-](https://www.codingame.com/servlet/fileservlet?id=41409364165150){width=70%}

---

### Ponteiros | Aplicabilidade 

![-](https://blog.cod3r.com.br/wp-content/uploads/2020/11/ArvoreBinaria-1024x790.png)

---

### Pontieros | Aplicabilidade

![-](https://sites.google.com/site/maratonaufabc/_/rsrc/1463123952263/topicos/grafos/DiGraph_cid.png)

---

### Git do gueto

---

### Normalmente, aprendemos por ódio

![-](https://i.imgur.com/mWRKjlm.png)

---

### 3 Áreas do git

![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/269b3ed0-0ad8-407f-8423-efbafac857c9/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220720%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220720T224015Z&X-Amz-Expires=86400&X-Amz-Signature=44e42637ffc224474b1dde6b5fa24385ca5abcb9c1f2b0ae13871b8508a6a70f&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

---

### Working directory

Área do dia a dia

---

### Staging area
A partir daqui temos a benção do pai git

---

### Local repository
Tudo que existe dentro da **temida** pasta _/.git_

---

### Vamos lá, agora é de verdade

---

### Mas antes, um aviso importante
![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4a391d7b-4157-49d2-aa4c-218f586a6e3f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220720%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220720T224506Z&X-Amz-Expires=86400&X-Amz-Signature=2b3d9197262445fe6703c4462e5c3a0bcaeb3384702e1b5ef18d6252e5e3512c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

**NÃO** Tenha medo das strings SHA1

---

### 3 Objetos git
- commit
- tree
- blob

---

### Commit
- Autor
- Mensagem 
- Ponteiro para uma Tree
- Ponteiro para o pai
- É um print (snapshot) do estado atual

---

### Tree

- Ponteiros para blob
- Ponteiros para outra Tree
- Abstrai nossas pastas

---

### Blob

- Dados em si
- Não possui metadados

---

### Funcionamento interno

---

### O que é o git
O git é, essencialmente, **um banco de dados de ponteiros**. Ou ainda, um grafo direcionado acíclico

---

### HEAD
Um ponteiro que aponta para a branch atual

---

### SHA1
![-](https://cibersistemas.pt/wp-content/uploads/2020/03/Hash_function_long.png)

A função SHA1 usa a função de hash criptográfica SHA1 para converter uma string de comprimento variável em uma string de 40 caracteres

---

### SHA1

- Unico
- Alta entropia
- Dois inputs iguais geram o mesmo resultado

---

### SHA1, exemplo
1. File => SHA1 => ```0b064b56112cc80495ba59e2ef63ffc9e9ef0c77```
2. Storage: ```.git/objects/0b/064b56...```

---

### Exemplo prático

---

### Situação no dia a dia
![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/60ee3275-1533-4b0c-ac02-59d9c350f8a4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220720%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220720T231541Z&X-Amz-Expires=86400&X-Amz-Signature=a3750f10b54803825fa75a1b17e2226dab74a8da81f95d233a32cde650dd2a42&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

- Meu repositório possui apenas 3 arquivos, localizados em:
    - `test-utils.tsx`
    - `/login/functions.ts`
    - `/login/ListSpaceModal/styles.ts`

---

### Sitação no dia a dia (Manhã)
Durante a manhã mexi em todos os 3 arquivos e fiz um commit com todas as alteações
- `test-utils.tsx`
- `/login/functions.ts`
- `/login/ListSpaceModal/styles.ts`

---

### Sitação no dia a dia (Tarde)
Na parte da tarde eu fiz alterações apenas no arquivo de estilos dentro de ListSpaceModal
- `/login/ListSpaceModal/styles.ts`

---

### Sitação no dia a dia (Noite)
A noite, final do expediente eu só mudei algo nos meus testes, mudei apenas o arquivo test-utils
- test-utils.tsx

---

### Árvore de commits

![-](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7e205858-a330-4bd5-af19-71010771536f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220720%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220720T231935Z&X-Amz-Expires=86400&X-Amz-Signature=56b865ffcf6e226ae666dc0e177f0b5e9f0d963d3456d11bbd00cea7a40b089e&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

### Branchs

---

### O que é uma branch? (advinhem)

> Uma branch é um ponteiro que aponta para o último commit em um dado contexto

Stackoverflow Blog

---

### O que é uma branch? 
![-](https://lh6.googleusercontent.com/cj5EZhz3pkPXlbbjUV42uZdQ4aq3nhzh3-DkoOVDdcOS5zKXwfrt2RXjguQmV6b0tU8PDymgIt86C552fgPPbkcMSKv9Z5U62-8p3LNFAA-_eg5WkjVNHWg9N4ifUJSEht73Z6Cn)

---

### O que é uma branch?

![-](https://lh4.googleusercontent.com/wGwKGWC3LqLBHzf15cS9WRbwNGpFkP4dEeY2EgsAATXJE_zar1QxmXLLmNuQtsOYpFpryfxIpgbJNQ0dD1l2dCkfZJXJCaZsOupUdzddvgAUYjFiDGh8iMlPuKUik5Dgoh6Fzx5v)

O ponteiro é movido para o último commit automaticamente

---

### E onde fica esse ponteiro no disco? (advinhem)

![-](https://lh4.googleusercontent.com/z0fy3yKkcQxhQzz0waoY1ewHwBSELi31DVWqcWuJnmPFQG62U6fitHwT8kgRU_EceKZwLKNFcNeAs0F5s2cYX2pDOJGVHeUEjq4WKXYXBY6T454iSlXI4tTuvDtwucckHnzGAEDR)

---

### E advinhem o que tem dentro?

![-](https://lh3.googleusercontent.com/N_-no0VdZfwbOERuc-woel78qE4khxCBzHtb8xo1gGmJ9JAnhoOugt86k3qEJRGRMebG2adZdDzE6QzfGxwqtDJiuyp8dyB9KDeqZ_oiQ_kRu9J1bnbKnU8vVxO3BDRzKTNqvrIc)

---

### Merges

---

### Fast-forward
![-](https://media.geeksforgeeks.org/wp-content/uploads/20191231172842/Fast-Forward-Merge.png)

---

### Recursive strategy
![-](https://git-scm.com/book/en/v2/images/basic-merging-1.png)

- Uma mesclagem começa com o Git localizando o commit comum do qual as ramificações de mesclagem divergiram mais recentemente.
- O Git então calcula dois diffs
- Para formar o commit do merge, o Git aplica os dois diffs à base do merge.

---

### Exemplo

![-](https://cdn.discordapp.com/attachments/839151579416363048/999461554200248330/unknown.png)

---

1. O Git primeiro descobre que a base de mesclagem.
2. O Git então calcula o diff de C até G(porque G é master) e o diff de C até Z (porque Zé otherbranch).
3. O Git então aplica ambos os diffs à C simultaneamente — e confirma o resultado em master. 
4. Agora a branch master aponta para o commit de merge, o qual possui dois pais 

---

### Dúvidas

---

### Luís Antônio (Tonhão)
- Linkedin: Luís Santiago
- GitHub: luis-antonio-dev
- Instagram: dev__luis