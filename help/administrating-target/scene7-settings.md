---
keywords: scene7;dynamic media classic;administración de recursos digitales;assets;dam;biblioteca de contenido;intercambiar imagen
description: Aprenda a integrar Adobe [!DNL Target] con Adobe Dynamic Media Classic (anteriormente Scene7) para proporcionar administración de activos digitales (DAM) en la biblioteca de contenido.
title: ¿Cómo configuro la integración de Dynamic Media Classic (Scene7)?
feature: Administración y configuración
role: Administrator
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 28%

---

# Configuración de Dynamic Media Classic (anteriormente Scene7)

[!DNL Adobe Target] se puede integrar con  [!DNL Adobe Dynamic Media Classic] (anteriormente  [!DNL Scene7]) para proporcionar la administración de activos digitales (DAM) en la biblioteca de  [!UICONTROL contenido].

>[!NOTE]
>
>Al integrar [!DNL Target] con [!DNL Dynamic Media Classic] se habilita el envío de recursos (como parte de las actividades) cargados en la carpeta de recursos [!DNL Adobe Experience Cloud]. Esta integración no permite el acceso a todos los recursos cargados en [!DNL Dynamic Media Classic] para su envío en actividades [!DNL Target].

Si ya tiene una cuenta [!DNL Dynamic Media], puede proporcionar las credenciales existentes. Si no tiene una cuenta, puede solicitar una cuenta [!DNL Dynamic Media Classic] de uso restringido sin cargo adicional a su representante [!DNL Adobe]. Esta cuenta se puede usar con fines restringidos para usar solo en [!DNL Target]. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Si esta configuración no está configurada, la opción [!UICONTROL Swap Image offer] dentro del flujo de trabajo de creación de actividades no está disponible. Después de definir esta configuración, la opción de intercambiar/cambiar las ofertas de imágenes está disponible tanto en el  [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). A continuación, puede aprovechar las ofertas de imágenes con imágenes que se han cargado desde [!DNL Adobe Experience Cloud] para usarlas en actividades [!DNL Target].

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. No hay forma de obtener la URL publicada de una imagen cargada en [!DNL Experience Cloud] para consumir directamente o fuera de los flujos de trabajo de objetivos mediante [!DNL Target]. Esta funcionalidad no está permitida según el contrato.

Tenga en cuenta que la dirección URL de almacenamiento y las direcciones URL de publicación finales de imágenes de [!DNL Dynamic Media] son diferentes y debe *NOT* crear ofertas utilizando el enlace de almacenamiento de imágenes, ya que el envío no funcionará en estos casos. Debe utilizar la capacidad de ofertas de imágenes como se explica en nuestra documentación de ayuda.

Para integrarse con [!DNL Dynamic Media Classic] ([!DNL Scene7]), debe especificar la siguiente información.

1. Haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

   ![Página de Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique la siguiente [!DNL Dynamic Media Classic] información de cuenta:

   **Región:**[!DNL Dynamic Media] La región de la cuenta de , que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc:** La ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a [!DNL Dynamic Media].

   **Dirección de correo electrónico:** la dirección de correo electrónico usada para iniciar sesión en  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Contraseña:** la contraseña utilizada para iniciar sesión en  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Haga clic en **[!UICONTROL Enviar]**.
