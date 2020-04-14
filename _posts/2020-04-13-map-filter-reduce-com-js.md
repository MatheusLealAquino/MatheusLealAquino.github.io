---
layout: post
title: Map, Filter e Reduce com JS
author: Matheus Leal
date: '2020-04-13 09:02:00 +3'
category: JavaScript
summary: Aprenda sobre map, filter e reduce com JS
thumbnail: javascript.png
---

<p>Olá a todos! hoje iremos falar sobre map, filter e reduce utilizando javascript. </p>

<b>Imagine que temos o seguinte conjunto de dados:</b>
<pre>
  const carros = [
    {
      nome: 'Onix',
      motor: 1.0,
      fabricante: 'Chevrolet',
      kmRodados: 10010,
      lancamento: 2019
    },
    {
      nome: 'Kwid',
      motor: 1.0,
      fabricante: 'Renault',
      kmRodados: 10000,
      lancamento: 2018
    },
    {
      nome: 'Up!',
      motor: 1.0,
      fabricante: 'Volkswagen',
      kmRodados: 100000,
      lancamento: 2017
    },
    {
      nome: 'Sandero',
      motor: 1.6,
      fabricante: 'Renault',
      kmRodados: 20000,
      lancamento: 2018
    },
    {
      nome: 'Uno',
      motor: 1.0,
      fabricante: 'Fiat',
      kmRodados: 20500,
      lancamento: 2000
    }
  ]
</pre>

<h5>Map:</h5>

```
The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.
```
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map"> texto retirado de developer.mozilla.org </a> <br>

E como isso funciona? Vamos imaginar o nosso array de objetos com informações sobre carros acima. Recebemos uma tarefa que é necessário multiplicar por dois todos os valores de quilômetros rodados dos carros. Nesta situação, podemos utilizar o map porque este método percorre todos os valores do nosso array e utiliza nossa função de callback para cada elemento.<br>

<pre>
  carros.map(el => {
    // Multiplica valor do objeto e atribui a variável do objeto
    el.kmRodados *= 2;
    return el;
  })
</pre>

<b>Temos nosso array de carros modificado:</b>
<pre>
  [
    {
      nome: 'Onix',
      motor: 1.0,
      fabricante: 'Chevrolet',
      kmRodados: 20020,
      lancamento: 2019
    },
    {
      nome: 'Kwid',
      motor: 1.0,
      fabricante: 'Renault',
      kmRodados: 20000,
      lancamento: 2018
    },
    {
      nome: 'Up!',
      motor: 1.0,
      fabricante: 'Volkswagen',
      kmRodados: 200000,
      lancamento: 2017
    },
    {
      nome: 'Sandero',
      motor: 1.6,
      fabricante: 'Renault',
      kmRodados: 40000,
      lancamento: 2018
    },
    {
      nome: 'Uno',
      motor: 1.0,
      fabricante: 'Fiat',
      kmRodados: 41000,
      lancamento: 2000
    }
  ]
</pre>

<h5>Filter:</h5>

```
The filter() method creates a new array with all elements that pass the test implemented by the provided function.
```
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter"> texto retirado de developer.mozilla.org </a> <br>

<p>O método filter retorna um novo array com base nos valores que retornarem <i>true</i> do método passado como callback. Utilizando nosso array de carro, vamos filtrar para os carros que foram lançados após 2017.</p>

<pre>
  const carrosMaisNovos = carros.filter(el => {
    return el.lancamento > 2017;
  })
</pre>

<b>Temos como retorno:</b>
<pre>
  [
    {
      nome: 'Onix',
      motor: 1.0,
      fabricante: 'Chevrolet',
      kmRodados: 20020,
      lancamento: 2019
    },
    {
      nome: 'Kwid',
      motor: 1.0,
      fabricante: 'Renault',
      kmRodados: 20000,
      lancamento: 2018
    },
    {
      nome: 'Sandero',
      motor: 1.6,
      fabricante: 'Renault',
      kmRodados: 40000,
      lancamento: 2018
    }
  ]
</pre>

<p>Bem simples, não? O método filter é bem útil para implementar, por exemplo, uma busca em uma tabela na sua aplicação.</p>

<h5>Reduce:</h5>

```
 The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.
```
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce"> texto retirado de developer.mozilla.org </a> <br>

<p>Após multiplicar as quilometragens, reduzir nosso array para os carros que possuem o lançamento após 2017, agora vamos realizar a soma do total de quilometragem destes carros filtrados. E para isso usaremos o reduce em que este método consiste em percorrer o array e retornar um único valor após sua execução. Este método possui um acumulador que é a variável que mantém o registro da última soma realizada, uma variável currentElement que é o <i>n</i> item do array utilizado e a variável initialValue que passa o valor inicial para a variável acumuladora.</p>

<pre>
  const initialValue = 0;
  const totalKm = carrosMaisNovos.reduce((accumulator, currentElement) => {
    return accumulator + currentElement.kmRodados;
  }, initialValue);
  // totalKm = 80020
</pre>

<p>O map, filter e reduce são métodos que me auxiliam bastante no meu dia a dia durante o desenvolvimento pois são métodos poderosos e não são difíceis de serem utilizados.</p>
<p>Espero que este breve tutorial possa te ajudar e qualquer dúvida pode entrar em contato comigo pelo meu email ou em alguma das minhas redes sociais.</p>
Até o próximo post!