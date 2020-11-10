---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library
description: Target Standard se puede integrar con Adobe Dynamic Media Classic para proporcionar administración de recursos digitales (DAM) en la biblioteca de contenido.
title: Integración de la configuración de la integración de Dynamic Media Classic
feature: administration general
translation-type: tm+mt
source-git-commit: 76ab5aef33f5e9c5de08b33e83e459b588bb0fba
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 28%

---


# Configuración de Scene7 {#scene-settings}

[!DNL Target] se puede integrar con [!DNL Adobe Dynamic Media Classic] para proporcionar administración de recursos digitales (DAM) en la biblioteca [!UICONTROL de]contenido.

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials.

>[!NOTE]
>
>Ya no se admite una cuenta gratuita [!DNL Dynamic Media Classic] de uso restringido para [!DNL Adobe Target] nuevos clientes o usuarios. Las credenciales de inicio de sesión existentes funcionan como de costumbre.

If this setting is not configured, the [!UICONTROL Swap Image offer] option within the activity creation workflow is not available. Después de definir esta configuración, la opción de intercambiar/cambiar las ofertas de imágenes está disponible tanto en el  [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). You can then leverage image offers with images that have been uploaded from the [!DNL Adobe Experience Cloud] for use in [!DNL Target] activities.

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. There is no way to obtain the published URL of an image uploaded into the [!DNL Experience Cloud] to consume directly or outside of targeting workflows using [!DNL Target]. Esta funcionalidad no está permitida según el contrato.

Note that the storage URL and the final publish URLs of images from [!DNL Dynamic Media] are different and one must *NOT* create offers using the storage link of images as delivery will not work in such cases. Debe utilizar la función de ofertas de imagen como se explica en nuestra documentación de ayuda.

To integrate with [!DNL Dynamic Media Classic] ([!DNL Scene7]), you need to specify the following information.

1. Haga clic en **[!UICONTROL Administración]** > Configuración **[!UICONTROL de]** Scene7.

   ![Página de Scene7](/help/administrating-target/assets/scene7.png)

1. Specify the following [!DNL Dynamic Media Classic] account information:

   **Región:**[!DNL Dynamic Media] La región de la cuenta de , que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc:** La ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a [!DNL Dynamic Media].

   **Dirección de correo electrónico:** Dirección de correo electrónico utilizada para iniciar sesión en [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Contraseña:** La contraseña usada para iniciar sesión en [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Haga clic en **[!UICONTROL Enviar]**.
