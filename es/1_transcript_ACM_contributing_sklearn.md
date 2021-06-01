<p float="left">
 <a href="https://www.dataumbrella.org"> <img src="../images/full logo-transparent copy.png" height="40%" width="40%" /> </a>
  <img  width="150" />
   <a href="https://github.com/scikit-learn" target="_blank"> <img src="../images/1280px-Scikit_learn_logo_small.svg.png" width="15%" height="15%" />  </a>
</p>


# [Data Umbrella](https://www.dataumbrella.org): Curso Intensivo de Contribución de [scikit-learn](https://github.com/scikit-learn)

## Transcripción del Video
- Ponente:  [Andreas Mueller](https://twitter.com/amuellerml)
- Video:  [Scikit-learn Sprint Instructions](https://youtu.be/5OL8XoMMOfA) (30 minutes)
- PDF diapositivas: [Crash Course in Contributing to Open Source Projects](https://github.com/data-umbrella/2020-sklearn-sprint/blob/master/data-umbrella-sprint-intro.pdf)
- Transcriptora: [Reshama Shaikh](https://twitter.com/reshamas)

## Enlaces principales
- Data Umbrella [Discord](https://discord.gg/mEzEbYT)
- Gitter: [scikit-learn](https://gitter.im/scikit-learn)
- **[Contributing Workflow Commands](contributing/workflow.md)** (configuración de entorno, repositorio, envío de un PR)
- [Scikit-learn Contributing Documentation](http://scikit-learn.org/stable/developers/contributing.html)

## Video Updates (not `master`, but `main`)

<a href="https://scikit-learn.org/dev/developers/contributing.html"><img src="../images/master_main.png" width="90%" style="padding:1px;border:thick solid red;" align="top"/></a>


## Video
<a href="https://youtu.be/5OL8XoMMOfA?t=1"><img src="../images/sklearn_video1.png" width="90%" /></a>

---

### Diapositiva 1: Introducción (0:00)
<a href="https://youtu.be/5OL8XoMMOfA?t=1"><img src="../images/sklearn_video1.png" width="50%" /></a>


¡Hola a todos! Este es un video con las instrucciones de cómo contribuir a los proyectos de open source, en particular a la librería scikit-learn. Soy Andreas Mueller, uno de los principales desarrolladores del proyecto scikit-learn. Quiero dar las gracias a Reshama y a Data Umbrella por organizar este sprint. Quiero darles un breve resumen de la tecnología que está detrás de la contribución del open source y de los pasos para seguir en vuestras primeras contribuciones. 

### Diapositiva 2: Instructiones de Sklearn (0:40) 
<a href="https://youtu.be/5OL8XoMMOfA?t=40" target="_blank"><img  src="../images/sklearn_video2.png" width="50%" /></a>


En primer lugar, la mejor manera de comunicarse con los desarrolladores es por el canal de Gitter. Lo puedes encontrar en [gitter.im/scikit-learn](https://gitter.im/scikit-learn). Para el sprint, hay un canal llamado “sprint”: [gitter.im/scikit-learn/sprint](https://gitter.im/scikit-learn/sprint). Y también hay un canal  de scikit-learn que es el canal general: [gitter.im/scikit-learn/scikit-learn](https://gitter.im/scikit-learn/scikit-learn). Durante este sprint, también vamos a usar Discord y durante el sprint, Discord puede ser la mejor manera de comunicarse. Pero después de que el sprint se acabe, los principales desarrolladores no van a estar en Discord, pero tu siempre puedes ir al canal de Gitter para solicitar ayuda.


### Diapositiva 3: Reazones para Contribuir (1:24)
<a href="https://youtu.be/5OL8XoMMOfA?t=84" target="_blank"><img  src="../images/sklearn_video3.png" width="50%" /></a>

Así que, si ya te has unido a nosotros o por lo menos estás viendo este video, yo espero que tu estés muy motivado para empezar a contribuir. Aunque, yo quiero explicar un par de razones por las cuales tu deberías de contribuir. Para muchas personas, contribuir es ayudar a los proyectos que ellos están usando normalmente. Así que los usuarios de los proyectos son normalmente los mejores contribuidores. Y esperanzadoramente los proyectos de open source te han ayudado en el código que usas día a día y en tu trabajo y en más cosas. Y contribuyendo es la mejor manera de ayudar a la comunidad. También, te da una muy buena oportunidad de aprender de las personas que estaban envueltas en el proyecto y que muchas veces son desarrolladores seniors que te darán una revisión acerca de cómo escribes el código y también de cómo usar los diferentes proyectos y cómo interactuar. También te deja hablar de problemas que siempre te estás preguntando acerca de la librería: como arreglar cosas, como arreglar la documentación o simplemente como mejorar los proyectos.

### Diapositiva 4: Reazones para Contribuir (2:33)
<a href="https://youtu.be/5OL8XoMMOfA?t=153" target="_blank"><img  src="../images/sklearn_s4.png" width="50%" /></a>


También, te familiarizarás con las herramientas de las ciencias de datos si estás contribuyendo directamente en los proyectos. Definitivamente, contribuyendo a un open source, te podría ayudar si buscas trabajos, pero si esta es tu única motivación, no creo que te funcione porque open source es acerca de la comunidad. Y si no estás de verdad interesado en el proyecto, probablemente no estarás en él por mucho tiempo. Así que realmente, nosotros estamos aquí para ayudar con el proyecto, interaccionar con otros contribuidores y simplemente divertirnos mientras trabajamos en los proyectos.  

### Diapositiva 5: Configurar el Entorno de Python(3:16)
<a href="https://youtu.be/5OL8XoMMOfA?t=196" target="_blank"><img  src="../images/sklearn_s5.png" width="50%" /></a>
 
Así que ahora vamos a la parte técnica. Primero quiero hablar sobre la configuración. Si deseas desarrollar un proyecto de Python, obviamente, primero debes de tener una instalación local. Entonces, si ya tienes un entorno Python en funcionamiento, está bien. Si no, diría que simplemente instales Anaconda. Por lo general, es la forma más fácil de hacerlo. Si ya tienes un entorno de trabajo, asegúrate de que no estás usando el sistema Python en OS X, pero que estás usando un entorno separado para realizar su desarrollo. Si ya tienes una instalación de Anaconda, simplemente crea un entorno virtual separando otro entorno para el sprint.

Entonces os doy el comando aquí que es: `conda create -n` y le di un nombre para el entorno, aquí lo llamo `sklearndev`. Y luego todos las librerías de las que dependerá: `numpy scipy matplotlib pytest sphinx cython ipykernel`. Entonces, en realidad no estamos instalando scikit-learn usando conda. Vamos a instalar la versión de desarrollo. Y entonces puede activar este entorno usando `source activate sklearndev` or `conda activate sklearndev`, creo que principalmente en Windows.


```bash
conda create -n sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel
source activate sklearndev
conda install -c conda-forge sphinx-gallery
```
Luego, si deseas trabajar en la documentación, también debes de instalar la librería sphinx-gallery. Esto no está en conda principal, por lo que debes de instalarlo desde el canal conda-forge usando `conda install -c conda-forge sphinx-gallery`.


### Diapositiva 6: Fork sklearn en GitHub (4:57)
<a href="https://youtu.be/5OL8XoMMOfA?t=297" target="_blank"><img  src="../images/sklearn_s6.png" width="50%" /></a>

Muy bien, ahora tienes la configuración de tu entorno de Python. Tienes un entorno separado para el desarrollo de scikit-learn. Ahora obtendrás la versión de desarrollo más reciente de scikit-learn. Para hacer esto, primero vete al repositorio principal de scikit-learn github.com barra scikit-learn, barra scikit-learn: [github.com/scikit-learn/scikit-learn](https://github.com/scikit-learn/scikit-learn) y crea un pull request, o un PR. El PR es básicamente tu propia copia personal del repositorio en GitHub.



### Diapositiva 7: Clona el Fork (5:26)
<a href="https://youtu.be/5OL8XoMMOfA?t=326" target="_blank"><img  src="../images/sklearn_s7.png" width="50%" /></a>

Puedes hacer esto, haciendo clic en el botón de PR en la parte superior derecha, aquí. Esto creará tu PR personal y lo llevará allí. Para que puedan ver, aquí arriba a la izquierda, este es mi PR, Amueller slash scikit-learn. Amueller es mi identificador de GitHub, por lo que tu tendrás tu identificador de GitHub allí. Y puedes ver que es un PR de scikit-learn slash scikit-learn, el repositorio principal.


Así que esta es ahora tu propia copia privada en GitHub. Por lo tanto, tienes acceso de escritura a esta copia y puedes realizar cambios en ella. A partir de ahí, obtendrás tu propia copia local en tu propia máquina clonándola. Y entonces está este botón verde clon o descarga que puedes ver aquí. Haces clic en esto y puedes copiar el enlace y hacer `git clone` con este URL. Y esto descarga una copia a tu máquina local, tu computadora portátil o PC. Cuando haces esto, una cosa que es importante es que uses HTTPS. Entonces, haz clic aquí y debes usar HTTPS y obtendrás una dirección HTTPS. Estoy usando SSH, que es más fácil si tienes las claves SSH configuradas en tu máquina local. Si no tiene las claves SSH configuradas y no las has puesto en tu cuenta de GitHub, etc., simplemente usa HTTPS. Será mucho más fácil. Una vez que descargaste el repositorio de tu clon, también querrás agregar el repositorio principal como un upstream para que puedas descargar la versión más reciente del repositorio  si alguien más realiza cambios. Puedes hacer esto dentro de tu repositorio haciendo `git remote add upstream` y luego la URL después de mi repositorio, github.com slash scikit-learn slash scikit-learn dot git: https://github.com/amueller/scikit-learn.git.


### Diapositiva 8: Cree y Ejecute Pruebas(7:25)
<a href="https://youtu.be/5OL8XoMMOfA?t=443" target="_blank"><img  src="../images/sklearn_s8.png" width="50%" /></a>

Muy bien, ahora tienes tu copia local de la versión de desarrollo de scikit-learn y ahora queremos instalarla. Por eso queremos construirlo e instalarlo. Y la forma más fácil es ir a la carpeta que acabas de clonar y hacer pip install - e dot: `pip install -e .` Esto hace una instalación que hace la construcción y la agregaremos a tu ruta de Python. El - e lo convierte en una instalación comestible, editable (no comestible), instalación editable. Lo que significa que si cambias los archivos en esta carpeta, se refleja automáticamente en tu instalación. Esto sobrescribirá las instalaciones existentes, así que asegúrate de no tener una instalación de scikit-learn. Así que asegúrese de hacer `conda uninstall scikit-learn` en este entorno si lo instalaste antes.


#### Windows (8:14)
Si estás en Windows para instalarlo, necesitarás un compilador de C ++, por lo que debes instalar el kit de herramientas de Visual Studio. Y si intentas hacer una instalación de pip - e dot, probablemente te dará un mensaje de error. El mensaje de error te dirá exactamente qué descargar y dónde. Para OS Access Linux, probablemente ya tendrás el compilador instalado, por lo que no tendrás que preocuparte por eso. Entonces tienes tu instalación de compilación, tu nueva instalación de la rama de desarrollo de scikit-learn.

### Diapositiva 9: Comenzando con Problemas (8:50)
<a href="https://youtu.be/5OL8XoMMOfA?t=530" target="_blank"><img  src="../images/sklearn_s9.png" width="50%" /></a>

Ahora tienes que elegir un problema para empezar. Hablaré un poco más sobre esto más adelante, pero seleccionamos algunos de los problemas, por lo que podría ser más fácil elegir uno de estos problemas. Encontrarás un URL aquí. Es de esperar que descargue las diapositivas para no tener que escribir todo esto. Luego comenta sobre el problema, diga "Estoy trabajando en esto" o también hay un comando ahora donde puede simplemente decir "tomar" y el bot le asignará el problema. Antes de comenzar a trabajar, asegúrate de tener la versión más reciente del repositorio principal. Puede hacer esto haciendo `git pull upstream master`. Es por eso que antes agregamos el repositorio upstream.


#### Fetch un PR de otra persona (9:38)
Si deseas comenzar desde un PR de otra persona, donde ya comenzaron a trabajar pero luego se detuvieron, y luego desea terminarlo, puede obtener tu código usando este comando git aquí, obtener buscar y luego agregar una URL a tu repositorio y luego tu nombre de rama, dos puntos, cualquier nombre de rama que quieras usar localmente. 

`git fetch https://github.com/theirusername/reponame.git theirbranch:ourbranch`

### Diapositiva 10: Comenzando con Problemas (9:59)
<a href="https://youtu.be/5OL8XoMMOfA?t=600" target="_blank"><img  src="../images/sklearn_s10.png" width="50%" /></a>

Entonces, antes de comenzar a programar, tienes que crear una nueva rama para tu función. Puedes hacer esto haciendo git checkout dash b ((`git checkout -b <branchname>`) y luego un nombre para su rama.

No deberías trabajar en tu rama master. No debes realizar cambios en tu rama master. Siempre debes trabajar en una rama de funciones. Entonces, por ejemplo, si deseas mejorar la documentación para random forests, puedes hacer: get check out - b random forests o algo como esto ((`git checkout -b randomforests_docs`). Esto es principalmente para ti, pero es útil si tienes un nombre que se entienda.

Luego haces tus cambios. Hablaremos un poco más sobre eso. Así que arregla algunos errores o mejora la documentación, lo que sea que quieras hacer. Luego, ejecuta las pruebas con `pytest sklearn`. `pytest sklearn` ejecutará todas las pruebas. También puedes ejecutar solo archivos de prueba individuales si lo deseas. Y finalmente ejecuta flake eight (`flake8`) en todos los archivos modificados. flake8 es una herramienta para deshilachar. Te mostrará errores de formato y declaraciones similares no utilizadas, etc. Si no hace esto, probablemente haya problemas más adelante, en la integración continua, y definitivamente tendrás que solucionarlos antes de que podamos fusionar tu pull request.

### Diapositiva 11: Creando un PR (11:20)
<a href="https://youtu.be/5OL8XoMMOfA?t=680" target="_blank"><img  src="../images/sklearn_s11.png" width="50%" /></a>

Entonces, supongamos que solucionas los problemas que deseas solucionar. Los comprometió localmente en su rama y ejecuta las pruebas y ejecuta flake8 y todo pasa. Luego, puedes enviar los cambios que realizó localmente a tu repositorio de GitHub usando git push origin y luego el nombre de su rama. Esto lo empujó a su bifurcación por usted, por lo que a su copia personal de scikit-learn en GitHub. Luego, para llevarlo al repositorio principal, haces lo que se llama un PR, que básicamente les pide a los desarrolladores que tomen tus cambios y los integren en el repositorio principal. Puede crear una PR yendo al repositorio principal scikit-learn slash scikit-learn, y si empuja a su repositorio, verá este botón verde aquí que dice comparar y PR.

### Diapositiva 12: Describiendo PR (12:17)
<a href="https://youtu.be/5OL8XoMMOfA?t=739" target="_blank"><img  src="../images/sklearn_s12.png" width="50%" /></a>

Entonces, esto te llevará a una interface donde puedes crear un PR. Automáticamente completarán las cosas aquí, en la parte superior que básicamente dirán desde su bifurcación, su rama, desea hacer un PR a la rama maestra de scikit-learn. Pero, por lo general, se completará automáticamente. Lo que tienes que hacer es primero darle un título. Si lo deseas, puedes comenzar el título con MRG, si crees que su trabajo está listo para ser revisado y fusionado. O WIP si crees que es un trabajo en progreso, lo que significa que aún necesita hacer algunos cambios. Solo quieres mostrar el trabajo que has realizado hasta ahora. Por lo general, debes darle un nombre descriptivo, de modo que alguien lo pueda leer y sepa exactamente en qué está trabajando. Y recuerda que scikit-learn es grande y, por lo tanto, si dice cambio y atributo de clases, y no dice en qué modelo está, esto podría no ser muy útil. Sé preciso y específico, pero no lo alargue demasiado. Si haces referencia a un problema que está solucionando en el título, GitHub en realidad no lo vincularía. Pero, por lo tanto, es muy importante que hagas referencia a cualquier problema que estés solucionando o en el que lo escriba o cualquier PR que está asumiendo, en la descripción del PR. Entonces aquí, aquí quiere decir "Soluciona el problema x". En realidad, hay algunas palabras mágicas en GitHub que significan que si dices "Reparar x" o "Cierra x", y luego se fusiona el PR, GitHub la cerrará automáticamente como un PR. Entonces, si estás solucionando completamente algo que es un problema, puedes decir "solucione este problema" y luego los PRs se cerrarán automáticamente. Si está solucionando solo una parte de un problema, o si tu problema tiene muchas partes pequeñas, y estás haciendo una de ellas, no diga "soluciona el problema" o "cierra el problema" porque entonces si tu problema ha combinado, GitHub cerrará automáticamente todo el problema para todos. Y luego alguien más debe volver a abrirlo si está actualizado. Por lo tanto, usa el número de problema de correcciones, pero solo cuando sea apropiado y definitivamente menciona cualquier problema o PR que esté relacionada.

**Anexo:**  Es posible que desee utilizar "Problema de referencias #xxxxx" (en lugar de "arreglos" o "cierres")

### Diapositiva 13: Pruebas de Regresión (14:45)
<a href="https://youtu.be/5OL8XoMMOfA?t=887" target="_blank"><img  src="../images/sklearn_s13.png" width="50%" /></a>

Muy bien, digamos que abriste tu PR. Luego, en la parte inferior, verás la suite de integración continua en ejecución. Por lo tanto, los diagramas serán un poco diferentes en estos días porque usamos principalmente canalizaciones de Azure. Y entonces tu quieres que todos estos sean marcas de verificación verdes. Si no es así, puede hacer clic en los detalles y te dirá por qué la prueba está fallando. Y, con suerte, esto te dirá lo que debes cambiar. Si esto no está claro para usted, simplemente haz una pregunta en el PR o en el rastreador de problemas en cualquier lugar y la gente estará feliz de ayudarle a aclarar qué es lo que necesita corregir para que pase una prueba.

Además, no es suficiente que pasen las pruebas que estaban allí antes. Siempre que cambies el código, también quieres agregar una prueba que pruebe el código que agregaste. Si corriges el error, se llama prueba de regresión. Pero también si agregas una función, definitivamente debes de agregar una prueba que pruebe la función. No pasamos ningún PR sin una prueba. Básicamente, si realizaste algún cambio en el código, es muy probable que también necesites hacer un cambio en tus pruebas o hacer una adición a las pruebas. Si no sabes qué archivo de prueba buscar, probablemente puedas hacer un git grep para encontrarlo. De lo contrario, pregunta en qué archivo debes de ingresar o qué debe probarse.

### Diapositiva 14: ¿Que sigue? (16:15)
<a href="https://youtu.be/5OL8XoMMOfA?t=975" target="_blank"><img  src="../images/sklearn_s14.png" width="50%" /></a>

Muy bien, digamos que editas tus pruebas. Todas las pruebas pasan. Todo está verde. ¿Qué sigue? Entonces probablemente obtendrás revisores de los desarrolladores principales. Esto puede llevar algún tiempo, especialmente durante el sprint, porque la gente está bastante ocupada. Por lo general, las revisiones tendrán comentarios. Es muy inusual que alguien diga "oh, tu PR es excelente, podemos fusionarla". Las revisiones de los PRs son una parte realmente importante del open source, y es la forma principal en que se discuten las nuevas funciones. Así que no te decepciones si alguien dice "bueno, en realidad creo que deberíamos hacerlo de esta manera o de esa manera". Esta es realmente la principal forma en que se comunican los desarrolladores. Por lo tanto, no es como si estuvieran rechazando sus PRs. Básicamente, todos los PRs experimentan cambios.

He estado con el proyecto durante mucho tiempo y, básicamente, cualquier PR que hagas tendrá una larga discusión y se someterá a muchas iteraciones antes de fusionarse, si se fusiona. Entonces, si está menos familiarizado con el proyecto, probablemente necesitará incluso más iteraciones. Y eso es completamente normal y es la forma en que aprenderá sobre las prácticas en el proyecto y también cómo aprenderá a mejorar su estilo de programación. Para abordar cualquier comentario, puedes actualizar la rama que tiene localmente y enviarla a su bifurcación. Eso actualizará automáticamente el PR. Por lo tanto, no es necesario cerrar el PR y abrir un nuevo PR. El PR se actualizará automáticamente con cualquier cambio que tenga. Esto probablemente retrocederá un par de veces y luego, una vez que los revisores estén contentos, aprobarán la solicitud de extracción o tal vez cambiarán el título para fusionar más uno ([MRG + 1]).

Pero creo que en estos días usualmente usamos la función de aprobación de GitHub. Necesitas dos aprobaciones de los desarrolladores principales de scikit-learn, por lo que estas son personas con derechos de commit en el repositorio de scikit-learn. Una vez que tengas dos aprobaciones, tu PR probablemente se fusionará. A veces puedes llevar algún tiempo obtener reseñas, así que ten paciencia. Pero también puedes hacer ping y solicitar revisiones. Entonces, haz ping a los desarrolladores en su PR o en un chat o en persona. Bueno, en persona es difícil estos días, pero como en cualquier plataforma en línea en la que estemos colaborando.

### Diapositiva 15: Encontrar Problemas (18:52 )
<a href="https://youtu.be/5OL8XoMMOfA?t=1132" target="_blank"><img  src="../images/sklearn_s15.png" width="50%" /></a>

Un aspecto que creo que es bastante importante es encontrar temas en los que trabajar. Así que lo ideal es que encuentres algo que te interese, pero también deberías comenzar con algo que sea realmente simple. Si esta es tu primera contribución de open source o incluso si es su primera contribución al proyecto scikit-learn; incluso si has contribuido a otros proyectos antes, realmente comienza con algo súper simple. Como habrás notado, hay muchos procesos en todo esto, como trabajar con Git, trabajar con la integración continua trabajando con los revisores, etc. Y así, incluso si es solo un cambio de código de una sola línea o un cambio de documentación de una sola línea, puede ser realmente útil. Y es importante hacer algo para ponerse al día y fusionarlo. Antes de atacar algo grande, haz algo simple primero.

Como dije antes, hay algo que está vinculado aquí en la parte inferior donde colocamos algunos problemas que están específicamente marcados para este sprint. Así que probablemente todos sean bastante buenos. Aparte de eso, hay etiquetas en el repositorio. La etiqueta más importante es quizás un buen primer número. Los problemas de "Buen primer número" son buenos si no has contribuido antes a scikit-learn y eso debería ser bastante fácil y directo. Las cosas que necesitan que alguien trabaje en ellas deben etiquetarse con "necesidad de colaborador", aunque eso a veces puede estar desactualizado. Pero debes verificar las cosas que son buenas en la primera edición y necesitan un colaborador.

TTambién hay cosas que están marcadas como fáciles o rápidas. Tan fáciles son aquellas que son fáciles pero tal vez no sean buenas para los primeros contribuyentes o, a veces, pueden tener ambas etiquetas. 

Entonces, también hay otras formas de contribuir, después de encontrar un problema y trabajar en él. También puedes corregir algo en los documentos que no esté claro. No es necesario que abras un problema para esto, así que simplemente mejora la documentación si hay algo que no le gusta de él. O simplemente problemas abiertos. Problemas abiertos sobre documentos poco claros, sobre funciones que te parecen raras, sobre ejemplos que no son útiles, sobre errores con los que te encuentras.

Por lo tanto, un sprint puede ser una gran oportunidad para abrir problemas sobre cosas que no te gustan de los proyectos, problemas con los que te encuentras. Y tener esta retroalimentación es realmente importante para mejorar el proyecto.

Otra cosa que puedes hacer es buscar PR que otra persona realizó pero no finalizó. Entonces, si hubo revisiones por parte de los desarrolladores pero luego dicen que después de un mes o dos personas no regresaron y abordaron sus problemas, generalmente asumimos que el problema está en juego. Es de buena educación preguntar, pero es posible que no tengan tiempo de responderte en el tiempo que lleva esto, como en el único día del sprint. Así que simplemente pregunte y diga "¿todavía está trabajando en esto?" o, en algún caso, podría estar bien, simplemente comience a trabajar en él y diga que está bien, parece que ya no está trabajando en esto.

En esta y cualquier otra comunicación sobre el rastreador de problemas, por supuesto, sea siempre amable, cortés, productivo y constructivo en sus comentarios.

### Diapositiva 16:  Revisando (22:22)
<a href="https://youtu.be/5OL8XoMMOfA?t=1342" target="_blank"><img  src="../images/sklearn_s16.png" width="50%" /></a>

También puede comenzar a revisar. En particular, revisar los PRs o los problemas abiertos por otras personas en el sprint puede ser útil porque generalmente se encuentran en un nivel más introductorio. Pero puede intentar revisar los PRs y los problemas. Revisar los problemas puede ser un poco más sencillo. Entonces, si desea verificar un problema, puede buscar:
- ¿Es este problema reproducible?
- ¿Está claro lo que informa la persona?
- ¿Dieron el mínimo ejemplo reproducible?
- si es así, ¿puede reproducirlo en su máquina?
- ¿Proporcionaron datos?
- si no pudieran proporcionar los datos, ¿podrían reproducirlos con un ejemplo hipotético?

Y estas son, en cierto modo, todas las cosas que deben estar presentes. Si no están presentes, puede pedirle a la persona que abrió el problema que se los proporcione. Si algo no está claro sobre el tema, también siéntase libre de aclarar o pedir una aclaración, quiero decir. Y luego puede intentar reproducir el problema. Así que simplemente reproducirlo y asegurarse de que sea fácil de reproducir, ya es bastante útil. Es posible que algunos de los problemas ya se hayan solucionado, por lo que puede decir que esto ya se ha solucionado en esta versión porque tenemos problemas muy antiguos que se remontan a varios años. Por lo tanto, clasificar los problemas es algo muy útil. Algunos errores no están confirmados, por lo que puede ver si puede confirmarlos y en qué condiciones.

También puede revisar los PRs para documentar si son claras. ¿El lenguaje es claro? También puede revisar los cambios de código. O bien, ¿tienen pruebas agregadas? ¿Se adhieren a los estilos? ¿Pasa la integración continua? ¿Y luego tal vez mencionaron el tema que están abordando en su descripción? Entonces, todas las cosas que dije que debería hacer para su PR, puede verificar, son las otras personas en el sprint o, en general, cualquier persona que tenga un PR. ¿Se están adhiriendo a estos estándares? Si no, puede pedirles que lo hagan. Por supuesto, sé siempre amable y educado. También puede intentar revisar los cambios de código para ver si realmente están abordando lo que quieren abordar. ¿Y lo están abordando de una manera que usted cree que es buena? Esto puede ser un poco más complicado, pero definitivamente deberías intentarlo. Y si algo no está claro, simplemente pida una aclaración. Y tampoco dude en enviar comentarios. Solo sea siempre cortés al decir, oh, tal vez lo hubiera hecho de esta manera, ¿hay alguna razón por la que lo haga de esta manera, y no diga no digas como oh, esta es una mala manera de hacerlo tú, deberías hacerlo? Por aquí. Probablemente haya una razón por la que alguien lo hizo de la manera en que lo hizo, así que siempre sea amable y pida una aclaración en lugar de asumir.

### Diapositiva 17: Recordatorios de Flujo de Trabajo (25:25)
<a href="https://youtu.be/5OL8XoMMOfA?t=1524" target="_blank"><img  src="../images/sklearn_s17.png" width="50%" /></a>

Un par de cosas sobre el flujo de trabajo durante el sprint. Por lo tanto, le recomendamos encarecidamente que realice una programación en pareja. Encuentro que es mucho más divertido y puedes hacer mucho más durante la programación en pareja. Esta vez será la programación de pares remotos usando Discord. Tal vez no sea tan bueno como hacer una programación en pareja en persona, pero creo que sigue siendo muy divertido. Si está haciendo un PR o un problema, simplemente @ menciona a la otra persona que está trabajando en él para que todos reciban un ping en sus correos electrónicos. Asegúrese de hacer un seguimiento de su trabajo. Por lo tanto, espere que haya muchos intercambios y discusiones, así que asegúrese de captar las críticas que obtenga en sus PRs. Y realmente es importante pedirle al proyecto que realmente combine sus contribuciones y, por lo tanto, realmente intente obtener un seguimiento durante el sprint, pero también idealmente un seguimiento después del sprint. Realmente lo que más amamos es encontrar nuevos colaboradores que sigan regresando al proyecto y sigan contribuyendo. Será más fácil y más satisfactorio contribuir al proyecto cuanto más se involucre y más se familiarice.

Podrás hacer cosas cada vez más interesantes. Podrá agregar nuevas funciones interesantes al proyecto, etc. Y, por tanto, también es realmente una forma de crecer con el proyecto y de aprender mucho más al comprometerse más a largo plazo.

Así que probablemente intentaremos hacer algunos eventos de seguimiento para los sprints. De lo contrario, no dude en realizar un seguimiento del seguimiento de problemas. El rastreador de problemas es realmente la forma principal de comunicación de los desarrolladores. También hay una comunidad mensual, llamada de desarrollador mensual a la que puede unirse si lo desea. Únase a la lista de correo electrónico o simplemente hable con nosotros en gitter. Y así, asegúrese de saber qué dirección de correo electrónico usa en su cuenta de GitHub y verifique esa dirección de correo electrónico para ver las notificaciones o verifique las notificaciones directamente en GitHub.


### Diapositiva 18: Recordatorios de Flujo de Trabajo(27:44)
<a href="https://youtu.be/5OL8XoMMOfA?t=1666" target="_blank"><img  src="../images/sklearn_s18.png" width="50%" /></a>

Entonces dije que podría haber algunas cosas que hacer que no puedas terminar durante el sprint. Es realmente genial si puede hacer un seguimiento y fusionar tus PRs. Entonces, el PR y GitHub es realmente la mejor manera de comunicarse y esta es una discusión pública donde todos los desarrolladores principales o realmente cualquier otra persona en Internet pueden responder preguntas y ayudar. Y como dije antes, usaremos Discord durante el sprint, pero los desarrolladores principales probablemente no estarán en Discord la mayor parte del tiempo después del sprint. Por lo tanto, una buena idea es ir al canal de sprint de scikit-learn o simplemente al canal general de scikit-learn o simplemente hablar sobre los problemas y los PRs.

Así que realmente estamos enfatizando que es una buena idea comenzar con algo realmente muy simple como primera contribución y luego ir avanzando desde allí. Mi primera contribución a scikit-learn fue corregir algunos errores tipográficos en nuestra documentación. Y si comienzo a contribuir a cualquier otro proyecto, generalmente lo primero que hago es arreglar una línea de su documentación y, ya sabe, comenzar con el proyecto y comenzar a comunicarse y comenzar a ingresar al flujo de trabajo.


### Diapositiva 19: Ultimas Palabras (29:00)
<a href="https://youtu.be/5OL8XoMMOfA?t=1709" target="_blank"><img  src="../images/sklearn_s19.png" width="50%" /></a>

Sí, así que si desea agregar funciones importantes a scikit-learn, probablemente no sea algo que pueda hacer en un día. Agregar un nuevo modelo a scikit-learn suele ser algo que lleva muchos meses y no es algo que deba intentar al principio. Entonces, realmente comience con algo simple y luego, tal vez, si recibió sus primeros dos PRs y puede trabajar para agregar una característica más pequeña, pero no cuente con agregar una característica grande en el corto plazo. Eso se debe a que scikit-learn ya es una biblioteca bastante madura y, por lo tanto, se mueve con bastante lentitud. Por lo tanto, es difícil agregar algo grande o hacer grandes cambios nuevos. Además, puede haber muchos temas interesantes que no estén etiquetados adecuadamente. Entonces, si está interesado en un tema en particular, puede buscar el tema en el rastreador de problemas o en los PRs y ver si sucede algo interesante allí.

### Diapositiva 20: Gracias (29:59)
<a href="https://youtu.be/5OL8XoMMOfA?t=1797" target="_blank"><img  src="../images/sklearn_s20.png" width="50%" /></a>

Así que con esto quiero decirles que disfruten el sprint y gracias a todos por su ayuda y espero que se diviertan mucho. Aprenderá mucho trabajando junto con su compañero de sprint. Y espero que regrese para más sprints o simplemente siga participando en el rastreador de problemas. ¡Muy bien, muchas gracias!
