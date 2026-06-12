<div id="e2dc1195" class="cell markdown" id="e2dc1195">

# Notas internas: sólo para Óscar y Juanjo

## Se trata de, a partir de los notebooks de jupyter de la asignatura, que contienen tanto texto **LaTeX** como **Markdown** y **html** y código **Python**, crear una página con todos esos ficheros usando **quarto**

<img align="right" height="100 pt" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQCDYEVMIpQs1vcJwsH-FG-Kc9W7G5NaYqirw&s">
<img align="right" height="120 pt" src="https://www.ugr.es/~ossanche/images/fotoCuba.jpg">

(Se acompaña un ejemplo de fichero que corresponde a una brevísima
introducción a *Python - numpy* y a *Jupyter notebooks*)

</div>

<div id="ba61dffe" class="cell markdown">

En cafa fichero .ipynb

- Lo primero **siempre** es: **\# Título del tema, (sin número)**

- Brebe intro al tema. Puede estar en la misma celda que el título, no
  importa.

- Eventualmente ponemos una imagen, pero siempre **después** del título
  y con `align="right"`.

La **estructura** ya **no** hace falta porque:

- En Google Colab, se ve en el menú de la izquierda.
- En el html que sale al quartizar, estará en un menú autogenerado a la
  derecha.

Y ya está; ponemos una ralla con el `<hr>` y pasamos al tema

- primero:
  `{python} #inicio de todas las librerías que se usan para este tema import numpy as np`

- iniciamos celda nueva con la sección 1 usando \# Sección <hr>

</div>

<div id="iFh860t9W0BP" class="cell code" id="iFh860t9W0BP">

``` python
#inicio de todas las librerías que se usan para este tema
import numpy as np
import time
```

</div>

<div id="2d696b66" class="cell markdown" id="2d696b66">

## 1. Numeración de secciones

</div>

<div id="-1-BQpGsSCpN" class="cell markdown" id="-1-BQpGsSCpN">

Contenidos en texto

Numeramos con `#` secciones y ponemos número 1 2 3 (el número del Tema
NO aparece

Numeramos con `##` sub secciones y ponemos número 1.1 1.2 1.3

</div>

<div id="9QOvtySCSFe1" class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:12,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1769766168800,&quot;user&quot;:{&quot;displayName&quot;:&quot;JUANJO NIETO&quot;,&quot;userId&quot;:&quot;02589853982522161924&quot;},&quot;user_tz&quot;:-60}"
id="9QOvtySCSFe1" outputId="7d09cef0-b350-4a65-a650-9c5add1bdbb9">

``` python
print("contenidos codigo")
```

<div class="output stream stdout">

    contenidos codigo

</div>

</div>

<div id="heRXFfwHSjjL" class="cell markdown" id="heRXFfwHSjjL">

## 2. Presentación asignatura ¿dónde va?

Para hacer libro con quarto, este contenido lo vamos a colocar en el
fichero `index.qmd`, del que se creará el home: `index.html`

</div>

<div id="NpKYF-JJTvuH" class="cell markdown" id="NpKYF-JJTvuH">

### 2.2. Contenido literal del fichero index.qmd

</div>

