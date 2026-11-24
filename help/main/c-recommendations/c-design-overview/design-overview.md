---
keywords: diseño de recomendaciones;plantilla;crear diseño;entrega;resultado
description: Aprenda a utilizar diseños en Adobe [!DNL Target] Recommendations para definir cómo aparecerán las recomendaciones en una página (1X4, 1X6, 2X2, etc.).
title: Introducción a los diseños
feature: Recommendations
exl-id: 348b1d77-49c9-4a6b-ba85-7ba051713d5b
TQID: 'https://experienceleague.adobe.com/08jboJLkp6MhgXiISjkVzh2kVze5DRrxO8BbQBFLeA4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%
---
# Introducción a los diseños {#design-overview}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo los diseños definen el diseño y el formato de las recomendaciones en [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Los diseños de [!DNL Adobe Target Recommendations] definen cómo aparecen las recomendaciones en una página. Un diseño define el diseño y el formato de las recomendaciones.

[!DNL Recommendations] viene con varios diseños predeterminados (pregenerados), y también se pueden crear diseños personalizados. Para obtener más información, consulte [Crear un diseño](/help/main/c-recommendations/c-design-overview/create-design.md).

[!DNL Target] puede proporcionar el aspecto completo de las recomendaciones, tal como se muestra en la siguiente ilustración. El diseño puede incluir HTML, JavaScript y CSS. Este diseño se denomina diseño 4 x 1: cuatro espacios en una fila.

![Ejemplo de un diseño de 4 x 1 titulado &quot;Otras actividades divertidas&quot;, con cuatro artículos que muestran una foto, un nombre, un precio, una calificación y una distancia](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

[!DNL Target] también puede enviar las recomendaciones como objetos JSON que se pueden usar en mensajes de correo electrónico, dispositivos IoT (Internet de las cosas), consola o casos de uso de voz (Amazon Alexa o Google Home).

Los diseños determinan:

* Cuántos artículos se muestran en una recomendación
* Cómo se muestran los elementos (en una fila, columna, cuadrícula o tabla)
* Indica si los visitantes solo ven el número de elementos especificado o si pueden desplazarse por varios elementos
