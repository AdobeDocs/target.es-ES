---
keywords: cookie;cookies;eliminar cookie;eliminar cookie de target;google chrome;chrome;mozilla firefox;firefox;microsoft edge;safari
description: Obtenga información sobre cómo eliminar su [!DNL Target] cookies del explorador para que pueda validar sus experiencias.
title: ¿Cómo elimino la variable [!DNL Target] ¿Cookie?
feature: Privacy & Security
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 4%

---

# Elimine el [!DNL Target] cookie

Puede eliminar su [!DNL Adobe Target] cookie del explorador (mbox) para que pueda validar todas las experiencias durante las pruebas.

Si no hay [!DNL Target] cookie (mbox), se le considera un visitante nuevo y se le muestra una experiencia nueva. Hay varias formas de eliminar la de mbox sin eliminar las cookies del explorador.

>[!NOTE]
>
>Las siguientes instrucciones son correctas para los exploradores y las versiones que aparecen en la lista. Busque en Internet instrucciones para su navegador o versión específicos.

## Elimine el [!DNL Target] cookie de Google Chrome

Versión 84.0.4147.105

1. Haga clic en el **Chrome** menú > **Preferencias**.
1. Haga clic en el **Privacidad y seguridad** pestaña .
1. Haga clic en **Cookies y otros datos del sitio**.
1. Haga clic en **Ver todas las cookies y los datos del sitio**.
1. Expanda el `adobe.com` seleccione **mbox** y, a continuación, haga clic en el icono eliminar (X).

## Elimine el [!DNL Target] cookie de Mozilla Firefox

Versión 79.0

### Eliminar todas las cookies asociadas con `adobe.com`

1. Haga clic en el **Firefox** menú > **Preferencias**.
1. Haga clic en el **Privacidad y seguridad** pestaña .
1. En **Cookies y datos del sitio**, haga clic en **Administrar datos**.
1. Seleccione el `adobe.com` sitio y, a continuación, haga clic en **Eliminar selección**.

   >[!NOTE]
   >
   >Esto elimina todas las cookies asociadas con la variable `adobe.com` sitio. Si desea eliminar una cookie individual para un sitio, siga las instrucciones que se indican a continuación.

### Eliminar una cookie individual (mbox)

1. En Firefox, haga clic en **Herramientas** > **Desarrollador web** > **Inspector de almacenamiento**.
1. Haga clic en el **Avanzadas** pestaña .
1. Vaya a la página web que contiene la cookie que desea eliminar.
1. Expanda el **Cookies** y, a continuación, haga clic en `https://experience.adobe.com`.
1. Haga clic con el botón derecho en el **mbox** y, a continuación, haga clic en **Eliminar**.

## Elimine el [!DNL Target] cookie de Microsoft Edge

Versión 84.0.522.52

1. Haga clic en el **Microsoft Edge** menú > **Preferencias**.
1. Haga clic en el **Permisos del sitio** pestaña .
1. Haga clic en **Cookies y datos del sitio**.
1. Haga clic en **Ver todas las cookies y los datos del sitio**.
1. Expanda el `adobe.com` seleccione **mbox** y, a continuación, haga clic en el icono eliminar (X).

## Elimine el [!DNL Target] cookie de Apple Safari

Versión 13.1.2

### Eliminar todas las cookies asociadas con `adobe.com`

1. Haga clic en el **Safari** menú > **Preferencias**.
1. Haga clic en el **Privacidad** pestaña .
1. Haga clic en **Administrar datos de sitio web**.
1. Seleccione los sitios para las cookies que desee eliminar y haga clic en **Eliminar**.

   >[!NOTE]
   >
   >Esto elimina todas las cookies asociadas con la variable `adobe.com` sitio. Si desea eliminar una cookie individual para un sitio, siga las instrucciones que se indican a continuación.

### Eliminar una cookie individual (mbox)

1. Haga clic en el **Safari** menú > **Preferencias**.
1. Haga clic en el **Avanzadas** pestaña .
1. Seleccione el **Mostrar menú Desarrollo en la barra de menús** .
1. Vaya a la página web que contiene la cookie que desea eliminar.
1. Haga clic en el **Desarrollo** menú > **Mostrar inspector web**.
1. Haga clic en el **Almacenamiento** pestaña .
1. Expanda el **Cookies** y, a continuación, haga clic en `www.adobe.com`.
1. Haga clic con el botón derecho en el **mbox** y, a continuación, haga clic en **Eliminar**.
