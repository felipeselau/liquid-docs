# Liquid Basics

## Linguagem de Programação Liquid

Liquid é uma linguagem de programação simples e flexível usada para criação de templates em diversas aplicações web. Ela é frequentemente utilizada em conjunto com plataformas como Shopify e Jekyll. Com Liquid, você pode gerar conteúdo dinamicamente, aplicar lógica e manipular dados nos templates.

Algumas características importantes do Liquid incluem:

- Variáveis: Você pode atribuir e usar variáveis para armazenar e exibir dados.
- Filtros: Os filtros permitem modificar a saída das variáveis ou realizar operações nelas.
- Tags: As tags são usadas para fluxo de controle e lógica, como declarações condicionais e loops.
- Objetos: Objetos representam estruturas de dados e podem ser acessados e manipulados usando notação de ponto.

Liquid oferece um conjunto poderoso de ferramentas para criar templates dinâmicos e personalizáveis. É relativamente fácil de aprender e oferece grande flexibilidade para desenvolvedores e designers.

A principal área de atuação do Liquid é a criação de templates em aplicações web. Para usar Liquid, é necessário ter conhecimentos básicos de programação, como variáveis, lógica condicional e loops. Também é importante ter familiaridade com a manipulação de dados e a sintaxe da linguagem. Com esses conhecimentos, é possível utilizar o Liquid para gerar conteúdo dinâmico e personalizado nos templates.

### Variáveis em Liquid

Em Liquid, as variáveis são usadas para armazenar e exibir dados. Elas podem ser usadas para exibir informações dinâmicas nos templates.

Para criar uma variável em Liquid, você pode usar o seguinte formato:

```
{% assign nome_da_variavel = valor %}

```

Aqui está um exemplo de como criar e exibir uma variável chamada "nome" com o valor "John":

```
{% assign nome = "John" %}
{{ nome }}
```

Neste exemplo, a variável "nome" armazena o valor "John" e é exibida no template usando

 `{{ nome }}`.

Você também pode atribuir o valor de uma variável a outra variável:

```
{% assign nome = "John" %}
{% assign sobrenome = nome %}
{{ sobrenome }}
```

Neste caso, a variável "nome" é atribuída à variável "sobrenome" e a saída será "John".

As variáveis em Liquid são extremamente úteis para a exibição de dados dinâmicos nos templates.

## Objetos em Liquid

Em Liquid, os objetos representam estruturas de dados e podem ser usados para acessar e manipular informações nos templates. Eles são frequentemente utilizados para exibir dados de produtos, pedidos ou outras informações relacionadas.

Para acessar as propriedades de um objeto em Liquid, você pode usar a notação de ponto. Por exemplo, se tiver um objeto chamado "produto" com as propriedades "nome" e "preco", você pode acessar essas propriedades da seguinte forma:

```
{{ produto.nome }}
{{ produto.preco }}

```

Aqui está um exemplo mais completo que mostra como utilizar objetos em Liquid:

```
{% assign produto = {
  "nome": "Camiseta",
  "preco": 29.99,
  "disponivel": true
} %}

Nome: {{ produto.nome }}
Preço: {{ produto.preco | currency }}
Disponível: {% if produto.disponivel %}Sim{% else %}Não{% endif %}

```

Neste exemplo, criamos um objeto chamado "produto" com as propriedades "nome", "preco" e "disponivel". Em seguida, exibimos essas informações no template utilizando a notação de ponto para acessar as propriedades do objeto. Além disso, utilizamos o filtro `currency` para formatar o valor do preço como uma moeda.

Os objetos em Liquid são muito úteis para exibir informações detalhadas e dinâmicas nos templates, como detalhes de produtos, informações de clientes, entre outros.

## Filtros em Liquid

Os filtros em Liquid permitem modificar a saída das variáveis ou realizar operações nelas. Eles são usados para formatar dados, converter tipos, aplicar cálculos e muito mais. Aqui estão alguns exemplos de filtros em Liquid:

### capitalize

O filtro `capitalize` é usado para capitalizar a primeira letra de uma string. Por exemplo:

```
{{ "hello world" | capitalize }}

```

Saída: Hello world

### upcase

O filtro `upcase` é usado para converter uma string em letras maiúsculas. Por exemplo:

