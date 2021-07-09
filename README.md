# Progrmación javascript
 
A continuación se presenta un resumen del libro eloquent javascript,
donde se encontrarán conceptos e información más destacada.


Cuando la acción deja de servirte, reúne información; cuando la  información deja de servirte, duerme..
*—Ursula K. Le Guin, La Mano Izquierda De La Oscuridad*

![Libro eloquent javascript](https://http2.mlstatic.com/D_NQ_NP_630894-MLM32153999967_092019-O.jpg)
## Conceptos Básicos

**Programaciòn:**  Es el acto de construir un programa - un conjunto
de instrucciones precisas que le dicen a una computadora que hacer.

**Còdigo:**  Es el texto que componen los programas.


## Historia de javascript
Javascript  esta integrado en cada navegador web moderno,
y por lo tanto esta disponible en casi todos los dispositivos. Este lenguaje usa el estandard ECMAScript.

Ha echo que las aplicaciones web modernas sean posibles, ya que aplicaciones con las que puedes interactuar ,
sin hacer una recarga de la página para cada acción a esto se le llama **interactividad**.

# Capitulo 1: Valores, tipos y operadores

Los datos son representados por bits, un bit es presentado por 0 y 1 formado por 8 digitos.

![Libro eloquent javascript](./imagenes/binarios.png)

Por ejemplo el número 13 esta representado en binario por 00001101, ya que 8 + 4 + 1 ,
es 13.


## Valores

Todos los valores estan formados por bits que juegan papeles diferentes. Cada valor tiene un tipo que determina su rol 
pueden ser números,pedazos de texto,funciones y asi sucesivamente.


Para llamar un valor solo se invoca su nombre, se almacenan en algun sitio de la memoria RAM.



## Nùmeros

Javascript utiliza valores de tipo number, los cuales utilizan especificamente 64 bits 
para poder alamacenar un solo valor nùmerico de tipo number, estos son por ejemplo:
* 5
* 13.4
* -4.9
* trillones(15 ceros)
* 2.989e8

### Aritmètica

Con los datos de tipo number se realizan operaciones aritmèticas como:
*suma,resta,multiplicaciòn,divisiòn y exponentes*.

Para realizar operaciones se usan signos a los que se les conoce como **operadores**:
suma(+), resta(-), multiplicaciòn(*), divisiòn(/) y residuo o modulo(%).

```javascript
let suma = 4 + 5
console.log(suma)
// 9
```

Recuerda que se usa:
* _Precedencia de operaciones:_ primero se realizaràn las divisiòn,multiplicaciòn y residuo. Despues las restas y sumas.
* _Tàmbien se respetan los parentesis_
* _En caso de no tener de realizan las operaciones de izquierda a derecha_

### Nùmeros especiales

Existen 3 valores especiales que no se comportan como números normales.
No se debe confiar mucho en estos valores ya que probablemente te puede dar un Nan(not a number)
* Infinity Infinidades: positivas
* -Infinity Infinidades: negativas


## Strings

Los valores de tipo string son usados para representar texto.
Existen 3 formas de representar un string:

```javascript
`Debajo en el mar`
"Descansa en el océano"
'Flota en el océano'
```

### Salto de linea

```
"Mi nombre es Brenda\nSoy ingeniera de Software"

// Mi nombre es Brenda
// Soy ingeniera de Software
```


### Concatenaciòn
 Se puede concatenar cadenas de texto usando el operador +.

```javascript
"Brenda" + "Yasmin"
// BrendaYasmin
```

### Interpolaciòn
Se usa para concatenar datos que no son de tipo string pero 
que necesita ser concatenados.

```javascript
let nombre = 4
console.log(`Mi nombre es ${nombre}`)

// Mi nombre es 4
```

### Operadores unarios

Se les llaman operadores unarios a los que se escriben con palabras por ejemplo:
Se le llama operador binario cuando se usan dos valores.
El operador de - es considerado como unario y bianario.


```javascript
let nombre = 4
console.log(typeof nombre)

// number
```


## Valores Booleanos

Este operador es para representar true o false.Para producir valores booleanos se
pueden generar asi:


```javascript
console.log(3>2)
// true
```

### Comparaciòn de string
Los string se pueden comparar las letras minùsculas son mayores,las mayùsculas son menores.
Despuès de izquierda a derecha comparando los còdigo Unicode uno por uno.

Puedes comparar con < (menor), > (mayor), >= (mayor o igual que), <= (menor o igual que), == (igual a), != (no igual a).

Solo hay un valor que no es igual a si mismo , y este es un NaN("No es un nùmero")


```javascript
console.log(NaN == NaN)
// false
```
Se supone que nan denota un resultado de una comparación sin sentido por lo tanto no es igual a otra comparación sin 
sentido.

### Operadores lògicos
Los operadores lógicos son usados para "razonar" sobre valores booleanos.
Existen 3 operadores logicos:
and (&&), not (||), diferente (!).

__Precedencia de operadores lògicos__
* ||
* &&
* Operadores de comparación(<,>,==,)
* Despuès el resto.


```javascript
1 + 1 == 2 && 10 * 10 > 50
// true
```

### Operadores ternarios
El operador ternario funciona como un if.
```javascript
// "resultado" ? "verdadero" : "falso"
console.log(true ? 1 : 2);
// 1
```

## Valores vacìos
Los valores null y undefined , que son usados
para denotar la ausencia de un valor significativo.
Producen undefined simplemente porque tienen
que producir algún valor.


## Conversiòn de tipo automàtica

Javascript puede aceptar cualquier cosa, incluso generando cosas extrañas.
Por ejemplo:

```javascript
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("cinco" * 2)
// → NaN
console.log(false == 0)
// → true
```

Cuando en un operador es aplicado u tipo de dato incorrecto, javascript  silenciosamente convertirà 
ese valor en el tipo que necesita , que usa una serie de reglas que no dan el resultado que quisieras 
se le conoce como  __coerciòn de tipo__.

Puedes compara con los operadores == o !=  un valor para _saber si es de tipo 
null,NaN,undefined_.

Cuando estas conviertiendo un string y numeros a un valor booleano cuando tus valores
__sean 0, Nan, (""") dan como resultado falso mientras que los demas valores regresan true.__


Los operadores === o !== prueba si el valor es precisamente igual  , el otro lo contrario.

Para prevenir que _conversiones de tipo inesperadas_ te estorben usa comparaciòn con los 3 signos,
pero cuando estés seguro de que el tipo va a ser el mismo en ambos lados, no
es problemático utilizar los operadores mas cortos.

### Corto circuito de operadores lògicos

__Funcion del operador O(||)__
Devolverá el valor de su izquierda cuando puede ser convertido a verdadero y de ser lo contrario devolverá el valor de la
derecha.

```javascript
// Devuelve el valor que es verdadero
console.log(null || "usuario")
// → usuario
console.log("Agnes" || "usuario")
// → Agnes

// Cuidado con la evaluaciòn de corto circuito.
console.log(true || "x") // Ya queno evaluara el segundo valor
// → true
```

__Funcion del operador O(&&)__
Funciona de manera similar, pero de forma opuesta. Cuando el valor a su 
izquierda es algo que se convierte a falso, devuelve ese valor, y de
lo contrario, devuelve el valor a su derecha.


```javascript
// devuelve el valor falso
console.log(null && "usuario")
// → null
console.log("Agnes" && "usuario")
// → usuario

// Cuidado con la evaluaciòn de corto circuito
console.log(false && "x") // Ya queno evaluara el segundo valor
// → true
```
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript
https://eloquentjavascript.net/code/#1
https://guides.github.com/features/mastering-markdown/
https://react-tutorial.app/