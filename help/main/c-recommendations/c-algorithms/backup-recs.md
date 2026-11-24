---
keywords: recomendación;copia de seguridad;copia;seguridad
description: Aprenda a utilizar las recomendaciones de copia de seguridad en Adobe [!DNL Target Recommendations].
title: Usar una recomendación de copia de seguridad
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: 'https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 18%
---
# Usar una recomendación de copia de seguridad {#backup-recommendations}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo las recomendaciones de copia de seguridad llenan las ranuras restantes de un diseño en [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Cuando una recomendación no tiene suficientes artículos recomendados para rellenar el diseño, la característica de recomendación de copia de seguridad de [!DNL Adobe Target] muestra los resultados del algoritmo de copia de seguridad en lugar del contenido predeterminado. Sin una recomendación de copia de seguridad, el sistema muestra el contenido predeterminado al usuario.

>[!NOTE]
>
>Para obtener más información, incluida una matriz que explica los resultados de usar las opciones **[!UICONTROL Procesamiento parcial del diseño]** y **[!UICONTROL Mostrar contenido de copia de seguridad]** juntas o por separado, consulte la sección [Contenido de copia de seguridad de Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

La función de recomendación de copia de seguridad siempre utiliza los elementos más vistos del sitio para rellenar las ranuras restantes después de utilizar los datos del algoritmo. Por ejemplo, un diseño está configurado para mostrar cinco elementos recomendados, pero el algoritmo tiene datos suficientes para rellenar solo dos de las cinco ranuras. A continuación, la función de recomendación de copia de seguridad rellena las otras tres ranuras con los artículos más vistos.

Las recomendaciones de copia de seguridad se eligen al azar entre los 500 productos más vistos del sitio. El período de tiempo de los datos para las recomendaciones de copia de seguridad es de una semana.

Los 500 resultados más vistos se ordenan secuencialmente y luego se dividen en bloques de 20. Los contenedores se proporcionan en orden, pero los resultados dentro de cada contenedor se aleatorizan y se devuelven a la página, por lo que los usuarios que actualizan la página reciben resultados nuevos y aleatorios. Si el conjunto de resultados de la unión de la colección y las reglas de filtrado es menor que 20, los elementos se seleccionan aleatoriamente de la colección.

Este proceso de agrupamiento significa que las recomendaciones de respaldo se muestran en el siguiente orden:

1. Los 20 artículos más vistos, aleatorios.
1. Los siguientes 20 artículos más vistos, aleatorios.
1. Los siguientes 20 artículos más vistos, aleatorios, etc.

Sin agrupar, se podría mostrar el artículo 499.º más visto, seguido del artículo 200.º más visto, seguido del artículo 380.º más visto, etc. La agrupación garantiza que primero se recomienden los artículos más vistos.

Si los artículos se agrupan en colecciones, las recomendaciones de copia de seguridad generadas para cada criterio también utilizan la colección, por lo que solo los artículos de la colección se incluyen en la recomendación de copia de seguridad. Cualquier artículo excluido por las reglas de exclusión globales no se presenta como recomendación de copia de seguridad. Los duplicados se eliminan de los lotes de recomendaciones.

Las recomendaciones de copia de seguridad están habilitadas de forma predeterminada y rellenan las ranuras adicionales de un diseño con una selección aleatoria de los elementos más populares del sitio.

El uso de recomendaciones de copia de seguridad suele formar parte de la conversación con el equipo de implementación durante la configuración inicial. Para cambiar la configuración de la recomendación de copia de seguridad después de la implementación, póngase en contacto con el administrador de cuentas.

Cuando **[!UICONTROL Procesamiento parcial del diseño]** (consulte [Contenido de copia de seguridad](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)) no está habilitado y no se puede llenar el diseño, se muestran las recomendaciones de copia de seguridad (cuando están habilitadas) o el contenido predeterminado en su lugar.
