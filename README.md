# Proyecto Analitica III

## Descripcion
Este proyecto desarrolla un modelo de clasificacion para predecir mora mayor a 30 dias en un horizonte de 3 meses (`M3_30AC`) usando variables sociodemograficas y financieras de clientes.

El enfoque prioriza la deteccion de clientes morosos (recall de la clase positiva), ya que el costo de no detectar un cliente en riesgo es alto para el negocio.

## Que se hizo
Se ejecuto un flujo completo de analitica y modelado:

1. Carga de librerias y base de datos.
2. Revision general de estructura de datos.
3. Validacion de calidad: nulos, duplicados y estadisticas descriptivas.
4. Balanceo de clases con undersampling 1:2.
5. Codificacion de variables categoricas y limpieza final.
6. EDA con graficos de distribucion, densidad, boxplot, correlacion, ECDF y deciles.
7. Construccion del modelo base (red neuronal).
8. Optimizacion de hiperparametros.
9. Entrenamiento del modelo optimizado con variables seleccionadas.
10. Evaluacion comparativa y seleccion del modelo final.

## Datos
- Tamano de la base original: 21.091 registros.
- Variable objetivo: `M3_30AC`.
- Desbalance inicial aproximado: 96% clase 0 y 4% clase 1.
- Balanceo aplicado para entrenamiento: proporcion 1:2 (clase 1:clase 0).

## Donde esta la base de datos
Actualmente el notebook carga el archivo desde una ruta local:

`/Users/yedisoncuervo/Downloads/BD taller clasificación (2) (2).xlsx`

Sin embargo, se puede acceder la base de datos a través del siguiente link de drive.

# BD Drive
https://docs.google.com/spreadsheets/d/1qSyguOGmzchg6AjadiekvsqUAXytKLDf/edit?usp=sharing&ouid=106337131126808334437&rtpof=true&sd=true


Para facilitar la reproducibilidad, se recomienda mover el archivo a una carpeta `data/` dentro del proyecto y actualizar la ruta en el notebook.

## Estructura del proyecto
```text
PROYECTO_ANALITRICA_III/
├── README.md
└── src/
	└── Modelo_RN_1.ipynb
```

## Como ejecutar
1. Abrir `src/Modelo_RN_1.ipynb` en VS Code/Jupyter.
2. Verificar la ruta del archivo de datos en la celda de carga.
3. Ejecutar las celdas en orden, de arriba hacia abajo.

## Herramientas principales
- Python
- pandas, numpy
- matplotlib, seaborn, scipy
- scikit-learn
- TensorFlow / Keras

## Resultado general
Se compararon un modelo base optimizado y un modelo con variables seleccionadas con diferentes arquiteturas y parametros. La seleccion final se hizo con base en desempeno predictivo (especialmente recall de clase positiva), estabilidad y simplicidad del modelo.