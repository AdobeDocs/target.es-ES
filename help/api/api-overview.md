---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Información sobre las API de Adobe Target, incluidas las API de administración, Envío, Sistema de informes y Perfil.
title: Información general sobre la API de Adobe Target
feature: APIs/SDKs
translation-type: tm+mt
source-git-commit: 9b57d5554884b06d278c3baef3b2c1d5f37bdeb5
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---


# Información general sobre la API de Adobe Target

[!DNL Adobe Target] Las API se pueden agrupar según el tipo.

| Tipo de API | Lo que le permite hacer | Vínculo de descarga | Otros vínculos útiles |
| --- | --- | --- |--- |
| Administración | Cree, modifique y elimine actividades, audiencias, ofertas y otros objetos (incluidas las entidades [!DNL Recommendations], criterios, diseños, etc.). Las API [!DNL Recommendations] son un tipo de API de administración). | <UL><li>[API de administración de destinatario Colección Postman](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Uso de Recommendations ](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) API en Tutorials  *Adobe Target* |
| Entrega | Recupere contenido optimizado y personalizado de [!DNL Target] para envío a un usuario final. | [API de destinatario Envío Colección Postman](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Creación de informes | Exportar resultados de actividad y otros resultados de sistema de informes. | Las API de sistema de informes se incluyen en la [colección Postman de la API de administración de Destinatario](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Perfil | Recuperar y modificar perfiles de usuario almacenados en Adobe Target. | [API de destinatario Perfil Colección Postman](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Existen importantes distinciones entre las [!DNL Target] API de administración (incluidas las [!DNL Recommendations] API) y las [!DNL Target] API de Envío:
>
>* Las API de administración permiten configurar varios aspectos de [!DNL Target] que también se pueden configurar en la [!DNL Target] interfaz de usuario. Las API de administración requieren autenticación.
   >
   >
* Las API de envío permiten recuperar contenido. Las API de envío no requieren autenticación.
>
>
Para utilizar [!DNL Target] API de administración, primero debe configurar la autenticación mediante Adobe I/O. Para obtener más información, consulte [Configurar autenticación](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) en *Tutorials de Adobe Target*.
