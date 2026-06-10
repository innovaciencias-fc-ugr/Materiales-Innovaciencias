---
marp: false
---

<!--LTeX: language=es-->

Esto es una prueba para hoy. Yo puedo escribir en español sin ningún problema. ¿En qué más puedo ayudarte?


# Título del documento

Empiezo mi teexto aquí. Puedo escribir en español y continuar con el contenido del documento.


---

## Listas

### Listas sin numeración

- Primer elemento
- Segundo elemento
- Tercer elemento
  - Sub-elemento uno
  - Sub-elemento dos
- Cuarto elemento

Se pueden usar asteriscos.

* otra forma
* otra forma más

---

### Listas numeradas

1. Primer elemento
1. Segundo elemento
1. Se me olvidó uno
1. Tercer elemento
    1. otra cosa
    1. y otra más
        1. otra más 
1. Una más

---

## Algunos tipos de letra

Puedo usar **negrita** para resaltar texto importante. Si quiero usar *cursiva*, también es posible. Incluso puedo combinar ambos estilos como en ***este ejemplo***. Otra opción es usar __negrita__ y _cursiva_ con guiones bajos. Una combinación de ambos es _**así**_.

---

## Tablas

| Uno | Dos | Tres y más |
| :--- | :---: | ---: |
|  Ambos lados  |  B  |  C   |
|  D  |  E  |  F   |
|  G  |  H  |  I   |

| Algo | Otra cosa |
| --- | --- |
| 123 | 456 |
| 789 | 012 |


---

## Enlaces

Puedes visitar [Google](https://www.google.com) para buscar información. También puedes ir a [Wikipedia](https://www.wikipedia.org) para obtener artículos enciclopédicos.

En la página de la [Universidad de Granada][UGR] encontrarás información sobre sus programas académicos y eventos, y en la página de la [univerisidad][UGR] también encuentras otras cosas.

[UGR]: https://www.ugr.es 

----

## Imágenes

Igual que los enlaces, pero con un signo de exclamación al principio:

![Logo de Markdown](https://markdown-here.com/img/icon256.png)

![Parábola](parabolic-calculator/math4you_00010.jpg)

![logo de la UGR](https://secretariageneral.ugr.es/sites/webugr/secretariageneral/public/inline-files/UGR-MARCA-01-color.png)

---

## Citas

Esto os va a sonar:

> La vida es como una caja de chocolates, nunca sabes lo que te va a tocar.
> Forrest Gump


## Código

Código en línea `print("Hola, mundo!")`

```python
def saludar():
    print("¡Hola, mundo!")
```

```latex
\documentclass{article}
\begin{document}
Hola, mundo!
\end{document}
```

Otra forma

    Esto es un párrafo citado


$$
E = mc^2
$$