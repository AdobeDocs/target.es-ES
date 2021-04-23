---
keywords: aplicación móvil;sdk de aplicación móvil;aplicación móvil target;sdk de target móvil;sdk de aplicación móvil; habilitar target en sdk
description: Aprenda a añadir el SDK de Adobe Mobile Services a su aplicación móvil.
title: ¿Cómo se habilita [!DNL Target] en el SDK de Adobe Mobile?
feature: Implementar Mobile
role: Developer
exl-id: c34bd50c-e17f-4dfb-8470-8f4c8639ee9f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 79%

---

# Habilitar [!DNL Target] en el SDK

Añada el SDK de Adobe Mobile Services a su aplicación.

1. Si todavía no ha instalado el SDK de Adobe Mobile Services en su aplicación, use las credenciales de Analytics o Experience Cloud y descargue el SDK desde el sitio web de [Adobe Mobile Services](https://mobilemarketing.adobe.com).

1. Añada el SDK de Adobe Mobile Services a su aplicación.

   Encontrará las instrucciones en [Implementación básica y ciclo de vida](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html).

1. Añada código de cliente, tiempo de espera y habilite SSL.

   En Experience Cloud, abra Mobile Services y vaya a **[!UICONTROL Administrar configuración de aplicación]** > **[!UICONTROL Opciones de Target de SDK]**.

   Añada el código de cliente y el tiempo de espera de Target. El código de cliente es exclusivo de la cuenta o compañía. El tiempo de espera es el número de segundos que Target espera la respuesta antes de mostrar el contenido predeterminado. Compruebe que la opción **[!UICONTROL Utilizar HTTPS]** esté marcada en la página Administrar configuración de aplicación de Adobe Mobile Services. Si HTTPS no está habilitado, todas las llamadas que se hagan en iOS9+ se bloquearán a menos que realice la lista de permitidos del servidor de Target.

   ![](assets/mobile-clientcode.png)

1. Cuando haya creado o encontrado la aplicación, busque la configuración de la aplicación y descargue el SDK que quiera.

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> Si no tiene acceso a la interfaz de marketing móvil, puede hacer los cambios directamente en el archivo de configuración en el código de la aplicación, pero no se sincronizarán con la página de configuración de la interfaz de usuario.
