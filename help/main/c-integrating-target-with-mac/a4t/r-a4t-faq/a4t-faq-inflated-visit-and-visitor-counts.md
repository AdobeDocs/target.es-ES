---
keywords: preguntas frecuentes;faq;analytics para target;a4T;visita;infladas;visitante;hit parcial;huérfano;huérfana
description: Encuentre respuestas a preguntas sobre recuentos inflados de visitas y visitantes al usar Analytics for [!DNL Target] (A4T). Aprenda a minimizar los "datos parciales".
title: ¿Dónde puedo encontrar preguntas frecuentes sobre recuentos inflados de visitas y visitantes con A4T?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 69%
---
# Recuentos inflados de visitas y visitantes: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre los recuentos inflados de visitas y visitantes al usar Analytics como fuente de informes para Target (A4T).

## He observado un pico en las visitas. ¿Cómo sé si estas visitas están causadas por visitas de datos parciales? {#section_28506672C6224ED18AC74F6A02F6F811}

+++Respuesta
Puede ponerse en contacto con el [Servicio de atención al cliente de Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para recuperar un informe de datos parciales. Esta información no se puede obtener directamente desde la interfaz de usuario de [!DNL Analytics].

+++

## ¿Qué puede provocar los hits de datos parciales? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++Respuesta
Los hits de datos parciales suelen deberse a un fallo en la implementación, como una desalineación de ID de grupos de informes. También puede ser por causas legítimas, como páginas lentas, errores de página, ofertas de redireccionamiento en una actividad o versiones de bibliotecas antiguas.

+++

## ¿Hay algún tipo particular de actividades [!DNL Target] con mayor probabilidad de generar visitas de datos parciales? {#section_69837442A9B84366BEFDA4588B31E574}

+++Respuesta
Las ofertas de redireccionamiento envían inmediatamente a un usuario a una página distinta, por lo que la llamada de [!DNL Analytics] no se activa en la primera página.

+++
