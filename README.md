# PROYECTO-MAML
Proyecto Grupo 2 Clase de metodologías agiles con machine learning. 
# Proyect Charter
Grupo 2 
Nathalia Carolina Chacón Monrroy 
Eloth de Jesús Luna García 
Diego Felipe Acuña Toloza 


## Modelo de riesgo de Proyectos de vivienda y Saneamiento básico  

# ANTECEDENTES EMPRESARIALES 

Quien es el cliente, en qué ámbito empresarial se encuentra el cliente 

El cliente es la Contraloría general de la Republica esta es una entidad de orden público nuestro cliente interno es el jefe de unidad de análisis de la DIARI, referente al sector vivienda y saneamiento básico  

Que problemas empresariales se pretenden resolver 

El problema consiste en que no se cuenta con indicadores adecuados, para determinar el nivel de riesgo de incumplimiento en los proyectos de vivienda y saneamiento básico, y para agrupar aquellos proyectos con características similares que puedan ser considerados de alto riesgo. 

El problema consiste en que no se cuenta con un score de riesgo que sea lo suficientemente preciso para determinar qué proyectos se encuentran en riesgo 

# ALCANCE 

¿Qué soluciones de ciencia de datos estamos tratando de construir? 

La solución de ciencia de datos que vamos a implementar es la creación de un modelo no supervisado para identificar las características de los proyectos de vivienda y saneamiento básico, que permitan asociar estas características a los criterios de riesgo de incumplimiento. 

# ¿Que vamos a hacer? 

Modelo de reducción de dimensionalidad (Análisis de correspondencias multiples) teniendo en cuenta la base de datos del SIGEVAS, FONVIVIENDA  

# ¿Como va a ser consumido por el cliente? 

A través de un tablero en Power Bi el usuario puede consultar de una manera ágil, los proyectos que pueden considerarse como alertas, también podrá visualizar características que influyen en los criterios de riesgo y además podrá hacer seguimiento periódico para evaluar el avance de los mismos.  

# PERSONAL 

¿Quiénes están en el proyecto? 

Jefe de proyecto: Diego Felipe Acuña Toloza 

Product Manager: Natalia Carolina Chacón Monrroy 

Científico de Dato: Eloth de Jesus Luna 

Jefe de Unidad de análisis      Christian Humberto Sanabria 

# MÉTRICAS 

¿Cuáles son los objetivos cualitativos? 

Identificar patrones entre los proyectos, que nos permitan conocer detalladamente como influyen variables de tipo lugar, valor de la obra, contratista, etc en el seguimiento de proyectos y en los criterios de riesgo. 

 

# ¿Cuáles son las métricas cuantificables? 

 Aumentar el nivel de confiabilidad del score de riesgo, alertando un mayor número de proyectos con altas probabilidades de pérdida del recurso. 

Lograr la ejecución completa de aquellos proyectos con mayores desfases en ejecución a través del seguimiento 

 

Cuantificar que mejora de los valores de la métrica es útil para el escenario del cliente 

La métrica central consiste en cuantificar el número de alertas, sobre el total de contratos de obra que arroja el modelo con riesgo alto 

Métrica 1 = Número de alertas / Contratos salida modelo 

Métrica 2 (Precisión) = Número de alertas con riesgo alto / Numero de alertas totales 

Para nuestro modelo queremos aumentar la precisión del score de riesgo (Métrica 2)  

 

# ¿Cuál es el valor de referencia de la métrica? 

Métrica 2 (Precisión)= Número de alertas con riesgo alto / Numero de alertas totales = 37% 

El objetivo con el modelo que se plantea es calcular un score de riesgo más preciso, y aumentar la precisión del modelo en la generación de alertas. 

Métrica 1 = Número de alertas / Contratos salida modelo = 12% 

Con la métrica 1 se tiene una idea general de los proyectos que presentan riesgo en este negocio y en el contexto de los datos estudiados. 

 

# ¿Cómo mediremos la métrica? 

A medida que se corran los diferentes modelos, vamos a obtener diferentes scores de riesgo, y a medida que el score sea más preciso, se puede calcular la métrica para cada modelo que se esté probando 

 

# PLAN 

Vamos a utilizar la metodología CRISP-DM para este proyecto en las fases realizaremos las siguientes actividades 
Fase 1: Entendimiento del negocio 

Actualmente estamos trabajando en el entendimiento de negocio, a través de realizar alertas sobre proyectos de agua y vivienda, revisando los contratos y teniendo en cuenta criterios de riesgo que nos permiten determinar cuándo un proyecto se encuentra en riesgo, también validando los avances de obra con actas de interventoría y soportes documentales 

# Fase 2: Entendimiento de los datos 

Contamos con la base de datos del SIGEVAS para los proyectos de agua y saneamiento básico, y la información de FONVIVIENDA a través de información que se le ha solicitado directamente a los ejecutores a través de matrices de seguimiento 

# Fase 3: Preparación de los datos 

Hito 1: Crear un notebook de Python para el desarrollo del modelo (Base de datos de trabajo) 

Hito 2: Crear variables derivadas de la base original (Crear variables adicionales como el desfase de cronograma, el tiempo trascurrido frente al plazo inicial etc) 

Hito 3: Estandarizar las variables 

Hito 4: Determinar la base de datos de entrenamiento (Alertas previas) 

 

Fase 4: Modelamiento 

Hito 1: Modelo no supervisado PCA (con las variables cualitativas originales de la base de datos y con las variables derivadas) 

Hito 2: Modelo supervisado (Mejorar el score de riesgo con el que contamos, para predecir los parámetros de nuestro score) 

Hito3: Contrastar los resultados con la intuición del negocio, y con la medición de las métricas planteadas 

 

Fase 5: Evaluación 

Hito 1: Tabla de comparación de las salidas del modelo frente a los proyectos alertados previamente 

Hito 2: Evaluar la efectividad de los diferentes modelos, planteados e identificar las oportunidades de mejora del modelo 

Hito 3: Enunciar los insights encontrados en el ejercicio del pca para las variables cualitativas 

   

Fase 6: Despliegue 

Hito 1: Visualización en power bi  

Hito 2: garantizar la automatización de la salida del modelo con la actualización de los datos 

 

Arquitectura 

Datos 

¿Qué datos esperamos? 

Para el caso del SIGEVAS contamos con una vista materializada del sistema SIGEVAS el cual es un sistema del ministerio de vivienda, con el cual se registra la información del seguimiento de los proyectos de agua y saneamiento básico a lo largo del país. Los campos más importantes para el modelo son el avance físico ejecutado, avance financiero, fechas de inicio, fecha inicial de finalización, información de prórrogas etc 

Para el caso de FONVIVIENDA mensualmente nos reportan información en una matriz de seguimiento, y se solicitan campos determinados por la CGR. 

A partir de las bases entregadas por el cliente, se realizan una serie de validaciones de los datos, se limpian y preparan los datos, y posteriormente generamos variables adicionales para el análisis. 

 

¿Qué herramientas y recursos de almacenamiento o/y análisis se utilizarán para la solución? 

Las herramientas que utilizaremos son las siguientes  

SQL (Pre procesamiento de los datos) 

Python (Modelamiento) 

Modeler (Modelamiento) 

Power BI (Visualización de los resultados) 

 

Comunicación  

¿Cómo nos mantendremos en contacto? 

Para ir avanzando en el desarrollo del proyecto, vamos a reunirnos de lunes a viernes de 2:30 pm a 3:00 pm  

También planteamos una reunión semanal con los profesores del curso de metodologías, para validar los avances, principalmente en el planteamiento del modelo de machine learning   

  

 
