---
keywords: api;api;api de administrador;api de envío;api de informes;api de perfil
description: Busque las API de Adobe [!DNL Target] , incluidas las API de administrador, envío, informes y perfil.
title: ¿Dónde puedo encontrar la documentación de API y SDK [!DNL Target] ?
feature: API/SDK
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Información general sobre la API de Adobe [!DNL Target]

[!DNL Adobe Target] Las API se pueden agrupar según el tipo: API de administrador, envío, informes y perfil.

| Tipo de API | Qué permite hacer | Vínculo de descarga | Otros vínculos útiles |
| --- | --- | --- |--- |
| Administración | Cree, modifique y elimine actividades, audiencias, ofertas y otros objetos (incluidas entidades [!DNL Recommendations], criterios, diseños, etc.). Las API [!DNL Recommendations] son un tipo de API de administrador). | <UL><li>[Recopilación de Postman de la API de administración de Target](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Usar la ](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) API de Recommendations en los Tutorials de  *Adobe Target* |
| Entrega | Recupere contenido optimizado y personalizado de [!DNL Target] para su envío a un usuario final. | [Recopilación de Postman de la API de envío de Target](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Creación de informes | Exportar resultados de actividad y otros resultados de informes. | Las API de informes se incluyen en la [API de administración de Target en la colección Postman](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Perfil | Recupere y modifique perfiles de usuario almacenados en Adobe Target. | [Recopilación Postman de la API del perfil de Target](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Existen distinciones importantes entre las [!DNL Target] API de administración (incluidas las [!DNL Recommendations] API) y las [!DNL Target] API de envío:
>
>* Las API de administración permiten configurar varios aspectos de [!DNL Target] que también puede configurar en la interfaz de usuario de [!DNL Target]. Las API de administración requieren autenticación.
   >
   >
* Las API de envío permiten recuperar contenido. Las API de envío no requieren autenticación.
>
>
Para utilizar [!DNL Target] API de administración, primero debe configurar la autenticación mediante Adobe I/O. Para obtener más información, consulte [Configuración de autenticación](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) en *Tutorials de Adobe Target*.
