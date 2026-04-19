# Estructura Utilizada por I3 (Gestor de Ventanas por Mosaico)

## Propuesta

<div align=center>

![](/entregas/alvaradoCarlos/images/propuestaI3.svg)

</div>

### Justificación

Yo propongo que lo que la herramienta **I3** utiliza para almacenar y gestionar las ventanas en forma de mosaico es un **Árbol N-Ario**.

#### ¿Porqué un Árbol N-Ario?

A diferencia de los árboles binarios, que únicamente pueden tener máximo 2 hijos por nodo. Este tipo de árbol puede tener una cantidad N de hijos, lo que es fundamental para el gestor ya que, al momento de iniciar a abrir ventanas, el puntero de foco (que sería la referencia enlazada de padre) estará apuntando al nodo raiz (Nodo Pantalla en el diagrama), si no le especificamos exclusivamente que la nueva referencia de foco apuntará a alguna de las ventanas hijas existentes.

Por lo qué siguiendo esa lógica, nosotros podriamos añadir cuantas ventanas de terminales, aplicaciones o editores que queramos, aún sin que especifiquemos el puntero del foco. Algo que no se podría realizar si la estructura utilizada fuera un árbol binario, que nos limitaría a únicamente tener 2 nodos como máximo sin especificar el foco.


#### Demostración Gráfica de Disposición

<div align=center>

![](/entregas/alvaradoCarlos/images/EjemploDeDisposicionDeMosaico1.png)

</div>

Aquí se puede ver que a partir de una ventana, se dividen en 2 y ahora la ventana azul pasa a ser compuesta por la ventana verde y amarilla. Si suponemos que el puntero del foco al padre siga siendo la ventana azul, obtendriamos:

<div align=center>

![](/entregas/alvaradoCarlos/images/EjemploDeDisposicionDeMosaico2.png)

</div>

Se añadiría una nueva división la cual parte en 3 partes iguales la pantalla original, pero no dividió ninguna de las 2 ventanas hijas. Ya qué no se le especificó en ningún momento el cambio de la referencia de foco.

<div align=center>

![](/entregas/alvaradoCarlos/images/EjemploDeDisposicionDeMosaico3.png)

</div>

Si se cambia la referencia del puntero de foco a cualquiera de las ventanas hijas, aquí si es cuando se empieza a comportar como árbol binario, dividiendo el espacio de la ventana padre en otras 2 ventanas hijas que siguen la misma línea.