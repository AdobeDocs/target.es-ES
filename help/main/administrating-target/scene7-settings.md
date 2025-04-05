---
keywords: scene7;dynamic media classic;administración de activos digitales;assets;dam;biblioteca de contenido;intercambiar imagen
description: Obtenga información sobre cómo integrar Adobe  [!DNL Target]  con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
title: ¿Cómo configuro la integración de Dynamic Media Classic (Scene7)?
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 85%

---

# Configuración de Dynamic Media Classic (anteriormente Scene7)

[!DNL Adobe Target] se puede integrar con [!DNL Adobe Dynamic Media Classic] (anteriormente [!DNL Scene7]) para proporcionar la administración de activos digitales (DAM) en [!UICONTROL Content Library].

{{permissions-update}}

>[!NOTE]
>
>Al integrar [!DNL Target] con [!DNL Dynamic Media Classic], se habilita la entrega de activos (como parte de las actividades) cargados en la carpeta de activos de [!DNL Adobe Experience Cloud]. Esta integración no permite el acceso a todos los activos cargados en [!DNL Dynamic Media Classic] para su publicación en las actividades de [!DNL Target].

Si ya tiene una cuenta de [!DNL Dynamic Media], puede proporcionar sus credenciales existentes. Si no tiene una cuenta, puede solicitar una cuenta de uso restringido [!DNL Dynamic Media Classic] sin costes adicionales a su representante de [!DNL Adobe]. Esta cuenta se puede utilizar con fines restringidos solo en [!DNL Target]. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Si esta opción no está configurada, la opción [!UICONTROL Swap Image offer] del flujo de trabajo de creación de actividades no estará disponible. Una vez configurado este ajuste, la opción de intercambiar/cambiar ofertas de imágenes estará disponible tanto en el [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). De este modo, puede aprovechar las ofertas de imágenes con imágenes que se han cargado desde [!DNL Adobe Experience Cloud] para usarlas en las actividades de [!DNL Target].

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. No hay forma de obtener la URL publicada de una imagen cargada en [!DNL Experience Cloud] para consumirla directamente o fuera de los flujos de trabajo de segmentación con [!DNL Target]. Esta funcionalidad no está permitida según el contrato.

Tenga en cuenta que la URL de almacenamiento y las URL de publicación finales de imágenes de [!DNL Dynamic Media] son diferentes y *NO* debe crear ofertas utilizando el vínculo de almacenamiento de imágenes, ya que la entrega no funcionará en estos casos. Debe usar la capacidad de ofertas de imagen como se explica en nuestra documentación de ayuda.

Para integrar con [!DNL Dynamic Media Classic] ([!DNL Scene7]), debe especificar la siguiente información.

1. Haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

1. Especifique la siguiente información de la cuenta de [!DNL Dynamic Media Classic]:

   **Región:** La región de la cuenta de [!DNL Dynamic Media], que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc:** La ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a [!DNL Dynamic Media].

   **Dirección de correo electrónico:** la dirección de correo electrónico usada para iniciar sesión en [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Contraseña:** la contraseña usada para iniciar sesión en [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Haga clic en **[!UICONTROL Submit]**.
