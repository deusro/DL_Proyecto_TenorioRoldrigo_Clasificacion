# DL_Proyecto_TenorioRoldrigo_Clasificacion
- Se escogio la ruta de Proyecto de clasificación
- Se uso el dataset RSNA-ATD: 512x512 PNG v2 Dataset el cual son imagenes transformadas a formato PNG del dataset original RSNA 2023 Abdominal Trauma Detection, un dataset de una competencia de kaggle en el 2023, este dataset originalmente contiene imagenes en formato DICOM.
- Se uso tanto  GPU 100 de kaggle como GPU T4 de colab se puede usar cualquiera, si se usa desde el colab debes poner tu json de kaggle que use para exportar el dataset, desde kaggle ya esta llamado lo cual lo hace más sencillo, con un tiempo aproximado de 25- 45 minutos en correr todo ( si se corre en colab se demorar unos 10 minutos más)
- Puedes descargar el dataset original de la competencia en este enlace: https://www.kaggle.com/competitions/rsna-2023-abdominal-trauma-detection/data, si deseas el dataset que se uso especificamente en este notebook con las transformaciones a formato png ya hechas entonces es este enlace: https://www.kaggle.com/datasets/awsaf49/rsna-atd-512x512-png-v2-dataset
## Cómo Entrenar y Evaluar (Pasos Breves)
Para entrenar los tres modelos comparativos y evaluar su rendimiento, sigue estos pasos dentro del notebook de Colab:
Preparación del Entorno:
- Si es en colab cuando se te solicite, sube tu archivo kaggle.json para autenticarte con la API de Kaggle. ( ignorar el segundo recuadro del notebook)
- Si es en kaggle ya deberia llamarse el dataset de por si. ( ignorar el primer recuadro del notebook)
- El notebook se encargará de instalar las librerías necesarias y descargar el dataset automáticamente.
## Procesamiento de Datos:
- Ejecuta las celdas para cargar los metadatos (train.csv), crear las rutas a las imágenes y dividir los datos en conjuntos de entrenamiento y validación.
- Ejecuta la celda que define y crea los pipelines de datos (tf.data), los cuales preparan los lotes de imágenes para el entrenamiento.
## Entrenamiento de Modelos:
- Ve a la sección "Entrenamiento de Modelos".
- Ejecuta las celdas secuencialmente. El notebook definirá la arquitectura del modelo y luego entrenará, uno por uno, los tres modelos: EfficientNetB0, ResNet50V2 y MobileNetV2.
- El historial de entrenamiento de cada modelo se guardará automáticamente para su posterior análisis. ( Variable "histories").
## Evaluación:
- La evaluación se realiza de forma continua durante el entrenamiento sobre el conjunto de validación.
- Las métricas finales de Accuracy, Precision y Recall para cada modelo se imprimirán en la consola al finalizar el proceso de entrenamiento y se usarán en los siguientes pasos para generar los resultados finales usando matplot.
