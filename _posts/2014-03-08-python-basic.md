---
layout: post
title: Python Iniciando
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

##Python - Onde escrever AnD o que acontece???


Python é uma linguagem multiplataforma nativa em Linux/Unix, e facilmente instalada em <a href="http://www.python.org/download/windows/">Windows</a>. Não é necessário uma <i>IDE</i> para desenvolvimento, um bom editor de textos com sublime-text em conjunto com alguns <a href="https://sublime.wbond.net/packages/Python%20PEP8%20Autoformat">plugins</a> são suficientes para desenvolver bons softwares. Para fins de teste, o uso do próprio interpretador, sem a utilização de um editor de textos é indispensável, para usuários OSX existe o aplicativos chamado **IPython** como interpretador interativo do python. Abaixo links para conhecimento.

* <a href="http://www.sublimetext.com/3">Sublime-text</a>
* <a href="http://ipython.org/">Ipython</a>
* <a href="http://legacy.python.org/dev/peps/pep-0008/">Style Guide for Python Code - pep8</a>

Abrindo o terminal da máquina e digitando nele **python** será aberto o interpretador interativo do python, abaixo um exemplo.

<figure class="">
	<img src="/images/terminal_python.png" alt="">
</figure>

Com isso, tudo que for digitado após o  `>>>` será interpretado pelo **python** e não mais pelo SO.


###Primeiro programa

O programa abaixo foi retirado do site <a href="http://coffeeghost.net/pybat">**coffeeghost.net**</a> e modificado para explicação de alguns conceitos importantes da linguagem, salve em um arquivo com o nome `meu_primeiro_programa.py`

{% highlight python linenos %}
{% raw %}

import os


def main():

    print "Hello World"
    print "Hello World's"
    print 'Hello World\'s'

    functionTest(1, 25)

    print '=' * 10
    text = 'Diretório corrente é '
    print text + os.getcwd()

    counter = 0
    counter += 1

    foods = ['apple', 'orange', 'rice']

    for food in foods:
        print 'I like to eat ' + food

    print "Count to ten"

    for i in range(1, 11):
        print i


def functionTest(param1, param2):

    res = param1 + param2

    print "%s + %s = %s" % (param1, param2, res)

    if res < 50:
        print "Menor que 50"

    elif (res <= 50) and ((param1 == 42) or (param2 == 25)):
        print "Menor ou igual a 50 e param1 = 42 ou param2 a 25"

    else:
        print "Maior que 50"

        return res
        """
	Comentário de multiplas linhas
	"""

if __name__ == '__main__':
    main()
{% endraw %}
{% endhighlight %}


###Explorando o código


Salvando esse código em um arquivo chamado `meu_primeiro_programa.py` ele se torna um **módulo python**, módulos python são arquivos textos contendo código fonte python. Esse arquivo texto será processado pelo interpretador python, que irá parsear o código de cima para baixo da esquerda para direita. O python nem sempre trabalha com textos, ele sempre começa de um arquivo texto e cria um bytecode, esses bytecodes são cacheados em arquivos `.pyc` tendo uma melhor performance em uma próxima execução.

Na primeira linha do arquivo `meu_primeiro_programa.py` o interpretador do python encontra o comando `import os`, isso faz com que o python procure um módulo chamado `os.py` no diretório `site_packages`, leia o arquivo, processe de cima para baixo da esquerda para direita, gere o python cache `.pyc`, instancie um **objeto módulo** que se referencie aos objetos do módulo `os`. Na prática, dentro do programa `meu_primeiro_programa.py` será possível acessar as funções que estão escritas no módulo `os`, como podemos ver na linha 14, executamos a função `os.getcwd()` com isso estamos acessando uma instância de `os.py` chamada de `os`, e o `.getcwd()` se refere a uma função que não recebe parâmetros escrita no módulo `os.py`.

Python possui como demais linguagens de programação, palavras reservadas, `def` é uma delas e é utilizada para definição de função. Na linha 4 estamos definindo uma função que terá o nome de `main`. Python não possui **entry point** fixo, isso quer dizer que o nome main não é necessário, poderia ser carro ou bicicleta e funcionaria sem problemas. Após o nome `main` é utilizado o `()` que deixa explicito que main é uma função que não recebe argumentos, por último o caracter`:`, após o caracter `:` esperasse uma mudança na indentação, isso é necessário para definir o bloco de código que faz parte da função main.

Python diferencia um programa de uma biblioteca com as linha 50 e 51 do `meu_programa.py`, todo **entry point** em python é o próprio nome do módulo, só que o python sobrescreve no atributo do módulo chamado `__name__` a string `__main__` com isso utilizando o `if` é possível utilizar o mesmo código como biblioteca e programa.

As linhas 6, 7 e 8 demostram que python aceita `"` e  `'` para delimitar uma string, sendo necessário apenas abrir e fechar com o mesmo tipo.

Na linha 30 temos novamente a palavra reservada `def` seguida de `functionTest(param1, param2):` com isso é definido uma função chamada `functionTest` que irá receber dois parâmetros para seu funcionamento. A linha 10 chama a função passando os dois parâmetros separados por `,` quando python encontra o comando `functionTest(1, 25):` ele irá pular para linha 30 executar todo código do bloco da função e retornar para a linha 11.


Por ser uma linguagem fortemente tipada, não é possível realizar operações matemáticas sem ocorrer erros entre tipos diferentes de dados, porém, python nos dá um funcionalidade bastante interessante, que é a multiplicação de string, a linha 12 por exemplo irá imprimir `==========`
Na linha 14 temos a função `getcwd` que retorna o diretório atual, é utilizado `os.getcwd()` pois essa função esta presente no módulo `os`.`