```
{{ "hello world" | upcase }}

```

Saída: HELLO WORLD

### downcase

O filtro `downcase` é usado para converter uma string em letras minúsculas. Por exemplo:

```
{{ "HELLO WORLD" | downcase }}

```

Saída: hello world

### date

O filtro `date` é usado para formatar uma data. Ele aceita um argumento opcional para especificar o formato da data. Por exemplo:

```
{{ "2022-01-01" | date: "%d/%m/%Y" }}

```

Saída: 01/01/2022

### size

O filtro `size` é usado para obter o tamanho de uma string, array ou objeto. Por exemplo:

```
{{ "hello" | size }}

```

Saída: 5

### plus

O filtro `plus` é usado para adicionar um número a uma variável. Por exemplo:

```
{% assign number = 5 %}
{{ number | plus: 3 }}

```

Saída: 8

Esses são apenas alguns dos filtros disponíveis em Liquid. Eles oferecem uma ampla gama de funcionalidades para manipulação e formatação de dados nos templates.

## Lógica e Tomada de Decisões em Liquid

Em Liquid, você pode usar tags condicionais para realizar renderização condicional com base em certas condições. Aqui estão algumas das tags condicionais mais comuns em Liquid:

### if

A tag `if` é usada para realizar uma verificação condicional. Você pode usar operadores de comparação, como `==`, `!=`, `<`, `>`, `<=`, `>=`, para comparar valores ou variáveis. Aqui está um exemplo de uso da tag `if`:

```
{% if condition %}
  <!-- Se a condição for verdadeira, execute este bloco de código -->
{% else %}
  <!-- Caso contrário, execute este bloco de código -->
{% endif %}

```

### unless

A tag `unless` é semelhante à tag `if`, mas executa o bloco de código apenas se a condição for falsa. Aqui está um exemplo de uso da tag `unless`:

```
{% unless condition %}
  <!-- Se a condição for falsa, execute este bloco de código -->
{% else %}
  <!-- Caso contrário, execute este bloco de código -->
{% endunless %}

```

### elsif

A tag `elsif` é usada para adicionar condições adicionais em uma estrutura `if`. Ela verifica se uma condição é verdadeira após as condições anteriores terem sido avaliadas como falsas. Aqui está um exemplo de uso da tag `elsif`:

```
{% if condition1 %}
  <!-- Se a condição 1 for verdadeira, execute este bloco de código -->
{% elsif condition2 %}
  <!-- Caso contrário, se a condição 2 for verdadeira, execute este bloco de código -->
{% else %}
  <!-- Caso contrário, execute este bloco de código -->
{% endif %}

```

### case/when

A tag `case/when` é usada para realizar uma verificação condicional com várias opções. Ela verifica uma variável ou valor em relação a várias condições e executa o bloco de código correspondente à primeira condição verdadeira. Aqui está um exemplo de uso da tag `case/when`:

```
{% case variable %}
  {% when value1 %}
    <!-- Se a variável for igual a value1, execute este bloco de código -->
  {% when value2 %}
    <!-- Caso contrário, se a variável for igual a value2, execute este bloco de código -->
  {% else %}
    <!-- Caso contrário, execute este bloco de código -->
{% endcase %}

```

Essas são algumas das tags condicionais que você pode usar em Liquid para realizar renderização condicional e tomada de decisões nos seus templates. Elas permitem que você exiba ou execute blocos de código com base em condições específicas.

## Loops e Iterações em Liquid

Em Liquid, você pode usar tags de loop para realizar iterações em listas, arrays e outros tipos de dados. Isso permite que você execute blocos de código repetidamente com base nos elementos de uma coleção.

Aqui estão algumas das tags de loop mais comuns em Liquid:

### for

A tag `for` é usada para iterar sobre uma coleção de elementos. Você pode especificar uma variável de loop e um objeto ou array para iterar. Aqui está um exemplo de uso da tag `for`:

```
{% for item in collection %}
  <!-- Execute este bloco de código para cada item na coleção -->
  {{ item }}
{% endfor %}

```

Você também pode acessar o índice do item e o número total de itens usando a variável `forloop`. Aqui está um exemplo:

```
{% for item in collection %}
  Item: {{ item }}
  Índice: {{ forloop.index }}
  Total: {{ forloop.length }}
{% endfor %}

```

