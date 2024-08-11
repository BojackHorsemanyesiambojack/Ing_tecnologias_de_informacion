# Ing_tecnologias_de_informacion - Material de estudio mdfks
<code>//Autor: Johandry Luna</code>
## Nada de introducciones, empecemos.

## 1-Javascript


### 0 - Preparacion del entorno

Para preparar el entorno deberas crear el archivo html de toda la vida, sin embargo deberas agregar la etiqueta:

```Javascript
<script src = 'DIRECCION DE TU ARHIVO JS'></script>
```
Esta etiqueta conecta tu archivo html con el arhivo javascript, sin embargo es recomendable ponerla hasta el final del archivo
(ANTES DE CERRAR EL <code>`<body>`</code>) Ya que de esta forma el archivo se cargara cuando el navegador haya leido el resto del html.
### 1 - Basicos
---

#### 1:1 - Variables

Para declarar variables en javascript, a diferencia de lenguajes como Java, c#, c++ o otros, no necesitas especificar el tipo de la variable, en 
javascript se dispone de 3 formas para declarar una variable:

```Javascript
const variable1 = 1;
let variable2 = 2;
var variable3 = (variable1 + variable2); //Aunque no se suele usar 'var' ya que se considera una mala practica.
//El valor de variable3 es 3.
```
Aunque sin embargo puedes usar el metodo <code>typeof</code> para ver de que tipo es una variable.
```Javascript
console.log(typeOf('SoyUnString');
//Esto imprime 'String'
```
En javascript constamos con varios tipos de objetos:
```Javascript
const intV = 2; //Number
const StrV = 'String';
const boolV = true; //Boolean
const arrV = []; //Array: los arrays en javascript pueden contener diferentes tipos de objetos sin restricciones
const ObjV = {} //Objeto: los objetos de javascript almacenan objetos con indices textuales EJEMPLO ADICIONAL DE OBJETO:
let person = {
  name: "Alice",
  age: 30,
  greet: function() {
    console.log("Hello!");
  }
};

}
```

#### 1:2 - Hola Mundo en javascript

Para hacer un hola mundo en javascript podemos usar la funcion:
<code>alert()  //Esta funcion mostrará un aviso personalizado a la parte superior de la pantalla,recibe un valor a mostrar</code>
Ahora para hacer tu sencillo hola mundo con tu entorno preparado, debes pasar el valor a mostrar a la funcion <code>alert()</code>
```Javascript
alert('Hola mundo');
```
Luego de ejecutar esto, listo, tu pagina deberia mostrar un aviso diciendo 'Hola mundo'.

Otra forma es usar la funcion <code> console.log //imprime en la consola de inspeccion </code>
de esta manera igualmente:
```Javascript
console.log('Hola mundo')
```
Para ver lo que acabas de imprimir, entra a inspeccion y luego a consola.

#### 1:3 Acceder a elementos HTML desde Javascript

Para guardar los elementos HTML como variables, se usaran las funciones de <code>document //libreria integrada dedicada a manipular el DOM</code>
las cuales son:
```Javascript
document.getElementById(ID DE TU ELEMENTO);
document.getElementsByClass(CLASE QUE QUIERES USAR);
document.querySelector(AQUI PUEDES COLOCAR UNA #ID o .CLASE);
```

Ahora supongamos que tienes este elemento en tu html:

```HTML
<h1 id = "soy-un-h1>Hola</h1>
```
Para usarlo en javascript podemos declarar la variable de la siguiente manera

```Javascript
const miH1 = document.getElementById('soy-un-h1');
```

#### 1:4 Funciones
Las funciones en javascript pueden retornar o no retornal algun valor y se pueden declarar de la siguiente manera:
```Javascript
function HolaMundo(){
return "Hola mundo";
}

//o puedes usar la "funcion flecha"

const HolaMundo => () = {
return "Hola mundo";
}
```

#### 1:5 onClick (html)
Los botones de html poseen la funcion <code>onClick()</code> que recibe la funcion a invocar en el javascript (sobra decir que ya debes tener le javascript vinculado).
por ejemplo:
```HTML
<body>
 <script>const holaMundo = () => {alert('Hola mundo)}</script>
 <button onclick = "holaMundo()">Decir Hola Mundo</button>
</body>
<!--Al presionar el boton, la pagina lanzara una alerta con el texto 'Hola mundo'-->
```
#### 1:6 InnerHtml / InnerText 

El InnerText permite manipular el texto de un objeto html (DOM) de cualquier manera, haremos algo sencillo, supongamos que tienes este elemento en tu html:
```HTML
<h1 id = "test">Cambia este texto</h1>
```
Cambiaremos ese texto usando javascript, seria bueno agregar un boton:
En javascript:
```Javascript
const test = document.getElementById('test');

function cambiarTexto(){
test.innerText = 'Cambiado'
}
```
En html:
```HTML
<h1 id = "test">Cambia este texto</h1>
<button onclick="cambiarTexto()">Cambiar texto</button>
//El texto del h1 cambia a 'Cambiado' cuando se presiona el boton.
```
InnerHtml se diferencia en el hecho de que controlamos todo el DOM del objeto y no solo el texto, podemos usarlo para limpiar un div entero:
```Javascript
const test = document.getElementById('test');

function LimpiarDiv(){
test.innerHTML = '';
}
```
```HTML
<div id="test">
 <ul>
 <li>Carlos es cochon</li>
 <li>Fernanda Bermudez se la come</li>
 <li>Jennifer color Carton</li>
 <li>Por eso no tienes novia</li>
 <ul>
</div>
<button onclick="LimpiarDiv()">Limpiar</button>
//El div se a limpiado al presionar el boton.
```
Ahora hagamos una funcion que agregue algo en ese div.
```Javascript
function decirVerdad(){
 test.innerHTML = '<h1>A Carlos lo sorprendio un negro</h1>';
}
```
```HTML
<div id="test">
</div>
<button onclick="decirVerdad()">Limpiar</button>
//Va a aparecer un h1 diciendo una verdad en el div cuando se presione el boton
```

#### 1:7 createElement(), appendChild()

Podemos crear un nuevo elemento html con la funcion createElment() que recibe en string el tipo de algun objeto HTML,
a la vez tenemos la funcion appendChild la cual hace que un objeto html renderize otro elemento dentro de si y se accede dentro de objetos html en js.
<b>Ejemplo</b>
```Javascript
let test = document.getElementById('test'); //supongamos que es una lista

let element document.createElement('li');
element.innerText = 'Esto es el objeto de una lista';
test.appendChild(element);

//La lista 'test' renderizara 'element' dentro de si.
```

###Ejercicio practico: Crea una pagina que muestre un numero que inicie en 0, al lado un boton que cuando lo presiones haga que el numero vaya aumentando.
