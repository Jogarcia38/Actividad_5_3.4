# Jose Rene García Aroca

# Lab 3.4: Training a Machine Learning Model

![Evidencia 1](Pantallazos/Imagen%205.1.png)

Primero inicio de sesión en la plataforma aws, luego selecciono MyNotebook y damos clic en abrir JupyterLab.

![Evidencia 1](Pantallazos/Imagen%205.2.png)

# Configuración laboratorio en GitHub

![Evidencia 1](Pantallazos/Imagen%205.3.png)

![Evidencia 1](Pantallazos/Imagen%205.4.png)

Posteriormente se abrio una terminal en JupyterLab, se clonó el repositorio remoto y se accedió al directorio correspondiente; luego, se incorporó el archivo 3_4-machinelearning.ipynb al repositorio y se verificó su estado mediante git status; a continuación, se agregó el archivo con git add y se configuraron los datos de usuario requeridos por Git para realizar el commit. Por último, se registraron los cambios mediante un commit con el mensaje “Agregar actividad 3.4 Machine Learning” y se ejecutó git push origin main, permitiendo enviar los cambios realizados al repositorio remoto.

# Inportación de datos

![Evidencia 1](Pantallazos/Imagen%205.5.png)

En esta parte de la actividad se preparó el entorno instalando e importando las librerías necesarias para trabajar con los datos; posteriormente, se descargó e importó el conjunto de datos y se convirtió en un DataFrame para facilitar su procesamiento. Finalmente, se transformaron las etiquetas de la columna class a valores numéricos, con el fin de dejar los datos preparados para su posterior análisis y entrenamiento del modelo de Machine Learning.

# Paso 1: Explorar los datos

![Evidencia 1](Pantallazos/Imagen%205.6.png)

Se exploró el conjunto de datos, se identificaron 310 registros y 7 columnas, tambien se revisaron las variables y se inició la preparación de los datos, ubicando la columna objetivo class en la primera posición para continuar con el procesamiento en XGBoost.

# Paso 2: Preparar los datos

![Evidencia 1](Pantallazos/Imagen%205.7.png)

En esta etapa del laboratorio se colocó como primera columna class porque corresponde a la variable objetivo que se utilizará en el procesamiento con XGBoost, luego se revisó el orden para comprobar que class quedara correctamente ubicada; a continuación, se utilizó train_test_split para separar los datos en conjuntos, permitiendo posteriormente entrenar y evaluar el modelo, finalmente se empleó stratify=df['class'] para conservar la distribución de las clases durante la división.

# División de los datos

![Evidencia 1](Pantallazos/Imagen%205.8.png)

Seguidamente se dividió el conjunto de datos en entrenamiento, validación y prueba utilizando train_test_split, con el fin de disponer de datos separados para las diferentes etapas del desarrollo y evaluación del modelo; asimismo, se aplicó stratify para conservar la distribución de la variable class en cada conjunto y, se verificaron las dimensiones y la cantidad de registros por clase para comprobar que la división se realizó correctamente.

# Carga de los datos a Amazon S3

![Evidencia 1](Pantallazos/Imagen%205.9.png)

Luego se configuraron las variables necesarias para almacenar los datos en Amazon S3, definiendo el bucket, las rutas y los nombres de los archivos correspondientes a entrenamiento, prueba y validación; también, se creó una función para convertir cada conjunto de datos a formato CSV y cargarlo en S3, con el propósito de dejar los datos organizados y disponibles para continuar con el entrenamiento del modelo.

# Paso 3: Entrenar el modelo

![Evidencia 1](Pantallazos/Imagen%205.10.png)

A continuación se configuró el proceso de entrenamiento del modelo en Amazon SageMaker, se definió la ubicación de salida en Amazon S3, el algoritmo XGBoost y los canales correspondientes a los datos de entrenamiento y validación, con el fin de que el modelo pudiera acceder a la información previamente almacenada; luego, se ejecutó el entrenamiento mediante xgb_model.fit(), permitiendo generar el modelo entrenado para continuar con las siguientes etapas del laboratorio.

# Entrada

![Evidencia 1](Pantallazos/Imagen%205.11.png)

Para finalizar se verificó que el entrenamiento del modelo XGBoost en Amazon SageMaker finalizara correctamente y, posteriormente, se ingresaron datos de ejemplo para realizar una predicción, con el propósito de comprobar el funcionamiento del modelo entrenado, por ende, se obtuvo y mostró el resultado de la predicción, completando así el proceso de entrenamiento y prueba básica del modelo.
