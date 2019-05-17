---
description: Target Standard se puede integrar con Adobe Scene7 para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
seo-description: Target Standard se puede integrar con Adobe Scene7 para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.
seo-title: Configuración de Scene7
solution: Target
subtopic: Primeros pasos
title: Configuración de Scene7
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Configuración de Scene7{#scene-settings}

Target Standard se puede integrar con Adobe Scene7 para ofrecer la administración de activos digitales (DAM) en la biblioteca de contenido.

>[!NOTE]
>
>Al integrar Target con Scene7, se habilita la entrega de activos (como parte de las actividades) cargados en la carpeta de activos de Adobe Experience Cloud. Esta integración no permite el acceso a todos los activos cargados en Scene7 para su publicación en las actividades de Target.

Si tiene una cuenta de Scene7, puede proporcionar sus credenciales de Scene7. Si no la tiene, póngase en contacto con su representante de Adobe, que puede configurar esta funcionalidad con una cuenta de Scene7 gratuita dedicada a su cuenta de Target. Esta cuenta se puede utilizar para fines restringidos para utilizar solo en Target. Este servicio está a disposición de los clientes para flujos de trabajo que necesitan la funcionalidad de intercambio de imágenes.

Si esta configuración no está establecida, la opción de Intercambiar oferta de imagen dentro del flujo de trabajo de creación de actividades no estará disponible. Después de definir esta configuración, la opción de intercambiar/cambiar las ofertas de imágenes está disponible tanto en el   [Compositor de experiencias visuales (VEC) como en el Compositor de experiencias basadas en formularios](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). De este modo, puede aprovechar las ofertas de imágenes con imágenes que se han cargado desde Adobe Experience Cloud para usarlas en las actividades de Target.

Si desea hacer referencia a una URL de imagen pública directamente en una oferta o un código personalizado durante la creación de la actividad, debe implementar la imagen en sus propios servidores web y usar su propia URL en el código. No hay forma de obtener la URL publicada de una imagen cargada en Experience Cloud para consumirla directamente o fuera de los flujos de trabajo de segmentación con Adobe Target. Esta funcionalidad no está permitida según el contrato.

Tenga en cuenta que la URL de almacenamiento y las URL de publicación finales de Scene7 son diferentes y NO debe crear ofertas utilizando el vínculo de almacenamiento de imágenes, ya que la entrega no funcionará en estos casos. Se debe usar la capacidad de ofertas de imagen como se explica en nuestra documentación de ayuda.

Para integrarlo con Scene7 es necesario especificar información de este.

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Configuración de Scene7]**.
1. Especifique la siguiente información de la cuenta de Scene7:

   **Región de Scene7:** la región de la cuenta de Scene7, que puede ser Norteamérica, Europa o Asia.

   **Carpeta adhoc de Scene7:** la ubicación de contenido que reside fuera de la carpeta de destino y que se transfiere de forma manual a Scene7.

   **Dirección de correo electrónico de Scene7:** la dirección de correo electrónico usada para iniciar sesión en Scene7.

   **Contraseña de Scene7:** la contraseña usada para iniciar sesión en Scene7.
1. Haga clic en **[!UICONTROL Enviar]**.