<div id="PIUpvwMUT2Vo" class="cell markdown" id="PIUpvwMUT2Vo">

    ---
    title: "MÉTODOS NUMÉRICOS I<br>Manual interactivo de la asignatura con ejercicios y prácticas en **Python**"
    ---

    ## <img  width="40px" name="Creative Commons - Attribution icon" src="https://mirrors.creativecommons.org/presskit/buttons/88x31/png/by-nc-sa.png"> (2025) Profesores Juanjo Nieto y Óscar Sánchez<br>
    <font size=+2> **1<sup><u>o</u></sup>. del grado en Matemáticas**</font><BR> <img  width="250px" name="Logo UGR" src="https://secretariageneral.ugr.es/sites/webugr/secretariageneral/public/inline-files/UGR-MARCA-02-color.png">



    <hr >

    ## Presentación de este manual interactivo:

    Este **MANUAL INTERACTIVO DE LIBRE USO** ha sido preparado por los profesores Juanjo Nieto y Óscar Sánchez para la asignatura **Métodos Numéricos I** y pretende ser un material completo a la par que adaptable y dinámico.

    Por un lado, comprende unos **apuntes completos de la asignatura**, con contenidos teóricos, resultados, demostraciones y ejemplos, que permitan a los estudiantes seguir la asignatura de un modo autónomo, aunque nunca sustituirán por completo la labor docente en el aula. Por otro lado, con la doble experiencia de los autores tanto en el aula como en la elaboración de varios manuales *estáticos* de contenido numérico, este manual no solo contiene códigos asociados a los algoritmos estudiados, sino que se aprovecha de la existencia de la aplicación web de código abierto **Jupyter Notebook**, para presentar y ejecutar (en línea y/o localmente) tanto texto científico para los contenidos (en particular **LaTeX**) como lenguajes de programación (en particular **Python**) para los algoritmos, de modo que el estudiante pueda, **tanto durante el desarrollo de las clases como en su estudio posterior**, manipular, modificar, ampliar o resaltar a su conveniencia tanto lo uno como lo otro. Además de usar los **Jupyter Notebook**, el manual completo se ha renderizado mediante **quarto** para ser presentado como **página web** y pueda ser consultado (aunque no ejecutado) a través de cualquier navegador, en cualquier parte del mundo, y sin necesidad de adquirir software adicional.

    El resultado se publica por primera vez en el curso 2025/26 tanto en **ipynb** como  en **html** aunque, como acabamos de anunciar, lo previsible es ir añadiendo contenidos (ejemplos en principio, aunque no exclusivamente) en cursos sucesivos. Rompemos pues con la clásica edición-reedición de libros impresos para pasar a este material interactivo, vivo y personalizable, por supuesto **de libre uso y gratuito** bajo una licencia [*Creative Commons BY-NC-SA*](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.es) que garantiza que el conocimiento sea abierto y esté disponible gratuitamente para que todos puedan aprender, descubrir y contribuir.

    Por lo tanto, también nos situamos en la línea del **ODS4 de la UNESCO** (*Educación, 2030*), donde se refleja uno de los puntos clave pretendidos en este manual: eliminar disparidades económicas, garantizando el acceso a educación técnica/superior de calidad para todos.



    Por todo lo anterior **se prohíbe explícitamente su distribución en cualquier medio físico u online que conlleve cualquier tipo de beneficio económico**. <br><br>

    <p align=right>Juanjo Nieto y Óscar Sánchez<br>
    Profesores de la Universidad de Granada</p><br>

    **PS**. Aunque somos conscientes de que existe software científico específico para los métodos numéricos, y por tanto eventualmente mejores que *Python* para este fin, lo hemos elegido como lenguaje de programación por varias razones, incluyendo su sintaxis clara, su rápida curva de aprendizaje y versatilidad, pero sobre todo, por ser de acceso libre y por el elevadísimo número de usuarios y colaboradores (el más usado en 2025) en todos los ámbitos. No obstante, estas notas NO son, y no pretenden ser, un manual de *Python*. Aunque son autocontenidas y, por tanto, hemos incluido lo necesario para abordar los algoritmos tratados, se ajustan a los contenidos y (sobre todo) a los tiempos de la asignatura Métodos Numéricos I, lo que no deja espacio para abordar en profundidad este lenguaje de programación. En particular, este tema inicial 0.A. es muy muy básico y está pensado como un *motor de arranque* para quienes nunca han usado ningún lenguaje de programación. Se incluyen, no obstante, aquí y a lo largo del manual, algunas referencias externas (de acceso libre) para que el estudiantado pueda ampliar conocimientos, con numerosos *guiños* o invitaciones a hacerlo.

</div>

<div id="3SMyFeI8hBSI" class="cell markdown" id="3SMyFeI8hBSI">

## 3. Quarto

</div>

<div id="fySojH1rwJhc" class="cell markdown" id="fySojH1rwJhc">

- **Todos** los **proyectos** de **Quarto** incluyen un archivo de
  configuración `_quarto.yml`.<br>

