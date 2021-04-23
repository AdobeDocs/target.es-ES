---
keywords: cookie;cookies;eliminar cookie;eliminar cookie de target;google chrome;chrome;mozilla firefox;firefox;microsoft edge;safari
description: Aprenda a eliminar las cookies del explorador [!DNL Target] para poder validar las experiencias.
title: ¿Cómo elimino la cookie [!DNL Target] ?
feature: Privacidad y seguridad
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 4%

---

# Eliminar la cookie [!DNL Target]

Puede eliminar la cookie del explorador [!DNL Adobe Target] (mbox) para poder validar todas las experiencias durante las pruebas.

Si no hay ninguna cookie [!DNL Target] (mbox), se le considerará un visitante nuevo y se le mostrará una experiencia nueva. Hay varias formas de eliminar la de mbox sin eliminar las cookies del explorador.

>[!NOTE]
>
>Las siguientes instrucciones son correctas para los exploradores y las versiones que aparecen en la lista. Busque en Internet instrucciones para su navegador o versión específicos.

## Eliminar la cookie [!DNL Target] de Google Chrome

Versión 84.0.4147.105

1. Haga clic en el menú **Chrome** > **Preferencias**.
1. Haga clic en la pestaña **Privacy and Security**.
1. Haga clic en **Cookies y otros datos del sitio**.
1. Haga clic en **Ver todas las cookies y datos del sitio**.
1. Expanda la sección `adobe.com` , seleccione la cookie **mbox** y haga clic en el icono de eliminación (X).

## Eliminar la cookie [!DNL Target] de Mozilla Firefox

Versión 79.0

### Eliminar todas las cookies asociadas con `adobe.com`

1. Haga clic en el menú **Firefox** > **Preferencias**.
1. Haga clic en la pestaña **Privacy and Security**.
1. En **Cookies y datos del sitio**, haga clic en **Administrar datos**.
1. Seleccione el sitio `adobe.com` y haga clic en **Quitar selección**.

   >[!NOTE]
   >
   >Esto elimina todas las cookies asociadas con el sitio `adobe.com`. Si desea eliminar una cookie individual para un sitio, siga las instrucciones que se indican a continuación.

### Eliminar una cookie individual (mbox)

1. En Firefox, haga clic en **Herramientas** > **Desarrollador web** > **Inspector de almacenamiento**.
1. Haga clic en la pestaña **Advanced**.
1. Vaya a la página web que contiene la cookie que desea eliminar.
1. Expanda la sección **Cookies** y haga clic en `https://experience.adobe.com`.
1. Haga clic con el botón derecho en la cookie **mbox** y, a continuación, haga clic en **Eliminar**.

## Eliminar la cookie [!DNL Target] de Microsoft Edge

Versión 84.0.522.52

1. Haga clic en el menú **Microsoft Edge** > **Preferencias**.
1. Haga clic en la pestaña **Permisos del sitio**.
1. Haga clic en **Cookies y datos del sitio**.
1. Haga clic en **Ver todas las cookies y datos del sitio**.
1. Expanda la sección `adobe.com` , seleccione la cookie **mbox** y haga clic en el icono de eliminación (X).

## Eliminar la cookie [!DNL Target] de Apple Safari

Versión 13.1.2

### Eliminar todas las cookies asociadas con `adobe.com`

1. Haga clic en el menú **Safari** > **Preferencias**.
1. Haga clic en la pestaña **Privacy**.
1. Haga clic en **Administrar datos del sitio web**.
1. Seleccione los sitios para las cookies que desea eliminar y haga clic en **Quitar**.

   >[!NOTE]
   >
   >Esto elimina todas las cookies asociadas con el sitio `adobe.com`. Si desea eliminar una cookie individual para un sitio, siga las instrucciones que se indican a continuación.

### Eliminar una cookie individual (mbox)

1. Haga clic en el menú **Safari** > **Preferencias**.
1. Haga clic en la pestaña **Advanced**.
1. Seleccione la opción **Mostrar menú Desarrollo en la barra de menús**.
1. Vaya a la página web que contiene la cookie que desea eliminar.
1. Haga clic en el menú **Desarrollo** > **Mostrar inspector web**.
1. Haga clic en la pestaña **Storage**.
1. Expanda la sección **Cookies** y haga clic en `www.adobe.com`.
1. Haga clic con el botón derecho en la cookie **mbox** y, a continuación, haga clic en **Eliminar**.
