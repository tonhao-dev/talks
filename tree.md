---
theme: "white"
transition: "slide"
title: "Árvores e o DOM"
enableMenu: true
enableSearch: false
enableChalkboard: true
controls: true
slideNumber: true
hashOneBasedIndex: false
---

### Árvores

_Luís Antônio (tonhao.dev)_

---

### Árvores na teoria da computação
![-](https://static.javatpoint.com/ds/images/tree.png)

---

### Alguns nomes

![-](https://cdn-media-1.freecodecamp.org/images/Kan51et5e844FH0GbUNDMl8R2Hyb2Ck1-1xB)

---

### Habilidade importante
![-](https://res.cloudinary.com/practicaldev/image/fetch/s--r1Bf3DES--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3y3715dktvg2w96l7uwh.jpeg)

---

### Fibonacci
```js
function fib(n) {
    if (n <= 2) return 1;
    return fib(n - 1) + fib(n - 2);
}

fib(6)
```

---

### Fibonacci Tree
![-](https://willrosenbaum.com/assets/img/recursive-fibonacci/tree.png)

---

### Alvo
![-](https://media.geeksforgeeks.org/wp-content/uploads/n-ary-tree.png)

---

### Node
```js
class Node {
    constructor(value) {
        this.value = value;
        this.children = [];
    }
}
```

---

### Tree - Constructor
```js
class Tree {
    constructor(root) {
        this.root = root;
    }
}
```

---

### Tree - Insert
```js
class Tree {
    ...
    insert(key, node) {
        this.insertNode(this.root, key, node);
    }
    ...
}
```

---

### Tree - Insert Node
```js
class Tree {
    ...
    insertNode(currentNode, key, newNode) {
        if (currentNode.value === key) {
            currentNode.children.push(newNode);
            return;
        }

        for (const node of currentNode.children) {
            this.insertNode(node, key, newNode);
        }
    }
    ...
}
```


---

### Árvore do exemplo
![-](https://media.geeksforgeeks.org/wp-content/uploads/n-ary-tree.png)

---

### Recriando no código
```js

const tree = new Tree(new Node(1))
tree.insert(1, new Node(2))
tree.insert(1, new Node(3))

tree.insert(2, new Node(4))
tree.insert(2, new Node(5))
tree.insert(2, new Node(6))

tree.insert(5, new Node(7))
tree.insert(5, new Node(8))

tree.insert(3, new Node(9))
```

---

### Output
![-](https://media.discordapp.net/attachments/865042948571136022/1106253644925513739/image.png)

