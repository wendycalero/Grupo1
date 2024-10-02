Presentacion Oral Churn:
El problema: "Churn", o tasa de abandono, PwC menciona que en 2020, las empresas de telecomunicaciones globales enfrentaban tasas de churn de entre el 15% y el 30% anual
Adquirir nuevos clientes resulta considerablemente más costoso que retener a los ya existentes. Según estudios Harvard Business, la pérdida de un cliente puede costar entre 5 a 25 veces más que retenerlo.

Precios altos, calidad del servicio, insatisfacción con soporte al cliente, y campañas de marketing de sus competidores. Además, el avance en la tecnología ha permitido que los consumidores comparen y cambien de manera rápida y sencilla.

Nuestro Modelo de predicción de churn busca identificar a los clientes con mayor riesgo de deserción, permitiendo a la empresa tomar acciones proactivas para retenerlos. Esto se traduce en un aumento de la fidelización de clientes.

Soluciones existentes: Algunas soluciones que se encuentran en el mercado en el ámbito tecnológico son las siguientes:
•	Movistar: Programa de Fidelización de Clientes la cual utiliza big data y ML para ofrecer recompensas y beneficios personalizados a los clientes.
•	Orange: Modelos Predictivos de Churn analiza datos en tiempo real y predecir quienes estan en riesgo de abandonar la empresa.
•	T-Mobile: Patrones de uso y quejas, empleo modelos de análisis predictivo para reducir el churn entre sus clientes.
El contexto de nuestros datos es que tenemos 7043 clientes de los Estados Unidos en especifico del estado de California del 3er trimestre, también se encontró valores faltantes en los features de Offer e Internet Type los cuales se trato y reemplazo de forma pertinente.

Metodología: Se observa en los diferentes graficos el histograma de algunas variables entre ellas, tenemos a la edad donde la mayor densidad de clientes se encuentra entre los 40 a 60 años, sin embargo, hay una frecuencia considerablemente alta en los clientes que están alrededor de sus veintes. En total Extra Data Charges notamos que los clientes no suelen gastar más allá de su plan original porque el ratio oscila entre 0 y 1. Y en Monthly Charge los valores del cargo mensual de los clientes suelen ser de alrededor de $20 pero también hay algunos clientes que pagan más de $100 mensual.

En Distribución de la variable de satisfacción la mayoría de los clientes con un 37.5% tiene un nivel de satisfacción del 3 seguido de un 25.5% con 4 y hay una minoría del 7.3% con un nivel de 2%.
Por otra parte, en la distribución de numero de dependientes más del 70% de nuestros clientes no tienen dependientes, es decir, que el servicio que consumen de la empresa suele ser individual y solo un pequeño porcentaje lo comparte con algunos de sus dependientes que estos están entre 1 hasta 3 personas.

Se observa que la variable relacionándolo con la target que es el churn label, es decir, la tasa de deserción del cliente se encuentra en dos extremos cuando la satisfacción del cliente esta entre 1 y 2 hay un 100% de probabilidad que abandone el cliente la empresa mientras que si tiene un 4 o 5 este tiende a permanecer en la empresa en todos los casos.

Aquellos que tienen seguridad online tienden a quedarse en un 85% en comparación a aquellos que no tienen con un 67%. También mientras mas tiempo el cliente tenga con la empresa menos probabilidad de que la abandone.

Procesamiento de datos se dividió de la siguiente manera el train data con un 70% son los datos que se usará para entrenar el modelo y es probable que el modelo tenga suficiente información para aprender de manera efectiva. Validation data fueron usados para optimizar el modelo y ajustar hiperparametros y test data los cuales son independientes para evaluar el rendimiento final del modelo con un 15% para cada una.

Feature Engineering:
•	Extra Charges Ratio: (Total Extra Data Charges)/(Total Charges)
El propósito de este ratio era para conocer el porcentaje exacto extra que los clientes utilizan fueran de su plan de servicio contratado.
•	Has Streaming Service ('Streaming TV', 'Streaming Movies', 'Streaming Music')
Para conocer por cliente si alguno tenia al menos uno de los servicios anteriormente mencionados si lo tenia se llenaba el valor de 1 y sino 0.
•	Región California, se dividió de la siguiente manera:
Norte de California: Si la latitud es mayor a 38.
Centro de California: Si la latitud está entre 36 y 38 (inclusive).
Sur de California: Si la latitud es menor a 36.
Porque las ciudades eran mas de 1000 que no se repetían pues eran valores únicos y por su dificultad de codificaciones se opto por dividirlos en regiones.
Codificación de features categóricos:
Se utilizo: OrdinalEncoder y funciones para iterar y acelerar el proceso de reemplazo en valores booleanos. Hay valores excluyentes tales como; Population, Zip Code y Customer ID.

Entrenamiento y tuneo de hiperparámetros
La métrica que se buscó optimizar fue el f1 para nuestro primer modelo por dos razones:
•	Balance entre precisión y sensibilidad: La F1 considera tanto la capacidad del modelo para identificar correctamente a los clientes que se irán (recall) y La precisión mide cuántos clientes que el modelo predice que se irán realmente tienen la intención de irse, evitando gastos innecesarios.
•	Efectividad en situaciones de clases desbalanceadas: Dado que en la mayoría de los casos de churn (abandono) existe un desbalance de clases, con muchos más clientes que se quedan comparado con los que se van, la F1 ayuda a evaluar de manera más justa el rendimiento del modelo.

