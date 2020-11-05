---
description: Target Standard se puede integrar con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
title: Integración con Dynamic Media Classic integración de configuración
feature: administration general
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 36%

---


# Configuración de Scene7 {#scene-settings}

Target can be integrated with [!DNL Adobe Dynamic Media Classic] (formerly [!DNL Scene7]) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use [!DNL Dynamic Media Classic] account at no additional charge from your [!DNL Adobe] representative. This account can be used for purposes restricted for use in [!DNL Target] only. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

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
