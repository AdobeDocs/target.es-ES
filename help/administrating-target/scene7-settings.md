---
description: Target Standard se puede integrar con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
title: Integración con Dynamic Media Classic integración de configuración
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 85%

---


# Integración con Dynamic Media Classic{#scene-settings}

Target se puede integrar con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.

>[!NOTE]
>
>La información de este tema se ha actualizado para ayudarle a obtener un pico en los cambios de la interfaz de usuario que se producirán en la versión Target Standard/Premium 20.6.1 (julio de 2020). La mayor parte de la información presentada en este tema se aplica a la IU actual; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes.

>[!NOTE]
>
>Al integrar Target con Dynamic Media Classic, se habilita la entrega de recursos (como parte de las actividades) cargados en la carpeta de recursos de Adobe Experience Cloud. Esta integración no permite el acceso a todos los recursos cargados en Dynamic Media Classic para su publicación en las actividades de Target.

Si ya tiene una cuenta de Dynamic Media, puede proporcionar sus credenciales existentes. Si no tiene una cuenta, puede solicitar una cuenta de Dynamic Media Classic restringida sin costes adicionales a su representante de Adobe. Esta cuenta se puede utilizar para fines restringidos para utilizar solo en Target. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

Si esta configuración no está establecida, la opción de Intercambiar oferta de imagen dentro del flujo de trabajo de creación de actividades no estará disponible. Después de definir esta configuración, la opción de intercambiar/cambiar las ofertas de imágenes está disponible tanto en el  [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). De este modo, puede aprovechar las ofertas de imágenes con imágenes que se han cargado desde Adobe Experience Cloud para usarlas en las actividades de Target.

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. No hay forma de obtener la URL publicada de una imagen cargada en Experience Cloud para consumirla directamente o fuera de los flujos de trabajo de segmentación con Adobe Target. Esta funcionalidad no está permitida según el contrato.

Tenga en cuenta que la URL de almacenamiento y las URL de publicación finales de imágenes de Dynamic Media son diferentes y NO debe crear ofertas utilizando el vínculo de almacenamiento de imágenes, ya que la entrega no funcionará en estos casos. Se debe usar la capacidad de ofertas de imagen como se explica en nuestra documentación de ayuda.

Para realizar la integración con Dynamic Media Classic (Scene7), debe especificar la siguiente información.

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Settings]**.

   ![Página de Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique la siguiente información de la cuenta de Dynamic Media Classic:

   **Región:** La región de la cuenta de Dynamic Media, que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc:** La ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a Dynamic Media.

   **Dirección de correo electrónico:** La dirección de correo electrónico usada para iniciar sesión en Dynamic Media Classic (Scene7).

   **Contraseña:** La contraseña utilizada para iniciar sesión en Dynamic Media Classic (Scene7).

1. Haga clic en **[!UICONTROL Enviar]**.
