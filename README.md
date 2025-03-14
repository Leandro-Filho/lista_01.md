# M1 do Leandro Precaro B. Filho

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
``a) A saída será undefined seguido de erro ``

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


```javascript
JUSTIFICATIVA: no primeiro console.log deu apenas indefinido porque, por ser var, ele identifica que existe uma variavel x no código por poder ser lida no código inteiro, mas como a variavel está abaixo do console, ele não consegue identificar. Já o segundo console.log deu erro, por conta da variável ser let, assim, só o que está abaixo dele ou dentro do  escopo que ele pertence consegue indentificar se existe aquela variável, por estar abaixo, o console ve que não existe nenhuma variavel y, dando erro.
```

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

``b) Substituir if (a || b === 0) por if (a === 0 && b === 0)``

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

```javascript
JUSTIFIQUE: primeiramente é necessario trocar ||(OU) por &&(E), já que queremos retiar a possibilidade das duas icógnitas serem nulas. Segundo, precisamos dividir a verificação do numero nulo porque juntos, como tava inicialmente, verifica o seguinte: se um dos numeros for igual a zero, dara "erro: número inválido", mas como queremos que ele verifique que OS DOIS não sejam nulos, o certo será verificar um de cada vez.
```
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
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

a) O código imprime 1000.

``b) O código imprime 200.``

c) O código imprime 50.

d) O código gera um erro.


```javascript
JUSTIFIQUE: como é um switch, ele analisará cada caso antes do break, como existe apenas uma variavel, a que aparecer na linha mais abaixo será o valor na hora de imprimir. O break acontece no primeiro porque no console.log, ele pede para verificar case("eletronico"), então ele irá parar no primeiro break que aparecer. Como existe dois valores para preco antes do primeiro case, o que vale é o que está mais abaixo, que no caso é o case("vestuário") que tem o valor de 200.
```

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

``d) 24``


```javascript
JUSTIFIQUE: let numeros é uma lista. Analisando o let resultado, temos o seguinte passo a passo: primeiro ele pede para multiplicar cada item da lista por dois, feito isso temos [2, 4, 6, 8, 10], depois ele pede pra filtrar/retira os valores menores que 5, ficando [6, 8, 10]. Após isso, ele pede para somar todos os valores da lista, então 6+8+10=24.
```
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

``c) ["banana", "abacaxi", "manga", "laranja"]``

d) ["banana", "maçã", "uva", "abacaxi", "manga"]


```javascript
JUSTIFIQUE: novamente uma lista com quatro itens, no qual as posições são 0, 1, 2, 3 respectivamente. Na segunda linha, ele chama a lista e pede para emendar na posição 1 e 2 os itens "abacaxi" e "manga", assim trocando o que estava na lista horiginal pelo o que vai ser emendado.
```
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


``a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.``

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.


```javascript
JUSTIFIQUE: item 1 é verdadeiro pelo o que é a herança em javaScript, no qual o que ta escrito é a definição pura de como ela funciona. Já a 2 é verdadeira porque para interligar uma classe a outra é necessário sempre utilizar class ITEM1 extends ITEM2 para que o item 1 herde os métodos e propriedades do ITEM2. E sim, a segunda justifica a primeira pelo fato de ao herdar coisas de outra classe, não é necessário reescrever o código.
```
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

``a) I e II são verdadeiras.``

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

```javascript
JUSTIFICATIVA: a 1 está correta porque a class filha (funcionario) consegue modificar atributos da class mãe (pessoa) através do super(), ou seja, modifica diretamente o que foi herdado. a 3 ta errada porque o JavaScript consegue sim supportar a herança, tanto que a questão 1 e 2 está correta.
```
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

``b) A asserção é verdadeira e a razão é falsa.``

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

```javascript
JUSTIFIQUE: razão está errada porque não tem o método sobrecarga nativamente em JavaScript, mas em outras linguagens como C++ da sim para ter a sobrecarga.
```

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicando sua solução para cada problema.

```javascript
function somaArray(numeros) {
    let soma = 0;//criar variavel soma = 0 para defini-la e iniciar com valor nulo
    for (i = 0; i < numeros.length; i++) { // colocamos length para que percorra a lista inteira 
        soma += 2*numeros[i]; // adicionamos (soma +=...) para que ele some todas as multiplicações feitas em cada elemento da lista
    }
    return soma; //retornar com os valores multiplicados e somados em um unico resultado 
}
console.log(somaArray([1, 2, 3, 4])); //imprimir o resultado =20 e lista colocada subtituira a variavel numeros
```

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`
```javascript
class Produto { //classe Pai
    constructor(nome, preco){ //propriedades
        this.nome = nome;
        this.preco = preco;
    }
    calcularDesconto(){
        return this.preco*0.1; //Metodos
        
    }
}

class Livro extends Produto { //classe  filha
    constructor(nome, preco){ //propriedades herdadas da classe pai
        super(nome, preco);
    }
    calcularDesconto2(){ //metodos
        return super.calcularDesconto() * 2; //metodo herdado da classe pai, aproveitando o código, só dobramos a porcentagem
    }
}

//descobrir se o código da calsse pai está funcionando
const produto1 = new Produto("Agenda", 30);
console.log(`Desconto do Produto: R$ ${produto1.calcularDesconto()}`); 

//descobrir se o código da calsse filha está funcionando
const livro1 = new Livro("O Príncipe: Maquiavel", 400);
console.log(`"Desconto no Livro 'O Príncipe: Maquiavel': R$ ${livro1.calcularDesconto2()}`);

```