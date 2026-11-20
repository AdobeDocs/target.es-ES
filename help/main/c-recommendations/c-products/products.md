---
keywords: producto;colecciones
description: Obtenga información acerca de las entidades en Adobe [!DNL Target] Recommendations. Las entidades hacen referencia a los elementos que desea recomendar mediante [!DNL Target], como artículos, películas o productos.
title: ¿Cómo se utilizan las entidades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: ffe23eea-b914-4c86-ad54-c63c1cc1c0d7
TQID: 'https://experienceleague.adobe.com/zfISb59XJ5qrD1-FA0syglPPswIL8cA0N0pBpY4tgIE'
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
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%
---
# Introducción a las entidades {#get-started-entities}

>[!BEGINSHADEBOX]

**En esta página:** Conozca qué entidades están en [!DNL Adobe Target Recommendations] y dónde administrarlas.

>[!ENDSHADEBOX]

Las entidades son los elementos que [!DNL Recommendations] puede recomendar. Una entidad puede ser un producto, un fragmento de contenido (como un artículo, una presentación de diapositivas, una imagen, una película o un programa de TV), una lista de trabajos, un restaurante, etc.

[!DNL Recommendations] muestra elementos de sus colecciones de acuerdo con los criterios que configuró.

## Cómo llegan las entidades a Recommendations

La información sobre las entidades se puede pasar a [!DNL Recommendations] de varias maneras, entre ellas:

* Con [atributos de entidad](/help/main/c-recommendations/c-products/entity-attributes.md) enviados desde sus páginas, usando un mbox o `targetPageParams`.
* Con [fuentes](/help/main/c-recommendations/c-products/feeds.md), que pueden usar archivos CSV, el formato de fuente [!DNL Google Product Search] o [!DNL Adobe Analytics] clasificaciones de productos.
* Con la API de envío.

Si [!DNL Target] recopila datos de un elemento tanto de una fuente como de un mbox, se utilizarán los datos más recientes.

Las entidades cargadas y los valores de atributos de entidad caducan al cabo de 61 días. Envíe cada elemento de nuevo al menos una vez cada 60 días. De lo contrario, [!DNL Target] considera que el elemento ya no es relevante y lo elimina del catálogo.

## Administrar las entidades

Utilice las siguientes páginas para trabajar con las entidades:

* [Atributos de entidad](/help/main/c-recommendations/c-products/entity-attributes.md) y [Atributos de entidad personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md): defina la información de producto o contenido que pase a [!DNL Recommendations].
* [Fuentes](/help/main/c-recommendations/c-products/feeds.md): obtenga información de contenido o entidad en sus recomendaciones.
* [Búsqueda en el catálogo](/help/main/c-recommendations/c-products/catalog-search.md): Busque elementos en su catálogo.
* [Colecciones](/help/main/c-recommendations/c-products/collections.md): configure sus colecciones. Se selecciona una colección para cada experiencia al crear una actividad [!DNL Recommendations].
* [Exclusiones](/help/main/c-recommendations/c-products/exclusions.md): impide que se muestren determinados elementos en las recomendaciones. Las exclusiones se aplican a todas las actividades de la cuenta.
