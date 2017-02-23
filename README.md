# RETO_11

Este ejercicio consiste en demostrar las posibilidades de uso del Notebook Jupyter. Para realizarlo se usara la imagen de docker que se describe en https://hub.docker.com/r/jupyter/all-spark-notebook/

Para arrancar el servidor se ejecuta "docker run -p 8888:8888 jupyter/all-spark-notebook" que devuelve una url con un token

Se accede desde un navegador con  la url http://<dockerhostip>:8888/?token=<tokenquedevuelveelcomandoanterior>

Creamos un Notebook nuevo de R y ejecutamos un codigo de ejemplo,  por ejemplo el que aparece al final de https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/mtcars.html

Creamos un Notebook nuevo de Python y ejecutamos algo de codigo, por ejemplo el que hay en http://matplotlib.org/examples/pylab_examples/simple_plot.html

Creamos un Notebook nuevo de Spark (Apache-Toree-Scala) y ejecutamos un Map reduce. Por ejemplo:

<pre>
val textFile = sc.textFile("file:///etc/hosts")
val counts = textFile.flatMap(line => line.split(" ")).map(word => (word, 1)).reduceByKey(_ + _).sortBy(-_._2)
counts.take(5).foreach(println)
</pre>

Y la cuestion aqui es si estamos usando realmente Spark o no con el ultimo ejercicio.
