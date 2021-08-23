---
keywords: api;adobe i/o
description: Obtenga información sobre cómo realizar la transición de las API heredadas de Adobe [!DNL Target] Classic a las nuevas API en Adobe I/O.
title: ¿Cómo puedo pasar de las API heredadas a la Adobe I/O?
feature: Implementación del lado del servidor
role: Developer
exl-id: 4b4274a9-b91a-4a79-9b40-8b1909a2d1d1
source-git-commit: f509fca07305d72cfc3ffd99d0e9a21b19dc6521
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 82%

---

# Transición de las API heredadas de [!DNL Target] a Adobe I/O

Información para ayudarle a pasar de las API heredadas de Target a las nuevas API de Adobe I/O.

Con la retirada de Adobe Target Classic, las API conectadas a su cuenta de Target Classic también han dejado de estar disponibles. Este documento le ayudará en la transición de las integraciones basadas en API heredadas a las API de Target con tecnología Adobe I/O.

Para obtener más información sobre la documentación de la API de Target, consulte   [API de Target y SDK de NodeJS](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md#concept_5718EC1FF2ED4436935D0BCCD7AA29A6).

## Terminología   {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| Término | Descripción |
|--- |--- |
| API heredadas | Las API vinculadas a su cuenta de Target Classic. Estas llamadas a API se basan en una autenticación mediante nombre de usuario y contraseña, y utilizan el nombre de host `testandtarget.omniture.com`. Si sus llamadas a API incluyen en la URL de solicitud un nombre de usuario y una contraseña, debe pasarse a las API de Adobe I/O. |
| Adobe I/O | Adobe I/O es el nuevo portal para las API de Target. Estas API están conectadas a su cuenta de Target Standard/Premium. Las API de Target en Adobe I/O utilizan autenticación JWT, el estándar del sector para API empresariales seguras. |

## Cronología   {#section_A478EBF637554A2DB5A31661955121ED}

Las API heredadas se retirarán del mercado al mismo tiempo que Target Classic:

| Fecha | Detalles |
|--- |--- |
| 17 de octubre de 2017 | Se han retirado todos los métodos API que realizan una operación de escritura (`saveCampaign`, `copyCampaign`, `saveHTMLOfferContent` y `setCampaignState`).<br>La fecha es la misma en la que todas las cuentas de usuario de Target Classic quedaron en estado de solo lectura. |
| 14 de noviembre de 2017 | Se han retirado las API restantes. Esta es la fecha en que se retiró la interfaz de usuario de Target Classic. |

Las API de Recommendations Classic no se ven afectadas por este cronograma.

## Métodos equivalentes   {#section_DDB42CCC172545B09CB728D794CC466B}

La siguiente tabla muestra la correspondencia entre los nuevos métodos de API de Target y los métodos de API heredadas. Las nuevas API devuelven JSON, en comparación con la respuesta XML de las API heredadas.

Los nuevos métodos API contienen vínculos a la sección correspondiente en el sitio de documentación de las API. Se proporciona un ejemplo para cada método API. También puede utilizar la colección Admin Postman, que contiene ejemplos de llamadas a API para todos los nuevos métodos API de Adobe en Adobe I/O.

| Grupo | Método de las API heredadas | Método de las nuevas API | Notas |
|--- |--- |--- |--- |
| Campaña/Actividad | Creación de campaña | [Crear actividad AB](https://developers.adobetarget.com/api/#create-ab-activity)<br>[Crear actividad XT](https://developers.adobetarget.com/api/#create-xt-activity) | Las nuevas API proporcionan métodos de creación distintos para AB y XT |
|  | Actualización de campaña | [Actualizar actividad AB](https://developers.adobetarget.com/api/#update-ab-activity)<br>[Actualizar actividad XT](https://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | Copiar campaña | N/A | Se usan las API de creación de actividad |
|  | Lista de campañas | [Listar actividades](https://developers.adobetarget.com/api/#list-activities) |  |
|  | Estado de la campaña | [Actualizar el estado de la actividad](https://developers.adobetarget.com/api/#update-activity-state) |  |
|  | Vista de la campaña | [Obtener actividad AB por ID](https://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[Obtener actividad XT por ID](https://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | ID de campaña de terceros | N/D | Si utiliza un thirdpartyID, pueden usarse los métodos de actividad relevantes |
| Ofertas | Creación de oferta | [Crear oferta](https://developers.adobetarget.com/api/#create-offer) |  |
|  | Obtención de oferta | [Obtener oferta por ID](https://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | Lista de ofertas | [Listar ofertas](https://developers.adobetarget.com/api/#list-offers) |  |
|  | Lista de carpetas | N/D | Las carpetas no son compatibles con Target Standard/Premium |
| Creación de informes | Informe de rendimiento de la campaña | [Obtener informe de rendimiento AB](https://developers.adobetarget.com/api/#get-ab-performance-report)<br>[Obtener informe de rendimiento XT](https://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | Informe de auditoría | [Obtener informe de auditoría](https://developers.adobetarget.com/api/#get-audit-report) |  |
|  | Informe de contenido 1-1 | [Obtener informe de rendimiento AP](https://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| Configuración de la cuenta | Obtener grupos de hosts | [Listar entornos](https://developers.adobetarget.com/api/#list-environments) |  |

## Excepciones {#section_09CF9A0E289149279783B4801D1B6D4C}

Si necesita una excepción, póngase en contacto con el gestor de éxito de los clientes.

## Ayuda   {#section_591F850E2B7A4342B1C233693425415C}

Póngase en contacto con ClientCare de Adobe Target (tt-support@adobe.com) si tiene cualquier pregunta o necesita ayuda en la transición a las nuevas API de Target en Adobe I/O.