Explicabilidad del modelo
En la gráfica de SHAP Summary Plot ilustra la importancia de cada característica en un modelo predictivo, usando colores para distinguir entre valores altos (rosa) y bajos (azul). La anchura de cada variable refleja su impacto en la predicción. Características como "Satisfaction Score" y "Online Security" tienen una influencia significativa en el resultado del modelo.
Por otra parte en SHAP Feature Importance Plot muestra las variables más importantes del modelo, ordenadas según su impacto promedio (valor SHAP) en las predicciones. Las variables con mayor influencia son:
1.	Satisfaction Score: Tiene el mayor efecto en el modelo.
2.	Online Security: Importancia moderada.
3.	Contract y Monthly Charge: Tienen menor impacto comparado con las anteriores, pero aún relevantes.
Las demás variables, como Age, Total Charges, y Tenure in Months, contribuyen menos al resultado final del modelo.

Resultados:
El proyecto se enfoca en maximizar la retención de clientes en riesgo de abandonar el servicio, clasificados como en riesgo de abandonar el servicio. 
El objetivo principal es implementar una estrategia que priorice un alto recall, asegurando que la mayoría de los clientes propensos a abandonar sean identificados y reciban intervenciones efectivas, como campañas de retención, ofertas especiales o llamadas de seguimiento personalizadas.
Simultáneamente, se busca mantener una alta precisión en las predicciones para evitar que los recursos de marketing se desperdicien en clientes que no presentan riesgo de abandono. De esta manera, se optimizan los esfuerzos de retención al concentrar los recursos en los clientes que realmente necesitan atención.
Matriz de confusión expresada en dolares.
De acuerdo con un estudio de la Evan Bailyn de First Page Sage, En el sector de telecomunicaciones, el costo promedio de adquisición de clientes (CAC) es de aproximadamente $694 USD.
Bajo este contexto:
True Negative (TN): $3,086,051 (Costo en el que se incurriria por remplazar a estos clientes que se quedan y el modelo predijo correctamente que se quedarán).
False Positive (FP): $38,170 (Costo en el que se incurre para retener a clientes que el modelo predijo que se irían, pero realmente se quedan. Estos son falsos positivos).
False Negative (FN): $153,662 (Costo que no se incurrrio por clientes que el modelo predijo que se quedarían, pero en realidad se van. Son falsos negativos, debido a esta medida no se realiza ninguna acción de retención).
True Positive (TP): $185,992 (Clientes que se irán y el modelo predijo correctamente que se irán).

Clientes mal clasificados como "se quedan" cuando realmente se van:
Estos $153,662 son los más críticos, ya que el modelo no los identificó correctamente como en riesgo de abandonar el servicio. Por lo tanto, no se tomarían medidas para retenerlos, lo que significa que se perderán y necesitarás 153k para reemplazarlos.
Estos valores pueden parecer alarmantes, sin embargo, el modelo identificó correctamente el 93% de los TN y el 95% de los TP, siendo asi que en valores relativos, el modelo permite un uso eficiente de los recursos destinados a la retencion de clientes.

FEATURE IMPORTANCE:
Este gráfico muestra la explicabilidad del modelo utilizando SHAP (SHapley Additive exPlanations) para identificar las características más importantes que influyen en la predicción de un cliente en particular. En este caso, el gráfico está mostrando la contribución de cada característica (feature) a la predicción realizada por el modelo de machine learning.

En nuestro segundo grafico  nos muestra que las características más influyentes que reducen la probabilidad de churn son Online Security, Total Charges, y Contract (contrato a largo plazo). Por otro lado, factores como no haber hecho referidos, tener un servicio de streaming, y el costo mensual aumentan ligeramente la probabilidad de churn, aunque estos impactos son pequeños en comparación con las características más importantes


Proceso de Implementación
Integración en el Sistema de CRM:
El modelo se integrará con el sistema de gestión de relaciones con los clientes (CRM) existente. Esto permitirá que las predicciones de churn se realicen en tiempo real, cada vez que se actualicen los datos del cliente.
 
Segmentación de Clientes:
Se crearán grupos de alto, medio y bajo riesgo, lo que permitirá personalizar las estrategias de retención.

Aquellos clientes con alto churn, tendran ofertas personalizadas, descuentos, o contacto B2B. 
Clientes con un chutm medio recibirán comunicaciones que incentiven su lealtad, como programas de fidelización o recordatorios de beneficios.
 
Feedback y Monitoreo:
 (KPI)
 Satisfacción del cliente
 Net promote score NPS
 
Rol del Modelo en la Solución
 
   Decisiones Supervisadas por Humanos:
       El modelo generará informes de riesgo de churn, que serán revisados por el equipo de atención al cliente y marketing. 
       
Las decisiones finales sobre las acciones a tomar estarán basadas en las predicciones del modelo, pero también en el juicio y la experiencia del personal.
 
   Automatización de Acciones:
   Respuestas automatizadas, como el envío de correos electrónicos.
 
Alineación con el Rendimiento del Modelo y el Negocio

Evaluación Continua:
Garantizar que las predicciones sean precisas y relevantes. Esto incluirá la reentrenamiento del modelo con datos nuevos y ajustes en las estrategias de retención según los resultados obtenidos.
 
Retorno de Inversión (ROI):
Se calculará el ROI de las acciones de retención basadas en las predicciones del modelo. Esto ayudará a demostrar el valor del modelo para la empresa y a justificar futuras inversiones en mejoras tecnológicas.
 
Alineación Estratégica: 
Aumentar la retención y mejorar la satisfacción del cliente. 
Permitir un crecimiento sostenible a largo plazo.

Limitaciones y autocritica
Falta de variables predictivas relacionadas con factores externos o temporales (Competencia y tedencias), que podrian influir en la variable objetivo.
Falta de datos que expliquen una temporalidad o estacionalidad.
El tamaño del conjunto de datos limita la capacidad del modelo, para aprender patrones generalizables.
La interacción de las variables no fue explorada a fondo.  
