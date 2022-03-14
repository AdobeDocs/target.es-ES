---
keywords: api;api;api de administrador;api de envío;api de informes;api de perfil
description: Buscar Adobe [!DNL Target] API, incluidas las API de administrador, envío, informes y perfil.
title: Dónde puedo encontrar [!DNL Target] ¿Documentación de API y SDK?
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# Adobe [!DNL Target] Información general de API

[!DNL Adobe Target] Las API se pueden agrupar según el tipo: API de administrador, envío, informes y perfil.

| Tipo de API | Qué permite hacer | Vínculo de descarga | Otros vínculos útiles |
| --- | --- | --- |--- |
| Administración | Crear, modificar y eliminar actividades, audiencias, ofertas y otros objetos (incluidos [!DNL Recommendations] entidades, criterios, diseños, etc. La variable [!DNL Recommendations] Las API son un tipo de API de administración). | <UL><li>[Recopilación de Postman de la API de administración de Target](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Uso de las API de Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) en *Tutorials de Adobe Target* |
| Entrega | Recupere contenido optimizado y personalizado de [!DNL Target] para su envío a un usuario final. | [Recopilación de Postman de la API de envío de Target](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Creación de informes | Exportar resultados de actividad y otros resultados de informes. | Las API de informes se incluyen en el [Recopilación de Postman de la API de administración de Target](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Perfil | Recupere y modifique perfiles de usuario almacenados en Adobe Target. | [Recopilación Postman de la API del perfil de Target](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Hay importantes distinciones entre [!DNL Target] API de administrador (incluido el [!DNL Recommendations] API) y [!DNL Target] API de envío:
>
>* Las API de administración permiten configurar varios aspectos de [!DNL Target] que también puede configurar en la variable [!DNL Target] IU. Las API de administración requieren autenticación.
>
>* Las API de envío permiten recuperar contenido. Las API de envío no requieren autenticación.
>
>Para usar [!DNL Target] API de administrador, primero debe configurar la autenticación mediante Adobe I/O. Para obtener más información, consulte [Configurar la autenticación](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) en *Tutorials de Adobe Target*.
