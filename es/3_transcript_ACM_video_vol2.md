<p float="left">
 <a href="https://www.dataumbrella.org"> <img src="../images/full logo-transparent copy.png" height="40%" width="40%" /> </a>
  <img  width="150" />
   <a href="https://github.com/scikit-learn" target="_blank"> <img src="../images/1280px-Scikit_learn_logo_small.svg.png" width="15%" height="15%" />  </a>
</p>


# [Data Umbrella](https://www.dataumbrella.org): Video de Andrea con las Instruccuines de scikit-learn Volume 2 

## Transcripción del Video
- Ponente:  [Andreas Mueller](https://twitter.com/amuellerml)
- Video:  [Scikit-learn Sprint Instructions: Volume 2 FAQs](https://youtu.be/p_2Uw2BxdhA) (15 minutes)
- PDF diapositivas: [Open Source Sprint Instructions for scikit-learn](https://onedrive.live.com/view.aspx?resid=4D2D28C53EB310F1!1533&ithint=file%2cpptx&authkey=!AM7c29_RJfitJrc)
- Transcriptora: [Victoria Levchenko](https://www.instagram.com/autotelic.computer/)

## Enlaces principales
- [Contributing Workflow Commands](https://github.com/data-umbrella/data-umbrella-scikit-learn-sprint/blob/master/contributing/workflow.md)
- [Scikit-learn Contributing Documentation](http://scikit-learn.org/stable/developers/contributing.html)


## Video
<a href="https://youtu.be/p_2Uw2BxdhA?t=1"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-01.png" width="90%" /></a>

---

### Diapositiva 1: Introducción (0:00)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-01.png" width="50%" /></a>

Hola a todos, este es otro video que brinda información sobre cómo contribuir a scikit-learn, en particular como parte de un sprint de código abierto. Reshama está organizando otro sprint junto con Data Umbrella, esta vez con un enfoque geográfico en África y Oriente Medio. Hemos recibido muchos comentarios sobre sprints pasados y estoy tratando de aclarar algunos de los puntos con los que la gente tuvo problemas en nuestros sprints pasados en este video aquí.

### Diapositiva 2: Echa un Vistazo a los Conceptos Básicos (0:31)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-02.png" width="50%" /></a>

Si aún no lo ha hecho, consulte los videos que publicamos antes. Le di una breve descripción general de cómo contribuir a scikit-learn y Reshama hizo un recorrido completo para crear su primer PR. Si eres nuevo en contribuir al código abierto y / o scikit-learn, te recomiendo que revises ambos.


Este video asumirá que comprende los conceptos básicos que describimos allí y discutiremos algunos de los temas con más detalle.

### Diapositiva 3: Programando por Parejas (0:59)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-03.png" width="50%" /></a>

Primero, estamos programando por parejas. Durante un sprint, recomendamos encarecidamente a las personas que trabajen en parejas mediante un proceso de Agile Development llamado programación en parejas. La programación en pareja es genial. La programación en pareja es excelente porque permite a los participantes compartir conocimientos. Por lo general, aumenta mucho la diversión de programar, en particular si es nuevo en su base de código. Es común tener problemas y tener más ojos en el código a menudo ayuda.

En la programación de pares, tiene dos desarrolladores trabajando juntos en el mismo problema con una persona conduciendo que realmente escribe el código. La otra persona observa y comenta la programación con la persona que conduce. En este momento, es probable que no esté en el mismo espacio que la persona con la que está codificando, pero las plataformas en línea como Discord le permiten compartir fácilmente su pantalla y tener un canal de audio privado. Poder hablar mientras se escribe el código es muy importante para que la programación por pares sea productiva.

### Diapositiva 4: Programando por Parejas: CONSEJOS (2:04)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-04.png" width="50%" /></a>

Una buena programación en pareja depende de que ambas personas sean buenos comunicadores y sean pacientes entre sí, lo cual requiere mucha práctica. Ustedes dos deberían estar hablando juntos básicamente constantemente.

Recomendaría que la persona que esté menos familiarizada con el código base o que se sienta menos segura acerca del trabajo conduzca la mayor parte del tiempo. Esto puede ser un poco intimidante al principio, pero les brindará una gran oportunidad de aprendizaje a ambos. Si la persona más experimentada está conduciendo, es muy fácil que pierda al otro. Con la persona menos experimentada conduciendo, la persona que conduce probablemente aprenderá algunos consejos de programación del otro mientras que el observador practicará explicando sus ideas en detalle. En otras áreas, es posible que tengan una fuerza complementaria y aprenderán unos de otros. Puedes cambiar quién conduce, pero yo no cambiaría muy a menudo. En cambio, hablaría juntos sobre cualquier obstáculo.

### Diapositiva 5: Navegando por el código (3:06)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-05.png" width="50%" /></a>

Bien. Digamos que ha encontrado un socio y ha encontrado un problema en el que desea trabajar. Si ambos son nuevos en scikit-learn, es una buena idea orientarse un poco. En general, creo que la concisión de Python significa que es bastante fácil navegar manualmente incluso por bases de código complejas, pero contar con la ayuda de una herramienta de programación ayuda. Solía codificar en Vim, pero en estos días estoy usando VSCode. Te mostraré cómo navegar por el código base con él. Sin embargo, puede hacer lo mismo con cualquier otro IDE o editor.

### Demostración 1: VSCode (3:41)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-demo-01.png" width="50%" /></a> 

Entonces aquí abrí el repositorio scikit-learn en VSCode. Puede ver todos los archivos y carpetas en el lado izquierdo. Por lo general, un proyecto de Python tiene un `setup.py` en el nivel superior del repositorio, que puede ver aquí. Y luego está la carpeta que contiene el módulo real que es `sklearn` en este caso. Solo el código que es parte de la biblioteca estará en esta carpeta. Entonces puede haber varias otras carpetas. Scikit-learn se ha vuelto bastante complejo a lo largo de los años, por lo que hay muchas carpetas. No quiero pasar por todos ellos.

Muchos de los archivos y carpetas configuran en realidad varias infraestructuras de integraciones continuas y canalizaciones automáticas para la liberación de paquetes. Eso es, por ejemplo, `.circleci` y .`.github` y muchos de los archivos yaml que verá aquí para las canalizaciones de Travis y Azure, etc. Es relativamente poco probable que en un sprint toque alguno de estos. Es más probable que trabaje en otras dos carpetas relacionadas con la documentación, que son `examples` y `doc`.

La carpeta de `examples` contiene ejemplos de scripts de Python que también se representan en el sitio web. Como puede ver, cada una de estas carpetas aquí tiene varios archivos de Python. Y la carpeta `doc` contiene el código del sitio web y de toda la guía del usuario. Y te contaré un poco más sobre esto en un momento.
Las pruebas en scikit-learn se entrelazan con el código en carpetas de prueba separadas. Entonces, dentro de la carpeta `sklearn`, tiene una carpeta de `tests` aquí. Y dentro de cada una de las subcarpetas, tiene una carpeta de `tests` que es específica para este submódulo en particular. Por ejemplo, si desea trabajar en la regresión logística, la regresión logística se encuentra en la carpeta `sklearn/linear_model`. Y aquí hay un archivo `_logistic.py` que contiene regresión logística. Y las pruebas correspondientes estarán en la carpeta del modelo lineal en la subcarpeta `tests/test_logistic.py`.

Bien. Por tanto, supongamos que quiere abordar un problema en particular.


### Demostración 2: scikit-learn PR (6:08)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-demo-02.png" width="50%" /></a> 

Por ejemplo, este de aquí. En este número, hay una queja sobre docstring. Entonces, esta es una cadena de documentación de la puntuación de Calinski-Harabasz. Digamos que queremos encontrar esto.

### Demostración 3: Buscando función (6:30)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-demo-03.png" width="50%" /></a> 

La forma más sencilla de hacerlo es utilizar la función de búsqueda en su editor. Si su editor no tiene una función de búsqueda, también puede usar `git grep`. Afortunadamente, este nombre es bastante único y, por lo tanto, los resultados de búsqueda son bastante pequeños. Aún así, le ayuda a comprender las diferentes carpetas en las que se encuentran los resultados. Así que aquí están los `doc/modules`. Esta es la documentación:  `sklearn/metrics`. Este es el código, por lo que es la implementación real. Entonces aquí, estas son las pruebas. También podemos encontrar breve y rápidamente la definición simplemente poniendo `def` delante de ella.

Y ahora vamos al código real. El problema era sobre la cadena de documentos. En los documentos, la cadena de documentos es parte de la documentación que está con el código. Así que aquí tienes la definición de la función. Y justo después de la definición de la función tienes esta cadena. Esto es lo que se mostrará en la documentación de la API en el sitio web, que es diferente a la guía del usuario. La guía del usuario se encuentra en la carpeta `doc`. Y ahora, si quieres hacer un cambio, puedes hacerlo aquí.

### Diapositiva 7: Basics of Sphinx (7:58)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-07.png" width="50%" /></a>

Ahora entremos un poco más en la documentación y el sitio web. La documentación se genera usando una herramienta llamada Sphinx y está escrita principalmente en un lenguaje de marcado llamado reStructuredText o RST. No es un lenguaje muy común fuera de la documentación de Python y necesita acostumbrarse un poco.

Todos los archivos de la carpeta de documentación (carpeta `doc`) están escritos en RST. Son analizados por la herramienta Sphinx, que luego genera el sitio web. Sphinx también puede generar otras salidas como archivos PDF, pero normalmente utilizamos principalmente la salida HTML para nuestro sitio web. Sphinx también lee parte de la documentación que está dentro del código. Las cadenas de documentos que vimos están incrustadas con las definiciones de la clase de función. Luego, estos también se representan en el sitio web. Como dije antes, Sphinx también lee los ejemplos y los pone en el sitio web. Entonces, si desea modificar la parte de la documentación que es parte de su cadena de documentos, como le mostré, debe hacerlo en el código fuente. Entonces, todo lo que se representará en la documentación de la API está escrito en el código fuente. Si desea modificar la guía del usuario, esta se escribirá en RST dentro de la carpeta `doc`.

La cadena de documentos tiene un formato particular: el formato `numpydoc`. Tenemos varias otras convenciones nosotros mismos. Puede encontrar todos estos en la guía para colaboradores.

### Diapositiva 8: Actualizando su branch(es) (9:29)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-08.png" width="50%" /></a>

Está bien. Entonces, finalmente, quiero hablar sobre dos problemas con git con los que la gente a menudo lucha. En los otros videos, ya analizamos el flujo de trabajo básico, pero hay dos tareas que a menudo surgen y quiero resaltar.

Durante un sprint, puede haber mucha actividad en el repositorio y los cambios que hacen las personas pueden ser relevantes para lo que sea en lo que estés trabajando. Esto puede generar conflictos o hacer que trabaje en una versión desactualizada del código. Antes de comenzar cualquier cosa y siempre que GitHub le muestre que su rama no está sincronizada, debe actualizar su rama de funciones para sincronizar con el repositorio principal. Para eso, asegúrese de que actualmente tiene su rama de características verificada con `git checkout feature_branch`, donde feature branch es el nombre de su branch. Luego, suponiendo que haya agregado el repositorio principal como su control remoto llamado upstream, puede hacer `git pull upstream master` para buscar y fusionar con la rama master upstream. Si hay algún conflicto, debe resolverlo ahora. Luego, una vez que se complete la fusión, puede enviarla, su rama de características, a su bifurcación (por lo que el origen es remoto) con `git push origin feature_branch`. Si tiene una solicitud de extracción basada en la rama de su función, el PR se actualizará automáticamente.

### Diapositiva 9: Branches y tu segundo pull request (PR) (10:54)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-09.png" width="50%" /></a>

Lo último que quiero mencionar es un error común pero fácil de evitar al comenzar con el flujo de trabajo de GitHub. Entonces, si ha seguido los otros videos, sabe cómo bifurcar y extraer un repositorio, crear una rama y realizar una primer PR. Luego, por lo general, toma un tiempo revisar una contribución y es posible que desee comenzar con su próximo número. Recuerde que ahora mismo su carpeta refleja el contenido de su PR. Si desea comenzar con otra cosa, asegúrese de que su base esté en la rama maestra actual, no en su PR. Así que revisa tu rama maestra y `git pull upstream master` para tener la versión actual de la rama maestra. Luego, cree una nueva rama con `git checkout -b another_feature_branch` desde la rama maestra, no desde su rama de características.

Y solo para estar seguro, cada vez que cree una nueva solicitud de extracción, mire la `diff ` que se muestra en GitHub y verifique si incluye algún cambio que no quería incluir. Si descubre que tiene más cambios de los esperados antes de crear el PR, puede volver atrás y ver si puede arreglar su rama. Si puede, si no se da cuenta al principio, aún puede deshacer los cambios y actualizar su PR presionando nuevamente hacia la rama. Una forma relativamente fácil de reescribir su historial es hacer `git reset --soft upstream/master`. Esto deshará todas sus confirmaciones, pero mantendrá los archivos como están, por lo que básicamente su historial volverá al estado de maestro ascendente, pero todos sus archivos serán como los cambie.

Desde allí, puede confirmar de forma selectiva todos los cambios que desea realizar, mientras omite todo lo que no desea incluir, luego vuelve a presionar a su rama de características (potencialmente necesita forzar la inserción), y luego puede actualizar su pull request.

### Diapositiva 10: Científicos de datos (13:04)
<a href="https://www.youtube.com/watch?v=p_2Uw2BxdhA"><img src="../images/volume2/data-umbrella-sprint-vol2-faqs-10.png" width="50%" /></a>

Eso es todo lo que tenía para el próximo sprint. Sin embargo, hay muchas otras bibliotecas que podrían usar su ayuda y Data Umbrella ha seleccionado una serie de videos sobre cómo contribuir a varios proyectos de Python, incluidos numpy, pandas y core python como scikit-learn. Estos son proyectos bastante grandes y establecidos. Si eres un desarrollador experimentado que contribuye a un proyecto de este tipo, puede ser muy gratificante. Así que ve y mira estos videos.

Sin embargo, lograr que un cambio sea aceptado en un proyecto maduro a veces puede ser un desafío y también puede buscar proyectos nuevos más pequeños que estén menos establecidos. A menudo es más fácil contribuir a los nuevos proyectos y suelen ser muy entusiastas si reciben contribuciones externas. También podría brindarle una mayor oportunidad de colaborar en la configuración de la visión del proyecto. Así que asegúrese de revisar un pequeño proyecto que esté utilizando o en el que esté interesado y vea si están buscando colaboradores o pregúnteles si no está seguro. A menudo hay mucho trabajo interesante por hacer y es una excelente manera de involucrarse con el código abierto. Eso es todo y espero verte en el sprint.

