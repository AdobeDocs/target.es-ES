---
description: Target Standard se puede integrar con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
seo-description: Target Standard se puede integrar con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
seo-title: Integración con Dynamic Media Classic
solution: Target
subtopic: Primeros pasos
title: Integración con Dynamic Media Classic
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Integración con Dynamic Media Classic{#scene-settings}

Target Standard se puede integrar con Adobe Dynamic Media Classic (antes llamado Scene7) para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.

>[!NOTE]
>
>Al integrar Target con Dynamic Media Classic, se habilita la entrega de recursos (como parte de las actividades) cargados en la carpeta de recursos de Adobe Experience Cloud. Esta integración no permite el acceso a todos los recursos cargados en Dynamic Media Classic para su publicación en las actividades de Target.

Si ya tiene una cuenta de Dynamic Media, puede proporcionar sus credenciales existentes. Si no tiene una cuenta, puede solicitar una cuenta de Dynamic Media Classic restringida sin costes adicionales a su representante de Adobe. Esta cuenta se puede utilizar para fines restringidos para utilizar solo en Target. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

Si esta configuración no está establecida, la opción de Intercambiar oferta de imagen dentro del flujo de trabajo de creación de actividades no estará disponible. Después de definir esta configuración, la opción de intercambiar/cambiar las ofertas de imágenes está disponible tanto en el [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). De este modo, puede aprovechar las ofertas de imágenes con imágenes que se han cargado desde Adobe Experience Cloud para usarlas en las actividades de Target.

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. No hay forma de obtener la URL publicada de una imagen cargada en Experience Cloud para consumirla directamente o fuera de los flujos de trabajo de segmentación con Adobe Target. Esta funcionalidad no está permitida según el contrato.

Tenga en cuenta que la URL de almacenamiento y las URL de publicación finales de imágenes de Dynamic Media son diferentes y NO debe crear ofertas utilizando el vínculo de almacenamiento de imágenes, ya que la entrega no funcionará en estos casos. Se debe usar la capacidad de ofertas de imagen como se explica en nuestra documentación de ayuda.

Para integrarse con Dynamic Media Classic (Scene7), debe especificar la siguiente información.

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Configuración de Scene7]**.
1. Especifique la siguiente información de la cuenta de Dynamic Media Classic:

   **Región:** La región de la cuenta de Dynamic Media, que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc:** La ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a Dynamic Media.

   **Dirección de correo electrónico:** La dirección de correo electrónico usada para iniciar sesión en Dynamic Media Classic (Scene7).

   **Contraseña:** La contraseña utilizada para iniciar sesión en Dynamic Media Classic (Scene7).
1. Haga clic en **[!UICONTROL Enviar]**.
