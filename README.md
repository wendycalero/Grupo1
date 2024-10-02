Presentacion Oral Churn:


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