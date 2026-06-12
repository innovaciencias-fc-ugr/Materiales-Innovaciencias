<div id="PiHy3YBzQoNd" class="cell markdown" id="PiHy3YBzQoNd">

# Introducción a *numpy-Python*

<img align="right" width="200px" src="https://miro.medium.com/v2/1*N8S4mZz_21EqEkfnecekVQ.png">

Existe software científico específico para métodos numéricos,
eventualmente mejor que *Python* para este fin, pero lo hemos elegido
como lenguaje de programación por varias razones:

- sintaxis clara,
- su rápida curva de aprendizaje y versatilidad,
- ser de acceso libre,
- elevadísimo número de usuarios y colaboradores (el más usado en 2025)
  en todos los ámbitos.

No obstante, queremos dejar claro desde el principio, que estas notas NO
son, y no pretenden ser, un manual de *Python*.

</div>

<div id="zfRpmMnSh4w8" class="cell markdown" id="zfRpmMnSh4w8">

# 1. Sobre *Jupyter-notebook*

</div>

<div id="eeeff4cc" class="cell markdown" id="eeeff4cc">

El **jupyter-notebook** (o **navegador Jupyter**) es parte de un
proyecto **Jupyter** que abarca mucho más de lo que aquí nos interesa.
Solo resaltamos aquí lo que nos interesa.

- Es un *navegador interactivo*, permite *editar* y *ejecutar* con
  diversos programas, pero también *exportar* todo a otros formatos que
  no requieren tener nada instalado (pdf o html).

- Se estructura a base de **CELDAS** (editables y móviles) que son,
  esencialmente, de 2 **tipos**:

  - Celdas tipo
    [*Markdown*](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html),
    para poner múltiples tipos de `texto`;<br>
  - Celdas tipo
    [*Code*](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Running%20Code.html),
    para introducir y ejecutar códigos en `Python` (... y otros que no
    usaremos aquí).

- **Crearemos** una celda, de texto o de código, desde el menú `Insert`.
  Según la versión local instalada o la versión online usada puede haber
  diferencias en el manejo, atajos de teclado, etc, de estas celdas..

- En ambos tipos de celdas escribiremos exclusivamente `texto plano`
  desde nuestro teclado (aunque algunas versiones admiten otros objetos
  como iconos, etc), que luego ha de ser **ejecutado** pulsando
  `Mayúsculas`+`Enter` (u otras variantes según versión). Si es celda de
  texto, se visualizará con su aspecto final y, si es de código, ejecuta
  su contenido y crea una celda debajo con las salidas correspondientes.

- **Editaremos** una celda haciendo doble click sobre ella,
  visualizándola así en `texto plano` (en algunos editores, es posible
  visualizar simultáneamente tanto el texto plano como la celda
  ejecutada en sendas ventanas, e incluso asistentes basados en IA para
  ayudar a su edición).<br><br>

<img align="right" width="100px" src="https://quarto.org/docs/get-started/images/jupyter-logo.png">

**IMPORTANTE**. Puedes hacer una **INSTALACIÓN** gratuita en tu
ordenador:

