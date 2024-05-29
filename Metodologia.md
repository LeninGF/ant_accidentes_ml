# Modelos de Machine Learning

Los modelos de Machine Learning (i.e aprendizaje automático) se
utilizan para obtener predicciones a partir de los datos. Debido a las
pérdidas humanas y materiales que los siniestros de tránsito acarrean,
éstos modelos pueden ser utilizados para reducir o prevenir incidentes
similares.

En el presente trabajo se utilizaron modelos supervisados de ML para
realizar la predicción de la gravedad del siniestro de tránsito
(clasificación), así como predecir el número de lesionados y
fallecidos (regresión).

## Metodología
A fin de obtener resultados a partir de los datos, se utilizan los
datos históricos disponibles en la ANT. El repositorio contiene
información desde 2017 hasta el 2024 con varias variables. Sin
embargo, una de los fenómenos relacionados con los accidentes de
tránsito es el clima, cuyos datos no están disponibles en el
dataset. Con los datos, se inicia el análisis exploratorio de los
mismos y de su análisis se puede derivar la pertinencia de los modelos
a utilizar. A fin de obtener una medida de la letalidad del accidente
se propone usar la medida denominada *tasa de letalidad* definida como
el número de fallecidos dividido para el total de lesionados y

$\tau = \frac{fallecidos}{fallecidos+lesionados}$

La medida definida se caracteriza por estar normalizada con valores
entre 0 y 1. Para los casos en que $fallecidos = lesionados = 0$ la
tasa se define en 0. Considerando la pirámide de Bird como una
referencia para definir una escala de la letalidad del accidente, se
definieron tres niveles de graduación que son:

- Fatal $\tau\geq 0.8$
- Grave $0.6 \leq \tau \le 0.8$
- Leve

### Generación de Dataset
Consiste en completar con datos meteorológicos la información
existente en el dataset de siniestros de tránsito. Para esto se
utilizó la librería XX que permite descargar información declarando un
punto geográfico con latitud y longitud y una fecha de inicio. Sin
embargo, dado que no existen datos registrados para todas las
referencias geográficas, se ha estimado suficiente considerar que las
condiciones climáticas pueden suponerse las mismas de la provincia que
contenga el punto geográfico sin información. 
