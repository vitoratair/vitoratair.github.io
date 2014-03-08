---
layout: post
title: Python tipos de dados
description: "Python básico"
modified: 2014-03-06
tags: [python, software, desenvolvimento]
image:
  feature: abstract-3.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
comments: true
share: true
---

##Tipos de dados

Tudo em python é objeto, e sua filosofia vai além de outras linguagens de programação OO, todos os valores de dados no Python são encapsulados em classes de objetos, e tudo em um programa python é um objeto acessível a partir do programa, até mesmo o código fonteque se esta escrevendo.

Em C, por exemplo, para se armazenar um número inteiro deverá ter um código como o abaixo.

{% highlight C linenos %}
{% raw %}

int var;
var = 19;

{% endraw %}
{% endhighlight %}

Em um código escrito em Python, simplesmente se tem

{% highlight python linenos %}
{% raw %}

var = 19

{% endraw %}
{% endhighlight %}

Por trás, o runtime do python cria um objeto integer e designa a variável para fazer referência ao novo objeto, e a mágica é que por ser uma linguagem de tipagem dinâmica, é possivel atribuir valores de outros tipos na mesma variável que python irá alterar o objeto para o tipo necessário sem interferencia do programador.

<figure class="">
	<img src="/images/type-var-python.png" alt="">
</figure>

##Operadores aritmétricos

<figure class="">
	<img src="/images/operadores.png" alt="">
</figure>

##Operações bit-a-bit

<figure class="">
	<img src="/images/bit-a-bit.png" alt="">
</figure>