### cycle

A tag `cycle` é usada para alternar entre valores em loops. Ela permite que você alterne dinamicamente entre uma lista de valores em cada iteração. Aqui está um exemplo de uso da tag `cycle`:

```
{% for item in collection %}
  {{ item }} - {% cycle 'odd', 'even' %}
{% endfor %}

```

Neste exemplo, a tag `cycle` é usada para alternar entre os valores 'odd' e 'even' a cada iteração.

### limit

A tag `limit` é usada para limitar o número de iterações em um loop. Ela permite que você especifique o número máximo de vezes que o loop deve ser executado. Aqui está um exemplo de uso da tag `limit`:

```
{% for item in collection limit:3 %}
  <!-- Execute este bloco de código para os primeiros 3 itens na coleção -->
  {{ item }}
{% endfor %}

```

Neste exemplo, o loop é limitado a 3 iterações.

### break

A tag `break` é usada para interromper um loop antes que todas as iterações sejam concluídas. Ela permite que você saia do loop prematuramente com base em uma condição. Aqui está um exemplo de uso da tag `break`:

```
{% for item in collection %}
  {% if condition %}
    <!-- Se a condição for verdadeira, saia do loop -->
    {% break %}
  {% endif %}
  {{ item }}
{% endfor %}

```

Essas são algumas das tags de loop que você pode usar em Liquid para realizar iterações e loops nos seus templates. Elas permitem que você execute blocos de código repetidamente e manipule os elementos de uma coleção de dados.

## Listas e Ordenação de Listas

Em Liquid, você pode manipular listas e realizar ordenações de diferentes maneiras. Aqui estão algumas das funcionalidades relacionadas a listas em Liquid:

### Criando uma lista

Você pode criar uma lista em Liquid utilizando a seguinte sintaxe:

```
{% assign minha_lista = [item1, item2, item3] %}

```

Por exemplo, para criar uma lista de frutas, você pode usar:

```
{% assign frutas = ["maçã", "banana", "laranja"] %}

```

### Acessando itens de uma lista

Para acessar um item específico de uma lista em Liquid, você pode utilizar o índice do item. Os índices começam em 0, ou seja, o primeiro item tem índice 0, o segundo item tem índice 1 e assim por diante. Aqui está um exemplo de como acessar itens de uma lista:

```
{% assign frutas = ["maçã", "banana", "laranja"] %}
Primeira fruta: {{ frutas[0] }}
Segunda fruta: {{ frutas[1] }}
Terceira fruta: {{ frutas[2] }}

```

Neste exemplo, estamos acessando e exibindo itens específicos da lista de frutas.

### Iterando sobre uma lista

Para iterar sobre os itens de uma lista em Liquid, você pode utilizar a tag `for`. Aqui está um exemplo de como iterar sobre os itens de uma lista:

```
{% assign frutas = ["maçã", "banana", "laranja"] %}
{% for fruta in frutas %}
  {{ fruta }}
{% endfor %}

```

Neste exemplo, estamos iterando sobre a lista de frutas e exibindo cada item individualmente.

### Ordenando uma lista

Em Liquid, você pode ordenar uma lista em ordem alfabética ou numérica utilizando o filtro `sort`. Aqui está um exemplo de como ordenar uma lista em ordem alfabética:

```
{% assign frutas = ["maçã", "banana", "laranja"] %}
{% assign frutas_ordenadas = frutas | sort %}
{% for fruta in frutas_ordenadas %}
  {{ fruta }}
{% endfor %}

```

Neste exemplo, estamos ordenando a lista de frutas em ordem alfabética e, em seguida, iterando sobre a lista ordenada e exibindo cada item.

Você também pode ordenar uma lista em ordem numérica utilizando o filtro `sort_natural`:

```
{% assign numeros = [10, 2, 5, 1, 8] %}
{% assign numeros_ordenados = numeros | sort_natural %}
{% for numero in numeros_ordenados %}
  {{ numero }}
{% endfor %}

```

Neste exemplo, estamos ordenando a lista de números em ordem numérica e, em seguida, iterando sobre a lista ordenada e exibindo cada número.

### Revertendo uma lista

