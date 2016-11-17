# Synthetical Awesome Stylesheets WS

## Introducción

Este es un taller básico para los que quieran aprender a utilizar SASS (syntetically awesome stylesheets). Contiene conceptos como nesting, variables, mixins y extends.

## Objetivos

* Ver como transforma el código scss a css.
* Simplificar el código css de manera drástica

En este taller tenemos un html plano y comenzaremos a darle estilo. Por cierto, yo no soy diseñador, no esperen que la página se vea hermosa! 

# Lets get started!

## Por que usar SASS

Escribir CSS suena divertido, pero muchas veces el código se puede volver inmantenible. SASS te hace la vida más sencilla con las funciones que tiene, en especial al momento de leer el código.

Veremos de que manera puede ser eso.

## CSS Plano

Que es...?

* Selectores
* Propiedades y valores
* Propiedades básicas
    * background-color
    * color
    * font-family
    * display
    * float
    * height & width
    * left, right, top & bottom
    * border
    * padding

![alt-text](https://ironion.com/wp-content/uploads/2015/07/boxmodel.png)

## Variables

Así como en cualquier otro lenguaje de programación, nosotros también podemos usar variables. Aquí, las variables se definen de la siguiente manera:

``` 
$variable = valor;
```

Para que nos sirven las variables:
* Mejor control 
* Fácil acceso
* Evitar repetición de código

Una variable puede tomar valores como: 
* color
* numero
* text
* propiedades (como bottom, top, etc)

## Nesting

Básicamente es una declaración dentro de otra declaración. En CSS normal, algo como ```.clase1 .clase2``` puede llegar a sonar repetitivo. Ahora imagina que tienes 3 o más de esa y ocupas agregar una 4ta. 

SASS nos ayuda a que esto sea sencillo. En otras palabras, nesting es:

```
.clase1 {
    .clase2 {
        background-color: blue;
    }
}
```

Donde esto se compila a CSS como:

```
.clase1 .clase2 {
    background-color: blue;
}
```

## Mixins

Cuando llegamos a tener mucho código repetido, ocupamos una manera sencilla de manejarlo sin copiar y pegar este mismo. 

Los mixins en SASS nos ayudan a definir reglas que usaremos mucho y que simplemente incorporaremos dentro de nuestras condiciones. Ejemplo:
 
```
@mixin sample {
    font-size: 12px;
}

p {
  @include sample;
}
```

Esto nos generará un código de la siguiente manera:
 
```
p {
  font-size: 12px;
}
```

## Extends

Extends sirve para cuando tienes una regla en un selector que el 2do selector donde lo estás usando aplique para ella. Ejemplo:

```
.selector-A {
    @extend .selector-B;
    unicorn: true;
}

.selector-B {
    rainbow: true;
}
```

Esto se interpreta como:

```
.selector-A {
    unicorn: true;
}

.selector-B,
.selector-A {
    rainbow: true;
}
```
## Buena estructuración

Para mantener todo ordenado, es necesario tener una estructura sólida desde la base. Para ello, la manera sass de tener estructurado tu proyecto es tener en orden las siguientes cosas:

1. Modulos: mixins, funciones, variables
2. Partials: Reglas, donde se construye el proyecto en si
3. Vendor: todo lo que se trate de 3rd party services (librerias)

## SASS Orientado a Objetos

Una de las reglas de nesting es: no llegar a un nivel más de 4. Esto puede ser complicado de mantener y de sobreescribir. Para solucionar esto, es necesario tener una mentalidad orientado a objectos.

Dejar que los elementos del DOM tomen los atributos necesarios para definir su comportamiento. Por ejemplo, tenemos estas 3 clases:
 
```
.btn {
    border-radius: 10px;
}

.btn-primary {
    background: blue;
}

.btn-large {
    width: 200px;
    height: 100px;
}

```

Con esto, en el html definimos cuales botones serán primarios, cuales botones serán grandes, y así.\

## Conclusion

SASS puede ser una gran herramienta, solo hay que saber usarla. No puedes esperar que un carpintero se vuelva maestro sin saber usar un martillo. 
 
Sucede lo mismo para un desarrollador de frontend. SASS es el martillo y tu el desarrollador que quieres saber manejarlo para tener una herramienta más en tu caja.

Aprende a usarlo responsablemente y todo estará bien.

## Más referencias

http://www.webdesignerdepot.com/2014/08/5-reasons-you-should-be-using-sass-today/

http://sass-lang.com/guide

http://thesassway.com/

http://paletton.com/

Online playground: http://codepen.io/pen/