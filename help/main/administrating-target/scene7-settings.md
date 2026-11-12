---
keywords: scene7;dynamic media classic;administración de activos digitales;assets;dam;biblioteca de contenido;intercambiar imagen
description: Conecte Adobe Target a Adobe Dynamic Media Classic (Scene7) para que los autores puedan utilizar ofertas de imágenes e intercambiar imágenes de recursos de Experience Cloud en las actividades.
landing-page-description: Configure la configuración de Scene7 en Administración para habilitar ofertas de imágenes, flujos de trabajo DAM de la biblioteca de contenido y acciones de intercambio de imágenes en el VEC y el Compositor de experiencias basadas en formularios.
short-description: Configure la configuración de Scene7 en Administración para habilitar ofertas de imágenes, flujos de trabajo DAM de la biblioteca de contenido y acciones de intercambio de imágenes en el VEC y el Compositor de experiencias basadas en formularios.
title: ¿Cómo configuro la integración de Dynamic Media Classic (Scene7)?
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
TQID: 'https://experienceleague.adobe.com/LKbjwlGIxrgaU-2i6Ddn1wi-VjsSmpQPAxYkFHRNOYQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%
---
# Configuración de Dynamic Media Classic (Scene7)

Use la ficha **[!UICONTROL Configuración de Scene7]** en **[!UICONTROL Administración]** para conectar [!DNL Adobe Target] a [!DNL Adobe Dynamic Media Classic] (anteriormente [!DNL Scene7]). La integración incorpora la administración de activos digitales (DAM) en la [!UICONTROL biblioteca de contenido] y habilita los flujos de trabajo de intercambio de imágenes en las actividades.

Para ver cómo encaja esta ficha con otras tareas de administración, consulte [¿Cómo administro Target?](/help/main/administrating-target/administrating-target.md). Para localizar **[!UICONTROL Administración]** en la interfaz, consulta [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md).

**Información general**

1. [Lo que habilita la integración](#what-it-enables): ofertas de imágenes, intercambio de imágenes y recursos aptos.
1. [Cuenta y credenciales](#account-and-credentials): Cuentas [!DNL Dynamic Media] existentes y tipos de cuenta admitidos.
1. [Directrices de uso](#usage-guidelines): direcciones URL, envío y elementos no admitidos.
1. [Configurar Scene7 en Target](#configure-scene7): Configuración de inicio de sesión y región.

{{permissions-update}}

## Qué habilita la integración {#what-it-enables}

Cuando la **[!UICONTROL configuración de Scene7]** está configurada, los autores pueden utilizar imágenes cargadas en la carpeta de recursos [!DNL Adobe Experience Cloud] en [!DNL Target] actividades. La opción **[!UICONTROL Intercambiar oferta de imagen]** aparece en el flujo de trabajo de la actividad, incluidos [Compositor de experiencias visuales y Compositor de experiencias basadas en formularios](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Para ver el comportamiento de intercambio en el VEC, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

Si esta opción no está configurada, **[!UICONTROL Intercambiar oferta de imagen]** no estará disponible durante la creación de la actividad.

La integración ofrece recursos que forman parte de las actividades de la carpeta de recursos de Experience Cloud. No expone **not** todos los recursos de [!DNL Dynamic Media Classic] para su uso en [!DNL Target] actividades.

Después de la configuración, administre las ofertas de imágenes en la biblioteca [!UICONTROL Ofertas]. Ver [Administrar contenido](/help/main/c-experiences/c-manage-content/manage-content.md).

## Cuenta y credenciales {#account-and-credentials}

Si ya tiene una cuenta de [!DNL Dynamic Media], ingrese esas credenciales en la página **[!UICONTROL Configuración de Scene7]**.

Adobe ya no aprovisiona cuentas de uso restringido y sin cargo [!DNL Dynamic Media Classic] para nuevos clientes o usuarios [!DNL Target]. Si su organización ya tiene credenciales de inicio de sesión para esta integración, seguirán funcionando. Si tiene alguna pregunta sobre la cuenta, comuníquese con el representante de [!DNL Adobe].

## Directrices de uso {#usage-guidelines}

Tenga en cuenta las siguientes restricciones al utilizar imágenes con esta integración:

* **Ofertas de imágenes, no direcciones URL de almacenamiento.** [!DNL Dynamic Media] direcciones URL de almacenamiento y direcciones URL de envío publicadas son diferentes. No cree ofertas desde vínculos de almacenamiento; la entrega falla. En su lugar, use [ofertas de imagen](/help/main/c-experiences/c-manage-content/manage-content.md) y flujos de trabajo de intercambio de imágenes.
* **URL públicas en código personalizado.** Para hacer referencia a una URL de imagen pública directamente en una oferta o código personalizado, aloje la imagen en sus propios servidores web y utilice esa URL. No puede obtener una dirección URL publicada para una imagen cargada en Experience Cloud para usarla fuera de [!DNL Target] flujos de trabajo de segmentación; ese uso no está permitido en el contrato.
* **Activos aptos.** Solo los recursos cargados en la carpeta de recursos de Experience Cloud (y los flujos de trabajo admitidos por esta integración) están en ámbito, no el catálogo completo de [!DNL Dynamic Media Classic].

## Configuración de Scene7 en Target {#configure-scene7}

Siga estos pasos para conectar [!DNL Dynamic Media Classic] ([!DNL Scene7]):

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Configuración de Scene7]**.
1. Escriba la información de su cuenta de [!DNL Dynamic Media Classic]:

   | Campo | Descripción |
   | --- | --- |
   | **Región** | Región de la cuenta de [!DNL Dynamic Media]: Norteamérica, Europa o Asia. |
   | **Carpeta ad hoc** | Ubicación del contenido fuera de la carpeta Target que se carga manualmente en [!DNL Dynamic Media]. |
   | **Dirección de correo electrónico** | Dirección de correo electrónico usada para iniciar sesión en [!DNL Dynamic Media Classic] ([!DNL Scene7]). |
   | **Contraseña** | Contraseña utilizada para iniciar sesión en [!DNL Dynamic Media Classic] ([!DNL Scene7]). |

   ![Campos de configuración de Scene7](/help/main/administrating-target/assets/scene7-1.png)

1. Haga clic en **[!UICONTROL Enviar]**.
