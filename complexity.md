---
theme: "white"
transition: "fade"
title: "Complexidade de algoritmos"
enableMenu: true
enableSearch: true
enableChalkboard: true
slideNumber: true
controls: true
---

### Complexidade de algoritmos

---

![-](https://i0.wp.com/hyperspec.ai/wp-content/uploads/2023/01/3D7CAC80-4CF0-452A-81D5-8540D3C6C8CB.png?fit=620%2C654&ssl=1)

---

### Definição
A complexidade é usada para medir a velocidade de um algoritmo

---

### Por que isso é importante?

1. Limites de tempo estipulados.
2. Estratégias de resolução de problemas

---

### Qual será a nossa ferramenta?

Notação assintótica

---

### Exemplos de funções

- N²
- (3/2) *  N²
- 9999  * N²
- N²/1000
- N²+ 100 * N
- etc.

---

### Gráfico

![-](https://media.discordapp.net/attachments/865042948571136022/1238916825803128913/image.png?ex=664106b5&is=663fb535&hm=a32b9ac319d08d5f9b6baf0275bd65241a2b53f68750224ef1f459b7b498830b&=&format=webp&quality=lossless&width=638&height=643)

---

### Mesma classe

O(N²)

---

### Agora, no código

---

```cpp
int main() {
    vector<int> vetor = {4, 7, 2, 9, 1, 5, 8, 3, 6};
    int valorBusca = 5;
    int N = vetor.size();
    
    int indice = -1;
    for (int i = 0; i < N; ++i) {
        if (vetor[i] == valorBusca) {
            indice = i;
        }
    }
    
    return 0;
}
```

---

### Qual a complexidade de código que vimos?

---

### O código é O(N), mas por que?

Tamanho da entrada VS Quantidade de vezes que o código repete

---

### Outro exemplo

```cpp
int main() {
    vector<int> vetor = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    
    int soma = 0;
    for (int i = 0; i < vetor.size(); ++i) {
        soma += vetor[i];
    }
    
    cout << "A soma dos elementos do vetor é: " << soma << endl;
    
    return 0;
}
```

---

### Resposta: O(N)

---

```cpp
int main() {
    int N = 5; // Tamanho da matriz (5x5)

    vector<vector<int>> matriz(N, vector<int>(N));
    int valor = 1;

    for (int i = 0; i < N; ++i) {
        for (int j = 0; j < N; ++j) {
            matriz[i][j] = valor;
            valor++;
        }
    }
}
```

---

### Resposta: O(N^2)

---

```cpp
int buscaBinaria(vector<int>& vetor, int chave) {
    int esquerda = 0;
    int direita = vetor.size() - 1;

    while (esquerda <= direita) {
        int meio = esquerda + (direita - esquerda) / 2;
        
        if (vetor[meio] == chave)
            return meio; // Chave encontrada, retorna o índice
        else if (vetor[meio] < chave)
            esquerda = meio + 1; // Descarta a metade esquerda
        else
            direita = meio - 1; // Descarta a metade direita
    }

    return -1; // Chave não encontrada
}
```

---

### Resposta: O(log(N))

Vamos entender melhor

---

### N vs Iterações

- N = 1 | 1 iteração
- ...
- N = 3 | 2 iterações
- ...
- N = 6 | 3 iterações
- ...
- N = 9 | 4 iterações
- ...
- N = 17 | 5 iterações
- ...

---

### N vs Iterações

- N = 33 | 6 iterações
- ...
- N = 65 | 7 iterações
- ...
- N = 129 | 8 iterações


---

### 2^N | Iteração
<p>2^1 = 2 | 1 iteração</p>
<p>2^2 = 4 | 2 iterações</p>
<p>2^3 = 8 | 3 iterações</p>
<p>2^4 = 16 | 4 iterações</p>
<p>2^5 = 32 | 5 iterações</p>
<p>2^6 = 64 | 6 iterações</p>
<p>2^7 = 128 | 7 iterações</p>

---

### Ou seja

Na busca binária, para que eu faça 1 iteração a mais, a entrada precisa
dobrar de tamanho

---

### Dúvidas até aqui?

---

### Lets go

---

```cpp
int main() {
    int valor;

    cout << "Digite um valor inteiro: ";
    cin >> valor;

    int resultado = valor / 2;

    cout << "A metade do valor inserido é: " << resultado << endl;

    return 0;
}
```

---

### Resposta: O(1)

Quando o código repete um número fixo de vezes, independente da entrada

---

```cpp
int main() {
    vector<int> vetor = {9, 2, 5, 1, 7, 3, 8, 6, 4};

    sort(vetor.begin(), vetor.end());

    cout << "Vetor ordenado: ";
    for (int num : vetor) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}
```

---

### Resposta: O(N * log(N))

---

### E como que eu iria fazer para saber isso?

![-](https://media.discordapp.net/attachments/865042948571136022/1238925065626587186/image.png?ex=66410e61&is=663fbce1&hm=0064e774a958e8294f0685bfd55d7839f31b861b736dbb140aafe39e75bcf703&=&format=webp&quality=lossless&width=418&height=437)

---

### E como os limites ajudam a resolver questões?

---

### Limite do Judge

1s = 10^7, se quiser forçar um pouco, 10^8

---

### Questão beecrowd | 1259

![-](https://media.discordapp.net/attachments/865042948571136022/1238924130804437093/image.png?ex=66410d82&is=663fbc02&hm=c3f4d7a274d91ffffbd0a026fd6ecef22b796bcc85dbad0458840d99a24cabb8&=&format=webp&quality=lossless&width=1286&height=162)

---

### Uma solução O(N^2) passa?

---

### Então, vamos nos atentar aos limites

---

![-](https://media.discordapp.net/attachments/1131043448632397884/1224145170807914617/image.png?ex=6640ae48&is=663f5cc8&hm=1b0f59d6b4c87bca1eadce9abb6ab40d4e08a396442d2cd5058640315d29b371&=&format=webp&quality=lossless&width=798&height=643)

---

### Dúvidas?

---

![-](https://images3.memedroid.com/images/UPLOADED190/5ac8bc27abce2.jpeg)