- instalando primero
  [Python](https://wiki.python.org/moin/BeginnersGuide/Download)
- y posteriormente [Jupyter Notebooks](https://jupyter.org/install) (lo
  más simple, ejecutando `pip install notebook` desde el terminal de
  python). Así, para **abrirlo** basta ejecutar otra vez desde el
  terminal `jupyter-notebook` para que se abra **en tu navegador
  habitual**.

Alternativa para tu ordenador:

<img align="right" width="80px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Visual_Studio_Code_1.35_icon.svg/250px-Visual_Studio_Code_1.35_icon.svg.png">

- Si ya usas [Visual Studio
  Code](https://code.visualstudio.com/download) (o si quieres usarlo a
  partir de ahora), es una buena alternativa. Una vez instalado, hay que
  buscar e instalar la extensión para *Jupyter Notebook*.

Alternativa para usarlo **ONLINE**, sin instalar nada:

<img align="right" width="100px" src="https://colab.research.google.com/img/colab_favicon_256px.png">

- Puedes usar los *cuadernos* de [Google
  Colab](https://colab.research.google.com/), entrando con tu [cuenta
  go.ugr.es](https://csirc.ugr.es/sites/centros/csirc/public/ficheros/Tutoriales/CreacionCuentaGoUGR%20%28estudiantes%291.pdf),
- o bien creándote una cuenta en
  [AnacondaCloud](https://anaconda.cloud/) y accediendo a Jupyter.

**Nota**. En todos los casos, los ficheros usados (llamados *cuadernos o
notebooks* de *Jupyter*) son los mismos, con la extensión oficial
`*.ipynb` de un documento de *Jupyter Notebook*.

</div>

<div id="JpRMLdNY_q5g" class="cell markdown" id="JpRMLdNY_q5g">

## 1.1. Celdas tipo **Markdown** (texto enriquecido)

</div>

<div id="9cf6d50a" class="cell markdown" id="9cf6d50a">

**Markdown** es un *texto enriquecido* que engloba **muchas convenciones
existentes** (*html*, *LaTeX*, *códigos OS*...), que además se pueden
**mezclar** en una misma celda. Como hemos dicho, la forma de entrada es
*texto plano* y su salida al 'ejecutar' dependerá de la convención
usada. En esta [página
web](https://www.datacamp.com/es/tutorial/markdown-in-jupyter-notebook)
se encuentra más información; aquí ponemos sólo algunas utilidades:

> Para crear títulos de capítulos, secciones, subsecciones, etc..., se
> precede el texto de `#`, `##`...<br> El texto entre comillas
> invertidas \``texto`\` se mostrará tal cual y sombreado: `texto`<br>
> El texto encerrado entre asteriscos `*texto*` se mostrará en cursiva:
> *texto*<br> El texto encerrado entre dobles asteriscos `**texto**` se
> mostrará en negrita: **texto**<br> El texto encerrado entre dobles
> tildes `~~text~~` se mostrará tachado: ~~text~~<br> Texto con un
> enlace web: `[Web de la UGR](https://www.ugr.es/)`: [Web de la
> UGR](https://www.ugr.es/)<br><br> Acepta texto en código **html**:
> `<br>`, `&nbsp;`, etc;<br><br> Acepta texto en código **LaTeX**, cosa
> que vamos a usar muchísimo y recomendar muchísimo (para fórmulas
> matemáticas, en principio). Por ejemplo:
> `$$integral=\int_0^1 f(x)\, dx$$` produce al ser ejecutada:
> ``` math
> integral=\int_0^1 f(x)\, dx
> ```
> Acepta comandos unix/ms2 (es como un **terminal**)<br>   - precedidos
> de `%` es comando mágico, se adapta al sistema operativo: `%ls`<br>
>   - precedidos de `!` es comando propio, solo para su propio sistema
> operativo<br>   - (aunque estos dos no pueden compartir celda
> mezclados con otros tipos)

Esta celda es de tipo texto y está escrita en Markdown, así que con
*abrirla* puedes ver el texto plano que un usuario tendría que escribir
para da lugar al texto mostrado.

</div>

<div id="DNhhcJjj2jKK" class="cell markdown" id="DNhhcJjj2jKK">

## 1.2. Celdas tipo **Code** (*Python*)

</div>

<div id="4b6b21f4" class="cell markdown" id="4b6b21f4">

Al igual que las anteriores, este tipo de celda también permite ejecutar
todos los tipos de programas que se hayan instalado dentro del
**jupyter.lab** (aunque `Jupyter` es el sucesor del proyecto `IPython`
ahora ha añadido `núcleos` para poder ejecutar también *R*, *C++*,
*Julia*, *Perl*, *Octave/Matlab*,...) pero aquí sólo vamos a tratar un
poco de *Python*.<br>

Aquí sólo recordamos que una celda de tipo `Code`, tiene a la izquierda
un `In[ ]` donde se asignará un número (entre los corchetes) de entrada
una vez se ejecute. A diferencia de las de tipo texto, el resultado de
la ejecución aparecerá debajo de la celda, anexado a ella. Si la celda
contiene una sola ejecución y la salida es *algo* que se pueda guardar,
también se le asignará un número de salida `Out[ ]`.<br>

El contenido de la celda ha de ser, obviamente, código de *Python*, que
ahora introduciremos brevemente.<br>

**Comentarios**. El texto que se escriba en una misma línea tras un `#`
será automáticamente **ignorado** al ser ejecutada la celda de tipo
`Code`, lo **que permite introducir comentarios** útiles de todo tipo.

**Ojo**. Si la celda hace *varias cosas* pero no le pedimos
explícitamente que nos las enseñe todas (por ejemplo con un `print()`),
sólo nos mostrará la última ejecución. La siguiente celda de tipo código
justifica lo explicado en estas líneas.

</div>

<div id="2IRZAAQevxWw" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:10,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151048692,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="2IRZAAQevxWw" outputId="d576def4-b28d-4586-e7d3-ca53a9d48195">

``` python
# esto es un comentario
a = 1+1
print(a)
2+2
```

<div class="output stream stdout">

    2

</div>

<div class="output execute_result" execution_count="1">

    4

</div>

</div>

<div id="Rxx7HuJtGJyg" class="cell markdown" id="Rxx7HuJtGJyg">

# 2. Tipos de datos "simples" en *Python*

</div>

<div id="FbPR_pMmxzBP" class="cell markdown" id="FbPR_pMmxzBP">

Python trabaja con los tipos de datos habituales en los *lenguajes de
alto nivel*. En la práctica es bastante simple e intuitivo y no es
preciso *declarar* el tipo de número u objeto (como ocurre en otros
lenguajes) con el que trabajamos, aunque haremos algunos comentarios
conforme vayan apareciendo. Por ejemplo, si ejecutamos `2+3`, *Python*
"sabe" que hablamos de enteros y devuelve un `5`; sin embargo al hacer
`3/2` automáticamente "sabe" que trabajamos con números reales y
devuelve `1.5`, con su expresión decimal.

El comando `type(objeto)` nos dirá, cuando sea preciso, de qué tipo es
un objeto:<br> Por ejemplo, podremos trabajar con distintos datos de
[tipo
numérico](https://docs.python.org/es/3.14/library/stdtypes.html#numeric-types-int-float-complex):

- Números enteros: clase `int`.

- Números reales: clase `float`. Hablaremos largo y tendido sobre ellos
  en la parte de errores del Tema0B.

- Números complejos con parte real e imaginaria real: clase `complex`.
  La unidad imaginaria es `j` o `J` (aunque nunca se pone sola sino
  `1j`ó `1J` cuando no tenga otro coeficiente)

Y también vamos a trabajar con otros dos tipos de objetos:

- Objetos de [tipo
  lógico](https://docs.python.org/es/3.14/library/stdtypes.html#boolean-type-bool),
  también llamados **booleanos** con solo dos valores posibles:
  verdadero (**True** ó $`1`$) y falso (**False** ó $`0`$): clase
  `bool`.

- Objetos tipo [cadenas de
  caracteres](https://docs.python.org/es/3.14/library/stdtypes.html#text-sequence-type-str)
  o **strings**. Son básicamente texto entre comillas simples ' ',
  dobles " " e incluso triples: clase `str`.

  - Usaremos también algo llamado `f-string` o [*cadenas de caracteres
    formateadas*](https://docs.python.org/es/3.14/reference/lexical_analysis.html#f-strings)
    que, si bien no "son" un objeto distinto, sí son una herramienta que
    nos será muy útil para crear strings (texto) que incluyan
    información sobre las ejecuciones que realicemos.

**Nota**. Los *strings* en rigor no son "datos simples" sino del tipo
que viene a continuación: *datos estructurados secuencialmente*, aunque
por su *simplicidad*, hemos preferido presentarlos aquí.

Veamos unos ejemplos:

</div>

<div id="zkwLkWAxxjZO" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:22,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151048717,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="zkwLkWAxxjZO" outputId="073e6b9f-51ef-41d7-ebdf-674a864f791c">

``` python
print('type(2) da como salida:',type(2)) # Ejemplos, observamos que esta línea, iniciada con un `#` no se ejecuta
print('type(1.5) da como salida:',type(1.5))
print('type(1+3J) da como salida:',type(1+3J))
print('1>2 da como salida:',1>2)
print('type(1>2) da como salida:',type(1>2))
print('type(\'nombre\') da como salida:',type('nombre'))
# ojo, podemos guardar objetos en variables o identificadores; estos NO son strings
# ver más abajo la sección de Variables en Python
x = 2+1
print('type(x) da como salida:',type(x))
print(x)
```

<div class="output stream stdout">

    type(2) da como salida: <class 'int'>
    type(1.5) da como salida: <class 'float'>
    type(1+3J) da como salida: <class 'complex'>
    1>2 da como salida: False
    type(1>2) da como salida: <class 'bool'>
    type('nombre') da como salida: <class 'str'>
    type(x) da como salida: <class 'int'>
    3

</div>

</div>

<div id="Ay2sFodA0R8C" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:3,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151048763,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="Ay2sFodA0R8C" outputId="cf563061-c0c4-4ebb-b5ed-ae8f95072a5f">

``` python
# Ejemplos de strings
Str1 = 'Uno con comillas simples'
print(Str1)
str2 = "Uno con comillas dobles"
print(str2)
str3 = '''Uno multilínea
   empieza y acaba con
      comillas triples'''
print(str3)
# añadimos algunos "caracteres de escape" y los mostramos sin guardarlos previamente
print('Mensaje\n en dos líneas usando \\n')
print('Cómo poner algunos caracteres como \\ ; \' ; \t o tabulado ' )
```

<div class="output stream stdout">

    Uno con comillas simples
    Uno con comillas dobles
    Uno multilínea
       empieza y acaba con
          comillas triples
    Mensaje
     en dos líneas usando \n
    Cómo poner algunos caracteres como \ ; ' ; 	 o tabulado 

</div>

</div>

<div id="ywplyFoXeezS" class="cell markdown" id="ywplyFoXeezS">

Ejemplos de `f-string` (permite incrustar variables dentro de un
`string`)

</div>

<div id="2w1RZajdRvvA" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:56}"
executionInfo="{&quot;elapsed&quot;:11,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151048775,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="2w1RZajdRvvA" outputId="e73aeeea-a3e1-405e-8982-a20b825f3f44">

``` python
x = 1
a = f'x vale {x}'
a
```

<div class="output execute_result" execution_count="4">

``` json
{"type":"string"}
```

</div>

</div>

<div id="t1R-GgHU0cxV" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151048778,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="t1R-GgHU0cxV" outputId="d8ddb7b7-d6ea-4e15-d3da-273f77574b37">

``` python
a = 4
b = 3
print(f'Ejemplo de f-string: calcula: {a}^2 + {b}^2 = {a**2 + b**2}. \n  Cambia tú a y b y ejecuta de nuevo')
```

<div class="output stream stdout">

    Ejemplo de f-string: calcula: 4^2 + 3^2 = 25. 
      Cambia tú a y b y ejecuta de nuevo

</div>

</div>

<div id="Gc6dBrkF3NYi" class="cell markdown" id="Gc6dBrkF3NYi">

## 2.1. Algunas operaciones incluidas en el intérprete básico para datos *simples*

</div>

<div id="a017eda7" class="cell markdown" id="a017eda7">

Para ampliar ver [funciones
incorporadas](https://docs.python.org/es/3.13/library/functions.html) o
los enlaces anteriores.

Aritmética básica:

| Código | Resultado |
|----|:---|
| `a + b` ó `a+b` | devuelve la **suma** de los números `a` y `b` |
| `a - b` ó `a-b` | devuelve la **diferencia** de `a` menos `b` |
| `a * b` ó `a*b` | devuelve la **multiplicación** de los números `a` y `b` |
| `a / b` ó `a/b` | devuelve la **división** de `a` entre `b`, y siempre es un número real (tipo `float`) |
| `a ** b` ó `a**b` | devuelve la **potencia** de `a` elevado a `b` |
| `a**(1/n)` | (caso particular) devuelve la **raíz n-ésima** de `a` |
| `print(a,b,...)` | muestra los argumentos a, b, etc |

...y algunas más...

| Código | Resultado |
|----|:---|
| `abs(x)` | devuelve el valor absoluto o el módulo de x, según si es real o complejo |
| `round(a,n)` | devuelve el número a redondeado con n cifras decimales |
| `a // b` | devuelve el redondeo al entero inferior de la división entera entre a y b |
| `a % b` | devuelve $`a\  mod(b)`$, el resto de la división entera entre a y b (da $`0`$ si a es divisible por b) |
| `divmod(a,b)` | devuelve, en ese orden, los dos anteriores |
| `pow(a,b)` | devuelve `a` elevado a `b`, es como `a**b` |
| `help(comando)` | proporciona ayuda sobre el comando indicado |
| `input( )` | nos pide una `entrada` y siempre devuelve una cadena de caracteres |

Practica estas funciones con diferentes números de todo tipo.

Aquí dejamos un **ejemplo** de uso del `input( )`, (tal vez) más
complejo que el resto, y la división entera; es este caso es un
*programa* que calcula la [letra del
DNI](https://www.interior.gob.es/opencms/es/servicios-al-ciudadano/tramites-y-gestiones/dni/calculo-del-digito-de-control-del-nif-nie/).

</div>

<div id="BSgfbGLdS3e6" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:7564,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056342,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="BSgfbGLdS3e6" outputId="206da99c-b95c-4fd7-e32d-319f4632729f">

``` python
#Con este código se calcula el NIF asociado a un DNI
letra='TRWAGMYFPDXBNJZSQVHLCKE' #esta lista de letras hay que traerla sabida de casa

dni = int(input('Introduce tu DNI: ')) # ¿por qué ponemos int?
print('Tu NIF es:', dni,'-',letra[dni % 23])
```

<div class="output stream stdout">

    Introduce tu DNI: 123456789
    Tu NIF es: 123456789 - B

</div>

</div>

<div id="AgzqIIYd74kU" class="cell markdown" id="AgzqIIYd74kU">

# 3. Tipos de datos "secuenciales": datos estructurados secuencialmente

(Es decir, unos cuantos de tipo simple juntos, alineados uno detrás de
otro, separados por comas, indexados y ordenados).

</div>

<div id="pbG6tihB1QTo" class="cell markdown" id="pbG6tihB1QTo">

Según la documentación de *Python* existen tres tipos básicos de [datos
estructurados
secuenciales](https://docs.python.org/es/3.14/library/stdtypes.html#sequence-types-list-tuple-range)
que son:

- `tuplas`. Ejemplo `(1, 2, 'paco', True)`; secuencia heterogénea (sus
  componentes pueden ser de distintos tipos) e **inmutable**. Las
  usaremos muy poco/nada.

- `listas`. Ejemplo `[1, 2, 0, -4]`; secuencia también **heterogénea**
  pero **mutable** (sí se puede modificar su contenido a lo largo de un
  programa). Generalmente se utilizan para almacenar colecciones de
  elementos homogéneos, del mismo tipo, pero **no** están pensadas para
  realizar **operaciones aritméticas**. Nos interesan un poco, pero solo
  de forma auxiliar por su manejo y para generar los que nos interesan,
  los `arrays` que vendrán más abajo, y que sí serán homogéneos.

- `rangos`, es un tipo auxiliar y representa una secuencia inmutable de
  **números enteros** que se mueven en un cierto **rango**. Es muy útil
  en *bucles* o para crear/manipular los índices de otros datos
  secuenciales; la sintáxis básica es `range(inicio, tope, paso)`

  - el `inicio` por defecto es 0,
  - el `paso` por defecto es 1.

**OJO**

- **En cualquier secuencial ¡la primera posición no es la 1, es la 0!**
- **¡El `tope` de un `range` nunca se alcanza!**

Son **secuenciales** porque que sus componentes se organizan en una
secuencia de posiciones y **ordenadas** para que se puede acceder a
estas componentes por su posición. Por cierto, los `strings` también lo
son.

> **Nota**. Aparte de estos 3 básicos, el lenguaje *Python* proporciona
> **otros datos secuenciales** como los `diccionarios` de gran uso por
> ejemplo en análisis de datos, pero estos se escapan del interés de
> este curso.<br> Otro ejemplo que sí nos interesa y mucho son los
> `arrays`. Se usarán para representar y manipular **vectores y
> matrices**, que es lo que nos interesa en esta asignatura. Son los
> adecuados para realizar operaciones aritméticas (los algoritmos
> numéricos que vamos a tratar están obviamente llenos de ellas). Los
> presentaremos al final esta introducción porque requiere introducir
> previamente qué son las *librerías de Python* y, concretamente,
> `numpy`, de la que no nos separaremos en todo el curso.

Podemos crear una lista:<br>   • A mano, directamente usando corchetes
\[ \] y separando las componentes con comas;<br>   • Usando el
constructor, `list(secuencial)` que recibe como parámetro un objeto
secuencial, normalmente un `rango`;<br>   • Mediante **comprensión**
cuya sintaxis genérica es:<br>    
`lista = [expresion(contador) for contador in secuencial if condicion(contador)]`
(la condición es opcional y, de nuevo, el secuencial es normalmente un
rango).<br>

La comprensión supone una forma intuitiva y rápida y económica (menos
código) de recorrer una lista, aplicar una condición y obtener una nueva
lista.<br>

Veamos unos ejemplos.

</div>

<div id="6zjdwBNc0vXd" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:19,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056344,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="6zjdwBNc0vXd" outputId="d3715ce2-a757-4f9d-8588-45247d0c03cc">

``` python
# Ejemplos de tuplas
vectorcillo = (1, 22, 55)
print('Tupla de números enteros:', vectorcillo, ' que es de tipo:', type(vectorcillo))
tuplamixta = (33, 3.3, 'un texto')
print('Tupla mixta:', tuplamixta, ' que es de tipo:', type(tuplamixta))
```

<div class="output stream stdout">

    Tupla de números enteros: (1, 22, 55)  que es de tipo: <class 'tuple'>
    Tupla mixta: (33, 3.3, 'un texto')  que es de tipo: <class 'tuple'>

</div>

</div>

<div id="w0-N8LL-8FYo" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:15,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056345,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="w0-N8LL-8FYo" outputId="90df1299-428a-4794-a446-fe4584025eab">

``` python
# Ejemplo de lista hecha a mano
listilla = [1, 22, 55]
print('Lista de números enteros:', listilla, ' que es de tipo:', type(listilla))
```

<div class="output stream stdout">

    Lista de números enteros: [1, 22, 55]  que es de tipo: <class 'list'>

</div>

</div>

<div id="eax3lf74SA_p" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:11,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056345,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="eax3lf74SA_p" outputId="1ec7082e-5d03-4161-a548-e59b2b034823">

``` python
# lista heterogénea;  de discutible utilidad
listamixta = [33, 3.3, 'un texto',[1,4]]
print('Lista mixta:', listamixta, ' que es de tipo:', type(listamixta))
```

<div class="output stream stdout">

    Lista mixta: [33, 3.3, 'un texto', [1, 4]]  que es de tipo: <class 'list'>

</div>

</div>

<div id="B556xKokVEOd" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056348,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="B556xKokVEOd" outputId="eb5125fc-91f3-480f-ac03-c3b9bbe41bb1">

``` python
print('Lista a partir de una tupla: list((1,4.5,-1,0))\n',list((1,4.5,-1,0)))
```

<div class="output stream stdout">

    Lista a partir de una tupla: list((1,4.5,-1,0))
     [1, 4.5, -1, 0]

</div>

</div>

<div id="kjWno6i78IiO" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056351,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="kjWno6i78IiO" outputId="64e82d29-e492-4e77-b3f2-1f6a85b3f82d">

``` python
# Ejemplos de listas creadas con rangos
print(list(range(5)))
print(list(range(5, 10)))
print(list(range(5, 10, 2)))
print(list(range(5, 10, -2)))
print(list(range(10, -6, -2)))
print(list(range(10, -6, -7)))
print(list(range(-5)))
print(list(range(-5, 0)))
print(list(range(-5, 10, 3)))
```

<div class="output stream stdout">

    [0, 1, 2, 3, 4]
    [5, 6, 7, 8, 9]
    [5, 7, 9]
    []
    [10, 8, 6, 4, 2, 0, -2, -4]
    [10, 3, -4]
    []
    [-5, -4, -3, -2, -1]
    [-5, -2, 1, 4, 7]

</div>

</div>

<div id="TjLrYFTVWXJd" class="cell markdown" id="TjLrYFTVWXJd">

**Ejemplo** de lista por comprensión.<br> Vamos a declarar, de dos
formas distintas, la lista de los cuadrados de los múltiplos de 7
comprendidos entre 0 y 40.

</div>

<div id="BaPSFUajVNs1" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:31,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056383,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="BaPSFUajVNs1" outputId="b741ec6b-3027-405f-f310-01ebc0f4f5f0">

``` python
una = [k**2 for k in range(0,40,7)]         #usando el paso = 7 en el range
dos = [k**2 for k in range(40) if k%7==0 ]  #usando una condición "ser divisible por 7"

print(una)
print(dos)
```

<div class="output stream stdout">

    [0, 49, 196, 441, 784, 1225]
    [0, 49, 196, 441, 784, 1225]

</div>

</div>

<div id="i44_xkup-GOM" class="cell markdown" id="i44_xkup-GOM">

## 3.1. Algunas operaciones incluidas en el intérprete básico para *listas*

(Nos interesan porque son válidas para los `arrays`, que veremos a
continuación y que son los que nos interesan)

</div>

<div id="qr20HP04-EnU" class="cell markdown" id="qr20HP04-EnU">

Veamos una forma que vamos a usar muy a menudo de **extraer
componentes**, una o varias, de una lista (o array) dada, usando bien
**índices** bien trozos o *secciones* llamadas
[**slices**](https://docs.python.org/es/3.14/glossary.html#term-slice).
En esta celda, todo está referido a un `secuencial` llamado `s` con un
único contador de componentes (tipo vector, no matriz):

| El código | ... extrae de `s`... |
|----|:---|
| `s[i]` | el i-ésimo elemento (**comenzando por 0**), un índice concreto |
| `s[-1]` | el último elemento; (negativos significa "contando desde el final") |
| `s[i:j]` | la sección (**slice**) desde el $`i`$-ésimo hasta el ($`j-1`$)-ésimo (**no incluye el $`j`$**) |
| `s[:j]` | la sección desde el primero (el $`0`$-ésimo) hasta el ($`j-1`$)-ésimo (**no incluye el $`j`$**) |
| `s[i:]` | la sección desde el $`i`$-ésimo hasta el final |
| `s[:]` | todas las componentes |
| `s[i:j:k]` | la sección desde el $`i`$-ésimo hasta el ($`j-1`$)-ésimo, contando de $`k`$ en $`k`$ |
| `s[:j:k]` | la sección desde el primero hasta el ($`j-1`$)-ésimo, contando de $`k`$ en $`k`$ |
| `s[i::k]` | la sección desde el $`i`$-ésimo hasta el último, contando de $`k`$ en $`k`$ |
| `s[::-1]` | todos sus elementos pero reordenados al revés |

¡**Importante**! Como idea general el
[*slice*](https://docs.python.org/es/3.14/library/functions.html#slice)
funciona como un `range`; así `s[inicio:tope:paso]` se refiere a los
índices de `s` desde `inicio`, yendo de `paso` en `paso` y sin llegar al
`tope` por eso ¡**`tope` nunca se alcanza**!<br>

- El `inicio` por defecto es 0,
- el `tope` por defecto es `len(s)` (ver abajo), y
- el `paso` por defecto es 1.

Veamos algunas operaciones más de diversa índole que nos serán útiles
(ver esta
[página](https://docs.python.org/es/3.14/library/stdtypes.html) para
completar).

| Código | Resultado |
|----|:---|
| `s[i] = x` | sustituye la componente $`i`$-ésima por el valor $`x`$ |
| `del(s[i])` o `del s[i]` | elimina la componente $`i`$-ésima |
| `del(s[i:j])` | elimina la sección de $`i`$ a $`(j-1)`$ |
| `len(s)` | devuelve el número de elementos de s |
| `min(s)` | devuelve la componente más pequeña de s |
| `max(s)` | devuelve la componente más grande de s |
| `sum(s)` | suma los elementos de un iterable, de izquierda a derecha |
| `sorted(s)` | devuelve una nueva lista con los elementos de s ordenados de menor a mayor valor (no modifica s) |
| `x in s` | devuelve `True` si algún elemento de s es igual a x |
| `all(iterable)` | devuelve `True` si todos los elementos de s son verdaderos (o si s=\[\]) |
| `any(iterable)` | devuelve `True` si algún un elemento de s es verdadero (`False` si s=\[\]) |

</div>

<div id="uQNRtBM4YwSd" class="cell markdown" id="uQNRtBM4YwSd">

**Ejemplo**. Vamos a hacer algunas de estas operaciones sobre la lista
``` math
 s = [-0.5,-0.4,-0.3,-0.2,-0.1,0,0.1,0.2,0.3,0.4,0.5]; 
```
o mejor, por comprensión,
``` math
 \ s_k= -0.5+\frac{k}{10}, \quad k=0,1,...,10.
```

- Preguntaremos si $`0.3`$ es un elemento de $`s`$;
- Calculamos el máximo;
- Calculamos la suma de sus componentes.

</div>

<div id="h5ZYbaTeaCuk" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:8,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056384,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="h5ZYbaTeaCuk" outputId="960184ab-4f44-4195-ead2-2722aa494cb0">

``` python
s = [-0.5+k/10 for k in range(11)]
print(s[-1])
print(s[0:4])
```

<div class="output stream stdout">

    0.5
    [-0.5, -0.4, -0.3, -0.2]

</div>

</div>

<div id="V0HSx5Yw_6bn" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:5,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056384,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="V0HSx5Yw_6bn" outputId="19a77cec-796a-4343-83b9-cd2c5cac034b">

``` python
0.3 in s #debería salir True... ¿sale? ¿por qué? (visualiza s y ve al Tema0B)
```

<div class="output execute_result" execution_count="14">

    False

</div>

</div>

<div id="_Mr2RxwtA6V5" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:3,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056385,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="_Mr2RxwtA6V5" outputId="0eef237c-7394-4efb-d5e1-705202cbd4fa">

``` python
max(s)
```

<div class="output execute_result" execution_count="15">

    0.5

</div>

</div>

<div id="BXt0RLMRCNtr" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:6,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056391,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="BXt0RLMRCNtr" outputId="e18dc118-e76f-4086-dd8b-9bb447583455">

``` python
sum(s)
```

<div class="output execute_result" execution_count="16">

    0.0

</div>

</div>

<div id="41aIMkNxZj0v" class="cell markdown" id="41aIMkNxZj0v">

### 3.1.a. Funciones y Métodos en *Python*

Para ir cerrando esta parte, veamos "otro tipo" de operaciones que
contiene *Python*. Las que hemos visto hasta ahora se llaman
**funciones**:

> **Funciones en** *Python*: son bloques de código autónomos que se
> pueden llamar desde cualquier parte del programa para realizar una
> tarea. Se invocan directamente:
> $`\fbox{nombre-funcion(objeto-a-quien-se-aplica)}`$.

(Por cierto, más abajo veremos cómo crear nuestras propias funciones).
Pero hay "otro tipo" de operaciones que internamente se comportan de
forma distinta pero que, sobre todo para nosotros, tienen una sintaxis
distinta.

> **Métodos en** *Python*: operaciones que son parte de una clase y
> actúan sobre los datos de un objeto específico. Para invocarlas, el
> primer parámetro es el objeto al que se aplica:
> $`\fbox{objeto-a-quien-se-aplica.nombre-metodo()}`$ (eventualmente,
> también puede contener ciertos argumentos entre los paréntesis).

**Nota**. Hemos de tener cuidado, especialmente en esta asignatura, para
no confundir los **Métodos Numéricos** que estamos estudiando, y los
**Métodos en Python** como operaciones informáticas.

Vamos a ver unos ejemplos de métodos aplicables a secuenciales:

| Método sobre s | Resultado |
|:---|:---|
| `s.append(x)` | añade una componente a s con el valor de x al final |
| `s.insert(i,x)` | añade una componente a s con el valor de x en la posición i |
| `s.extend(lista)` | añade a s el contenido del secuencial `lista` |
| `s.clear()` | elimina todos los elementos de s |
| `s.copy()` | crea una copia de s (veremos su utilidad más adelante) |
| `s.sort()` | reordena s de menor a mayor valor; **no** es igual que `sorted(s)` |

Usemos algunos de ellos sobre un **Ejemplo**.

</div>

<div id="Ue43yA-C9Xdb" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:4,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056396,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="Ue43yA-C9Xdb" outputId="1c5dbf92-8100-48cc-c27f-44c3b8b78fb2">

``` python
s = [1, 5, 0, -2, -7]
b = s.copy()
print('s = ',s)
s.sort()
print('s = ',s,'después del sort')
s.append(2)
print('s = ',s,'después del append(2)')
print('b = ',b,'la copia no se ve afectada')
```

<div class="output stream stdout">

    s =  [1, 5, 0, -2, -7]
    s =  [-7, -2, 0, 1, 5] después del sort
    s =  [-7, -2, 0, 1, 5, 2] después del append(2)
    b =  [1, 5, 0, -2, -7] la copia no se ve afectada

</div>

</div>

<div id="jvsh5LfVZB97" class="cell markdown" id="jvsh5LfVZB97">

# 4. Definir nuestras funciones: **def - return** y **lambda**

</div>

<div id="5b8137fd" class="cell markdown" id="5b8137fd">

Algo que vamos a hacer mucho este curso es, una vez estudiados y
programados nuestros algoritmos, guardarlos para poder ser aplicados a
distintos ejemplos. Así funcionan, en general, las funciones de *Python*
(código abierto), se almacenan y empaquetan junto a otras de su mismo
tipo, y se dejan disponibles para que el resto del mundo las use,
escudriñe o modifique a placer.

Aquí no aspiramos (en principio) a tanto, pero sí con fines académicos
queremos guardar nuestros códigos para llamarlos directamente como
cualquier otro comando de *Python*.

El primer mecanismo en *Python* para definir funciones es:
`def -  return`

> <b><font color="blue">def</font></b>
> <font color="brown">nombrefuncion</font> (variables):<br>     '''
> texto (opcional) de apoyo '''<br>     **Instrucciones**: *el algoritmo
> o lo que sea que*<br>     *haya que hacer con las variables*<br>    
> <b><font color="purple">return</font></b> la salida (una o varias
> cosas separadas por comas).

**Nota**. Si tiene varias salidas, lo harán en forma de `tupla`

**Nota**. Al principio, los fallos más comunes son

- Olvidar los dos puntitos después de las variables;
- No indentar (esto es, sangrar) alguna línea.

También existe otro mecanismo útil, pero solo lo recomendamos **para
funciones muy muy simples**:

> <font color="brown">nombrefuncion</font> =
> <font color="blue">lambda</font></b> variable: lo que haya que hacer
> con la variable

</div>

<div id="emO_v647VmeM" class="cell markdown" id="emO_v647VmeM">

## 4.1. Ojo: no olvidar los dos puntitos y el indentado

</div>

<div id="VuZktkykVpaD" class="cell markdown" id="VuZktkykVpaD">

Hacemos hincapié de nuevo ¡y lo ponemos como sección para recalcarlo aún
más! en el **indentado**. El caracter `:` (**los dos puntitos**)
**indican que comienza un bloque indentado**; todo lo que está *dentro*
(y debajo) del `def`, incluido el `return`, ha de estar indentado. Basta
un espacio, o dos, o una tabulación (normalmente los editores te ayudan
a hacerlo por defecto, pero conviene hacerlo siempre igual) pero eso sí,
**todo alineado verticalmente**. Como esto no es solo para el comando
`def` sino en general en *Python* (véase la sección sobre flujos, por
ejemplo), a menudo hay comandos *anidados* uno dentro de otro y, por
tanto, los sucesivos llevarán doble indentación, triple, etc.

</div>

<div id="hWi9P00adKvj" class="cell code" id="hWi9P00adKvj">

``` python
# Función para calcular el cuadrado de un número usando def
def cuadrado(x):
  """
  función que eleva x al cuadrado
  """
  y = x**2
  return y
```

</div>

<div id="KQ65BJiLdn5z" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:8,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056406,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="KQ65BJiLdn5z" outputId="e0e516f3-fbc4-4bab-a4ae-9ddc4edbc8d1">

``` python
help(cuadrado)
cuadrado(4)
```

<div class="output stream stdout">

    Help on function cuadrado in module __main__:

    cuadrado(x)
        función que eleva x al cuadrado

</div>

<div class="output execute_result" execution_count="19">

    16

</div>

</div>

<div id="OrPLT3-OdznQ" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:1,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056408,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="OrPLT3-OdznQ" outputId="154b7527-e3b9-4b02-acf6-dc80e927f1ed">

``` python
# Función para calcular el cuadrado de un número usando lambda
cuadradolambda = lambda x: x**2

cuadradolambda(5)
```

<div class="output execute_result" execution_count="20">

    25

</div>

</div>

<div id="ZAYLDAFewtBU" class="cell markdown" id="ZAYLDAFewtBU">

# 5. Variables en *Python*, referencias compartidas y cambios en el lugar

</div>

<div id="8RpdeBpcwrQF" class="cell markdown" id="8RpdeBpcwrQF">

Como regla general, escribiendo:

> `x = 5`

creamos una variable llamada `x` que, a partir de ese momento, toma el
valor `5`. Pero conviene profundizar un poco en qué ocurre *dentro de
Python* cuando lo hacemos; lo que estamos haciendo es

- crear un objeto interno en la memoria, que llamaremos $`ID_1`$ y que
  se puede consultar con el comando `id()`, y que se usa para
  representar al valor 5
- y además crea la variable `x`, si no existía, y la convierte en una
  *referencia* que nos dirige a $`ID_1`$ (se dice que `x` "apunta" a
  $`ID_1`$).

Sin embargo, si a otra variable `y` le asignamos nuestra variable `x`
así:

> `y = x`

lo que ocurre es que ¡**en ese momento**! se crea esta "otra" variable
`y` pero que hace referencia a lo mismo que `x`, que ¡**en ese
momento**! será $`ID_1`$. Por ello, si, ¡**en otro momento posterior**!,
se cambia `x`, por ejemplo así:

> `x = 'otra cosa'`

entonces la variable x en ese momento hará referencia a un segundo
objeto $`ID_2`$ que se usará para apuntar al string `'otra cosa'`. Sin
embargo, la variable `y` seguirá haciendo referencia a $`ID_1`$ y por
tanto al preguntar por el valor de y, *Python* devolverá el valor 5.

</div>

<div id="CuTkzLsKSmK5" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:29,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056438,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="CuTkzLsKSmK5" outputId="51d15b94-ef4c-4d88-fc87-e14f8b263dab">

``` python
x=5
print (id(5)) # el objeto 5 será representado por el ID_1
print (id(x)) #
y=x
print (id(y))
x='cadena'
print (id('cadena'))
print(id(x))
print(y)
print(id(y))
```

<div class="output stream stdout">

    11654504
    11654504
    11654504
    133897664237600
    133897664237600
    5
    11654504

</div>

</div>

<div id="IhCVycZaR6Yy" class="cell markdown" id="IhCVycZaR6Yy">

Resaltamos un **ejemplo** en que este tipo de cambios pueden crear un
error inesperado al combinar variables que cambian a lo largo de un
proceso, pero usadas dentro de funciones (con **def** o con **lambda**)

``` python
m = 2
f2 = lambda x: x**m #creamos la función f(x) = x^2 en este momento
m = 3
# y sigo haciendo otras muchas cosas...
# ¿y esto afecta a f2?

f2(4)
64
```

Observamos que **primero** creamos la función $`f2(x) = x^2`$, usando
una variable **externa**: `m = 2`, y **después** creamos otra función
$`f3(x) = x^3`$ usando **la misma variable externa** `m` a la que hemos
cambiado su valor, ahora es `m = 3`. Por tanto, cuando evaluemos $`f2`$
en algún número, volverá **atrás** hasta su definición con `lambda`, y
por tanto tomará el valor que `m` tenga en ese momento, que en este
ejemplo ya no será 2, sino 3, y por tanto $`f2`$ no hace lo que
esperábamos que hiciese...

Esto ocurre más de lo que pueda parecer, por ejemplo, al usar bucles
(ver sección 8 abajo), pues habrá variables que van moviendo su valor a
lo largo de un código, y hay que cuidar que lo que hagamos con ellas
**en cada momento**, no cambie

Nótese la diferencia con este **otro ejemplo** en el que no hay
funciones involucradas: `x` se construye en un momento dado (usando una
variable `m`) y se le asigna el valor 16, y aunque después cambie el
valor de `m`, `x` no se ve alterada, porque no vuelve a reevaluar `m`.

``` python
m = 2
x = 4**m
m = 3

x
16
```

</div>

<div id="2Pu89GweSPFj" class="cell code" execution_count="16"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:14,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1781092661331,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-120}"
id="2Pu89GweSPFj" outputId="82a9380e-1671-4ae8-a937-adacef7216e4">

``` python
m = 2
f2 = lambda x: x**m #creamos la función f(x) = x^2
m = 3

f2(4)
```

<div class="output execute_result" execution_count="16">

    64

</div>

</div>

<div id="VrC2jMbsWodI" class="cell code" execution_count="21"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:10,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1781092698244,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-120}"
id="VrC2jMbsWodI" outputId="1a5f1a00-6012-438e-ca47-05ca52f521ea">

``` python
m = 2
x = 4**m

m = 3
x
```

<div class="output execute_result" execution_count="21">

    16

</div>

</div>

<div id="CxoKyOTGzGLq" class="cell markdown" id="CxoKyOTGzGLq">

Por tanto, hay que tener cuidado con las asignaciones ya que,
dependiendo de cómo se hace, bien podemos hacer cambios en el ID o bien
se hacen cambios en las componentes del objeto (denominados **cambios en
el lugar**). De hecho, la explicación anterior es básica para poder
comprender cómo manejar las componentes de un dato de tipo secuencial
mutable (una lista, o un array). Para profundizar, ver:
[geeksforce.org](https://www.geeksforgeeks.org/shared-reference-in-python/).

Otro **ejemplo** parecido, pero sin que intervengan funciones. Observa
en la secuencia que sigue como el cambio realizado en la variable `L1`
también tiene efecto en la variable `L2`:

</div>

<div id="PG0KtLLry5sk" class="cell code" execution_count="9"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:6,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1781090516717,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-120}"
id="PG0KtLLry5sk" outputId="32678361-71bc-4e1e-e060-fe1e26ba8cd5">

``` python
L1 = [1, 2, 3, 4, 5]
L2 = L1

L1[0] = 0

print(L1)
print(L2)
```

<div class="output stream stdout">

    [0, 2, 3, 4, 5]
    [0, 2, 3, 4, 5]

</div>

</div>

<div id="FZAKsq210O6s" class="cell markdown" id="FZAKsq210O6s">

Si lo que queremos es tener una copia de los valores de `L1`en una
variable totalmente independiente (con diferente ID, compruébalo) hay
que pedirle a Python que cree la nueva variable a partir de los valores
de `L1` de otra forma; damos dos ejemplos:

</div>

<div id="3_j81TuPzwda" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056443,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="3_j81TuPzwda" outputId="1370e222-e228-4aca-cd89-7847d80149ec">

``` python
L1 = [1, 2, 3, 4, 5]

L2 = L1[:]   #una forma
L3 = L1.copy() #otra forma

L1[0] = 0

print(L1)
print(L2)
print(L3)
```

<div class="output stream stdout">

    [0, 2, 3, 4, 5]
    [1, 2, 3, 4, 5]
    [1, 2, 3, 4, 5]

</div>

</div>

<div id="wzUsuQrKRh-M" class="cell markdown" id="wzUsuQrKRh-M">

### 5.1. Ojo: orden de las ejecuciones

Hemos resaltado varias veces en negrita el **momento** en que se hacen
las cosas; ¿por qué? Pues porque es importante y a veces lleva a error.
Tendemos a leer de arriba abajo y, por tanto, a pensar que las
ejecuciones van en el mismo orden (y así será si le damos a
$`\fbox{Ejecutar todas}`$ de un mismo notebook), pero cuando estamos en
medio de un proceso de *creación*, estaremos editando celdas,
moviéndolas de sitio, reusando y renombrando variables..., es muy fácil
pensar que lo que está arriba va antes que lo que está abajo... ¡y no
tiene por qué ser así!

Como decíamos al principio, una vez que se ejecuta una celda de código,
se le asigna un número; pues bien: ¡**este es en realidad el número de
orden**! independientemente de dónde esté escrita. Depende de **cuándo**
se ejecute, no de **dónde** esté escrita.

Y, para terminar, que una cosa esté *escrita* en una celda no basta; ha
de ser *ejecutada* para que *Python* lea lo que hay dentro.

</div>

<div id="sYVkW1hR2LGJ" class="cell markdown" id="sYVkW1hR2LGJ">

# 6. Bibliotecas o Librerías

</div>

<div id="0e3148ce" class="cell markdown" id="0e3148ce">

El núcleo del lenguaje Python es muy pequeño, pero hay disponibles
muchas *bibliotecas* de una calidad magnífica la gran mayoría en
repositorios de LIBRE ACCESO. La idea de fondo es **cargar solo lo que
se va a usar**. Hay decenas de librerías y sublibrerías, aquí solo
mencionamos unas poquitas. Además, hay que señalar que estas librerías
son **algo que evoluciona** ya que se actualizan con frecuencia. No sólo
eso, sino que incluso algunas de ellas dejan *de ser recomendadas* por
la aparición de otras *mejores*, lo que puede llevar a confusión al
usuario novel ya que los manuales/aplicaciones tanto de unas como de
otras siguen disponibles en la web y muchas veces son contradictorios
como veremos en el caso de los polinomios.

Para cargar estas bibliotecas en nuestros programas, usaremos la
sentencia **import** (al principio de nuestro programa) de una de estas
formas:

``` python
import librería #se carga, y se usa, son su nombre
import librería.sublibrería #idem, para no cargarla toda, sino
                            #solo la parte que se va a usar
import librería as abr #se carga, y se usa, son su nombre abreviado.
                       # Esto es lo más habitual
from librería import sublibrería as nombre
     #se carga solo una sublibrería y se le asigna un nombre
from librería import función as minombre
     #(se carga solo una función y se le asigna un nombre)
```

**IMPORTANTE**<br>

> <b>Los comandos/funciones contenidas en la librería que ha sido
> importada han de ser ejecutados anteponiendo el nombre (o la
> abreviatura) de la librería en la que están seguida de un
> punto</b>.<br> Esto se puede evitar importándola "sin nombre" como
> sigue:<br> <b><font color="green">from</font> librería
> <font color="green">import</font> \*</b><br> pero no se recomienda,
> porque siempre se usan varias y podemos liarla...<br>

Por ejemplo, para usar la función coseno `cos` o el número `pi`, ambos
dentro de la librería `numpy`, abreviado `np`, debemos ejecutar:

``` python
import numpy as np
In[1]    np.cos(np.pi)
Out[1]  -1.0
```

</div>

<div id="Ex8HWlXTWRPJ" class="cell markdown" id="Ex8HWlXTWRPJ">

# 6.1. Librería `NumPy`

<img align="right" width="200px" src="https://aprendeconalf.es/docencia/python/manual/img/numpy-logo.png">

</div>

<div id="jzcD3DHmWaoN" class="cell markdown" id="jzcD3DHmWaoN">

La que más nos interesa, especializada en el cálculo numérico y el
análisis de datos, particularmente para un gran volumen de datos. Es
necesaria para incorporar los **arrays** que permiten representar
**vectores y matrices** (colecciones de datos de un mismo tipo en varias
dimensiones). La abreviatura "usual" es *np*.

Aunque contiene un amplio abanico de funciones matemáticas (todas o casi
todas las funciones de la librería `Math`) para el uso de variables de
naturaleza particular tendremos que llamar a sublibrerías específicas.
Por ejemplo, veremos que en el caso de los polinomios tendremos que
cargar la sublibrería [*polynomial* de
*numpy*](https://numpy.org/doc/stable/reference/routines.polynomials-package.html#module-numpy.polynomial).

La relevancia de este paquete en el Cálculo Científico con Python en el
artículo [Array programming with
Numpy](https://www.nature.com/articles/s41586-020-2649-2) publicado en
Nature.

</div>

<div id="cFzJ_ypdWkD2" class="cell markdown" id="cFzJ_ypdWkD2">

## 6.2. Sub-Librería `Matplotlib.pyplot`

<img align="right" width="200px" src="https://matplotlib.org/2.1.1/_static/logo2.svg">

</div>

<div id="u29J4KgJWwVY" class="cell markdown" id="u29J4KgJWwVY">

*Matplotlib* Es una extensa biblioteca para crear gráficas de todo tipo:
visualizaciones fijas, interactivas y animadas. Usaremos a menudo sólo
la sublibrería *pyplot*.<br> La abreviatura 'usual' de *pyplot* es
*plt*.

</div>

<div id="Wouk8PzkXITw" class="cell markdown" id="Wouk8PzkXITw">

## 6.3. Otras librerías

</div>

<div id="ePenIHLGXJxK" class="cell markdown" id="ePenIHLGXJxK">

Aunque en este curso no van a ser de gran relevancia hay que señalar que
existen otra serie de librerías que pueden ser de mucha ayuda en otros
contextos; presentamos algunas.

> **Librería SciPy**

<img align="right" width="170px" src="https://www.fullstackpython.com/img/logos/scipy.png">

Numpy no será suficiente en algunas aplicaciones que vamos a trabajar en
esta asignatura por lo que en determinados momentos cargaremos
sublibrerías de [SciPy](https://scipy.org/es/) que proporciona
algoritmos para cálculo científico ampliando las ya proporcionadas por
Numpy.

> **Librería `Math`**

Contiene las funciones matemáticas definidas en el estándar de C<br> No
pueden ser usadas con números complejos, los valores retornados son
flotantes; pensando en los usuarios que no quieren aprender tantas
matemáticas como se requiere para comprender los números complejos.
Recibir una excepción en lugar de un resultado complejo permite la
detección temprana del número complejo inesperado utilizado como
parámetro, de modo que el programador pueda determinar cómo y porqué se
generó en primer lugar.

<img align="right" width="100px" src="https://upload.wikimedia.org/wikipedia/commons/5/54/Sympy_logo.svg">

> **Librería `Sympy`**

Especializada en el tratamiento simbólico.

> **Librería `Pandas`**

<img align="right" width="200px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Pandas_logo.svg/250px-Pandas_logo.svg.png">

Muy utilizada en la ciencia de datos ligados (fechas, nombres,
productos...). Se utiliza principalmente para el análisis, la
manipulación y la limpieza de los mismos.

</div>

<div id="l5Suwbs61Voh" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:1,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056444,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="l5Suwbs61Voh" outputId="0563c406-7320-47d2-c6e8-4f329c93ba3c">

``` python
import numpy as np  #así importamos la biblioteca NumPy con el nombre abreviado np
                    #NumPy funciones matemáticas definidas en el estándar de C
from numpy import random   #importamos solo la sublibrería random
random.rand(2,3)
```

<div class="output execute_result" execution_count="24">

    array([[0.65594388, 0.36723099, 0.96020353],
           [0.99909868, 0.86394065, 0.86042125]])

</div>

</div>

<div id="w8UKVg-7FbA5" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056447,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="w8UKVg-7FbA5" outputId="9e731127-653d-4c1f-dd91-217b24a556ea">

``` python
import math  #así importamos la biblioteca math, que contiene las
             #funciones matemáticas definidas en el estándar de C
print('el número pi es ',math.pi)
print('el número e es ', math.e)
print('el coseno de 0 es ',math.cos(0))
```

<div class="output stream stdout">

    el número pi es  3.141592653589793
    el número e es  2.718281828459045
    el coseno de 0 es  1.0

</div>

</div>

<div id="O3SDVk2yFmsg" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:3,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056450,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="O3SDVk2yFmsg" outputId="3c950134-e47a-41c7-e657-2cce9dbd381c">

``` python
from math import pi as PI #así importamos el valor 3.14... con el nombre PI
from math import sin as seno #así importamos la función sin con el nombre seno
print('\n ¿el seno de pi es 0?',seno(PI))
```

<div class="output stream stdout">


     ¿el seno de pi es 0? 1.2246467991473532e-16

</div>

</div>

<div id="Fiz8UUAQFdZL" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056461,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="Fiz8UUAQFdZL" outputId="ff396fbb-745e-444c-c1b3-b69a84d7b90f">

``` python
np.cos(np.pi)
```

<div class="output execute_result" execution_count="27">

    np.float64(-1.0)

</div>

</div>

<div id="ZfMlvEz_Fw_2" class="cell markdown" id="ZfMlvEz_Fw_2">

# 7. Arrays de NumPy

</div>

<div id="x7TYz3XiFvVf" class="cell markdown" id="x7TYz3XiFvVf">

Como ya venimos anunciando, el mejor objeto que *Python* tiene para
realizar operaciones aritméticas son los **arrays** vienen con la
**Librería `NumPy`** (su clase interna es `ndarray`, es decir, un tipo
de matriz n-dimensional de elementos simples del mismo tipo, enteros,
reales,...). En nuestra cabeza, sirven para representar números,
vectores, matrices, etc., y hacer las **operaciones usuales** con ellos.

Por tanto, **para todo lo que sigue en esta asignatura**, lo primero
será cargar la **Librería `NumPy`** abreviada con el estándar `np`
mediante:

> > > <b><font color="green">import</font></b> numpy
> > > <b><font color="green">as</font></b> np

Hay diferentes funciones destinadas a **crear arrays** en numpy como
[np.arange](https://numpy.org/doc/stable/reference/generated/numpy.arange.html)
o
[np.linspace](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html)
entre otros:

| El código | crea un array... |
|:---|:---|
| `np.array(lista_o_tupla)` | ...cuyas componentes son los elementos de la lista o tupla |
| `np.arange(inicio,tope,paso)` | ...tipo vector. Funciona como `range` pero sus entradas pueden ser números reales |
| `np.linspace(inicio,fin,n)` | ...tipo vector con n componentes equiespaciadas, siendo `inicio` la primera y `fin` (<b>incluida</b>) la última |
| `np.random.rand(n,m)` | ...tipo matriz de tamaño $`n\times m`$ con números "aleatorios entre 0 y 1" |
| `np.diag(vector)` o `np.diagflat(vector)` | ...tipo matriz cuadrada colocando el `vector` en su diagonal |
| `np.diag(matriz)` | ...tipo vector que contiene la diagonal de la `matriz` |
| `np.vstack([v1,v2,...])` | ...tipo matriz con los vectores `v1`, `v2`,... como sus filas |
| `np.eye(n)` | ...tipo matriz identidad de tamaño $`n\times n`$ |
| `np.zeros(n)` | ...tipo vector de ceros de longitud $`n`$ |
| `np.zeros((n,m))` | ...tipo matriz de ceros de tamaño $`n\times m`$ |
| `np.ones(n)` | ...tipo vector de unos de longitud $`n`$ |
| `np.ones((n,m))` | ...tipo matriz de unos de tamaño $`n\times m`$ |
| `np.mgrid[inicio1:fin1,inicio2:fin2]` | ...como el mesh en *Matlab*, para hacer mallados (lo veremos en las gráficas 3D) |

Y otra forma muy interesante de crear arrays es **extrayendo datos
contenidos en ficheros** provenientes de otras fuentes (simulaciones,
APIs, bases de datos diversas...), pero eso lo dejamos para más
adelante.

**Notas**.

- Los elementos de un array **solo pueden ser de un tipo**, es decir,
  son secuenciales **homogéneos** (a diferencia de las listas), aunque
  son **mutables**. Así, una matriz de números enteros solo puede
  contener números enteros y solo se le pueden agregar o modificar con
  números enteros (lo trataremos ampliamente en el tema de sistemas de
  ecuaciones lineales). Si queremos que sea de números reales, hay que
  introducir al menos una componente con la coma decimal.

- Listas y arrays pueden parecer similares es aspecto, pero NO LO SON.
  En la siguiente celda mostramos **por qué hemos de trabajar con arrays
  en esta asignatura**

</div>

<div id="pUgotSbiFgaX" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:30,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056490,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="pUgotSbiFgaX" outputId="2debedd1-3b78-4ea1-ccac-1216a1cc7328">

``` python
# Notemos una diferencia "clave" entre listas y arrays o
# el porqué usaremos arrays en esta asignatura

v=[1,2] #este es una lista
print(v+v,3*v) # La "suma" de listas es la concatenación
v=np.array([1,2])  # nótese que ya hemos importado numpy con el abreviado np
print(v+v) # Sin embargo la "suma" de arrays sí es lo que nosotros esperamos
print(3*v) # o el multiplicar por un escalar
```

<div class="output stream stdout">

    [1, 2, 1, 2] [1, 2, 1, 2, 1, 2]
    [2 4]
    [3 6]

</div>

</div>

<div id="fGnaKINdeDBO" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056491,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="fGnaKINdeDBO" outputId="8bcc99ef-91d5-42ab-d40d-37ac97e1e961">

``` python
vector = np.linspace(1,2,6)
print(vector)
print(len(vector))
```

<div class="output stream stdout">

    [1.  1.2 1.4 1.6 1.8 2. ]
    6

</div>

</div>

<div id="xSFwzig_PsJR" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:7,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151056497,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="xSFwzig_PsJR" outputId="6e4723ee-3f3e-4494-8ce6-0272c54da58f">

``` python
# para una matriz, podemos usar una lista de listas o lista anidada
M = np.array([[1.,2,3],[4,5,6]])
print(M,type(M))
```

<div class="output stream stdout">

    [[1. 2. 3.]
     [4. 5. 6.]] <class 'numpy.ndarray'>

</div>

</div>

<div id="wHzN6sJFg_hT" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:221}"
executionInfo="{&quot;elapsed&quot;:9,&quot;status&quot;:&quot;error&quot;,&quot;timestamp&quot;:1771151056508,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="wHzN6sJFg_hT" outputId="d63d8a8d-bab9-4df5-e488-fd0428d3b809">

``` python
# nótese que la homogeneidad hace que todas las filas de una array
# (tipo matriz) han de tener la misma logitud
lista = [[1.,2,3],[4,5,6],[2,6]]
np.array(lista)
```

<div class="output error" ename="ValueError"
evalue="setting an array element with a sequence. The requested array has an inhomogeneous shape after 1 dimensions. The detected shape was (3,) + inhomogeneous part.">

    ---------------------------------------------------------------------------
    ValueError                                Traceback (most recent call last)
    /tmp/ipython-input-2484683690.py in <cell line: 0>()
          2 # (tipo matriz) han de tener la misma logitud
          3 lista = [[1.,2,3],[4,5,6],[2,6]]
    ----> 4 np.array(lista)

    ValueError: setting an array element with a sequence. The requested array has an inhomogeneous shape after 1 dimensions. The detected shape was (3,) + inhomogeneous part.

</div>

</div>

<div id="u9qbgwHwfllT" class="cell markdown" id="u9qbgwHwfllT">

Y con arrays se pueden realizar **operaciones booleanas** (que no valen
para listas)

</div>

<div id="e98mVDeDfeUW" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:5,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151069863,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="e98mVDeDfeUW" outputId="bd79fd31-3fd7-491e-db01-91079a31f6c3">

``` python
identidad = np.eye(3)
identidad == 1
```

<div class="output execute_result" execution_count="32">

    array([[ True, False, False],
           [False,  True, False],
           [False, False,  True]])

</div>

</div>

<div id="fCY80xOIfvIP" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:5,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151073209,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="fCY80xOIfvIP" outputId="9b910c2e-cbd5-4757-efdc-5352f449a0ab">

``` python
aleatoria = np.random.rand(3,3)-0.5
print('la matriz es: \n',aleatoria)
    #vamos a seleccionar sus componentes no negativas y redondearlas
np.round(aleatoria,3)*(aleatoria >= 0)
```

<div class="output stream stdout">

    la matriz es: 
     [[ 0.17119631 -0.33640437  0.16439725]
     [-0.14068203 -0.45116879 -0.01890989]
     [-0.46669509 -0.03520839 -0.18203398]]

</div>

<div class="output execute_result" execution_count="33">

    array([[ 0.171, -0.   ,  0.164],
           [-0.   , -0.   , -0.   ],
           [-0.   , -0.   , -0.   ]])

</div>

</div>

<div id="z5f9qxDqfKr6" class="cell markdown" id="z5f9qxDqfKr6">

## 7.1. Algunos comandos de *Python* para el manejo de *arrays*

Para no alargar más este tema introductorio, emplazamos al lector a ir a
los Temas 1, 1/2, y 2, sobre Sistemas de Ecuaciones Lineales, matrices y
vectores, donde trataremos más en profundidad los *arrays* y sus
operaciones.

Resaltamos a modo de **ejemplo** algunos detalles **útiles** más sobre
las diferencias entre listas y arrays y sobre cómo extraer componentes
usando `[ ]`.

</div>

<div id="xUMlN0cqgH34" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:6,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1771151077513,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="xUMlN0cqgH34" outputId="2781bb11-b78f-451f-d8b3-4f62b31c9acb">

``` python
A = [[1.,2,3],[4,5,6]] # A es una lista tipo matriz (lista de listas)
M = np.array(A)        # M es un array "aparentemente" igual a A
print(A)
print(M)
```

<div class="output stream stdout">

    [[1.0, 2, 3], [4, 5, 6]]
    [[1. 2. 3.]
     [4. 5. 6.]]

</div>

</div>

<div id="RtoTjauKgke5" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:275}"
executionInfo="{&quot;elapsed&quot;:43,&quot;status&quot;:&quot;error&quot;,&quot;timestamp&quot;:1771151079580,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="RtoTjauKgke5" outputId="0020e1c3-269b-48d9-e57a-6c94fac9c0b5">

``` python
print('A[0][1] produce: ',A[0][1])
print('M[0][1] produce: ',M[0][1])
print('M[0,1] produce: ',M[0,1])
print('Pero A[0,1] (que es una lista) produce un error... ')

A[0,1]
```

<div class="output stream stdout">

    A[0][1] produce:  2
    M[0][1] produce:  2.0
    M[0,1] produce:  2.0
    Pero A[0,1] (que es una lista) produce un error... 

</div>

<div class="output error" ename="TypeError"
evalue="list indices must be integers or slices, not tuple">

    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    /tmp/ipython-input-3363683865.py in <cell line: 0>()
          4 print('Pero A[0,1] (que es una lista) produce un error... ')
          5 
    ----> 6 A[0,1]

    TypeError: list indices must be integers or slices, not tuple

</div>

</div>

<div id="mlsDcKNt2TAZ" class="cell markdown" id="mlsDcKNt2TAZ">

# 8. Primeros pasos hacia la programación:<br> Comandos de control de flujo

</div>

<div id="_OFVEFhu2VXP" class="cell markdown" id="_OFVEFhu2VXP">

En los temas sucesivos vamos a estudiar y programar diversos Métodos
Numéricos mediante *algoritmos*. De una forma muy general, el **flujo**
de un algoritmo es la secuencia **ordenada y lógica** de los pasos que
se ejecutan para alcanzar cierto objetivo; en cada uno de estos
**pasos** pueden intervenir varias funcionalidades básicas que componen
el [**control del
flujo**](https://docs.python.org/es/3.14/tutorial/controlflow.html):

- En cada **paso**...
  - ... seguir unas **instrucciones** que se repiten a modo de
    **bucle**...
  - ... bien recorriendo un cierto **rango de valores**...
  - ... o bien mientras se cumpla una **condición** ([o
    varias](https://docs.python.org/es/3.14/reference/expressions.html#booleans),
    juntas o anidadas)...
  - ... que suponga, bien un **error** en el proceso, bien el **alcance
    del objetivo** ,...
- ... y que produzca en cualquier caso la **detención del proceso**.

La lista de funciones asociadas a estos controles de flujo no es muy
extensa y, sin embargo, son la clave de todo algoritmo. Algunas como
`for - in`, e incluso `if`, ya han aparecido sucintamente al definir una
lista por comprensión.

Al igual que hemos hecho con los comandos para arrays, creemos que es
mejor estudiar todos estos **controles de flujo** a través de ejemplos
**conforme vayan apareciendo** en los Métodos Numéricos que vamos a
estudiar. Por eso ponemos aquí solo un breve listado con una sucinta
descripción (y referimos esta sección del manual sobre [herramientas de
control de
flujo](https://docs.python.org/es/3.14/tutorial/controlflow.html), o
directamente:
[while](https://docs.python.org/es/3.14/tutorial/introduction.html#first-steps-towards-programming),
[if, elif,
else](https://docs.python.org/es/3.14/tutorial/controlflow.html#if-statements),
[for](https://docs.python.org/es/3.14/reference/compound_stmts.html#for),
[break,
continue](https://docs.python.org/es/3.14/tutorial/controlflow.html#break-and-continue-statements)
para ampliar).

<hr>

- `for - in`

``` python
for k in secuencial:
  instrucciones(k)
```

**Para** `k` recorriendo todos los valores en el `secuencial` (rango,
lista, string,...), se ejecutan las `instrucciones` para cada valor de
`k`

<hr>

- `while`

``` python
while condición:
  instrucciones
```

**Mientras** que la `condición` sea `True` se ejecutan las
`instrucciones`

<hr>

- `if - elif - else`

``` python
if condición 1:
  instrucción 1
elif condición 2:  #opcionales
  instrucción 2
elif condición 3:
  instrucción 3
...
else:              #opcional
  instrucción final
```

Primero se evalúa **si** la `condición 1` es `True` o `False`; cuando es
`True`, se ejecuta la `instrucción 1`.<br> (Opcional), **pero si** la
`condición 1` es `False` y la `condición 2` es `True`, se ejecuta la
`instrucción 2` ... y así sucesivamente. <br> Y **si todas fallan**
(todas las condiciones son `False`) entonces ejecuta la la
`instrucción final` que hay tras el `else` (que también es opcional).

<hr>

- `break`

``` python
break
```

Dentro de un bucle (`for`, `while`...), si llega a ejecutarse en alguna
instrucción, lo **detiene** inmediatamente.

</div>

<div id="fJ9ojnjmjVZV" class="cell markdown" id="fJ9ojnjmjVZV">

**Nota**. Notemos que, en todos los casos, el caracter `:` (**los dos
puntitos**) **dan paso a un bloque indentado**; igual que ocurría con
`def`... e igual que ocurrirá siempre en *python*, pues esto viene de su
[orígen a partir de otro lenguaje de programación, el
ABC](https://es.wikipedia.org/wiki/Historia_de_Python), desde su misma
creación.

</div>

<div id="0G7AtTarK4g0" class="cell markdown" id="0G7AtTarK4g0">

**Ejemplo**. Muestra todos los múltiplos de 7 entre 1 y 100, usando
todos los controles de flujo previos.

</div>

<div id="UKCXMXpuC_HU" class="cell code" id="UKCXMXpuC_HU">

``` python
for i in range(7,100,7):
    print(i)
    i = 5 # esto solo para que veas que no afecta al bucle: i se sobreescribe
```

</div>

<div id="HiyZxw6KLhFp" class="cell code" id="HiyZxw6KLhFp">

``` python
i = 7
while i < 100:
    print(i)
    i = i+7
```

</div>

<div id="jlVWY5mtL6TO" class="cell code" id="jlVWY5mtL6TO">

``` python
i = 7
while i < 100:
  if i%7==0:    #recuerda que a%b es el resto de dividir a entre b
    print(i)
  i += 1    # otra forma de poner i = i+1
```

</div>

<div id="nLF9whYeMXmd" class="cell code" execution_count="22"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:16,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1781093905469,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-120}"
id="nLF9whYeMXmd" outputId="254da828-7ca9-48f2-9210-9459cedcba72">

``` python
numeros = [k for k in range(1,100000)]
for i in numeros:
  if i%7==0:
    print(i)
  elif i>100:
    break
```

<div class="output stream stdout">

    7
    14
    21
    28
    35
    42
    49
    56
    63
    70
    77
    84
    91
    98

</div>

</div>

<div id="MS95xCtah-FZ" class="cell markdown" id="MS95xCtah-FZ">

# Bibliografía y Referencias

</div>

<div id="NRnnYsCam4xJ" class="cell markdown" id="NRnnYsCam4xJ">

1.  [*Tutorial de
    Markdown*](https://www.datacamp.com/es/tutorial/markdown-in-jupyter-notebook).
    `https://www.datacamp.com/`

2.  [*Python:
    download*](https://wiki.python.org/moin/BeginnersGuide/Download).
    `https://wiki.python.org/moin/BeginnersGuide/Download`

3.  [*Google Colab*](https://colab.research.google.com/).
    `https://colab.research.google.com/`

4.  [*Python:
    tutorial*](https://docs.python.org/es/3.14/tutorial/index.html).
    `https://docs.python.org/es/3.14/tutorial/index.html`

5.  [*Python: índice
    general*](https://docs.python.org/es/3.14/genindex.html).
    `https://docs.python.org/es/3.14/genindex.html`

</div>
