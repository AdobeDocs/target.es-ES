---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Adobe Target se puede integrar con Adobe Dynamic Media Classic para proporcionar administración de recursos digitales (DAM) en la biblioteca de contenido.
title: Integración de la configuración de la integración de Dynamic Media Classic
feature: administration general
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 30%

---


# Configuración de Scene7 {#scene-settings}

[!DNL Target] se puede integrar con  [!DNL Adobe Dynamic Media Classic] para proporcionar administración de recursos digitales (DAM) en la biblioteca [!UICONTROL  de ]contenido.

>[!NOTE]
>
>La integración de [!DNL Target] con [!DNL Dynamic Media Classic] permite el envío de recursos (como parte de actividades) cargados en la carpeta [!DNL Adobe Experience Cloud] assets. Esta integración no permite el acceso a todos los recursos cargados en [!DNL Dynamic Media Classic] para envío en actividades [!DNL Target].

Si ya tiene una cuenta [!DNL Dynamic Media], puede proporcionar las credenciales existentes. Si no tiene una cuenta, puede solicitar una cuenta de [!DNL Dynamic Media Classic] uso restringido sin costo adicional a su representante [!DNL Adobe]. Esta cuenta se puede utilizar para fines restringidos para su uso únicamente en [!DNL Target]. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Si esta configuración no está configurada, la opción [!UICONTROL Intercambiar oferta de imagen] dentro del flujo de trabajo de creación de actividades no está disponible. Después de definir esta configuración, la opción de intercambiar/cambiar las ofertas de imágenes está disponible tanto en el  [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). A continuación, puede aprovechar las ofertas de imagen con imágenes cargadas desde [!DNL Adobe Experience Cloud] para usarlas en actividades [!DNL Target].

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. No hay forma de obtener la dirección URL publicada de una imagen cargada en [!DNL Experience Cloud] para consumir directamente o fuera de los flujos de trabajo de objetivo mediante [!DNL Target]. Esta funcionalidad no está permitida según el contrato.

Tenga en cuenta que la URL de almacenamiento y las URL de publicación final de imágenes de [!DNL Dynamic Media] son diferentes y que uno debe *NO* crear ofertas mediante el vínculo de almacenamiento de imágenes, ya que envío no funcionará en estos casos. Debe utilizar la función de ofertas de imagen como se explica en nuestra documentación de ayuda.

Para realizar la integración con [!DNL Dynamic Media Classic] ([!DNL Scene7]), debe especificar la siguiente información.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Configuración de Scene7]**.

   ![Página de Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique la siguiente información de la cuenta [!DNL Dynamic Media Classic]:

   **Región:**[!DNL Dynamic Media] La región de la cuenta de , que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc:** La ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a [!DNL Dynamic Media].

   **Dirección de correo electrónico:** la dirección de correo electrónico que se utiliza para iniciar sesión en  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Contraseña:** la contraseña usada para iniciar sesión en  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Haga clic en **[!UICONTROL Enviar]**.
