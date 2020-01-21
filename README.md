# Data Types

Los principales tipos de data primitivos que existen dentro de JavaScript son: 
- ```string``` - Conjunto de caracteres. Se escribe entre comillas o doble comillas.
- ```number``` - Un número cualquiera, y se escribe simplemente poniendo el número.
- ```boolean``` - Siguiendo la lógica booleana, puede ser ```true``` o ```false```
- ```object``` - Conjunto de data.
- ```undefined``` - Ausencia involuntaria de valor.
- ```null``` - Ausencia voluntaria de valor.

Ejemplos:
```javascript
let name = "Arturo";
typeof(name) // string

let age = 34;
typeof(age) // number

let awake = true;
typeof(awake) // boolean

let album = {titulo: "Train of Thought", artista: "Dream Theater"};
typeof(album) // object

let planet;
typeof(planet) // undefined

let command = null;
typeof(command) // object
```
:warning: Si os dais cuenta, el ```typeof``` de ```null``` da ```object```. Esto ocurre porque cuando se creó JavaScript no se tuvo en cuenta el data type ```null``` cuando se creó la propiedad de ```typeof```. Lo correcto sería que diese ```null```. En resumen: es un error que nunca se corrigió.

## Concatenación

Prácticamente todos los data types de JavaScript se pueden sumar unos con otros. Los ejemplos más comunes que probablemente te vayas a encontrar son:

### string + string

El resultado de dos o más ```string``` será la suma de todos los sumandos.

Por ejemplo:

```javascript
"abre" + "latas" /// "abrelatas"
"Mi nombre es" + " " + "Jaime" // "Mi nombre es Jaime"

let dogsName = "Firulais";
let catsName = "Misifu";

"Mi perro se llama " + dogsName + " y mi gato se llama " + catsName // "Mi perro se llama Firulais y mi gato se llama Misifu"
```

Con ES6, se introdujo otra forma de concatenación llamada **Template String**. La sintaxis es la siguiente:

```javascript
let numberOfCars = 2;
let numberOfBikes = 3;

`Tengo un total de ${numberOfCars} coches y ${numberOfBikes} bicicletas` // "Tengo un total de 2 coches y 3 bicicletas"
```

### <data <data type>type> + string

En el caso de que se sume prácticamente cualquier otro data type con un ```string```, JavaScript interpretará ambos elementos como si fuesen strings.

Por ejemplo:

```javascript
let premio = "Tesoro" + 5 // "Tesoro5"
typeof(premio) // string

let trying = "aprendiz" + undefined // "aprendizundefined"
typeof(trying) // string

let example = "aprendiz" + true // "aprendiztrue"
typeof(example) // string
```

### <data <data type>type>+ number

Ya hemos visto qué ocurre cuando sumamos un ```string``` con un ```number```. Veamos ahora otros ejemplos de qué ocurriría si sumamos un ```number``` a otro tipo de data type:

```javascript
let firstNumber = 5 + true // 6
typeof(firstNumber) // number
```
- En el caso de los booleanos, ```true``` toma el valor de ```1``` y ```false``` toma el valor de ```0```.
```javascript
let secondNumber = 0.4 + undefined // NaN
typeof(secondNumber) // number
```
- En este caso, vemos ```NaN``` como resultado. ```NaN``` significa _Not a Number_. Este valor aparece cuando intentamos sumar dos valores entre los cuales uno de ellos no es un número. Paradójicamente, como podemos ver en la segunda línea de código, ```NaN``` es del tipo```number```.

```javascript
let thirdNumber = 12 + null // 12
typeof(thirdNumber) // number
```
- En este caso, ```null``` toma el valor de ```0``` ya que carece de valor. Esta es una de las principales diferencias entre ```null``` y ```undefined```: La primera toma un valor de 'ausencia de valor' mientras que la segunda no tiene ningún valor directamente.