- Para quartificar basta, desde el terminal y una vez estemos en la
  carpeta donde están todos los ficheros, ejecutar:

``` python
quarto render
```

YML (o YAML) es un formato de serialización de datos, usado para
archivos de configuración y transferencia de datos, que utiliza
**sangría** (como Python) para estructurar la información en lugar de
etiquetas (como XML).

- Cualquier documento que esté dentro del directorio del proyecto
  heredará automáticamente en los metadatos definidos a nivel de
  proyecto (a menos que le indiquemos lo contrario).

</div>

<div id="3-powdlFgHGJ" class="cell markdown" id="3-powdlFgHGJ">

### 3.1. Contenido del fichero \_quarto.yml

</div>

<div id="tAQTQqxGVv_D" class="cell markdown" id="tAQTQqxGVv_D">

    project:
      type: website

      render:
      - "index.qmd"
      - "*.ipynb"
      - "!Plantilla.ipynb"

    website:
      title: "MET NUM I"
      navbar:
        search: false

        style: "docked"
        left:
          - href: "Tema0A-Intro-python.ipynb"
            text: "Tema 0A"
          - href: "Tema0B-Intro-Analisis-num.ipynb"
            text: "Tema 0B"
          - href: "Tema1-SEL-met-directos.ipynb"
            text: "Tema 1"
          - href: "Tema1ymedio-normas-espacios-matriciales.ipynb"
            text: "Tema 1&#189;"
          - href: "Tema2-SEL-met-iterativos.ipynb"
            text: "Tema 2"
          - href: "Tema4-Interpolacion.ipynb"
            text: "Tema 4"
          - href: "Tema5-MinimosCuadrados.ipynb"
            text: "Tema 5"   
          - href: "Tema3-valores-propios.ipynb"
            text: "Tema 3"

    format:
      html:
        theme:
          - cosmo
          - brand
        toc: true
        toc-title: Índice del tema
        toc-location: right
        toc-depth: 2
        toc-expand: 2
        number-sections: false
        html-math-method: katex
        lang: es
        title-block-banner: green
        title-block-banner-color: white
        code-fold: false
        code-summary: "Mostrar/ocultar el código Python"
        code-line-numbers: true
        code-link: true
        code-tools:
          source: false
          toggle: false
          caption: "Python"
        code-block-bg: true
        code-block-border-left: "#31BAE9"

</div>

<div id="1jxJ2G5eYNUI" class="cell markdown" id="1jxJ2G5eYNUI">

### 3.2. Sobre este contenido

</div>

<div id="mOWpVvUwppjy" class="cell markdown" id="mOWpVvUwppjy">

- Código *Python* desplegable

<!-- -->

    format:
      html:
        code-fold: false
        code-summary: "Mostrar/Ocultar Código"

Con `true` se ocultan los códigos python en el html, y aparece un
desplegable con un <ins>► Mostrar/Ocultar Código</ins><br> Sin el
`code-summary` aparece por defecto `Code` o `Código` (si tenemos el
español con `lang: es`)

<hr>

- Colores cabecera

<!-- -->

    format:
      html:
        title-block-banner: green
        title-block-banner-color: white

<hr>

- Índice de cada hoja

<!-- -->

    format:
      html:
        toc: true
        toc-title: Índice del tema
        toc-location: left
        toc-depth: 2
        toc-expand: 2

> - `toc: true` crea el índice.
> - `toc-title` cambia el título del índice.
> - `toc-location:` lo pone a izda o derecha según opción.
> - `toc-depth` indica hasta qué profundidad de sub-seccionado mete en
>   el índice
> - `toc-expand` indica qué profundidad se muestra por defecto (al
>   navegar se van abriedo las sucesivas)

<hr>

- Renderizar unos sí y otros no

<!-- -->

    project:
      render:
        - "*.ipynb"
        - "!Plantilla.qmd"

Por defecto quarto renderiza **todo** el contenido de la carpeta. Cuando
solo quieres unos cuantos, o quieres fijar un orden, se añade esto. <br>
Tal y como está, renderiza todos los .ipynb menos el que se llama
`Plantilla.ipynb`

<hr>

- Numerador de secciones (ponemos false, pues no queremos)

