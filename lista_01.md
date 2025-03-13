# ponderada_semana6
# Lista de Exercícios 01

## Questões Objetivas

### 1) Saída do código:
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
**Resposta:**
- **Alternativa certa:** a) A saída será `undefined` seguido de erro.
- **Justificativa:** A variável `x` sofre hoisting, mas apenas sua declaração é elevada, resultando em `undefined`. A variável `y`, declarada com `let`, não sofre hoisting da mesma forma e gera um erro quando acessada antes da declaração.

---

### 2) Correção do código:
```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```
**Resposta:**
- **Alternativa correta:** a) Substituir `if (a || b === 0)` por `if (a === 0 || b === 0)`
- **Justificativa:** O operador `||` não verifica `b === 0` corretamente. A verificação correta exige `a === 0 || b === 0` para validar se algum dos valores é zero.

---

### 3) Saída do código:
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }
    return preco;
}
console.log(calcularPreco("eletrônico"));
```
**Resposta:**
- **Alternativa correta:** b) O código imprime `200`.
- **Justificativa:** O `switch` não tem `break` após `preco = 1000;`, então ele continua para o próximo caso (`vestuário`) e redefine `preco` para `200` antes de sair.

---

### 4) Saída do código:
```javascript
let numeros = [1, 2, 3, 4, 5];
let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);
console.log(resultado);
```
**Resposta:**
- **Alternativa correta:** c) `18`
- **Justificativa:** Multiplicação por 2 gera `[2, 4, 6, 8, 10]`, filtrando valores `>5` fica `[6, 8, 10]`, e a soma total é `18`.

---

### 5) Conteúdo do array após `splice`:
```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```
**Resposta:**
- **Alternativa correta:** c) `["banana", "abacaxi", "manga", "laranja"]`
- **Justificativa:** O `splice(1, 2, "abacaxi", "manga")` remove `maçã` e `uva` e insere `abacaxi` e `manga` no lugar.

---

### 6) Sobre herança em JavaScript:
**Resposta:**
- **Alternativa correta:** a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.
- **Justificativa:** `extends` permite herança, e a herança evita repetição de código, tornando a reutilização mais eficiente.

---

### 7) Análise de código:
**Resposta:**
- **Alternativa correta:** a) I e II são verdadeiras.
- **Justificativa:** A classe `Funcionario` herda `Pessoa`, acessa diretamente `nome` e `idade` e usa `super.apresentar()` para manter a funcionalidade original antes de adicionar sua própria lógica.

---

### 8) Polimorfismo em JavaScript:
**Resposta:**
- **Alternativa correta:** b) A asserção é verdadeira e a razão é falsa.
- **Justificativa:** JavaScript permite polimorfismo por sobrescrita de métodos, mas não por sobrecarga como em outras linguagens (Java, C++).

---

## Questões Dissertativas

### 1) Correção do código:
```javascript
function somaArray(numeros) {
    let soma = 0; // Inicializa soma corretamente
    for (let i = 0; i < numeros.length; i++) { // Troca .size por .length
        soma += 2 * numeros[i]; // Acumula valores corretamente
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
**Correções:**
1. `soma` precisa ser inicializada (`let soma = 0;`).
2. `.size` não é uma propriedade válida para arrays, `numeros.length` é o correto.
3. A soma deve acumular os valores (`soma += 2 * numeros[i];`) ao invés de apenas substituir `soma`.

---

### 2) Herança com classes `Produto` e `Livro`:
```javascript
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    calcularDesconto() {
        return this.preco * 0.9; // 10% de desconto
    }
}

class Livro extends Produto {
    calcularDesconto() {
        return this.preco * 0.8; // 20% de desconto
    }
}

let produto1 = new Produto("Celular", 1000);
console.log(produto1.calcularDesconto()); // Saída: 900

let livro1 = new Livro("JavaScript Avançado", 100);
console.log(livro1.calcularDesconto()); // Saída: 80
```
**Explicação:**
- A classe `Produto` define atributos e um método `calcularDesconto()`.
- `Livro` herda de `Produto` e sobrescreve `calcularDesconto()` para aplicar um desconto maior.
- O uso de herança evita código duplicado e permite a personalização dos métodos nas subclasses.

---

**Instruções finais:**
- Teste os códigos no VS Code antes de enviá-los.
- Publique o arquivo `lista_01.md` no repositório e envie o link pela Adalove.
