---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Información sobre las API de Adobe Target, incluidas las API de administración, Envío, Sistema de informes y Perfil.
title: Información general sobre la API de Adobe Target
topic: APIs
translation-type: tm+mt
source-git-commit: 84cd5d41655baaaadeba63954858730ce956e039
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 2%

---


# Información general sobre la API de Adobe Target

Las API de Adobe Target se pueden agrupar según el tipo.

| Tipo de API | Lo que le permite hacer | Vínculo de descarga | Otros vínculos útiles |
| --- | --- | --- |--- |
| Administración | Cree, modifique y elimine actividades, audiencias, ofertas y otros objetos (incluidas [!DNL Recommendations] entidades, criterios, diseños, etc.). Las [!DNL Recommendations] API son un tipo de API de administración). | <UL><li>[API de administración de destinatario Colección Postman](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Uso de las API](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html) de Recommendations en los Tutorials de *Adobe Target* |
| Entrega | Recupere contenido optimizado y personalizado de [!DNL Target] para envío a un usuario final. | [API de destinatario Envío Colección Postman](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Creación de informes | Exportar resultados de actividad y otros resultados de sistema de informes. | Las API de sistema de informes se incluyen en la colección [de Postman de la API de administración de](https://developers.adobetarget.com/api/#admin-postman-collection)Destinatario. |  |
| Perfil | Recuperar y modificar perfiles de usuario almacenados en Adobe Target. | [API de destinatario Perfil Colección Postman](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Tenga en cuenta la distinción entre las API de **administración** (incluidas [!DNL Recommendations] las API), que le permiten configurar varios aspectos de Adobe Target, en comparación con las API **de** envío, que le permiten recuperar contenido. Las API de administración requieren autenticación, mientras que las API de envío no.
>
>Para utilizar las API de administración de Adobe Target, primero debe configurar la autenticación mediante E/S de Adobe. Para obtener más información, consulte [Configurar autenticación](https://docs.adobe.com/content/help/en/target-learn/tutorials/apis/configure-io-target-integration.html) en Tutorials *de* Adobe Target.
