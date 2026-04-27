🧾 Proceso de trabajo

A continuación detallo cómo he desarrollado el proyecto paso a paso, desde la definición inicial hasta la visualización final en Power BI.

📅 10/04/2026 — Inicio del proyecto

El proyecto comienza con la definición del problema: analizar los tiempos de espera en urgencias y entender qué factores pueden estar influyendo en ellos.

A partir de ahí, construyo un dataset simulado en Excel, con el objetivo de trabajar sobre un caso lo más realista posible.

Antes de analizar nada, hago una primera revisión del dataset para detectar errores y problemas de calidad de datos. En esta fase realizo:

Eliminación de valores nulos en columnas clave:
id_paciente
hospital
fecha
hora_llegada
tiempo_espera_min
tipo_urgencia
medico_id
Limpieza y estandarización de texto en variables categóricas como hospital y tipo_urgencia, utilizando funciones como:
=ESPACIOS(LIMPIAR(A2))

El objetivo aquí es asegurar que el dataset sea consistente antes de empezar el análisis.

📅 26/04/2026 — Análisis exploratorio (EDA)

Una vez limpio el dataset, paso al análisis exploratorio para entender qué está ocurriendo en los datos.

⏱️ Tiempo medio de espera

Calculo el tiempo medio de espera utilizando:

=PROMEDIO(G:G)

(asegurando previamente que el formato es numérico)

El resultado obtenido es:

👉 59,31 minutos

Esto me permite sacar una primera conclusión:

El tiempo medio de espera se sitúa en torno a 60 minutos, lo que indica posibles problemas de saturación en el servicio de urgencias.

Además, al comparar entre hospitales:

Los tiempos de espera son elevados en todos los hospitales, con diferencias mínimas entre ellos, lo que sugiere un problema generalizado más que localizado.

🕒 Análisis por horas (horas pico)

Para profundizar, creo una nueva variable (hora_llegada_base) a partir de la hora de llegada:

=HORA(E2)

A partir de ahí, construyo una tabla dinámica para analizar el comportamiento por hora.

Esto permite identificar patrones claros:

Los mayores tiempos de espera se concentran en primeras horas de la mañana y en franjas nocturnas.

Y una interpretación más interesante:

El análisis por hora muestra picos claros de espera en la mañana y la noche, lo que sugiere una posible relación con la distribución de turnos del personal sanitario.

📊 Visualización en Power BI

Una vez entendido el problema en Excel, paso a Power BI para construir un dashboard interactivo que permita explorar los datos de forma más clara.

En esta fase:

Creo un KPI principal con el tiempo medio de espera
Desarrollo un gráfico de líneas para visualizar la evolución por hora
Añado un filtro por hospital para poder analizar el comportamiento de forma dinámica
Incorporo etiquetas para facilitar la lectura de los valores

Esto permite confirmar visualmente los insights obtenidos en el análisis:

Los tiempos de espera presentan picos claros en determinadas franjas horarias, especialmente en primeras horas de la mañana y en horario nocturno.

🧠 Conclusión

Este proceso me ha permitido no solo analizar los datos, sino también plantear una hipótesis de negocio:

👉 La distribución de turnos del personal sanitario puede estar influyendo directamente en los tiempos de espera.
