# Tutorial de Angular Js V1

El siguiente tutorial tiene como objetivo, brindar de manera rapida pero eficiente, todos los conocimientos necesarios para empezar a desarrollar en Angular JS V1, esto quiere decir que finalizado el curso, deberian tenerse claro:

- Los conecptos y teoria fundamental de Angular JS
- Como integrar/Instalar el Framework en tu proyecto.
- Lo mas importante, como producir.

La idea es sobreyevar todos los temas de manera practica y directa al grano, sin desviaciones engorros, para que al finalizar, te sea posible desarrollar un producto en Angular con completa fluidez y confianza. Por supuestom no se cubre todo el contenido de angular, ya que es un Framework bastante extenso, y seria innecesario pues su documentacion es bastante completa: 

https://angularjs.org/

Sin embargo los elementos cubiertos son los necesarios para poder realizar un desarrollo minimo viable con el Framework. De antemano aclaro, el tutorial esta escrito con palabras claras y concisas, evitando el uso constante de terminos tecnicos en momentos no Idonoes, evitando confundir al lector, nuvamente hago incapie, el objetivo claro es: Tener la confianza y solides de producir.

## Contenido del Curso:

- Introduccion: Que es Angular Js.
- Conceptos basicos fundamentales.
    * Two ways data binding.
    * Scope
    * Bootstrapping
- Instalacion.
- Defnir el App de Angular.
- Configurar tu primer Controlador.
- Hola Mundo en Angular Js.
- Los Servicios
    * El servicio $http
- Las directivas
- Directivas mas usadas:
    * ng-app
    * ng-controller
    * ng-model
    * ng-click
    * ng-repeat
    * ng-if
    * ng-show
    * ng-hide
    * ng-class
    * ng-mouseover
    * ng-src
- Los filtros
- Filtros mas usados:
    * date
    * number
    * lowercase
    * uppercase
    * currency
- ***Proyecto 1***
- Filtros personalizados
- Servicios personalizados
- Directivas personalizadas
- Creando un SPA (Single page applications)
- Configuracion del modulo de Angular Js.
- Sistema de Rutas.
- ***Proyecto 2***

## Introduccion: Que es Angular Js.

Es un framework MVC de código abierto desarrollado por Google y escrito en Javascript, que trabaja del lado del cliente (client-side) y nos permite hacer más dinámica nuestra aplicación web, trabajando de la mano con otras tecnologías como HTML y CSS, así como librerías de terceros.El curso actual esta enfocado en Angular Js V1 en cualquiera de sus sub-versiones. 

En palabras simples, Angular hace mas practico el trabajo de integracion del modelo, es decir nuestra estructura de datos, con nuestro controlador, el lugar donde se ejecuta la logica que resuelve el problema, y la vista, e decir el HTML, el lugar donde se presenta la interfaz al usuario y se capturan los datos de entrada. Todo esta intercomunicacion del MVS ocurre en tiempo real gracias a un paradigma manejado por Angular, llamado ***Two ways data binding (TWDB)***, o algo asi en espaniols: ***Enlace de datos bi-dereccional***, si alteramos una variable o parametro bien sea en la vista o el controlador, angular se encarga de que ambos lados del modelo, esten al tanto del cambio.

```
vita (HTML)   < ---- (Angular TWDB) -------> Controller (Js file)
```

## Conceptos basicos fundamentales

### a) Two ways data binding

Ya hablamos anteriormente de este aspecto, no es mas que un paradigma utilizado por angular, el cual se encarga de mantener tanto la vista como el controlador "Actualizados" en tiempo real, en base a los cambios (Por ejemplo altrar el valor de una variable) realizados en cualquier de los lados. Mas adelante cuando se empiece el desarrollo sera mas facil comprender este aspecto por medio de la practica.

### b) Scope

En espaniol  ***ambito*** es el universo en el cual existe y perdura una variable, funcion, etc. Angular, con el objetivo de maximizar la modularizacion, pretende que trabajemos siempre en Ambitos, es decir, siempre que definamos un controlador con todas sus variables y funciones, estas mismas solo podran ser usadas en la vista asociada a este controlador, siempre y cuando las funciones y variables esten cargadas en el $scope o ambito. Si intentamos usar una variable fuera del template (html) asociado a un controlador particular, resultara en ***undefined***. Posteriormente veremos ejemplo practicos de esto al realizar el primer ejercicio, hola mundo!.

### c) Bootstrapping

Es concepto no es mas que el ambito el cual ***gobierna*** y existe la aplicacion de angular, si no realizamos este paso, la vista ni el controlador sabran de la existencia de Angular Js. Existen varias tecnicas para hacer el ***Bootstrapping*** de angular, por ejemplo, que gobierne todo el body del documento presente, de esta manera, en cualquier punto del proyecto donde se encuentre, existira Angular. En el curso aprenderemos a hacer el bootstraping a un elemento / tag html, esto lo veremos de manera rapida y clara en la seccion ***Defnir el App de Angular***.

