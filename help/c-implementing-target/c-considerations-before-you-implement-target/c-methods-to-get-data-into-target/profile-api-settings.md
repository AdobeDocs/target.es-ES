---
keywords: implementación;api;perfil;configuración de la API de perfil
description: Habilite o deshabilite la autenticación para actualizaciones en lote mediante API y genere un token de autenticación de perfil.
title: Configuración de la API de perfil
subtopic: Primeros pasos
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Configuración de la API de perfil{#profile-api-settings}

Habilite o deshabilite la autenticación para actualizaciones en lote mediante API y genere un token de autenticación de perfil.

Adobe Target crea y mantiene un perfil para cada usuario individual. Este perfil se almacena en el clúster perimetral de Target y se actualiza en tiempo real después de cada visita, aunque puede actualizar un perfil de forma individual o por lotes mediante API.

Como seguridad adicional, puede requerir que la llamada a la API de actualización por lotes solicite que se pase un token de acceso válido en el encabezado de la solicitud. Los usuarios con permisos de aprobador pueden generar y habilitar tokens de autenticación de la API del perfil.

**Para requerir autenticación y generar un token de acceso mediante la interfaz de usuario de Target:**

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]**.
1. En **[!UICONTROL Configuración de la API del perfil]**, utilice la lista desplegable **Requerir autenticación]para habilitar o deshabilitar los requisitos de autenticación.[!UICONTROL **

   ![](assets/profile_api_settings.png)

1. (Condicional) Si ha habilitado los requisitos de autenticación, haga clic en **[!UICONTROL Generar token de autenticación de perfil]**.

   ![](assets/profile_api_settings_2.png)

   El token caduca de acuerdo con los tiempos indicados en el cuadro [!UICONTROL Caduca en].

   >[!NOTE]
   >
   >También puede generar un token de autentificación de perfil mediante API. Para obtener más información, consulte [Perfiles](https://developers.adobetarget.com/api/#profiles) en el [sitio web de desarrolladores de Adobe Target](https://developers.adobetarget.com/).

1. Copie el token e inclúyalo en el encabezado de la solicitud con el formato: “Autorización” : “Portador ”

Haga clic en [!UICONTROL Regenerar token de autenticación del perfil] para volver a generar el token si lo necesita.

>[!IMPORTANT]
>
>Restablecer este token provoca que las llamadas a API realizadas con el token actual resulten fallidas. Deberá actualizar cualquier script o aplicación que utilice este token.

