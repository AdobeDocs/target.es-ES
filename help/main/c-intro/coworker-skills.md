---
keywords: Adobe Target;Compañero de trabajo;IA;habilidades;experimentación;Recommendations
title: Aptitudes de compañero para Adobe Target
description: Obtenga información acerca de las habilidades de Coworker disponibles para Adobe Target, como la detección de actividades, la creación de pruebas, el análisis, la composición de audiencias y la resolución de problemas de Recommendations.
feature: Overview
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: 4b90f47050b63c7e1e6ac5019d45a7b99b3a33b8
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%
---

# Aptitudes de compañero para Adobe Target {#coworker-skills}

>[!BEGINSHADEBOX]

**En esta página:** Descubra las habilidades de Coworker disponibles para Adobe Target, incluidas las habilidades para explorar actividades y audiencias, crear y configurar pruebas, analizar el rendimiento, componer audiencias y administrar Recommendations.

>[!ENDSHADEBOX]

Las habilidades de los compañeros ayudan a los profesionales de Adobe Target a utilizar el lenguaje natural para explorar sus programas de pruebas y personalización, crear y configurar actividades, analizar resultados y resolver problemas de entrega. Describa lo que desea hacer en Coworker Chat y, a continuación, revise las recomendaciones, la configuración o el análisis devueltos antes de tomar medidas.

[!DNL Adobe Target] herramientas MCP y Coworker están documentadas por separado y proporcionan diferentes capacidades:

* [Target MCP](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md) documenta las herramientas individuales expuestas por el servidor MCP directo, incluidos los tipos de actividades, parámetros, permisos y ámbito de lectura y escritura admitidos.
* [Coworker](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/overview#target-activities-and-audiences) proporciona una capa de orquestación en lenguaje natural independiente que puede combinar capacidades y aplicar flujos de trabajo adicionales.

La siguiente tabla es una comparación de alto nivel de las capacidades relacionadas.

| Función | MCP de Target | Coworker |
| --- | --- | --- |
| Enumerar la ejecución de experimentos, audiencias, ofertas o elementos modificados recientemente | Sí | Sí |
| Crear una actividad de Automated Personalization | No | No |
| Crear una audiencia de Target | Sí | Sí |
| Crear una actividad de VEC de Target, una actividad de segmentación de experiencias o una prueba A/B | Sí | Sí |
| Crear una actividad de Recommendations de Target | Sí | Sí |
| Creación de una oferta HTML o JSON en Target | Sí | Sí |
| Uso de un fragmento de contenido de AEM en una actividad de Target | No | Sí |
| Recomendar qué funciona y qué probar a continuación | Sin consejos o consejos genéricos | Sí |


## Complemento de Target

Las siguientes habilidades están disponibles en el complemento **Target**:

* **Examen de destino**

  Proporciona detección, inspección y recuento de solo lectura de entidades de Target, incluidas actividades, audiencias, ofertas y configuración relacionada.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;Enumerar mis actividades activas&quot;.
* &quot;¿Cuántas actividades se están ejecutando actualmente?&quot;
* &quot;Mostrarme las audiencias y ofertas utilizadas por esta actividad.&quot;

>[!ENDSHADEBOX]

* **Veredicto de actividad de destino**

  Determina si una actividad está lista para enviarse, si debe esperar más datos, si debe detenerse o si necesita una corrección, mediante cálculos de relevancia y comprobaciones de configuración.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;¿Debo enviar esta prueba?&quot;
* &quot;¿Está lista esta actividad para detenerse?&quot;
* &quot;¿Tiene problemas la configuración de actividad actual?&quot;

>[!ENDSHADEBOX]

* **Diseño de destino**

  Crea y configura actividades y ofertas, genera direcciones URL de control de calidad y crea u optimiza el contenido de las ofertas.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;Crear una prueba A/B para la página principal&quot;.
* &quot;Cree una oferta para la experiencia del visitante que regresa&quot;.
* &quot;Genere una URL de control de calidad para esta actividad&quot;.

>[!ENDSHADEBOX]

* **VEC de Target**

  Crea y edita actividades del Compositor de experiencias visuales y sus audiencias de envío de páginas.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;Crear una prueba A/B de VEC para la página principal&quot;.
* &quot;Editar el titular a pantalla completa en mi actividad VEC&quot;.
* &quot;Crear una audiencia de envío de página para esta actividad del VEC&quot;.

>[!ENDSHADEBOX]

* **Configuración de destino**

  Las guías completan la creación de actividades A/B, de segmentación de experiencias o del Compositor de experiencias visuales, incluidos los requisitos previos, la programación, el control de calidad y la activación.

>[!BEGINSHADEBOX]

    *Mensajes de ejemplo:*
    
    * &quot;Ayúdame a crear mi primera prueba.&quot;
    * &quot;¿Qué necesito antes de crear una actividad de segmentación de experiencias?&quot;
    * &quot;Guíame en la programación, el control de calidad y la activación de esta actividad.&quot;

>[!ENDSHADEBOX]

* **Inteligencia de destino**

  Auditorías Programa Target para detectar riesgos, colisiones, configuraciones erróneas, problemas de higiene y ventajas rápidas.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;Auditar mis actividades de Target&quot;.
* &quot;Encuentre conflictos o riesgos de configuración en todas mis actividades&quot;.
* &quot;¿Qué ventajas rápidas pueden mejorar la higiene de mi programa Target?&quot;

>[!ENDSHADEBOX]

* **Estratega de Target**

  Analiza los datos históricos de Target para detectar patrones ganadores y recomienda pruebas futuras.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;¿Qué debería probar a continuación según los resultados anteriores?&quot;
* &quot;¿Qué patrones aparecen en mis pruebas de mayor rendimiento?&quot;
* &quot;Recomiende una prueba de seguimiento basada en los resultados de esta actividad&quot;.

>[!ENDSHADEBOX]

* **Calculadora de prueba de destino**

  Planea el tamaño de muestra A/B/n, la duración y el alza detectable para las métricas de conversión e ingresos, con corrección de Bonferroni para comparaciones múltiples.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;¿Qué tamaño de muestra necesito?&quot;
* &quot;¿Durante cuánto tiempo debo ejecutar esta prueba A/B para detectar un alza del 5 %?&quot;
* &quot;¿Qué alza detectable puedo medir con este tráfico?&quot;

>[!ENDSHADEBOX]

* **Informe de Portfolio de destino**

  Proporciona resúmenes de rendimiento de solo lectura para todo el programa y análisis de tendencias e impulso de la actividad.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;¿Cuáles son mis mejores y peores pruebas?&quot;
* &quot;Mostrarme las tendencias de rendimiento en todas mis actividades&quot;.
* &quot;¿Qué actividades han ganado o perdido impulso recientemente?&quot;

>[!ENDSHADEBOX]

* **Compositor de audiencias de destino**

  Crea o edita audiencias nativas de Target a partir de descripciones en lenguaje natural o reglas explícitas.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;Cree una audiencia para los visitantes móviles que regresan&quot;.
* &quot;Edite esta audiencia para incluir visitantes de búsquedas orgánicas&quot;.
* &quot;Cree una audiencia de Target para los visitantes que vieron la página de precios&quot;.

>[!ENDSHADEBOX]

* **Recomendaciones de Target**

  Administra y trabaja con actividades y configuraciones de Recommendations de Target.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;Crear una actividad de Recommendations&quot;.
* &quot;Mostrarme las actividades y configuraciones de Recommendations&quot;.
* &quot;Actualice la configuración de esta actividad de Recommendations.&quot;

>[!ENDSHADEBOX]

* **Diagnóstico de recomendaciones de Target**

  Diagnostica problemas de entrega, configuración, catálogo y fuente de Recommendations.

>[!BEGINSHADEBOX]

*Mensajes de ejemplo:*

* &quot;¿Por qué no aparecen mis recomendaciones?&quot;
* &quot;Diagnostique la configuración de fuentes y catálogos para esta actividad de Recommendations.&quot;
* &quot;¿Los problemas de entrega o configuración afectan a mis recomendaciones?&quot;

>[!ENDSHADEBOX]
