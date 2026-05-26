# Análisis de Datos: Sistema de Bicicletas Compartidas (Citi Bike)

## DESCRIPCION DEL PROYECTO
Este proyecto tiene como objetivo analizar el comportamiento y la eficiencia operativa del sistema de bicicletas compartidas Citi Bike. A través de este EDA (Análisis Exploratorio de Datos), buscamos entender los patrones de movilidad urbana y las diferencias en el comportamiento entre suscriptores y clientes ocasionales.

## OBJETIVOS DEL ANALISIS
1. **Optimización Operativa:** Identificar estaciones críticas en horas punta para proponer mejoras en la redistribución.
2. **Comportamiento del Usuario:** Diferenciar patrones de uso entre suscriptores y clientes ocasionales.
3. **Análisis Temporal:** Evaluar cómo fluctúa la demanda según el día de la semana y cómo la hora del día influye en la eficiencia del viaje (velocidad/duración).

## DATASET

## Alcance de los Datos
El dataset analizado corresponde a una muestra de 40,575 viajes registrados durante una jornada de 24 horas (Martes). Este nivel de detalle permite una inspección profunda de la demanda horaria y operativa en un día laborable típico en Nueva York.

El conjunto de datos contiene registros históricos de viajes, incluyendo:
- Tiempos de inicio y fin.
- Ubicación de estaciones (latitud/longitud).
- Información del usuario (tipo, año de nacimiento, género).

## TIPOS DE INFORMACION (Columnas Típicas)
El archivo contiene información estructurada generalmente en las siguientes categorías:

## 1. Información Temporal:

- start time y stop time: Marca exacta de inicio y fin del viaje.
- trip duration: La duración del trayecto (generalmente en segundos).

## 2. Información de Estaciones:

- start station id, start station name: Identificación y nombre de la estación de origen.
- end station id, end station name: Identificación y nombre de la estación de destino.
- start station latitude/longitude y end station latitude/longitude: Coordenadas geográficas para análisis de rutas.

## 3. Información de la Bicicleta y Usuario:

- bike id: Identificador único de la bicicleta utilizada.
- usertype: Clasificación del usuario (generalmente distinguido entre "Subscriber" o suscriptor anual y "Customer" o usuario ocasional de pase diario/3 días).
- birth year: Año de nacimiento del usuario (utilizado para analizar la demografía de los ciclistas).
- gender: Género del usuario.



------------------------------------------------------------------------------------------------------------
DOCUMENTACION DEL FLUJO DE TRABAJO
------------------------------------------------------------------------------------------------------------

## 1. PREPARACION DE DATOS
El dataset cuenta con 40,575 registros y 15 variables. Se han realizado las siguientes acciones:
- Conversión de columnas temporales (`start_time`, `stop_time`) al formato `datetime`.
- Verificación de integridad: el dataset no presenta valores nulos en columnas críticas.
- Ingeniería de características: creación de variables de tiempo (`day_of_week`, `hour`, `periodo`) para facilitar el análisis de patrones temporales.

## Análisis de Comportamiento del Usuario
Se han identificado dos perfiles de usuario distintos dentro del sistema:
- **Suscriptores:** Demuestran una fuerte dependencia de los horarios laborales, con picos de uso marcados en las horas punta de la mañana (8:00 AM) y la tarde (6:00 PM).
- **Clientes Ocasionales:** Muestran una distribución de uso más uniforme durante la tarde, con duraciones de viaje significativamente mayores, lo que sugiere un uso enfocado al ocio.


## Resumen Ejecutivo
El análisis realizado sobre el dataset de Citi Bike ha permitido desglosar el funcionamiento de la red en una jornada laboral típica. Se ha confirmado una clara dicotomía en el comportamiento de los usuarios: mientras los suscriptores sostienen la demanda en horas punta (movilidad pendular), los usuarios ocasionales definen un perfil de uso recreativo con viajes de mayor duración. La identificación de estaciones críticas mediante el cálculo del flujo neto (Balance) proporciona una hoja de ruta accionable para la optimización logística y la redistribución de la flota.

## Conclusiones
1. **Diferenciación de Perfiles:** 
El sistema sirve a dos públicos distintos con necesidades opuestas. La infraestructura debe garantizar disponibilidad en puntos de salida para suscriptores por la mañana y capacidad de recepción para los ocasionales por la tarde.

2. **Nodos Críticos:** 
Se han identificado estaciones de alta demanda que actúan como sumideros o fuentes de bicicletas. Estas estaciones deben ser la prioridad en los planes de mantenimiento y redistribución.

3. **Eficiencia Operativa:** 
El patrón de uso, aunque predecible, requiere una gestión dinámica basada en el balance de flujo neto entre estaciones, especialmente en los picos identificados a las 8:00 AM y 6:00 PM.



## Resultados Visuales

A continuación, se presentan los hallazgos gráficos del análisis:

* **Demanda Horaria:** [Ver gráfico de horas](imagenes/Distribucion_de_viajes_por_hora_del_dia.png)
* **Comparativa de Usuarios:** [Ver gráfico de tipos de usuario](imagenes/Distribucion_de_viajes_por_tipo_de_usuario.png)
* **Movimiento en las estaciones:** [Estaciones con mas salidas](imagenes/Top_estaciones_de_salida.png)

> Nota: Los archivos de imagen se encuentran en la carpeta `/imagenes` del repositorio.