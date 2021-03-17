
# Ejemplo de contribución y envío de un Pull Request a [scikit-learn](https://github.com/scikit-learn)

<p float="left">
 <a href="https://www.dataumbrella.org" target="_blank"> <img src="../images/full logo-transparent copy.png" height="40%" width="40%" /> </a>
  <img  width="150" />
   <a href="https://github.com/scikit-learn" target="_blank"> <img src="../images/1280px-Scikit_learn_logo_small.svg.png" width="15%" height="15%" />  </a>
</p>

## Transcripción del Video
- Ponente:  [Reshama Shaikh](https://twitter.com/reshamas)
- Video:  [Scikit-learn PR Contributing Example](https://youtu.be/PU1WyDPGePI) (30 minutes)
- Transcriptora: [Reshama Shaikh](https://twitter.com/reshamas)


## Enlaces principales
- Data Umbrella [Discord](https://discord.gg/mEzEbYT)
- Gitter: [scikit-learn](https://gitter.im/scikit-learn)
- **[Comandos del flujo de trabajo de contribución](../contributing/workflow.md)** (configuración de entorno, repositorio, envío de un PR)
- [Documentación de contribución a Scikit-learn](http://scikit-learn.org/stable/developers/contributing.html)


## Video
<a href="https://youtu.be/PU1WyDPGePI"><img src="images/sklearn_rs_video.png" width="80%" /></a>

---

### Introducción

Hola, mi nombre es Reshama, y mostraré paso a paso un ejemplo de como enviar un
pull request, o un PR. Participé en mi primer sprint de scikit-learn hace
aproximadamente un año y medio y estoy feliz de compartir un ejemplo. Cuando
aprendas este ejemplo - será para el repositorio sklearn - pero cuando hayas
aprendido cómo hacerlo para este repositorio, podrás hacerlo para cualquier
repositorio en Github.

### Configuración de un entorno virtual

Entonces, lo primero que voy a hacer es asegurarme de tener mi, tengo algunas
cosas configuradas. Y lo primero es que estoy trabajando desde mi directorio
personal. Solo quiero asegurarme y ver qué Python estoy usando con el sistema
es Anaconda (usa comando: `which python`). Estoy usando la versión de Anaconda,
lo que es bueno. También quiero confirmar qué versión de Python estoy usando
(usa comando: `python --version`) y es la versión 3.6.8. Y solo quiero
verificar una cosa más, que es, tengo git instalado (usa comando: `git
--version`), y lo hago. Genial.

Entonces, lo siguiente que haré es configurar mi entorno de trabajo, mi entorno
virtual. Y para hacer eso, usaré `conda create -n`, como nombre, y el nombre de
mi entorno virtual será sklearn dev. Y voy a instalar los siguientes paquetes
en este entorno. Va a ser numpy, scipy, matplotlib, pytest, sphinx, cython
e ipykernel (usa el comando: `conda create -n sklearndev numpy scipy matplotlib
pytest sphinx cython ipykernel`). Y esto va a tomar solo un poco de tiempo, ya
que crea el entorno. Me preguntará si quiero continuar. Puedo presionar enter
o escribir sí enter.

Entonces se ha creado el ambiente. Nos dice aquí mismo que activemos este entorno, usa este comando, conda activate sklearn dev. O conda deactivate. Además, si desea ver una lista de sus entornos virtuales, simplemente escribo conda environment list (usa el comando: `conda env list`). Y para mí tengo dos entornos virtuales. Tengo mi entorno dash para otro proyecto que estoy haciendo. Y sklearn dev. Y quiero entrar en ese. Así que voy hacer un conda activate sklearndev. Y quiero hacer instalaciones adicionales dentro de este entorno virtual. Y para hacer eso voy a hacer `conda install -c conda-forge sphinx-gallery`. Y va a ser esta galería de sphinx dash. Aquí vamos. Sí estoy segura. Escribe sí, enter.

### Configurar el repositorio (3:46)

Okay, lo siguiente que haré es configurar mi repositorio. Y entonces voy
a revisar scikit-learn. Y este es el repositorio principal. Y entonces voy
a forkearlo, para obtener una copia dentro de mi propia cuenta, y lo voy
a forkear en mi GitHub allí. Solo toma un poco de tiempo. Muy bien, ahí vamos.
Así que, aquí, tiene mi repositorio forkeado y aquí tiene; bien, aquí está el
repositorio principal. Lo siguiente que voy a hacer es clonarlo aquí mismo.
Tengo configuradas mis llaves SSH, así que voy a usar esto. Si no lo haces,
querrás utilizar esta URL. Entonces voy a hacer clic, usar SSH. Voy a copiar
y luego voy a volver a mi terminal. Voy a borrarlo e ir a la parte superior
y voy a escribir `git clone`. Y voy a clonarlo.

Okay, entonces voy a escribir `ls` y eso solo enumera lo que tengo en esta
carpeta. Y muestra scikit-learn aquí mismo. Y voy a entrar en el con `cd`. `cd
scikit-learn`. Okay, y lo siguiente que voy a hacer es compilar desde el código
fuente, así que voy a hacer pip install -e espacio punto (usa el comando: `pip
install -e .`).

De acuerdo, tomó un poco de tiempo, pero parece que está hecho. Lo siguiente
que voy a hacer es verificar mis remotes para git (usa el comando: `git remote
-v`). Entonces tengo origin, tengo el mío. Y quiero agregar mi upstream. Y para
hacer eso, voy a ir acá. Voy a abrir esto en otra ventana. Voy a obtener la URL
correspondiente. Y la forma de hacerlo es `git remote add upstream`. Y le
agrego esta URL. De acuerdo, y luego, cuando reviso mis remotes, parece que
tengo el origin. Y tengo upstream, que está bien. Ahí es donde quiero estar.
Así que cloné el repositorio y está actualizado. Pero, digamos que vas a volver
a tu trabajo. Si quiero obtener los últimos cambios en scikit-learn, hago `git
pull upstream master`. Así que estoy actualizando de este remote upstream. Y es
la rama principal. De acuerdo, y me dice que ya está actualizado, lo cual
esperaba, porque acabo de clonar el repositorio.

### Trabaja en una Issue (7:28)

Lo siguiente que voy a hacer es ir a un issue que ya seleccioné y en el que voy
a trabajar. Y lo que va a ser es este issue que es uno cinco siete seis uno.
Y dice que la documentación de los valores predeterminados y muchas clases no
están incluidas o son inconsistentes, por lo que voy a hacer referencia a este
issue en mi trabajo. Va a ser uno cinco siete seis uno, y voy a ir a ver un
ejemplo de uno. Entonces, por ejemplo, aquí hay uno donde los valores
predeterminados son consistentes. Entonces dice que el valor predeterminado es
igual a dos, el valor predeterminado es Euclidiano, es la cadena. El valor
predeterminado es igual a None, por lo que esta es la forma, la forma coherente
que debería ser. En un ejemplo que encontré, por ejemplo, en la carpeta de
decomposition barra abajo dict barra abajo learning, encontré uno en el que no
es consistente. Aquí, en la línea 75 se muestra: puedes hacer esto un poco más
grande, muestra que es un número entero que va a 1000 por defecto Okay. Y solo
quiero arreglar este archivo bien. Entonces, lo que voy a hacer es volver a mi
terminal aquí y lo que puedo hacer es ir a este issue que está abierto, Okay.
Y puedo hacer un comentario al respecto y puedo decir que estoy trabajando en:
sklearn/decomposition/_dict_learning.py, Okay. Solo para que la gente sepa que
estoy trabajando en esto en el sprint para asegurarme de que alguien más no
esté trabajando en lo mismo al mismo tiempo.

### Crear una rama para un feature (9:35)

Y lo siguiente que voy a hacer es crear una rama de feature. Así que iré aquí
y llamaré a mi rama git checkout menos b, y lo llamaré doc porque estoy
trabajando en un cambio de documentación. Y lo voy a llamar dict learning (usa
el comando: `git checkout -b doc_dictlearning`). Y parece que ya estoy, porque
creé la rama de esta manera, estoy en la rama allí mismo. Y voy a abrir Visual
Studio Code, mi editor. Puedes usar cualquier editor que desees, pero estoy
usando Visual Studio Code. De acuerdo, estoy en el repositorio de scikit-learn,
mi copia de él, en mi computadora y está en decomposition, está en
decomposition y es dict barra abajo learning, Okay.

Entonces aquí estoy y estaba en la línea 75. Okay. Y bien, observa cómo dice
1000 por defecto. Y si quiero ser consistente, quiero decir que el valor
predeterminado es igual a 1000. Y voy a venir aquí y voy a hacer eso. Bien,
entonces voy a guardar este archivo y luego voy a volver a ... Voy a traer esto
aquí y lo siguiente que hago es confirmar mis cambios, así que voy a hacer `git
status`.

¡Ah! Me dice aquí mismo que he modificado este archivo aquí mismo, así que lo
agregaré y haré `git add sklearn/decomposition/_dict_learning.py`. Bueno.
Entonces, lo siguiente que haré después de git add es confirmar el archivo
y git commit -m, entonces la descripción es, voy a decir que voy a decir:
"Formato actualizado para el valor predeterminado o consistencia".

### Ejecutando pruebas (12:15)

Está bien, entonces el siguiente paso que voy a hacer antes de enviar mis
cambios es ejecutar algunas pruebas, así que voy a aprender a ejecutar los pruebas
de flake8 para formatear. Entonces es flake8 sklearn y aquí voy a poner la ruta
a mi archivo para que sea decomposition (usa el comando: `flake8
sklearn/decomposition/_dict_learing.py`) y ahí vamos ahora y me dice que en la
línea 75 yo creo que tengo un espacio en blanco al final. Así que volveré
a estar Okay haré control e para el final. Sí, no lo soy. Tenía un espacio
extra que no debería. Así que voy a retroceder uno. Voy a guardar este archivo
nuevamente, asegúrate de que se guarden mis cambios. Entonces voy a volver aquí
Okay. Cuando hago `git status`, debería mostrarme que he cambiado algo y lo
hace, me lo dice aquí mismo. Así que voy a pasar por el proceso nuevamente. Voy
a hacer `git add`. De acuerdo, decomposition y voy a hacer git commit, así que
voy a escribir lo mismo. Voy a decir que actualice mi commit, así que voy
a decir, "arreglando error de flake8". Ya lo tenemos.

Okay, voy a ejecutar el test de flake8 nuevamente solo para asegurarme, solo
hice una flecha hacia arriba, para asegurarme de que ahora que arreglé ese
espacio final, no me mostró más errores, así que eso es algo bueno. Lo
siguiente que haré es ejecutar la prueba de `pytest sklearn`. Ahora hice un
cambio de documentación y no espero que haya ningún error, pero este es un
ejemplo en el que muestra que estoy ejecutando el conjunto de pytests para
sklearn solo para ver cómo se ve el resultado.

Entonces, lo que está haciendo es pasar por todas los test que se crean y solo
asegurarse de que ninguno de los cambios que hice tenga un impacto adverso en
ninguno de ellos. [PAUSA] Muy bien, parece que una de las pruebas no pasó. Hice
un cambio de documentación y, ocasionalmente, algunas pruebas no pasan, pero no
impactan; en realidad, dice que aquí se omite.

### Enviando (push) al repositorio forkeado (15:50)

Así que veamos qué pasa. Había hecho un git add, un git commit ahora voy
a hacer un git push. Voy a hacer git push origin en mi remote y en el nombre de
mi rama, que es ver dict learning (usa el comando: `git push origin
doc_dictlearning`). Veamos qué pasa. Entonces ha enviado (push) a mi rama. Voy
a ir a mi repositorio forkeado. Solo actualizo esta página y me dice que tengo
un pull request que puedo comparar y enviar.

### Preparando el Pull Request (16:05)

Así que voy a hacer clic en eso. Está bien y aquí es donde agrego un título
significativo. De acuerdo, lo llamaré DOC porque es un arreglo de documentación
y diré que limpia el docstring del parámetro en decomposition/_dict_learning.py
y aquí es donde escribo algo de información. Y entonces voy a decir aquí que
soy este PR hace referencia a la que hace referencia 1 5 7 - observe que se
vincula automáticamente a los arreglos de documentación. Entonces puedo
contener eso. Puedo borrar esto. Recuerda que no quiero cerrar aquí ni nada por
el estilo. Voy a poner una descripción aquí que diga que actualicé la
documentación del valor predeterminado para mantener la coherencia. Está bien
y si lo he hecho, ¿tengo algún otro comentario? Lo que voy a hacer es asumir
que trabajé con mi pareja de socios de programación, de acuerdo, así que ella
también recibe las notificaciones y voy a asumir que es Miriam.

De hecho, esta bien. Y solo quiero leer esto, me dice que es un equipo flexible
de voluntarios, así que seamos pacientes al respecto. Lo he leído. Me
agradecieron por contribuir, ¡genial! Y tengo la información aquí que también
puedo obtener una vista previa aquí y me dice qué hace referencia a cuál. Me
dice eso y aquí puedo: hago clic en permitir ediciones por parte de los
mantenedores en caso de que sea necesario cambiar algo. Puedo pasar por aquí
que me dice que esto es exactamente lo que cambié, cambié una línea, y la línea
que cambié fue en lugar de mil, por defecto, es igual a mil, por lo que parece
que todo está en orden. Voy a crear el pull request.

### Pruebas de integración continua (19:30)

Bien, y ahora nota que estoy en el repositorio scikit learn y está ejecutando
algunas comprobaciones aquí. Esto está en dorado, por lo que significa que
todavía se está procesando allí. Voy a ir al repositorio. Voy a hacer clic en
las solicitudes de extracción y esta es solo una forma de ver cuáles son los
Pull Request que han enviado otras personas. Observe que está en verde. Tiene
el DOC. Tiene el círculo. Voy a volver a analizarlo solo para ver qué está
pasando. Hay un montón de comprobaciones aquí desde el progreso hasta
pendiente, neutral o exitoso. A veces, si sabes, si la verificación falla,
puede hacer clic en los detalles aquí. Este ha pasado, así que voy a abrirlo en
otra pestaña para ver qué está pasando. Y da algo de información - inicia
sesión en github - supongo que podría hacerlo más tarde. Y esto también puede
llevar un poco de tiempo y, a veces, cuando estamos en un sprint, mucha gente
está enviando solicitudes, lo que también lleva un poco más de tiempo. Veamos
qué pasa si inicio sesión aquí. Iniciaré sesión en Circle CI. Voy a autorizar.

Interesante. Muy bien, déjame hacer clic en estos detalles nuevamente y ver qué
sucede. Esto es lo que quería. Cero errores y cero advertencias. De acuerdo,
voy a volver aquí y solo miraré este de aquí. Y me dice que hay una prueba, una
falla exitosa y, por lo tanto, esta es en realidad una buena manera, ya que
estas pruebas se están ejecutando si fallan, puede hacer clic en estos detalles
y obtener más información sobre por qué fallaron. Así que me detendré aquí
y luego volveré a eso. [PAUSA]

He vuelto. Estoy comprobando mi solicitud de extracción. ¡Parece que todos los
controles han pasado, lo cual es genial! Solo para que sepas que la primera vez
que hice estos Pull Requests no tuve tanta suerte. Pero sabe que si una de sus
pruebas no pasa, puede abrir los detalles y buscar más - hacer clic - y buscar
más información sobre lo que hay allí. A veces, recibirá un comentario de un
revisor. Yo diría que esto tardó unos veinte minutos en ejecutarse, así que
téngalo en cuenta cuando lo esté, cuando esté ejecutando, cuando esté enviando
PRs. Y ese es un ejemplo de cómo enviar un PR con una simple, con un arreglo
muy simple.

### Resumiendo el proceso de PR (23:50)

Así que solo quiero repasar el Pull Request. Entonces, lo que desea hacer para
comenzar es asegurarse de tener la configuración de entorno correcta. Anaconda
siempre es bueno para usar. Python y git están instalados. Quieres configurar
tu entorno virtual. Quieres forkear y clonar y crear una rama. Quieres realizar
una actualización de un archivo comenzando con una pequeña corrección en la
documentación y luego pasar gradualmente a la edición de código. Ejecutando la
prueba y enviar un Pull Request.

### Errores que cometí (24:20)

Sabes que cuando configuras tu entorno virtual o en algún punto del camino, es
muy probable que te encuentres con fallas. Ciertamente lo hice. Y entonces,
depende de su configuración y del sistema operativo que esté utilizando y de
las versiones de las bibliotecas que tenga. Y muchas, muchas dependencias.
Entonces, hay varias formas de resolver estos problemas técnicos. Si te
encuentras con un error, puedes buscarlo en Google para ver qué información
hay. Es probable que otras personas también se hayan encontrado con ese error.
Si se encuentra en un entorno estructurado como este sprint de código abierto
ahora, puede solucionar problemas con su socio de programación par. Todos
vienen con antecedentes y experiencias diferentes. Y sabes que si necesitas
ayuda, la tenemos, quiero decir, esta es la razón por la que tenemos este
sprint. Tenemos nuestra cola de ayuda en Discord y puedes preguntarle a uno de
los mentores en el sprint y alguien te ayudará.

Así que solo quiero repasar algunos errores comunes que he cometido a lo largo
del camino. ¿Sabes qué? Lo más probable es que dejes esto en el sprint y luego
el trabajo de seguimiento vendrá más tarde. Y para volver a trabajar, solo
quiero asegurarme, ya sabes, ¿estoy en mi entorno virtual? A veces, en
realidad, no entro en mi entorno virtual y ejecuto pruebas. Y me encuentro con
todos estos errores y eso siempre es importante.

Siempre me aseguro de estar en la rama adecuada que también puede ser una causa
de problemas. Me aseguro de sincronizar mi repositorio con sklearn. Si regresas
y, ya sabes, trabajas en tu PR tres días, una semana, dos semanas después,
habrá actualizaciones que se han realizado en sklearn y solo debes asegurarte
de que tiene las últimas actualizaciones en su computadora local. Y solo tienes
que asegurarte de haber realizado la prueba. Asegúrate de haber ejecutado las
pruebas flake8 y también las pytests.

### Gracias

Y gracias por unirse. Espero ver los PRs y responder cualquier pregunta en
Discord o en Gitter o donde sea. Gracias por unirte. ¡Chau!