Em Liquid, você pode reverter a ordem dos itens em uma lista utilizando o filtro `reverse`. Aqui está um exemplo de como reverter uma lista:

```
{% assign frutas = ["maçã", "banana", "laranja"] %}
{% assign frutas_revertidas = frutas | reverse %}
{% for fruta in frutas_revertidas %}
  {{ fruta }}
{% endfor %}

```

Neste exemplo, estamos revertendo a ordem dos itens na lista de frutas e, em seguida, iterando sobre a lista revertida e exibindo cada item.

Essas são algumas das funcionalidades relacionadas a listas em Liquid. Elas permitem que você crie, acesse, itere, ordene e reverta listas de forma flexível nos seus templates.

## Herança de Templates

A herança de templates é uma poderosa funcionalidade do Liquid que permite reutilizar e estender templates existentes. Com a herança de templates, você pode criar um template base com elementos comuns e, em seguida, criar templates filhos que herdam esses elementos e podem adicionar ou substituir partes específicas.

Para criar uma herança de templates, você precisa definir um template base e templates filhos que estendem o template base. Aqui está um exemplo de como criar uma herança de templates:

Template base (`base.liquid`):

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>{% block title %}Título Padrão{% endblock %}</title>
  {% block styles %}{% endblock %}
</head>
<body>
  <header>
    <h1>{% block heading %}Cabeçalho Padrão{% endblock %}</h1>
  </header>
  <main>
    {% block content %}{% endblock %}
  </main>
  <footer>
    <p>{% block footer %}Rodapé Padrão{% endblock %}</p>
  </footer>
</body>
</html>

```

Template filho (`child.liquid`):

```
{% extends 'base.liquid' %}

{% block title %}Meu Título{% endblock %}

{% block styles %}
  <link rel="stylesheet" href="styles.css">
{% endblock %}

{% block heading %}Meu Cabeçalho{% endblock %}

{% block content %}
  <h2>Conteúdo Personalizado</h2>
  <p>Este é o meu conteúdo personalizado.</p>
{% endblock %}

{% block footer %}
  <p>Meu Rodapé</p>
{% endblock %}

```

Neste exemplo, o template base `base.liquid` define a estrutura básica do HTML e utiliza blocos (`{% block %}`) para indicar as áreas que podem ser estendidas ou substituídas pelos templates filhos. Os templates filhos (`child.liquid`) estendem o template base utilizando a diretiva `{% extends %}` e substituem ou adicionam conteúdo nos blocos definidos pelo template base.

Ao renderizar o template filho, o Liquid irá substituir os blocos definidos no template base pelos conteúdos específicos do template filho. O resultado final será a combinação do template base com as modificações e adições feitas pelo template filho.

A herança de templates é uma maneira eficiente e organizada de criar templates flexíveis e reutilizáveis, permitindo que você tenha um código mais modular e fácil de manter.

## Depuração e tratamento de erros

Embora a linguagem Liquid seja relativamente simples e não tenha tags específicas para depuração e controle de erros como algumas linguagens de programação mais complexas, você pode usar algumas técnicas e tags para ajudar a depurar e gerenciar erros em seus templates Liquid:

**Tag `{{ output | inspect }}`**: Você pode usar a tag **`{{ output | inspect }}`** para imprimir variáveis ou objetos em seu template. Isso pode ser útil para verificar o valor de uma variável e depurar problemas. Por exemplo:

```
{{ some_variable | inspect }}
```

**Tags condicionais**: Use tags condicionais como **`{% if %}`** para verificar se uma variável atende a determinadas condições. Isso pode ajudar a controlar o fluxo do seu template com base em valores variáveis. Por exemplo:

```
{% if product.price > 100 %}
  Este produto é caro.
{% else %}
  Este produto é acessível.
{% endif %}
```

**Tags `capture` e `assign`**: Você pode usar as tags **`capture`** e **`assign`** para armazenar valores em variáveis temporárias e usá-los posteriormente em seu template. Isso pode ser útil para simplificar seu código e torná-lo mais legível. Por exemplo:

```
{% capture product_title %}{{ product.title }}{% endcapture %}
```

**Gestão de exceções**: Embora Liquid não tenha um mecanismo completo de gestão de exceções como algumas linguagens de programação, você pode usar tags condicionais para lidar com erros. Por exemplo:
