---
keywords: implementation;api;profile;profile api settings;authentication token
description: Habilite o deshabilite la autenticación para actualizaciones por lotes mediante las API de Adobe Target y genere un token de autenticación de perfil.
title: Configuración de la API de perfil en Adobe Target
feature: api
subtopic: Getting Started
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: bd13fee3a0a2ef675d121a9832583c3aa125865d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 40%

---


# Configuración de la API de perfil

Habilite o deshabilite la autenticación para actualizaciones por lotes mediante las API de Adobe Target y genere un token de autenticación de perfil.

[!DNL Adobe Target] crea y mantiene un perfil para cada usuario individual. This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit; however, you can update a profile individually or in bulk via API.

Como seguridad adicional, puede requerir que la llamada a la API de actualización por lotes solicite que se pase un token de acceso válido en el encabezado de la solicitud.

**Para requerir autenticación y generar un token de acceso mediante la interfaz de usuario de Target:**

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.
1. Debajo de **[!UICONTROL Perfil API]** , deslice el conmutador **[!UICONTROL Requerir autenticación]** a la posición habilitada o deshabilitada.

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   El token caduca de acuerdo con los tiempos indicados en el cuadro [!UICONTROL Caduca en].

   Debe tener uno de los siguientes permisos de usuario para generar un autentificador:

   * Al menos [!UICONTROL permiso del editor] (o [!UICONTROL aprobador])

      Para obtener más información sobre [!DNL Target Standard] los clientes, consulte [Especificación de funciones y permisos](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *usuarios*. Para obtener más información sobre [!DNL Target Premium] los clientes, consulte [Configuración de permisos](/help/administrating-target/c-user-management/property-channel/properties-overview.md)de empresa.

   * Función de administrador en el nivel de espacio de trabajo/perfil del producto

      Los espacios de trabajo solo están disponibles para [!DNL Target Premium] los clientes. For more information, see [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Derechos de administrador (permiso de Sysadmin) en el nivel de [!DNL Adobe Target] producto
   >[!NOTE]
   >
   >También puede generar un token de autentificación de perfil mediante API. Para obtener más información, consulte [Perfiles](https://developers.adobetarget.com/api/#profiles) en el [sitio web de desarrolladores de Adobe Target](https://developers.adobetarget.com/).

1. Copie el token e inclúyalo en el encabezado de la solicitud con el formato: “Autorización” : “Portador ”

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>Restablecer este token provoca que las llamadas a API realizadas con el token actual resulten fallidas. Deberá actualizar cualquier script o aplicación que utilice este token.
