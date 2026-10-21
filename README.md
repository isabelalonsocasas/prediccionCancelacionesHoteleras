# Predicción de cancelaciones hoteleras

**Machine Learning aplicado a la predicción de cancelaciones de reservas.**

Proyecto académico desarrollado por **Isabel Alonso Casas** y **Bibiana Dorado Mateos** para la asignatura *Machine Learning I: Fundamentos y Aprendizaje Supervisado*, en la Universidad Pontificia Comillas — ICAI.

El proyecto analiza reservas hoteleras, compara nueve modelos o combinaciones de clasificación e interpreta sus predicciones. El objetivo es estudiar qué características se asocian con las cancelaciones y cómo podrían ayudar a gestionar la ocupación y los ingresos del hotel.

En los resultados guardados en el notebook, **Random Forest obtiene un 89,06 % de acierto y un ROC-AUC de 0,9559**, los mejores valores de estas métricas entre los modelos comparados.

**Tecnologías:** Python · pandas · NumPy · Matplotlib · Seaborn · scikit-learn · SHAP · Jupyter

[Ver notebook](codigo_final.ipynb) · [Leer informe final](docs/informe-final.pdf) · [Ver propuesta inicial](docs/propuesta.pdf)

## Datos

Se utiliza el conjunto **Hotel Booking Demand**, incluido en `hotel_bookings.csv`:

| Característica | Valor |
| --- | --- |
| Reservas originales | 119.390 |
| Columnas originales | 32 |
| Reservas canceladas | 44.224 — 37,04 % |
| Variable objetivo | `is_canceled`: 1 = cancelada; 0 = no cancelada |
| Reservas tras la limpieza | 117.863 |
| Variables de entrada tras la codificación | 52 |
| División de datos | 80 % entrenamiento y 20 % prueba, estratificada |

Las variables describen aspectos como la antelación de la reserva, el tipo de hotel, las noches de estancia, el precio medio diario, el depósito y las peticiones especiales.

**Fuentes del dataset:** [Hotel Booking Demand en Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) 

## Proceso de trabajo

1. **Análisis exploratorio:** estructura, valores ausentes, distribución de las cancelaciones, variables categóricas y correlaciones.
2. **Limpieza:** eliminación de identificadores `agent` y `company`, registros incompletos, reservas inconsistentes y valores anómalos de `adr`.
3. **Preparación:** creación de `room_changed`, agrupación de países, codificación de categorías y estandarización de variables numéricas con el escalador ajustado en entrenamiento. Se excluyen `reservation_status` y `reservation_status_date` de las entradas del modelo.
4. **Modelado:** entrenamiento y ajuste de hiperparámetros mediante validación cruzada en varios de los algoritmos.
5. **Evaluación:** comparación de acierto, precisión, sensibilidad, F1, especificidad y ROC-AUC, junto con matrices de confusión.
6. **Interpretación:** importancia de variables, importancia por permutación, gráficos de dependencia parcial y explicaciones SHAP.


## Contenido del repositorio

| Archivo o carpeta | Contenido |
| --- | --- |
| [codigo_final.ipynb](codigo_final.ipynb) | Notebook con código, análisis, resultados y gráficos guardados |
| [hotel_bookings.csv](hotel_bookings.csv) | Dataset utilizado por el notebook |
| [requirements.txt](requirements.txt) | Dependencias de Python para trabajar con el proyecto |
| [docs/informe-final.pdf](docs/informe-final.pdf) | Memoria final del trabajo |
| [docs/propuesta.pdf](docs/propuesta.pdf) | Propuesta inicial |
| [docs/img](docs/img) | Gráficos extraídos de las salidas originales del notebook |

## Autoras

**Isabel Alonso Casas · Bibiana Dorado Mateos**  
Universidad Pontificia Comillas — ICAI  
Machine Learning I: Fundamentos y Aprendizaje Supervisado
