---
keywords: añadir usuario;proyecto;grupo de usuarios;espacio de trabajo;propiedades;propiedad;administrar propiedad;at_property;funciones;permisos
description: Obtenga información sobre cómo agregar usuarios a Adobe Target, crear espacios de trabajo, grupos de usuarios y propiedades, actualizar la implementación y especificar funciones y permisos.
title: ¿Cómo configuro los permisos de Enterprise?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 0ab5b7d7cbfaef86b9a045883f597900dba72416
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 56%

---

# Configuración de permisos de Enterprise

Información sobre las tareas necesarias para agregar usuarios a la implementación de [!DNL Target]; crear espacios de trabajo, grupos de usuarios y propiedades; actualizar la implementación de [!DNL Target] para incluir el parámetro `at_property`; y especificar funciones y permisos.

>[!NOTE]
>
>La funcionalidad Propiedades y Permisos está disponible como parte de la solución [Target Premium](/help/main/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

La siguiente tabla enumera las tareas que debe realizar para crear propiedades y asignar funciones de usuario y permisos. Consulte las secciones siguientes para obtener más información sobre cada tarea.

| Tarea | Realizado en |
|--- |--- |
| 1. Agregar usuarios (opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Crear un espacio de trabajo (perfil de producto) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Crear grupos de usuarios (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Crear propiedades | IU de [!DNL Target] |
| 5: Actualice la implementación para incluir el parámetro `at_property` | [!DNL Target] interfaz de usuario, funciones de at.js o etiquetas en [!DNL Adobe Experience Platform] |
| 6. Especificar roles y permisos | [!DNL Adobe Admin Console for Enterprise] |

Para las tareas realizadas en [!DNL Adobe Admin Console for Enterprise], acceda a la consola siguiendo estos pasos:

1. En Adobe Target, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**.

   O

   Vaya a [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > inicie sesión con su Adobe ID si aún no lo ha hecho.


1. (Condicional) Si tiene acceso a [!DNL Admin Console for Enterprise] para más de una organización, haga clic en el avatar del usuario en la esquina derecha o en la barra de navegación superior y, a continuación, seleccione la organización que quiera.

## Paso 1. Agregar usuarios (opcional) {#section_A92AF0F921B743FEB9E9033433BD816A}

Cuando empiece a usar la nueva funcionalidad [!UICONTROL Properties], toda la administración de usuarios debe realizarse en [!DNL Adobe Admin Console for Enterprise]. Sin embargo, todos los usuarios existentes en [!DNL Target] se migrarán de [!DNL Target] a [!DNL Admin Console for Enterprise].

1. [En Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), haga clic en la ficha **[!UICONTROL Users]** en la parte superior de la página > **[!UICONTROL Add Users]** para crear usuarios nuevos o para editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos en Experience Cloud](https://helpx.adobe.com/es/enterprise/using/users.html) en la *Guía del usuario de Enterprise*.

## Paso 2: Creación de un espacio de trabajo (perfil de producto) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Un espacio de trabajo (perfil de producto) permite que una organización asigne un conjunto de usuarios específico a un conjunto de propiedades específicas. En muchos aspectos, un espacio de trabajo es parecido a un grupo de informes en [!DNL Analytics].

Las organizaciones pueden empezar a aprovechar la funcionalidad de permisos de Enterprise creando nuevos espacios de trabajo en [!DNL Admin Console], asignando propiedades de [!DNL Target] a dichos espacios y moviendo a los usuarios de la configuración &quot;Workspace predeterminado&quot; a los nuevos espacios de trabajo de acceso limitado.

Los clientes pueden utilizar estos espacios de trabajo para asignar a los equipos distintos accesos según su región, unidad de negocio, sección de sitio o cualquier otro método que se quiera.

Los usuarios pueden formar parte de varios espacios de trabajo y pueden incluso tener diferentes roles en cada uno de ellos.

1. En [!DNL Admin Console], haga clic en **[!UICONTROL Products]** y, a continuación, seleccione el nombre del producto deseado.

   ![workspace](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Cree el espacio de trabajo (perfil de producto) deseado:

   * **Acceso predeterminado:** todas las actividades existentes se combinarán en un solo proyecto llamado “Acceso predeterminado”. Esto no tendrá ningún impacto en los clientes. Todas las funciones de usuario y las funcionalidades se mantendrán exactamente igual que se encontraban antes este cambio.

     Todas las actividades creadas mediante [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] y [!DNL Target Classic] también formarán parte del espacio de trabajo “Acceso predeterminado”. No está permitido mover proyectos de “Acceso predeterminado” a otro proyecto.

   * **Nuevos espacios de trabajo (perfiles de producto):** puede comenzar a sacar provecho de la nueva funcionalidad de permisos haciendo lo siguiente:

      * Creación de nuevos espacios de trabajo en [!DNL Admin Console for Enterprise].
      * Asignar propiedades de Target a los espacios de trabajo.

   Puede utilizar estos espacios de trabajo para acceder a los diferentes equipos por región, unidad de negocio, sección del sitio o mediante cualquier otro método a su elección. Los usuarios pueden formar parte de varios espacios de trabajo y pueden tener diferentes funciones en cada uno de ellos.

1. Siga las instrucciones de [Creación y administración de configuraciones de producto](https://helpx.adobe.com/es/enterprise/help/manage-products-and-configurations.html) en la *Guía del usuario de Enterprise*.

>[!NOTE]
>Consulte el siguiente vídeo de formación para obtener más información sobre cómo configurar espacios de trabajo.

### Obtenga su ID de espacio de trabajo {#workspace-id}

Tendrá que pasar el ID de espacio de trabajo para aprovechar los permisos de Enterprise en [las API de Target](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html?lang=es){target=_blank}.

1. En [Adobe Admin Console](https://adminconsole.adobe.com), haga clic en la ficha [!UICONTROL Products] y, a continuación, haga clic en el producto en el menú izquierdo para mostrar la lista PLC (espacio de trabajo).
1. Haga clic en el PLC (espacio de trabajo) deseado y luego busque el ID de «perfiles» en la URL, como se muestra a continuación.

   ![ID de trabajo](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Paso 3. Crear grupos de usuarios (opcional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Puede crear grupos de usuarios, como Desarrolladores, Analistas, Especialistas en marketing, Ejecutivos, etc., y luego asignar privilegios en varios productos y espacios de trabajo de Adobe. Asignar todos los privilegios apropiados en diferentes productos de Adobe a un nuevo miembro del equipo puede ser tan fácil como añadirlos a un grupo de usuarios específico.

1. En Admin Console, haga clic en la ficha **[!UICONTROL Users]** en la parte superior de la página > **[!UICONTROL User Groups]** para crear grupos de usuarios nuevos o para editar los existentes.
1. Siga las instrucciones de [Administrar usuarios y grupos de una configuración de producto](https://helpx.adobe.com/es/enterprise/help/manage-products-and-configurations.html) en la *Guía del usuario de Enterprise*.

## Paso 4. Creación de propiedades {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Las propiedades se habilitan agregando un par nombre/valor específico como parámetro con cualquier llamada ([!DNL Target] llamada, llamada de API, etc.) a [!DNL Target].

Las propiedades pertenecen a canales específicos (web, móvil, correo electrónico y API/otros).

**Sugerencia**: consulte el vídeo de formación siguiente para obtener más información sobre la creación de propiedades.

1. En [!DNL Target], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Properties]** para mostrar la lista [!UICONTROL Properties].
1. Haga clic en **Crear propiedad**.

   Rellene los campos:

   * **Nombre de propiedad (obligatorio):** Especifique un nombre descriptivo para la propiedad.
   * **Descripción:** especifique una descripción opcional para la propiedad.
   * **Canal:** Seleccione el canal deseado para esta propiedad: web, aplicación móvil, correo electrónico o API/otro (por ejemplo, un cuadro en la parte superior o una consola PlayStation).

1. Haga clic en **[!UICONTROL Copy]** para copiar el código en el portapapeles que utilizará al realizar los pasos de [5: actualice la implementación para incluir el parámetro at_property](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Haga clic en **[!UICONTROL Save]** cuando termine.

>[!NOTE]
>Consulte el vídeo de formación siguiente para obtener más información sobre la creación de propiedades.

## Paso 5: Actualice la implementación para incluir el parámetro at_property {#section_9B17A59807A94712BE642942442EBBC8}

Para usar la funcionalidad de permisos de usuario de [!DNL Target], debe agregar el parámetro `at_property` a cualquier llamada que llegue a [!DNL Target] (llamada de Target, llamada de API, etc.).

**Para obtener el código del parámetro `at_property`:**

1. (Condicional) Utilice el código de implementación que ha generado y guardado en el Portapapeles mientras realiza los pasos de [4. Crear propiedades](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) y continuar con el paso 2.

   O

   En [!DNL Target], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Properties]** para mostrar la lista [!UICONTROL Properties].

   1. Pase el puntero del ratón sobre la columna [!UICONTROL Last Updated] para que se muestre la propiedad deseada y haga clic en el icono [!UICONTROL Code] ( ![Icono de código](/help/main/assets/icons/Code.svg) ).

      ![Código de pase de propiedad](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Haga clic con el botón derecho sobre el código de implementación destacado para copiarlo en el Portapapeles.

1. Actualice la implementación de [!DNL Target] con el código de implementación obtenido en el paso anterior.

   Existen varias formas de actualizar la implementación de [!DNL Target]. Por ejemplo, puede usar los siguientes métodos para páginas web:

   * **Mediante un &quot;Parámetro personalizado&quot; en las etiquetas de [!DNL Adobe Experience Platform]:**

     Para obtener más información, consulte [Agregar parámetros de mbox](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=es#add-mbox-params) en la documentación de *Información general sobre etiquetas*.

   * **Mediante la función targetPageParamsAll():** Coloque el siguiente código en las etiquetas `<head>`, encima de la referencia at.js.

     ```javascript
     <script>
      function targetPageParamsAll() {
       return {
        "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
       };
      }
     </script>
     ```

     Para obtener más información sobre cómo hacerlo con at.js, consulte [targetPageParamsAll](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparamsall.html?lang=es){target=_blank}.

## Paso 6: Especificar funciones y permisos {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. En Admin Console, haga clic en **[!UICONTROL Products]** y, a continuación, seleccione el nombre del producto deseado.

   ![Workspace](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Haga clic en el nombre del perfil deseado (por ejemplo, Workspace predeterminado).

   ![Espacio de trabajo predeterminado](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Haga clic en **[!UICONTROL Users]**.

   La ficha [!UICONTROL Users] muestra todos los usuarios de ese espacio de trabajo.

   ![usuarios de configuración](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Seleccione la función de permisos deseada (Aprobador, Editor, Observador o Publicador) utilizando la lista desplegable de cada usuario en la columna [!UICONTROL Product Role].

   ![Lista desplegable Función del producto](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Función | Descripción |
   |--- |--- |
   | Aprobador | Puede crear, editar y activar o detener actividades. |
   | Editor | puede crear y editar actividades antes de que estén activas, pero no puede aprobar el lanzamiento de una actividad. |
   | Observador | Puede ver actividades, pero no puede crearlas o editarlas. |
   | Editor | Similar a la función Observador (puede ver actividades, pero no puede crearlas o editarlas). Sin embargo, la función Publicador tiene el permiso adicional de activar actividades. |

   Para obtener más información, consulte [Administrar permisos y roles de producto en Admin Console](https://helpx.adobe.com/es/enterprise/help/manage-permissions-and-roles.html) en la *Guía del usuario de Enterprise*.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas características y mejorar la experiencia del usuario en todo el producto. La información de los siguientes vídeos es, en general, correcta; sin embargo, las opciones pueden estar en ubicaciones ligeramente diferentes. Los vídeos actualizados se publicarán próximamente.

### Cómo configurar espacios de trabajo de Adobe Target (6:55) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo explica cómo se crean espacios de trabajo.

* Acceso a Adobe Admin Console desde la interfaz de Adobe Target (3 métodos)
* Configuración de un espacio de trabajo en Adobe Admin Console

   * Agregación de usuarios a espacios de trabajo
   * Agregación de propiedades a espacios de trabajo

* Explicación de los espacios de trabajo predeterminados

>[!VIDEO](https://video.tv.adobe.com/v/3421730?captions=spa)

### Cómo crear propiedades en Adobe Target (3:05) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

* Cómo crear una propiedad en la interfaz de.[!DNL Adobe Target]
* Cómo se genera un token de propiedad para incluirlo en su implementación de propiedad
* Familiarícese con los tres métodos de implementación:

   * Web
   * Aplicación móvil
   * Correo electrónico, cuadro superior o llamadas de API

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
