---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Información sobre las API de Adobe Target, incluidas las API de administración, Envío, Sistema de informes y Perfil.
title: Información general sobre la API de Adobe Target
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---


# Información general sobre la API de Adobe Target

[!DNL Adobe Target] Las API se pueden agrupar según el tipo.

| Tipo de API | Lo que le permite hacer | Vínculo de descarga | Otros vínculos útiles |
| --- | --- | --- |--- |
| Administración | Cree, modifique y elimine actividades, audiencias, ofertas y otros objetos (incluidas [!DNL Recommendations] entidades, criterios, diseños, etc.). Las [!DNL Recommendations] API son un tipo de API de administración). | <UL><li>[API de administración de destinatario Colección Postman](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Uso de las API](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) de Recommendations en los Tutorials de *Adobe Target* |
| Entrega | Recupere contenido optimizado y personalizado de [!DNL Target] para envío a un usuario final. | [API de destinatario Envío Colección Postman](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Creación de informes | Exportar resultados de actividad y otros resultados de sistema de informes. | Las API de sistema de informes se incluyen en la colección [de Postman de la API de administración de](https://developers.adobetarget.com/api/#admin-postman-collection)Destinatario. |  |
| Perfil | Recuperar y modificar perfiles de usuario almacenados en Adobe Target. | [API de destinatario Perfil Colección Postman](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Existen importantes distinciones entre las API de [!DNL Target] administración (incluidas las [!DNL Recommendations] API) y las API de [!DNL Target] Envío:
>
>* Las API de administración permiten configurar varios aspectos de [!DNL Target] los que también se pueden configurar en la [!DNL Target] interfaz de usuario. Las API de administración requieren autenticación.
   >
   >
* Las API de envío permiten recuperar contenido. Las API de envío no requieren autenticación.
>
>
Para utilizar las API [!DNL Target] de administración, primero debe configurar la autenticación mediante E/S de Adobe. Para obtener más información, consulte [Configurar autenticación](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) en Tutorials *de* Adobe Target.
