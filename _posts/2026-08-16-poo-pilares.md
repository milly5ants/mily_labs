---
layout: post
title: "O que é classe, objeto e POO?"
date: 2026-08-16
category: "POO"
description: "Atualmente, a POO é um dos paradigmas de programação mais utilizados, especialmente quando se necessita flexibilidade e reaproveitamento de código. Mas o que é POO, classes e objetos?."
image: "/assets/images/poo_classe_objeto.png"
read_time: "5 min"
---

POO é um dos paradigmas de programação onde, basicamente, organizamos o código em objetos e classes que representam coisas do mundo real. 
Por exemplo, em um jogo temos:

- Personagem - objeto 
- Espada - Objeto
- Inimigo - Objeto
- Castelo - Objeto

Um objeto, em sentido geral é: Aquilo que existe como uma coisa concreta ou abstrata e que pode ser percebido, tem carcacteristicas e estadp ou sobre o qual uma ação pode ser realizada.

Por exemplo: uma caneta
é algo concreto que pode ser percebido e pensado - check 
é algo que pode ter uma ação sobre ela: destampar, tampar - check 
é algo que pode ser percebido, tem caracteristicas - tem cor, tem quantidade de tinta, tamanho de ponta check
é algo que tem estado: pode estar com 90% de tinta e tampada nesse momento, mas num segundo momento pode ter 10% de tinta e estar destampada

caracteristica = atributos
ação = metodos


## Classe x Objeto

De forma resumida, a classe é uma forma e o objeto é algo que pode ser criado a partir dessa forma. Uma mesma forma pode criar varios objetos com caracteristicas diferentes.

por exemplo: A classe: caneta 
pode criar o objeto: caneta azul, caneta vermelha, caneta verde, caneta preta
o mesmo molde, cria varias canetas com cores diferentes por exemplo 
cada caneta de cor diferente nesse exemplo é um objeto instanciado da classe caneta 
cada caneta de cor diferente foi criada a partir da mesma forma 'caneta'

Quando dizemos que instanciamos um objeto queremos dizer que criamos um objeto a partir da classe. ou seja, a classe caneta poderia ter sido criada, mas ainda nao teriamos as canetas verde, vermelha e 

## Como isso é visto em Java?

Primeiro vamos criar a classe (molde) caneta 

```java
public class caneta {
 
}
```

agora vamos definir o atributo cor de uma caneta

```java
public class Caneta {
    public String cor;
 
}
```
agora vamos instanciar um objeto, ou seja criar uma caneta

```java
public class Caneta {

    public String cor;

    Caneta canetaAzul = new Caneta(); 
 
}
```

e agora vamos dar uma cor para nosso objeto criado 

```java
public class Caneta {

    public String cor;

    Caneta canetaAzul = new Caneta(); 
    canetaAzul.cor = "Azul";
 
}
```

Pronto, agora temos um objeto caneta azul criado a partir de uma classe. Mas eu posso criar quantas canetas eu quiser, a partir da classe:

```java
public class Caneta {

    public String cor;

    Caneta canetaAzul = new Caneta(); 
    canetaAzul.cor = "Azul";

    Caneta canetaPreta = new Caneta(); 
    canetaPreta.cor = "Preta";

    Caneta canetaVermelha = new Caneta(); 
    canetaVermelha.cor = "Vermelha";
 
}
```

class Caneta = cria a classe
new Caneta() = cria um objeto a partir da classe 

Caneta canetaPreta = new Caneta(); 
classe nomeObjeto recebe(cria) novo objeto Caneta


## Atributos x Metodos

Os atributos como vimos antes são as caracteristicas de um objeto. 
por exemplo: Caneta azul, com ponta 0.5, da marca Bic seria descrita assim em java 


```java
public class Caneta {

    public String cor;
    public float ponta;
    public String marca;

    Caneta canetaAzul = new Caneta(); 
    canetaAzul.cor = "Azul";
    canetaAzul.ponta = 0.5f;
    canetaAzul.marca = "Bic";
 
}
```

AGora uma caneta vermelha, com ponta 1.5 e da marca bic seria escrita assim 


```java
public class Caneta {

    public String cor;
    public float ponta;
    public String marca;

    // CANETA AZUL

    Caneta canetaAzul = new Caneta(); 
    canetaAzul.cor = "Azul";
    canetaAzul.ponta = 0.5f;
    canetaAzul.marca = "Bic";

    // CANETA VERMELHA

    Caneta canetaVermelha = new Caneta(); 
    canetaVermelha.cor = "Vermelha";
    canetaVermelha.ponta = 1.5f;
    canetaVermelha.marca = "Bic";
 
}
```

Os metodos sao ações que um objeto pode ter, no caso da caneta: escrever, rabiscar, destampar, tampar
Metodos em java sempre ficam dentro de classes e sao escritos assim:

```java
public class Caneta {

    public String cor;
    public float ponta;
    public String marca;

    // CANETA AZUL

    Caneta canetaAzul = new Caneta(); 
    canetaAzul.cor = "Azul";
    canetaAzul.ponta = 0.5f;
    canetaAzul.marca = "Bic";

    //METODO ESCREVER

    void escrever(){

    }

    //METODO DESTAMPAR
    
    void destampar(){

    }
 
}
```
e cada metodo pode ter suas regras. Vamos imaginar que o objeto caneta azul estivesse tampada. Se chamassemos o metodo escrever, não seria possivel porque ela esta tampada. Por isso, precisariamos primeiro destampar e depois escrever. seria algo assim

```java
public class Caneta {

    public String cor;
    public float ponta;
    public String marca;
    public boolean tampada;

    //METODO ESCREVER

    void escrever(){

        if (tampada) {
            System.out.println("Não posso escrever porque a caneta esta tampada!");
        } else {
            System.out.println("Escrevendo...");
        }

    }

    //METODO DESTAMPAR
    
    void destampar(){

        tampada = false;

    }

    public static void main(String[] args) {

        // CANETA AZUL
        Caneta canetaAzul = new Caneta();
        canetaAzul.cor = "Azul";
        canetaAzul.ponta = 0.5f;
        canetaAzul.marca = "Bic";
        canetaAzul.tampada = true;

        canetaAzul.destampar();
        canetaAzul.escrever();
    }
 
}
```

Se eu tentar escrever com a caneta tampada, eu vou receber a mensagem Não posso escrever porque a caneta esta tampada!, por isso precisamos chamar canetaAzul.destampar(); para mudar o estado da caneta e depois podemos escrever canetaAzul.escrever();

## Resumo

Classe = Molde 
Objeto = é algo concreto ou abstrato que tem caracteristica, estado e ações 
metodo = ações que um objeto pode ter 
atributos = caracteristicas de um objeto 
