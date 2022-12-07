# HTML

En este apartado utilizaremos las abreviaturas de ***Emmet*** para acelerar nuestra manera de "codear" (o escribir código en criollo) en HTML.

A continuación un listado rápido

* [Construir esqueleto HTML](#construir-esqueleto-html "")
* [Etiquetas básicas](#etiquetas-básicas "")
* [Introducir una etiqueta dentro de otra](#introducir-una-etiqueta-dentro-de-otra "")
* [Clases](#clases "")
* [ID's](#ids "")
* [Combinatoria](#combinatoria "")
* [Atributos](#atributos "")
* [Contenido](#contenido "")

Ahora veremos "Emmet" algo más complicado
* [Emmet intermedio](#emmet-intermedio "")
* [Etiquetas hermanos e hijos](#etiquetas-hermanos-e-hijos "")
* [Escalando](#escalando "")
* [Agrupar](#agrupar "")
* [Crear varias etiquetas repetidas](#crear-varias-etiquetas-repetidas "")
* [Escribir una iteración numérica](#escribir-una-iteración-numérica "")
* [Multiplicación y $](#multiplicación-y "")
* [Nombres de etiqueta implícitos](#nombres-de-etiqueta-implícitos "")
* [Envolver con etiquetas](#envolver-con-etiquetas "")
* [Lorem Ipsum](#lorem-Ipsum "")
* [Codificando](#codificando "")

## Construir esqueleto HTML

Para ello tan solo será necesario escribir el siguiente carácter: ! y presionar ENTER o TAB.

Resultado:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```
## Etiquetas básicas

Para crear etiquetas HTML básicas, simplemente escriba el nombre de la etiqueta y presione Enter. Observe cómo **Emmet** coloca su cursor dentro de la etiqueta. Ahora está configurado para continuar escribiendo dentro de la etiqueta.

* Intente escribir: ``div`` y luego Enter, o ``h1`` Enter, o ``p`` Enter.
* Estos también funcionan: ``bq`` para un ``<blockquote>``, ``hdr`` para un ``<header>``, ``ftr`` para un ``<footer>``, ``btn`` para un ``<button>`` y ``sect`` para un ``section``.

## Introducir una etiqueta dentro de otra

Hay una forma muy útil para poder escribir varias etiquetas e introducirlas una dentro de otra.

El formato es el siguiente:

```CS
etiqueta>etiqueta2
```
### ***!!!NOTA***:

LA NOTACIÓN ES SIN ESPACIOS, A VECES DEJO ESPACIOS PARA FACILITAR LA LECTURA!!!

## Clases

Si está familiarizado con CSS, Emmet usa la misma forma para referirse a las clases usando un **``.``** ; para definir un ``class`` junto con la etiqueta:

* ``div.wrapper``
```HTML
<div class="wrapper"></div>
```
* ``h1.header.center``
```HTML
<h1 class="header center"></h1>
```

## ID's

Los ``id`` funcionan de manera muy similar:

* ``div#container``

```HTML
<div id="container"></div>
```
## Combinatoria

Se pueden comnar `id` y `class`

* ``div#container.wrapper``

```HTML
<div id="container" class="wrapper"></div>
```
## Atributos

También podemos especificar atributos para las etiquetas:

* ``img[src="cat.jpg"][alt="foto de gato"]``

```HTML
<img src="cat.jpg" alt="foto de gato" />
```
## Contenido

Para incluir contenido dentro de la etiqueta, simplemente envolvemos el contenido entre llaves **``{ }``**:

* ``p{Esto es un párrafo}``

```HTML
<p>Esto es un párrafo</p>
```

---
# Emmet intermedio

Ahora veremos `Emmet` más avanzado porque usaremos conjuntos de elementos.

## Etiquetas hermanos e hijos

Cada vez se pone mejor. También podemos especificar etiquetas hermanos e hijos usando los caracteres **``+``** y **``>``** :

* ``section+section``

```HTML
<section></section>
<section></section>
```

* ``ul>li``
```HTML
  <ul>
    <li></li>
  </ul>
```
Es decir, si queremos crear un contenedor ``div`` con una etiqueta ``section`` y meter dentro de ella otra etiqueta llamada ``article``, deberíamos escribir: ``div > section > article``:

```html
  <div>
    <section>
      <article></article>
    </section>
  </div>
```
Si queremos ir más allá y queremos meter otro ``div`` dentro de la etiqueta ``section`` y dentro de ese ``div`` un ``a``, deberíamos escribir:

    div>section>article>div>a

```HTML
  <div>
    <section>
      <article>
        <div><a href=""></a></div>
      </article>
    </section>
  </div>
```
Según vayamos escribiendo correctamente las estructuras con la correcta notación ``Emmet`` veremos un recuadro del resultado de esa abreviación.

## Escalando

Tienes que intentar imaginar lo que estás construyendo en tu cabeza mientras escribes la taquigrafía de Emmet. En este ejemplo, "treparemos" por la estructura HTML usando **``^``**.

* ``div+div>p>span+em^bq``
```HTML
<div></div>
<div>
  <p><span></span><em></em></p>
  <blockquote></blockquote>
</div>
```
Aquí, queríamos que la etiqueta en blockquote estuviera al mismo nivel que el párrafo. Por eso, necesitábamos "*trepar*". De lo contrario, estaría dentro del párrafo.

## Agrupar

Si su estructura es muy compleja, es posible que desee agrupar etiquetas en lugar de atravesar trepando.
En este ejemplo, crearemos un encabezado (header) y un pie de página (footer) sin escalar usando paréntesis **``( )``**.

* ``div>(header>ul>li>a)+footer>p``

```HTML
  <div>
    <header>
      <ul>
        <li><a href=""></a></li>
      </ul>
    </header>
    <footer>
      <p></p>
    </footer>
  </div>
```
## Crear varias etiquetas repetidas

Si queremos crear varias etiquetas repetidas, podemos utilizar el operador **``*``** seguido del número que indicará la cantidad de repeticiones.

* ``a*5``

```HTML
<a href=""></a><a href=""></a><a href=""></a><a href=""></a><a href=""></a>
```
Al ser una etiqueta en línea se repitieron una al lado de otro.

## Escribir una iteración numérica

Si queremos escribir una iteración numérica, debemos utilizar el símbolo **``$``** seguido del número que indicará la cantidad de iteraciones.

Si queremos crear 5 etiquetas p, y que cada una de ellas tenga una clase diferente, enumerada del 1 al 5, debemos poner:

* ``p.clase$*5``

```HTML
  <p class="clase1"></p>
  <p class="clase2"></p>
  <p class="clase3"></p>
  <p class="clase4"></p>
  <p class="clase5"></p>
```
Como vimos, el **``$``** hará que por cada iteración se sume 1 al número a introducir y el operador **``*``** lo que hará será crear la cantidad de p especificadas.

## Multiplicación y $

Como vimos antes nosotros podemos generar múltiples etiquetas multiplicando **``(*)``** y enumerando elementos en secuencia usando un signo de dólar **``($)``**.

* ``ul>li*5``

```HTML 
  <ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>
```
* ``ul>li{Item $}*3``

```HTML 
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
```
Incluso puede personalizar la secuencia de numeración rellenando con ceros, comenzando con un número específico e incluso en la dirección inversa.

* Pad con ceros: ``u>li.item$$$*5``

```HTML 
  <u>
    <li class="item001"></li>
    <li class="item002"></li>
    <li class="item003"></li>
    <li class="item004"></li>
    <li class="item005"></li>
  </u>
```
* Comience con un número específico: ``ul>li.item$@3*5``

```HTML 
  <ul>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
    <li class="item6"></li>
    <li class="item7"></li>
  </ul>

```
* Dirección inversa: ``ul>li.item$@-*5``

```HTML 
  <ul>
    <li class="item5"></li>
    <li class="item4"></li>
    <li class="item3"></li>
    <li class="item2"></li>
    <li class="item1"></li>
  </ul>
```
* Dirección inversa desde un número específico: ``ul>li.item$@-3*5``

```HTML 
  <ul>
    <li class="item7"></li>
    <li class="item6"></li>
    <li class="item5"></li>
    <li class="item4"></li>
    <li class="item3"></li>
  </ul>
```
## Nombres de etiqueta implícitos

Hay ciertas etiquetas que no es necesario escribir y pueden estar implícitas.

1. Una clase definida inicialmente sin etiqueta estará implícita como ``<div>``.

* ``.wrapper``
```HTML 
<div class="wrapper"></div>
```

2. Una clase definida dentro de una etiqueta de énfasis estará implícita como ``<span>``.

* ``em>.enfasis`` 
```HTML 
<em><span class="enfasis"></span></em>
```

3. Una clase definida dentro de una ``<li></li>`` estará implícita como un elemento de lista.

* ``ul>.item`` 
```HTML 
  <ul>
    <li class="item"></li>
  </ul>
```

4. Una clase definida dentro de una tabla estará implícita como ``<tr>`` y dentro de una fila será un ``<td>``.

* ``table>.fila>.col``

```HTML 
  <table>
    <tr class="fila">
      <td class="col"></td>
    </tr>
  </table>
```

## Envolver con etiquetas

Habrá ocasiones en las que tenga un código existente que desee envolver con una etiqueta.

Simplemente resalte el código que desea envolver y abra la paleta de comandos **(F1)**. Luego busque **Emmet:** *Encapsular con abreviatura* **``Emmet: Wrap with Abbreviation``**. A continuación, se le presentará un cuadro de diálogo donde puede escribir el ``elemento``.

* ``test`` en el documento HTML, y en el recuadro escribir ``div``

```HTML 
  <div>test</div>
```
También puede utilizar la sintaxis estándar de Emmet en este cuadro de diálogo. Intente ajustar un poco de texto con: 
* ``span.wrapper``

```HTML 
<span class="wrapper"></span>
```
De forma predeterminada, esta funcionalidad no está asignada a un método abreviado de teclado. Por lo tanto, si lo usa con frecuencia, es posible que desee agregar un acceso directo personalizado para él.

## Lorem Ipsum

*"Lorem Ipsum"* es un texto ficticio utilizado por los desarrolladores para representar datos en una página. Simplemente escriba ``lorem`` y presione Enter. Emmet generará 30 palabras de texto falso que puede usar como relleno en su proyecto.

También se puede definir la cantidad de palabras generadas.

* ``lorem10`` te dará 10 palabras de texto aleatorio.
* `lorem*5` te dará 5 párrafos aleatorios de texto de relleno.

```HTML 
<p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. In, temporibus.</p>
```

## Codificando

* ``ul .mi-lista > lorem10 .item-$ *5``
```HTML 
  <ul class="mi-lista">
    <li>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ratione, praesentium.</li>
    <li>Tempore eos harum totam dolores, fugiat non magnam amet ratione!</li>
    <li>Nam, officia aliquam eveniet recusandae corporis voluptatibus provident cumque facilis!</li>
    <li>Perferendis placeat sunt optio officiis quibusdam, sequi quos? Est, consectetur?</li>
    <li>Sint optio praesentium adipisci fugiat libero laboriosam consectetur necessitatibus obcaecati.</li>
  </ul>
```
* ``header>section>div>a[href=#][id=enlacito][name=enlacitito]*4{Hazme clic!}^p{Qué pasa?????}*4``

```HTML 
  <header>
    <section>
      <div><a href="#" id="enlacito" name="enlacitito">Hazme clic!</a><a href="#" id="enlacito" name="enlacitito">Hazme clic!</a><a href="#" id="enlacito" name="enlacitito">Hazme clic!</a><a href="#" id="enlacito" name="enlacitito">Hazme clic!</a></div>
      <p>Qué pasa?????</p>
      <p>Qué pasa?????</p>
      <p>Qué pasa?????</p>
      <p>Qué pasa?????</p>
    </section>
  </header>
```
---

[**&#11176;** *Anterior* &#11007;](/README.md "Menu principal") 
[Siguiente **&#129042;**](/CSS/01emmetCSS.md"")

---

[*Volver* **&ldca;**](/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")