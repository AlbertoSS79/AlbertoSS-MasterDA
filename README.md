# AlbertoSS-MasterDA
 
 04/01/25 Informe EDA con los pasos seguidos para elaborar las tablas y el Dashboard
 1. ACCIÓN: Importación de archivo CAJEROS.csv
 DESCRIPCION: Se trata de un archivo de datos sobre el número de cajeros automáticos (en adelante ATM) que existen en cada localidad de España en el año 2024, el número de transacciones que se han hecho cada ATM, el dinero en efectivo que ha sido retirado en cada uno, el numero de incidencias que ha sufrido cada ATM, y los días que ha estado inoperativo cada uno.
 DETALLES: Para elaborar este archivo CAJEROS, se ha utilizado un listado proporcionado por la WEB DEL BANCO DE ESPAÑA, en concreto se ha solicitado un listado sobre el nº de oficinas de entidades bancarias en cada localidad de España. Para completar los datos del Banco de España, se han añadido varias columnas ficticias, como el nº de transacciones, incidencias de Servicio Tecnico y días inoperativos. Estos datos los he añadido creando una funcion ALEATORIO con los rangos que he considerado aceptables.
 2. ACCIÓN: importación de archivo Población España 2024
 DESCRIPCIÓN: Se añade una nueva hoja que contiene datos sobre la población en cada localidad de España en 2024.
 DETALLES: El listado se ha obtenido de la página WEB DEL INE (Una consulta sobre datos del Censo de Poblaciones españolas en 2024).
 3. ACCIÓN: Añadir columna ID_Municipio en ambas hojas.
 DESCRIPCIÓN: El objetivo es tener un ID_Unico que coincida en ambas hojas, para poder anexar los datos de población a cada municipio de la tabla principal sobre ATMs.
 DETALLES: Se utiliza la función CONCATENAR, resultando así un código Provincia + Codigo Municipio.
 4. ACCIÓN: Anexado de datos de la hoja POBLACIÓN a la hoja DATOS ATM mediante la conexión ya creada del ID_Municipio.
 DESCRIPCIÓN: Al unir los datos de población en cada municipio con el nº de ATMs en cada municipio, se podrán extraer datos más concretos sobre la relación que existe entre ambas variables, y ello será útil para un estudio de mercado sobre ATMs.
 DETALLE: Para el anexado de datos de población a la tabla principal se ha utilizado la funcion BUSCARV
 5. ACCIÓN: Eliminación de dos filas vacías en la tabla principal, se observan al analizar cada columna en busca de patrones de limpieza, como (vacias), etc.
 6. ACCIÓN: Eliminación de columnas sobrantes vacías en tabla principal, limpieza de datos.
 7. ACCIÓN: Verificación de datos duplicados.
 DESCRIPCIÓN: Se eliminan 893 valores duplicados (tienen la misma entidad bancaria y el mismo ID_Municipio).
 8. ACCIÓN: Inserción de hoja con datos sobre Comunidades Autonomas (en adelante CCAA) en relación con cada municipio de España.
 DESCRIPCIÓN: El objetivo es poder extender el análisis de los datos al ámbito de una CCAA, además de por provincias y municipios.
 DETALLE: Se utiliza BUSCARV para extraer los datos mediante el ID_Municipio.
 9. ACCIÓN: Ocultar columnas innecesarias para el análisis posterior.
 10. ACCIÓN: Ocultar hojas Población, CCAA.
 11. ACCIÓN: Finalización de EDA, los datos que se utilizarán para el análisis se resumen en una tabla con 13 columnas y 10451 filas.
 DESCRIPCIÓN: 7 columnas numericas (oficinas, operaciones, incidencias, dias inactividad, población, hombres, mujeres) y 1 con formato moneda (retirada efectivo), el resto son texto.
 DETALLE: Cada fila se refiere a una ENTIDAD BANCARIA en un MUNICIPIO de España en 2024, el nº de ATMs de que dispone, el nº de operaciones que éstos han hecho durante el año, el dinero en efectivo que se ha retirado en sus ATMs, incidencias de Servicio Técnico que han sufrido, días totales que han estado los ATMs inoperativos por causa de esas incidencias, y la población del MUNICIPIO.
 12. ACCIÓN: Creación de hoja con el Dashboard (DB) y creación de una serie de Tablas Dinámicas que tienen su base en tabla Datos (también una tabla dinamica con base a la hoja Población 2024), las cuales darán soporte a los GRÁFICOS incluidos posteriormente en el Dashboard.
 DESCRIPCIÓN: El objetivo es poder observar la dispersión de ATMs en el territorio español, las zonas donde hay mas o menos, las zonas donde se producen más o menos incidencias, donde se retira más o menos dinero en efectivo, y todo ello ponerlo en comparación con los datos poblacionales de cada territorio.
 13. ACCIÓN: Creación de Gráficos en hoja DB, mas otros 4 KPIs interactivos con Gráficos de comparación de resultados, y un indicador fijo sobre el nº de habitantes en España en 2024.

 04/01/2025. Análisis de datos con el DASHBOARD.
 1. DATOS: Datos sobre población en España 2024.
 ANÁLISIS: Se observan las CCAA ordenadas en función de mayor a menor población.
 UTILIDAD: La cantidad de habitantes puede ayudar a seleccionar CCAA objetivo según nuestras necesidades de implantación de nuestro parque de ATMs, si queremos introducirnos en mercados con mucha población (mayor beneficio, mayor visibilidad) o menor población (mayor servicio a la "España Vaciada"). Podemos asi ser una entidad bancaria más generalista o tratar de ser una Entidad más específica y confiable en entornos geográficos más reducidos.
 2. DATOS: Datos de población relacionados con nº de ATMs en cada CCAA (Grafico Concentración ATMs).
 ANÁLISIS: Ciertas CCAA tienen más peso porcentual en la población general, pero menos peso porcentual en relación al nº de ATMs del total de España. Estas son por ejemplo Cataluña, Madrid o C.Valenciana, pero también en menor medida, Canarias o Murcia, quizás también Baleares. A la par en esa relación porcentual estarían Andalucía, Galicia o Cantabria, que podrían tratarse como objetivos secundarios.
 UTILIDAD: Estas CCAA con más peso de población que de ATMs podrían ser un mercado objetivo para instalar nuestro parque, debido a que disponen de población suficiente y el mercado no está tan saturado de ATMs como en otras zonas.
 3. DATOS: Datos sobre cantidad de ATMs que posee cada Entidad Bancaria en España (Gráfico Parque de ATMs).
 ANÁLISIS: La mitad del parque de ATMs pertenece a Caixabank (25%), BBVA y Banco Santander (3 Entidades Bancarias dominadoras del mercado de ATMs), y otro 25% se reparte entre otras entidades (Banco Sabadell, Ibercaja, Caja Rural y Cajamar). El resto de ATMs se reparten en Entidades Bancarias de menor dimensión y con menor peso específico en el mercado, con lo cual estarán más marcadas al ámbito de una CCAA o regiones específicas.
 UTILIDAD: Puede ser relevante conocer las entidades con mayor representación (fruto de fusiones y absorciones de años anteriores), ya que puede darnos una pista de cuáles pueden ser nuestros competidores si conocemos el peso específico que vamos a intentar tener en el mercado cuando nos implantemos.
 4. DATOS: Datos sobre cantidad de ATMs que posee cada Entidad Bancaria en cada CCAA (Gráfico Distribución de ATMs).
 ANÁLISIS: Se observan CCAA en las que predominan las Entidades propias de cada región, como puede ser el caso de C.Valenciana con Cajamar, Galicia con Abanca o Pais Vasco con Kuxabank, o algo con cierto peso como es el caso de Madrid y Castilla-La Mancha con Ibercaja. El resto de entidades tienen más o menos una distribución regular en el territorio.
 UTILIDAD: La posible implantación de nuestro parque de ATMs en CCAA en las que ya existe una cierta identificación de la población con ciertas Entidades Bancarias puede ser un poco problemático, en el sentido de que sería más difícil conseguir que la gente confíe en una nueva Entidad no asociada históricamente con dicha región geográfica.
 5. DATOS: Análisis de rendimiento de ATMs a nivel CCAA
 ANÁLISIS: Madrid destaca como zona con menor porcentaje de incidencias en sus ATMs, y pasan menos días inoperativos que en otras regiones. De esto se deduce que existe en Madrid mayor competencia entre Entidades Bancarias, y también que sus Servicios Técnicos disponen de más recursos para atender zonas prioritarias. Esto mismo pero algo menos marcado se observa también en Cataluña, País Vasco o Canarias. En cambio, hay otras CCAA en las que los ATMs tienen peores rendimientos, como C.Valenciana, Andalucía, Castilla y Leon, Castilla-La Mancha o Extremadura.
 UTILIDAD: Si queremos tener la oportunidad de marcar la diferencia en el mercado, sería interesante valorar la distribución de nuestro parque en zonas con peor ratio de rendimiento de los ATMs, puesto que de ello podríamos deducir que en esas zonas los clientes estarán menos satisfechos con la oferta actual de ATMs, y estarán quizás más abiertos a valorar el cambio a otra Entidad Bancaria en la que los ATMs tengan mejor rendimiento, estén mayor tiempo disponibles para retirar dinero cuando el cliente lo necesite.
 6. DATOS: Análisis de rendimiento de ATMs a nivel PROVINCIA.
 ANÁLISIS: Hay Provincias en las que se observa peor rendimiento de ATMs, como Valencia, Alicante, Badajoz, Granada, Toledo, Guipúzcoa, Jaen, Cadiz. Otras siguen destacando por su alto rendimiento, coincidiendo con las Provincias más importantes de España, que disponen de más recursos como ya se ha observado a nivel CCAA (Madrid, Barcelona, Vizcaya).
 UTILIDAD: Podrían determinarse como zonas interesantes aquellas Provincias que tienen peor rendimiento de ATMs, como la zona Mediterránea, parte de Andalucía, Toledo o Badajoz.
 7. DATOS: Análisis de rendimiento de ATMs a nivel MUNICIPIO.
 ANÁLISIS: Se observa que los municipios con mayor cantidad de ATMs son en realidad los que mejor rendimiento tienen, posiblemente debido al factor ya comentado de que se presta mayor atención y recursos a las zonas más influyentes de cada región geográfica.
 UTILIDAD: Es posible así no enfocar nuestro interés no sólo en los municipios más relevantes de cada región, sino también en aquellos que tengan algo menos de importancia en cuanto nivel poblacional, pero que tengan un cierto peso específico en dicho factor, con el fin de poder abordar con ciertas garántias nuestra implantación en el mercado.
 8. DATOS: Análisis de rendimiento de ATMs a nivel Entidad Bancaria.
 ANÁLISIS: Las principales Entidades (Caixabank, BBVA, Santander) son las que tienen también mejores tasas de rendimiento de sus ATMs, tienen mayor cantidad de recursos a su disposición, y pueden ejercer mayor peso en sus negociaciones con los proveedores de Servicio Técnico, estableciendo así unos SLAs mas rigurosos para la atención de sus ATMs.
 UTILIDAD: Para poder competir en el mercado, se hace necesario tomar medidas que busquen garantizar el buen funcionamiento de nuestros ATMs, las cuales pueden provenir de la compra de ATMs de marcas reconocidas y de calidad, la negociación de SLAs reducidos con proveedores de Servicio Técnico, así como en el ámbito de la Gestión de Efectivo (Recargas y Retiradas de Efectivo en los ATMs). Por ello no ha de atenderse solamente al factor cantidad de ATMs, ya que mucha cantidad con poca disponibilidad para los clientes podría tener consecuencias nefastas en la consecución de nuestros objetivos.
 9. DATOS: Análisis de Rendimiento de ATMs a nivel Operaciones, Volumen de Retirada de Efectivo.
 ANÁLISIS: Hay ciertas CCAA que destacan por tener una ratio bastante elevada de retirada de efectivo y operaciones en ATMs, en relación al nº de ATMs en su territorio. Esto puede deberse a que son zonas donde todavía se le da gran importancia al manejo de dinero en efectivo, frente a otras CCAA mas "cosmopólitas" donde van ganando terreno otro tipo de operaciones alternativas al efectivo, como los pagos con tarjeta, comercio electrónico, etc.
 UTILIDAD: Podemos dar importancia a estas zonas donde la utilización del dinero en efectivo es bastante superior a la media, si queremos que nuestro parque de ATMs tenga buenos ratios de operaciones y de retirada de efectivo. Las CCAA donde se observa esta tendencia con mayor intensidad son las de Aragón, Castilla-La Mancha, Castilla y León, Galicia y Navarra, y algo menos marcado en otras zonas como Extremadura, Canarias, Asturias o La Rioja.


