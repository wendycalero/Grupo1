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





