# CNN U-Net Image Segmentation

What is this project for?

Multiclass image segmentation

What is **image segmentation**
>Definition

Image: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

What is **CNN**
>Definition

Image: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

What is **UNet**
>Definition

Image: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## Getting Started

These instructions explain how to get a copy of the project, run it on your local machine for development and testing purposes.

### Prerequisites

You will need to install the following libraries:

Used libraries: keras, scikit-learn, opencv, etc. (version numbers are up to date: 19.06.2020)

### Installing

Installing, downloading, cloning the project:

How to install libraries/modules/how are they called:

```
open anaconda prompt
```

```
activate environment
```

```
pip install 'name'
```

For all libraries that are not already installed

## Explanation of each code. How they work

### image_segmentation

Explanations

### train.py

Explanations

### models.py

Explanations

## How to use it

### How to train a model

Explain

### How to load and evaluate a model

Explain

## Contributing

Feel free to submit pull requests

Please read [CONTRIBUTING.md](https://github.com/aritzLizoain/Image-segmentation/blob/master/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

Check where these are saved

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Acknowledgments

* Agustín Lantrero for the [image_detais.py](https://correct) and [image_simulation.py](https://correct) codes
* Rocío Vilar and Alicia Calderón for the help 

## Copyright

Copyright 2020, Aritz Lizoain, All rights reserved.






https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax

Son 8 archivos python:

*'image_details' e 'image_simulation' son los códigos de Agustín para generar las imágenes. Las imágenes creadas las guardo en la carpeta de 'Images/Train' e 'Images/Test'. Nada nuevo.

*'load_dataset' simplemente lee las imágenes y las guarda en arrays. Y luego hay una función llamada 'get_weights'. Lo que me pasa con estas imágenes es que aproximadamente 95% de los píxeles son de la categoría background, y por ejemplo los clusters son sólo un 0.1%. Esto hacía que cuando entrenaba el modelo me daba una precisión del 95%, pero lo único que hacía era decirme que todo es background. La forma de arreglar esto fue dándoles pesos a las clases, que se calculan como la inversa de la frecuencia con la que aparecen en las imágenes. Estos pesos los utilizo en la función de pérdida.
    
*'models' contiene la arquitectura del modelo. Un UNet normal, parecido al que tenía Alicia en su código. Tengo muchas capas escritas, pero algunas están comentadas. Como os lo mando es lo que me ha dado mejor resultado hasta ahora. Y tambien defino la función de pérdida que utiliza los pesos de cada clase. Esta función de pérdida la encontré en internet. Es un 'categorical_cossentropy' con el extra de que tiene en cuenta los pesos.
    
*'mask' es lo más interesante. Aquí creo los labels de todas las imágenes. Primero clasifico cada píxel en una de las clases mediante thresholds que corresponden al valor de píxel. Es decir, el color. Entiendo que esto es lo que queríamos hacer con las energías, en caso de que el color esté relacionado con la energía. De hecho sería más fácil, ya que en este he tenido que mirar qué valores de pixel corresponden a cada color, y hay valores que se mezclan. Dado que por ejemplo un pixel con valor 78 es a veces parte de un cluster, y a veces de un hot pixel, los label no son 100% correctos. Pero también es interesante ver si después la predicción es capaz de corregir estos píxeles. La idea de cómo funcionan las labels está muy bien explicado en https://www.jeremyjordan.me/semantic-segmentation/#advanced_unet. Tambien tengo dos imágenes, 'labels' y 'labels2', donde se ve cómo se clasifica cada clase. La mejor parte de esto es que ya no hago los labels como antes, que los hacía a mano con el ratón. Ahora puedo utilizar la cantidad de imágenes que quiera para entrenar.
    
*'augmentation' crea más imágenes a partir de las que le paso. Sólo aplico cambios geométricos (rotación, zoom, etc.). Aún así, como ahora puedo crear la cantidad de imágenes que quiera, no lo estoy utilizando. Pero bueno, ahí está.

*'train' es el archivo principal, dónde se entrena el modelo. Utiliza las distintas funciones de los archivos que he comentado. En él se puede configurar todo; las rutas de las imágenes, dónde guardar los resultados, características del modelo (por ejemplo que optimizador usar), etc. En la parte final se evalúa el modelo y he puesto un classification report, que es bastante útil para ver cómo ha funcionado cada clase. Os paso un fichero de texto llamado 'console' mostrando un ejemplo de lo que va apareciendo en pantalla al correr este archivo en spyder. Todas las gráficas que se generan se guardan en la carpeta 'Images/Outputs'. La carpeta 'Models' es donde se guardan los modelos entrenados y los datos de precisión y pérdida en cada época del entrenamiento.

*'load_model' carga el modelo ya entrenado y funciona como la última parte de 'train'. Hace las predicciones, la evaluación y el classification report. 




Things to use:

Lists
- George Washington
- John Adams
- Thomas Jefferson

Enumerate
1. James Madison
2. James Monroe
3. John Quincy Adams

Nested
1. First list item
   - First nested list item
     - Second nested list item
     
Classification Report

Class| Accuracy| Support
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

Use `git status` to list all new or modified files that haven't yet been committed.