<!-- -->

    format:
      html:
        number-sections: false

Si se pone `true`, las numera en el html... (pero no tiene que ver con
la numeración que tú pusiste en el jupyter).

<hr>

- Formateo de las celdas de código:

<!-- -->

    format:
      html:
        code-line-numbers: true
        code-link: true
        code-block-bg: true
        code-block-border-left: "#31BAE9"

`code-line-numbers: true`: Para que ponga en las celdas de código los
números de línea

`code-link: true`: supuestamente enlaza las funciones a su documentación
online

`code-block-bg: true`: crea una sombra que cubre todo el bloque

`code-block-border-left: "#31BAE9"`: añade una línea vertical del color
elegido

<hr>

- Para poner un menú extra que muestre/ oculte el código (no lo vamos a
  usar)

<!-- -->

    format:
      html:
        code-tools:
          source: false
          toggle: false
          caption: "Python"

</div>

<div id="b0zcEfbwrdX8" class="cell markdown" id="b0zcEfbwrdX8">

**Sugerencias para IMPRIMIR unas notas**

- Para que NO muestre las salidas del código

<!-- -->

    execute:
      output: false

- Para evitar el índice, y todo el espacio vertical que conlleva

<!-- -->

    format:
      html:
        toc: FALSE

</div>

<div id="ZbRFUxYddIBx" class="cell markdown" id="ZbRFUxYddIBx">

### 3.1. Problemas que hemos ido detectando al hacer **quarto render**

</div>

<div id="twV6J39fdOpU" class="cell markdown" id="twV6J39fdOpU">

- Antes de un *itemizado* con guiones `-` hemos de poner un espacio
  vertical `Enter`, si no no lo quartiza como itemizado

- Las secciones, subsecciones, etz, **no pueden llevar un espacio antes
  del \#**

- Los `\mbox{ }` entre dólares fallan mucho. Pero si usamos `\text{ }`
  sale bien. La otra alternativa es no poner nada.

