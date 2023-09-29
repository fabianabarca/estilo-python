# Guía de estilo para programación en Python

(En desarrollo)

Según las [guías de estilo](https://google.github.io/styleguide/) de Google:

> Cada proyecto de código abierto tiene su propia guía de estilo: un conjunto de convenciones (a veces arbitrarias) sobre cómo escribir código para ese proyecto. Es mucho más fácil entender una base de código grande cuando todo el código está en un estilo consistente.

Esta guía de estilo aplica para proyectos bajo mi supervisión en:

- TC-691 "Tropicalización de la tecnología"
- IE0405 - Modelos Probabilísticos de Señales y Sistemas
- IE0499 - Proyecto Eléctrico
- Trabajo Final de Graduación de Licenciatura

**Nota**: este también un ejercicio personal de recopilar la experiencia en el desarrollo de estos proyectos, de forma que no es, naturalmente, ni exhaustivo ni infalible.

Referencias:

- Guía de estilo para código de Python [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- [Guía de estilo](https://google.github.io/styleguide/pyguide.html) de Google para Python
- Convenciones de documentación (*docstrings*) de Python [PEP 257](https://peps.python.org/pep-0257/)
- Guía de estilo de documentación de Python de [NumPy](https://numpydoc.readthedocs.io/en/latest/format.html)
- Registro de cambios con [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)

## Formato

El código debe ser bonito y ordenado.

> El código se lee mucho más a menudo de lo que se escribe (Python BDFL)

### Consejos de la *Guía de estilo para código de Python* (PEP 8)

PEP 8 es una guía para que el código escrito en Python tenga una consistencia agradable a la vista. Pueden hacer lectura completa en la página oficial de [PEP 8](https://www.python.org/dev/peps/pep-0008/).

Aquí hay solamente la síntesis de unas cuantas recomendaciones que serán **regla** para el curso.

#### Recomendaciones y cosas que fastidian (*pet peeves*)

* Evitar espacios en blanco en medio de paréntesis redondos o cuadrados, o llaves.

:white_check_mark: **Correcto**
```python
spam(ham[1], {eggs: 2})
```
:x: ***Incorrecto***
```
spam( ham[ 1 ], { eggs: 2 } )
```

* Evitar espacios en blanco entre una coma final y un paréntesis cerrado siguiente:

:white_check_mark: **Correcto**
```python
foo = (0,)
```
:x: ***Incorrecto***
```
bar = (0, )
```

* Evitar espacios en blanco inmediatamente antes de una coma, punto y coma o dos puntos:

:white_check_mark: **Correcto**
```python
if x == 4: print x, y; x, y = y, x
```
:x: ***Incorrecto***
```
if x == 4 : print x , y ; x , y = y , x
```

* A pesar de lo anterior, en un segmento los dos puntos actúan como un operador binario y debe tener cantidades iguales en ambos lados:

:white_check_mark: **Correcto**
```python
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
```
:x: ***Incorrecto***
```
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : upper]
ham[ : upper]
```

* Evitar espacios en blanco inmediatamente antes del paréntesis abierto que inicia la lista de argumentos de una llamada de función:

:white_check_mark: **Correcto**
```python
spam(1)
```
:x: ***Incorrecto***
```
spam (1)
```

* Evitar espacios en blanco inmediatamente antes del paréntesis abierto que comienza una indexación o corte:

:white_check_mark: **Correcto**
```python
dct['key'] = lst[index]
```
:x: ***Incorrecto***
```
dct ['key'] = lst [index]
```

* Evitar más de un espacio alrededor de un operador de asignación (u otro) para alinearlo con otro:

:white_check_mark: **Correcto**
```python
x = 1
y = 2
long_variable = 3
```
:x: ***Incorrecto***
```
x             = 1
y             = 2
long_variable = 3
```

* Evitar dejar espacios en blanco en cualquier lugar. Debido a que generalmente es invisible, puede ser confuso para algunos editores de texto.

* Siempre rodear estos operadores binarios con un solo espacio a cada lado: asignación (`=`), la asignación aumentada (`+=`, `-=`, etc.), las comparaciones (`==`, `<`, `>`, `!=`, `<>`, `<=`, `>=`, `in`, `not in`, `is`, `is not`), Booleans (`and`, `or`, `not`).

* Si se utilizan operadores con diferentes prioridades, considerar agregar espacios en blanco alrededor de los operadores con las prioridades más bajas:

:white_check_mark: **Correcto**
```python
i = i + 1
submitted += 1
x = x*2 - 1
hypot2 = x*x + y*y
c = (a+b) * (a-b)
```
:x: ***Incorrecto***
```
i=i+1
submitted +=1
x = x * 2 - 1
hypot2 = x * x + y * y
c = (a + b) * (a - b)
```

* No usar espacios alrededor del signo `=` cuando se usa para indicar un argumento de palabra clave, o cuando se usa para indicar un valor predeterminado para un parámetro de función:

:white_check_mark: **Correcto**
```python
def complex(real, imag=0.0):
    return magic(r=real, i=imag)
```
:x: ***Incorrecto***
```
def complex(real, imag = 0.0):
    return magic(r = real, i = imag)
```

* Las declaraciones compuestas (declaraciones múltiples en la misma línea) generalmente no se aconsejan:

:white_check_mark: **Correcto**
```python
if foo == 'blah':
    do_blah_thing()
do_one()
do_two()
do_three()
```
:x: ***Incorrecto***
```
if foo == 'blah': do_blah_thing()
do_one(); do_two(); do_three()
```

### Nombre de variables

Una buena elección de nombres requiere un buen conocimiento del tema bajo estudio.

## Documentación

El código debe ser minuciosamente explicado, cuando no sea explícito de la sintaxis.

## Archivos y directorios

## Principios SOLID

## Filosofía

El Zen de Python

El Zen de Python (los principios para programar en Python, accesibles a través de `import this`):

- Hermoso es mejor que feo.
- Explícito es mejor que implícito.
- Simple es mejor que complejo.
- Complejo es mejor que complicado.
- Plano es mejor que anidado.
- Espaciado es mejor que denso.
- La legibilidad cuenta.
- Los casos especiales no son lo suficientemente especiales como para romper las reglas.
- Aunque la practicidad vence a la pureza.
- Los errores nunca deberían pasar en silencio.
- A menos que se silencien explícitamente.
- Frente a la ambigüedad, evitar la tentación de adivinar.
- Debería haber una, y preferiblemente solo una, forma obvia de hacerlo.
- Aunque esa forma puede no ser obvia al principio a menos que seas holandés.
- Ahora es mejor que nunca.
- Aunque nunca es a menudo mejor que *ahora* mismo.
- Si la implementación es difícil de explicar, es una mala idea.
- Si la implementación es fácil de explicar, puede ser una buena idea.
- Los espacios de nombres son una gran idea, ¡hagamos más de eso!
