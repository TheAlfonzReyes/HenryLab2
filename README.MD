# PROYECTO INDIVIDUAL N2 
# SINIESTROS VIALES EN CIUDAD DE BUENOS AIRES
![](foto_portada.jpg) 
## Introduccion : 
Este proyecto consiste en asumir el rol de un Data Science y Data Analyst y en base a la base de datos del gobierno de la Ciudad de Buenos Aires realizar un analisis de los siniestros viales para poder entregar informacion que permita a las autoridades locales tomar medidas para reducir la cantidad de victimas fatales. Para eso vamos a utilizar los archivos disponibles en su pagina oficial y realizarles un proceso de EDA , ETL y finalmente la creacion de una base de datos MySql para la creacion de un dash board en Power Bi. 
## Tecnologias utilizadas 
- SQLAlchemy
- Sql 
- MySql
- Python 
- Pandas 
- Numpy 
- Seaborn 
- Matplotlib 
- Power Bi 
- BeautifulSoup
## Archivo necesario para ejecutar el dash boar en Power Bi
1.  [Archivo .pbix(Power Bi)](pi02.pbix)
2.  [Data Set final ](DataFrameFinal.csv)
## Resolucion: 
### 1. [Web Scraping](ETL.ipynb):
Obtenemos los archivos para la creacion de la base de datos SQL y para realizar el dash board a traves de un proceso de web scraping que esta comentado y detallado al inicio del archivo ETL. Se uso Beautiful Soup.
### 2. [EDA](EDA.ipynb): 
Realice el proceso EDA  (Exploratory Data Analysis) en el DataSet  con el objetivo de identificar relaciones , insights , tendencias y/o patrones , tal que , sirvan para el proceso de ETL y la creacion del Data Set final. Todo el proceso esta comentado y registrado en el archivo EDA.ipynb.

Como por ejemplo en la sigiente imagen podemos ver un grafico que muestra la cantidad de accidentes en los diferentes tipos de calle.

[](Img/accidentescalle.png):

Con esto podemos ver que las avenidad son las mas peligrosas y propensas a estos accidentes.
Todo con mas detalle dentro del archivo EDA.

[](Img/accidentescalle2.png):

Igual podemos ver que representa mas del 60% de los accidentes.

### 2.1. [ETL](ETL.ipynb): 
En este paso se realizo el proceso de ETL para la obtencion del Data Set final y Data Sets especiales para le proceso EDA. Todo el proceso esta debidamente comentado en el archivo ETL.ipynb. 
Lo mas importante fue la limpieza de columnas que no utilizamos, normalizar los datos, quitar nulos y modificar los SD = Sin datos. Para el correcto manejo del ETL y posteriormente poder hacer las otras tareas como el EDA y el Dashboard.

### 3.[Base de Datos -MySql](SQL.ipynb):
Creamos una base de datos con MySQL a traves de python donde ingresamos la tabla obtenida de los paso anteriores para asi conectarla a Power Bi.
Importante crear la table, el schema y correr la base en local root. Esta BD se conectara al Dashboard y desde esta consumiremos la informacion.
Dejo una imagen de muestra usando SQL Workbench.

[](Img/sql.png):

### 4. [Creacion del Dash Board](pi02.pbix):
Para este paso se utilizo el Data set final llamado DataFrameFinal.csv Se crearon 5 Paginas dentro de la presentacion de Power Bi con el siguiente objetivo: 
1. Es un menu para navegar entre las otras  paginas. 
2. Es el Dash Board principal donde se pueden realizar todo tipo de consultas al Data Set y configurar con los filtros creados. 
3. La tercera pagina es el KPIs 1 : 
* Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.
Definimos a la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000
4. La cuarta pagina es el KIps 2 : 
* Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.
Definimos a la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100
5. La quinta pagina es el KPIs 3 : 
* Reducir en un 25% la cantidad de victimas menores de 25 años en CABA , respecto al año anterior. Su fórmula para medir la evolución de los accidentes mortales con víctimas menores a 25 años es: (Número de accidentes mortales con víctimas <= 25 años del año anterior - poblacion total ) / (poblacion total ) * 100 
#### Aclaracion : 
* Los datos de Poblacion total y poblacion total <= 25 años fueron extraidos de manera manual de (https://www.indec.gob.ar/) (Incluido en el repo, c2 proyecciones_nac)
* Poblacion total <= 25 años se obtiene al calcular el 37.97%(porcentaje de habitantes <= 25 años en Argentina ) de la poblacion total de CABA.
Esto con el fin de obtener informacion de distintas fuentes pero que fueran igualmente importantes para los KPIs
### 4.1 Estetica del Dash Board : 
Para este paso se busco un estilo minimalista en una paleta de colores comodos para mejorar el UX / UI.
Se utilizaron graficos externos a Power Bi , y se uso Photoshop y Figma para complementar el apartado grafico.

(Se agregara el dashboard y un preview al terminar las revisiones del proyecto.)