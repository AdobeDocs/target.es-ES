---
keywords: recomendaciones;actividad de recomendaciones;criterios;algoritmo;clave de recomendación;clave personalizada;sector comercial;minorista;comercio electrónico;generación de posibles clientes;b2b;servicios financieros;medios;publicación
description: Aprenda a utilizar criterios en Adobe [!DNL Target] [!DNL Recommendations].
title: ¿Cómo se usan los criterios en  [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 657
ht-degree: 7%

---

# [!UICONTROL Criterios]

Los [!UICONTROL criterios] de [!DNL Adobe Target] [!DNL Recommendations] son reglas que determinan qué productos o contenido se recomiendan en función de un conjunto predeterminado de comportamientos del visitante. Los criterios se pueden basar en tendencias populares, los comportamientos actuales y pasados de un visitante o productos y contenido similares. Puede probar distintos tipos de recomendaciones entre sí si se agregan varios criterios.

En las secciones siguientes se explica más información sobre las claves de criterios y la lógica de recomendación que puede utilizar para cada clave. Haga clic en los vínculos para obtener información más detallada.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Al crear un criterio, puede seleccionar un sector vertical en función de los objetivos de su actividad de recomendaciones.

| Sector | Objetivo |
|--- |--- |
| [!UICONTROL Venta minorista/Comercio electrónico] | Conversión que termina en compra |
| [!UICONTROL Generación de clientes potenciales/B2B/Servicios financieros] | Conversión sin compra |
| [!UICONTROL Medios/Publicación] | Participación |

Otras opciones de criterios cambian según el sector que seleccione. Puede establecer el sector predeterminado en vertical en la página **[!UICONTROL Administración] > [!UICONTROL Recomendaciones]** o especificar el sector vertical para cada criterio.

## Tipo de algoritmo {#section_885B3BB1B43048A88A8926F6B76FC482}

El tipo de algoritmo que seleccione determina los algoritmos disponibles.

En la tabla siguiente se explican los distintos tipos de algoritmos y los algoritmos que los acompañan.

| Tipo de algoritmo | Cuándo usar | Algoritmos disponibles |
| --- | --- | --- |
| [!UICONTROL Basado en el carro de compras] | Haga recomendaciones basadas en el contenido del carro de compras del usuario. | <ul><li>[!UICONTROL Las Personas Que Vieron Esto, También Vieron]</li><li>[!UICONTROL Otras Personas Que Vieron Esto, También Compraron]</li><li>[!UICONTROL Otras Personas Que Compraron Esto, También Compraron]</li></ul>Para obtener más información, consulte [Basado en el carro de compras](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) en *Basar la recomendación en una clave de recomendación*. |
| [!UICONTROL Basado en popularidad] | Haga recomendaciones basadas en la popularidad general de un elemento en el sitio o en la popularidad de elementos dentro de la categoría, marca, género, etc. favoritos o más vistos de un usuario. | <ul><li>[!UICONTROL Más visitados en todo el sitio]</li><li>[!UICONTROL Más visitados por categoría]</li><li>[!UICONTROL Más visitados por atributo de artículo]</li><li>[!UICONTROL Principales vendedores en todo el sitio]</li><li>[!UICONTROL Principales vendedores por categoría]</li><li>[!UICONTROL Principales vendedores por atributo de artículo]</li><li>[!UICONTROL Métrica superior por Analytics]</li></ul> |
| [!UICONTROL Basado en elementos] | Haga recomendaciones basadas en la búsqueda de artículos similares a los que el usuario está viendo en este momento o ha visto recientemente. | <ul><li>[!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]</li><li>[!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]</li><li>[!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]</li><li>[!UICONTROL Elementos con atributos similares]</li></ul> |
| [!UICONTROL Basado en usuario] | Haga recomendaciones basadas en el comportamiento del usuario. | <ul><li>[!UICONTROL Artículos vistos recientemente]</li><li>[!UICONTROL Recomendado para usted]</li></ul> |
| [!UICONTROL Criterios personalizados] | Cree recomendaciones basadas en un archivo personalizado que haya cargado. | <ul><li>Algoritmo personalizado</li></ul> |

Para obtener más información acerca de cada algoritmo, vea [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Uso de una clave de recomendación personalizada {#custom-key}

También puede basar las recomendaciones en el valor de un atributo de perfil personalizado.

>[!NOTE]
>
>Los parámetros de perfil personalizados se pueden pasar a [!DNL Target] mediante JavaScript, API o integraciones. Para obtener más información sobre los atributos de perfil personalizados, consulte [Perfiles de visitantes](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Por ejemplo, supongamos que desea mostrar películas recomendadas basadas en la película que agregó un usuario recientemente a la cola.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**.

1. Rellene la información de la [sección Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección [Algoritmo recomendado](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), seleccione **[!UICONTROL Basado en elementos]** de la lista **[!UICONTROL Tipo de algoritmo]**.

1. Seleccione **[!UICONTROL Las personas que vieron esto, vieron aquello]** de la lista **[!UICONTROL Algoritmo]**.

1. Seleccione su atributo de perfil personalizado de la lista **[!UICONTROL Clave de recomendación]** (por ejemplo, [!UICONTROL Última visualización agregada a la lista de observación]).

## Visualización de información de criterios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Para ver los detalles de los criterios, haga clic en los criterios deseados en la columna [!UICONTROL Nombre].

Las secciones **[!UICONTROL Atributos]** y Detalles le permiten ver información general sobre los criterios seleccionados, como su [!UICONTROL Nombre], [!UICONTROL Descripción], [!UICONTROL Sector vertical], [!UICONTROL Tipos de página], [!UICONTROL Clave de recomendación], [!UICONTROL Lógica de recomendación], [!UICONTROL ID de algoritmo] e información de la última modificación (fecha y quién modificó el algoritmo).

La sección **[!UICONTROL Uso]** le permite ver una lista de actividades que hacen referencia a los criterios seleccionados.

>[!NOTE]
>
>Actualmente, la característica [!UICONTROL Uso del algoritmo] solo es compatible con [!DNL Recommendations] actividades. Esta característica no se admite actualmente para las actividades de [!UICONTROL Prueba A/B], [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Segmentación de experiencias] (XT) que incluyen [recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).
