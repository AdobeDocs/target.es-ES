---
description: Elimine las cookies del navegador de Target para poder validar todas las experiencias.
title: Eliminar la cookie de Adobe Target
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: 79bcd452a9faa0883272d2e686efd7c4ddfa34a2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%

---


# Eliminar la cookie de Target{#delete-the-target-cookie}

Puede eliminar la cookie [!DNL Target] del explorador (mbox) para poder validar todas las experiencias durante la prueba.

If there is no [!DNL Target] cookie (mbox), you are considered a new visitor and shown a new experience. There are several ways to delete your [!DNL Target] cookies without deleting all of your browser cookies.

>[!NOTE]
>
>Las siguientes instrucciones son correctas para los exploradores y las versiones que aparecen en la lista. Busque en Internet instrucciones para su navegador o versión específicos.

## Eliminar la cookie de Destinatario de Google Chrome

Versión 84.0.4147.105

1. Haga clic en el menú **Chrome** > **Preferencias**.
1. Haga clic en la ficha **Privacidad y seguridad** .
1. Haga clic en **Cookies y otros datos** del sitio.
1. Haga clic en **Ver todas las cookies y los datos** del sitio.
1. Expanda la `adobe.com` sección, seleccione la cookie de **mbox** y, a continuación, haga clic en el icono Eliminar (X).

## Eliminar la cookie de Destinatario de Mozilla Firefox

Versión 79.0

1. Haga clic en el menú **Firefox** > **Preferencias**.
1. Haga clic en la ficha **Privacidad y seguridad** .
1. En **Cookies y Datos** del sitio, haga clic en **Administrar datos**.
1. Seleccione el `adobe.com` sitio y haga clic en **Eliminar selección**.

   >[!NOTE]
   >
   >Esto elimina todas las cookies asociadas con el `adobe.com` sitio. Si desea eliminar o editar las cookies individuales de un sitio, puede hacerlo en el inspector de [almacenamientos de las herramientas](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector)para desarrolladores. La cookie específica que debe eliminar se denomina &quot;mbox&quot;.

## Eliminar la cookie de Destinatario de Microsoft Edge

Versión 84.0.522.52

1. Haga clic en el menú **Microsoft Edge** > **Preferencias**.
1. Click the **Site Permissions** tab.
1. Haga clic en **Cookies y datos** del sitio.
1. Haga clic en **Ver todas las cookies y los datos** del sitio.
1. Expanda la `adobe.com` sección, seleccione la cookie de **mbox** y, a continuación, haga clic en el icono Eliminar (X).

## Eliminar la cookie de Destinatario de Apple Safari

Versión 13.1.2

1. Haga clic en el menú **Safari** > **Preferencias**.
1. Click the **Privacy** tab.
1. Haga clic en **Administrar datos** del sitio web.
1. Seleccione los sitios para las cookies que desee eliminar y haga clic en **Eliminar**.

>[!NOTE]
>
>Esto elimina todas las cookies asociadas con el `adobe.com` sitio. Si desea eliminar una cookie individual para un sitio, siga las instrucciones a continuación:

1. Haga clic en el menú **Safari** > **Preferencias**.
1. Click the **Advanced** tab.
1. Seleccione el menú **Mostrar desarrollo en la opción de la barra** de menús.
1. Vaya a la página web que contiene la cookie que desea eliminar.
1. Haga clic en el menú **Desarrollar** > **Mostrar inspector** web.
1. Click the **Storage** tab.
1. Expanda la sección **Cookies** y haga clic en `www.adobe.com`.
1. Haga clic con el botón secundario en la cookie de **mbox** y, a continuación, haga clic en **Eliminar**.