## Instalacion

Antes de nada, por favor clonar el repo actual para tener los ejemplos y trabajar en base a los mismos, despues de clonar y entrar al directorio clonado, continua el proceso.

Existen multiples maneras de instalar Angular, la forma mas simple simple, pero obsoleta, es descarga su js minificado, como en cualquier otra libreria, y llamarlo en en un tag script, en el header de tu html. puedes descargarlo del a siguiente url:

https://angularjs.org/

La manera mas moderna, es intalarlo con npm, aprovechando las nuevas tecnologias, una vez tengas instalado npm en tu OS, entra al directorio, example y ejecuta el comando a continuacion:

```
npm install angular@1.5.6
```

con esto, tendremos una copia local de angular en el directorio ***node_modules***, ya podemos usar el tag script para llamar a angular desde su version local minificada que puedes encontrar dentro de node_modules.

## Defnir el App de Angular

Como buenas practicas, vamos a crear un nuevo archivo llamado ***app.js*** dentro del directorio ***src***, este nombre es opcional, sin embargo es una convencion de la comunidad angular y es recomendarlo llamar asi.

En el contenido tendremos el siguiente codigo:

```
var app = angular.module('Nombre', []);
```

***EXPLICACION DEL CODIGO***

## Configurar tu primer Controlador

Ahora vamos a crear un nuevo archivo js para tener nuestro controllador, no es obligatorio pero se recomienda tener los controlladores separados, es decir un por js y usar la siguiente nomenclatura para su nombre: ***nombre.controller.js***. Dentro del a carpeta src/controllers, debe crear su primer controlador y llenarlo con el siguiente contenido:

```
app.controller("calendarCtrl", function($scopet){
    //contenido del controlador aqui
});
```

***EXPLICACION DEL CODIGO***

## Hola Mundo en Angular Js

NOTA: Usaremos el archivo index.html para llevar adelante el ejemplo.

Ya tenemos nuestra app y primer controlador, ahora, debemos llamar a ambos archivos js en nuestro proyecto por medio de tag script despues de haber llamado a angular js quedando similar a:

```
<script type="text/javascript" src="angular.js"></script>
<script type="text/javascript" src="app.js"></script>
<script type="text/javascript" src="nombre.controller.js"></script>
```

***NOTESE EL ORDEN***

- En nuestra etiqueta ***body*** agregamos el atributo ng-app. ***Explicacion***
- En nuestra etiqueta  ***div*** con clase container agregamos el atributo ng-controller. ***Explicacion***
- En nuestro controller agregamos el siguiente codigo:

```
$scope.titulo = "Hola mundo";
```

En el html remplazamos el contenido del <h2> por la etiqueta:

```
{{titulo}}
```

Explicacion de lo hecho hasta el momento:
- Bootstraping del app de Angular al body.
- Bootstraping del controlador a un div, solamente en este ambito existe el titulo!

## Los Servicios

Los servicios en Angular son usados desde el lado controlador, y tal como su nombre lo dice sirven, tienen comportamientos estandares deficinidos, como funciones, para simplicar la modularidad y el trabajo, el servicio que mas usamos es el $http.

***Como agregamos/inyectamos un servicio?***

### Servicio $http

```
// Simple GET request example:
$http({
  method: 'GET',
  url: '/someUrl'
}).then(function successCallback(response) {
    // this callback will be called asynchronously
    // when the response is available
  }, function errorCallback(response) {
    // called asynchronously if an error occurs
    // or server returns response with an error status.
  });
```

***Explicacion y ejemplo usando el json Local***

## Las directivas

Las directivas en AngularJS permite la manipulación y reutilización de código HTML, angular cuenta con una enorme cantidad de directivas, y la posibilidad de crear tus propias directivas para realizar componentes graficos como plugines, calendarios, datepickers, carruseles, o simplemente funciones que manipulen la manera visual como se muestra a data. Las directivas son usadas desde el lado VISTA pero creadas y configuradas desde el lado controllador. En el caso de las directivas nativas de angular todas ya estan configuradas por tanto las usaremos desde el lado VISTA (HTML).

## Directivas mas usadas:  

- ng-app
- ng-controller
- ng-model
- ng-src
- ng-repeat
- ng-if
- ng-show
- ng-hide
- ng-class
- ng-mouseover
- ng-click

## Los filtros

Tal como su nombre lo Indica permiten tanto filtrar como alterar los valores que Usamos en angular JS desde la vista o el controlador, mas frecuentemente lo hacemos desde la Vista. Con esta herramienta podemos "dar formato" a los valores que se pasan desde el controlador, diractamente en la vista sin alterar su valor original.


### Filtros mas usados:

***Referenciar el uso en la doc de angular***

- date
- number
- lowercase
- uppercase
- currency