- Los `\fbox{ }` fallan mucho, pero aún no sé como arreglarlo. <br>
  Posibles soluciones;

  - Para texto: usar el subrayado con código html `<ins>texto</ins>` que
    produce <ins>texto</ins> o bien<br> `<u>texto</u>` que produce
    <u>texto</u>
  - para fórmulas o texto: usar el resaltado a color con código html
    `<mark>texto</mark>` y `<mark>$i \Rightarrow ii$</mark>` que produce
    <mark>texto</mark> y <mark>$`i \Rightarrow ii`$</mark>
    respectivamente. (quarto lo compila bien, pero jupyter aveces sí y a
    veces no.

- Evitar los `\displaystyle` dentro del LaTeX... no van bien (bueno,
  puede que sea más lo que viene ahora...)

- En las fórmulas en línea de LaTeX, no dejar espacios justo después del
  primer dólar. `$x_0=1$` sí, pero `$ x_0=1$` NO

- En las fórmulas en línea de LaTeX, no dejar espacios justo antes del
  último dólar. `$x_0=1$` sí, pero `$x_0=1 $` NO

- En lugar de usar `mathop{BASE}^{algo}_{otro}` usaremos
  `\stackrel{algo}{BASE}` y `\underset{otro}{BASE}`.

- El tipo de letra `\cal` o `\mathcal` no funcionan en general en
  markdown (en particular en Colab), aunque si al renderizar en quarto

</div>

<div id="IXDZOMmlRSBl" class="cell markdown" id="IXDZOMmlRSBl">

## 4. Imágenes. Espacio donde alojaremos las imágenes

</div>

<div id="8nrdMrAwWI9s" class="cell markdown" id="8nrdMrAwWI9s">

<https://www.ugr.es/~jjmnieto/images/metNumI/>

Listado de imágenes:

| fichero | imagen |
|:---|---:|
| *algo.png* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/algo.png"> |
| *AnalysisNewton.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/AnalysisNewton.jpg"> |
| *aproximacion.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/aproximacion.jpg"> |
| *diferdivNewton.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/diferdivNewton.jpg"> |
| *error.png* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/error.png"> |
| *heron.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/heron.jpg"> |
| *interlineal.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/interlineal.jpg"> |
| *jacobi.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/jacobi.jpg"> |
| *overflow.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/overflow.jpg"> |
| *proyeccion.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/proyeccion.jpg"> |
| *spline.png* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/spline.png"> |
| *udc.png* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/udc.png"> |
| *64b.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/64b.jpg"> |
| *32b.jpg* | <img height="40 pt" src="https://www.ugr.es/~jjmnieto/images/metNumI/32b.jpg"> |

</div>

<div id="-7oRW_M0Yoab" class="cell markdown" id="-7oRW_M0Yoab">

## 5. Estilo

</div>

<div id="OjZ4i0-zYs44" class="cell markdown" id="OjZ4i0-zYs44">

### 5.1. Teoremas, lemas y definiciones

> **Teorema** (Si tiene subtítulo)<br> Lorem ipsum dolor sit amet,
> consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
> labore et dolore magna aliqua.
> ``` math
>  f(x)= \int^x g(s) ds = \underset{\text{texto abajo}}{\underbrace{x^2+x+5}} + \stackrel{\text{texto arriba}}{\overbrace{x^3-x+5}}
> ```
> Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
> nisi ut aliquip ex ea commodo. <ol type=i> <li> Sed ut perspiciatis
> unde omnis </li> <li> iste natus error sit voluptatem </li> <li>
> accusantium doloremque laudantium </li> </ol>

La anterior forma no mantiene indentados ni la numeración se ve bien en
GoogleColab, por lo tanto propongo esta sintaxis, que he comprobado se
ve perfectamente en VSCode y renderiza perfectamente en quarto.

> **Teorema** (Propiedades de las diferencias divididas)
>
> 1.  La diferencia dividida $`f[x_0,\dots,x_n]`$ es **simétrica**
>     respecto de los nodos $`x_0`$,..., $`x_n`$. Concretamente:
>     ``` math
>     f[x_0,\dots,x_n] = \sum_{j=0}^n \frac{y_j}{\displaystyle \prod{i=0,i\neq j}^n(x_j-x_i)}.
>     ```
> 2.  Se verifica la siguiente **relación de recurrencia**:<br>
>     i\) Para un solo nodo: $`f[x_k] = y_k`$;
>     ii\) Para $`k\geq 1`$, se cumple:
>     ``` math
>      f[x_0,\dots,x_k] = \frac{f[x_1,\dots,x_k]-f[x_0,\dots,x_{k-1}]}{x_k-x_0}.
>     ```
>     iii\)
>     ``` math
>      f(x)= \int^x g(s) ds = \underset{\text{texto abajo}}{\underbrace{x^2+x+5}} + \stackrel{\text{texto arriba}}{\overbrace{x^3-x+5}}
>     ```

**Notas importantes**

- Dejar un espacio con su `>` tras el título del teorema.
- No meter intros dentro de los dobles dólares.

</div>

<div id="BjkFlJhDZgIQ" class="cell markdown" id="BjkFlJhDZgIQ">

### 5.2. Demostraciones

Salvo que sean muy muy breves, en celda aparte.

Y si es muy muy larga, se le pone una subsección (`###`o más) para poder
comprimirla cuando estemos con *Jupyter*

Para comenzar pondermos:

--Demostración del loquesea-- <br>

y la demo.

</div>

<div id="tq_j4zpoeD3S" class="cell markdown" id="tq_j4zpoeD3S">

### 5.3. Algunos símbolos en html

</div>

<div id="y_9ZdOuEeJE8" class="cell markdown" id="y_9ZdOuEeJE8">

| fichero    | imagen |
|:-----------|:------:|
| `&#188;`   |   ¼    |
| `&#189;`   |   ½    |
| `&#190;`   |   ¾    |
| `&#35;`    |   \#   |
| `&#149;`   |        |
| `&#183;`   |   ·    |
| `&bullet;` |   •    |
| `&#176;`   |   °    |

</div>

<div id="6Rvjfb2KWEFQ" class="cell code" id="6Rvjfb2KWEFQ">

``` python
```

</div>
