---
keywords: host;hosts;grupo de hosts;solución de problemas;prácticas recomendadas;ubox;redirecciones;redireccionamiento;lista de direcciones permitidas;lista de permitidos;lista de direcciones bloqueadas;lista de bloqueados
description: Aprenda a organizar sus sitios web y entornos de preproducción para facilitar la administración y la creación de informes separados en Adobe Target.
title: ¿Qué son los hosts y cómo puedo utilizarlos?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 22%

---

# Hosts

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes separados en [!DNL Adobe Target].

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. La administración de hosts también permite separar los datos de los informes por [entorno](/help/main/administrating-target/environments.md).

Un host es cualquier dominio desde el cual un [!DNL Target] se realiza la solicitud. En un sitio web, suele ser la variable `location.hostname` propiedad de la dirección URL que crea la variable [!DNL Target] solicitud.

De forma predeterminada, [!DNL Target] no limita un host que pueda realizar [!DNL Target] solicitudes y recibir [!DNL Target] respuestas. Cuando los nuevos hosts realizan solicitudes, funcionan automáticamente. Este proceso también permite realizar pruebas en distintos dominios que no conoce o no puede anticipar. Si desea anular este comportamiento predeterminado, puede configurar una lista de permitidos o lista de bloqueados para limitar con qué hosts trabajan [!DNL Target].

Para administrar hosts, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Reconocer hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconocer un host y agregarlo al [!UICONTROL Hosts] , se deben cumplir las siguientes condiciones:

* Al menos una [!DNL Target] la solicitud debe existir en el host
* Una página del host debe tener   lo siguiente:

   * Una referencia a at.js precisa
   * A [!DNL Target] o una solicitud global generada automáticamente [!DNL Target] solicitud

* La página con la variable [!DNL Target] la solicitud debe verse en un explorador

Una vez visualizada la página, el host se enumera en la [!UICONTROL Hosts] , lo que le permite administrarla en un entorno, y obtener una vista previa de las actividades y pruebas e iniciarlas.

>[!NOTE]
>
>Esto engloba todos los servidores de desarrollo personal.

Cuando un host se añada a la lista [!UICONTROL Hosts], compruebe si se reconoce.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador. 


   De forma predeterminada, un host recién reconocido se coloca en la variable [!UICONTROL Producción] entorno. La variable [!UICONTROL Producción] es el entorno más seguro porque no permite que se vean actividades inactivas desde estos hosts.

1. (Condicional) Haga clic en el **[!UICONTROL Mover]** icono ( ![icono mover](/help/main/administrating-target/assets/icon-move.png) ) para mover el host al [!UICONTROL Desarrollo], [!UICONTROL Ensayo]u otro entorno.

>[!NOTE]
>
>La variable [!UICONTROL Producción] no se puede eliminar aunque se le cambie el nombre. Se da por hecho que este entorno es donde se sirven las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Ordenar o buscar la lista Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para ordenar el [!UICONTROL Hosts] , haga clic en cualquier encabezado de columna ([!UICONTROL Nombre], [!UICONTROL Entorno]o [!UICONTROL Última solicitud]) para ordenar la lista en orden ascendente o descendente.

Para buscar en el [!UICONTROL Hosts] , escriba un término de búsqueda en la [!UICONTROL Buscar hosts] en la ventana

## Crear listas de permitidos que especifiquen hosts autorizados para enviar [!DNL Target] solicitudes a [!DNL Target]. {#allowlist}

Puede crear una lista de permitidos que especifique los hosts (dominios) con autorización para enviar [!DNL Target] solicitudes a [!DNL Target]. Todos los demás hosts que generan solicitudes obtienen una respuesta de error de autorización comentada. De forma predeterminada, cualquier host que contenga un [!DNL Target] registros de solicitud con [!DNL Target] en el [!UICONTROL Producción] y tiene acceso a todas las actividades activas y aprobadas. Si no desea este método, puede usar la lista de permitidos para registrar los hosts específicos que pueden realizar [!DNL Target] solicitudes y recibir [!DNL Target] contenido. Todos los hosts siguen mostrándose en la variable [!UICONTROL Hosts] Los entornos de lista y pueden seguir utilizándose para agrupar estos hosts y asignar distintos niveles a cada uno, como si el host puede ver actividades activas o inactivas.

Para crear una lista de permitidos:

1. En el [!UICONTROL Hosts] lista, haga clic en **[!UICONTROL Autorizar hosts]**.
1. Active la variable **[!UICONTROL Habilitar los hosts autorizados para la entrega de contenido]** alternar.
1. Añada los hosts que quiera en la **[!UICONTROL El host contiene]** como desee.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Añada los hosts que quiera en la **[!UICONTROL El host no contiene]** como desee.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Guardar]**.

Si [!DNL Target] se realiza en un host no autorizado, la llamada responde con `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Prácticas recomendadas de seguridad**: Si utiliza la funcionalidad de la casilla de verificación [!DNL Target], esta lista de permitidos también controla la lista de dominios a los que se [redirectores](https://developer.adobe.com/target/implement/email/working-with-redirectors/){target=_blank} puede navegar. Asegúrese de añadir todos los dominios a los que desee redirigir cuando utilice ubox como parte de la implementación. Si la lista de permitidos se deja sin especificar, [!DNL Adobe] no puede verificar las direcciones URL de redireccionamiento ni protegerse de posibles redireccionamientos maliciosos.
>
>La lista de permitidos tiene prioridad sobre los entornos. Borre todos los hosts antes de utilizar la función de lista de permitidos y, a continuación, solo los hosts permitidos por la lista de permitidos aparecerán en la lista de hosts. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Si el dominio llama a at.js, aparecerá un dominio en la lista. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. Si no se pasa ningún entorno, el valor predeterminado del host de la llamada es [!UICONTROL Producción].

También puede crear una  de lista de bloqueados que especifique hosts (dominios) que no pueden enviar [!DNL Target] solicitudes a [!DNL Target] añadiendo los hosts que desee en la variable [!UICONTROL El host no contiene] en la ventana

>[!NOTE]
>
>La variable [!UICONTROL Hosts autorizados] se utiliza para [!DNL Target] hosts y hosts de redireccionamiento predeterminados. Agregue todos los dominios existentes aprobados para usar la variable [!DNL Adobe Target] SDK de JavaScript (at.js) *Y* todos los dominios utilizados en las direcciones URL de redireccionamiento predeterminadas de ubox. Agregue dominios similares nuevos a la lista de permitidos en el futuro.

## Eliminar un host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. En el [!UICONTROL Hosts] , haga clic en la **[!UICONTROL Eliminar]** icono.
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>El host vuelve a aparecer en la lista si alguien abre una página que contiene una [!DNL Target] en el host.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de la cuenta.**

* Actualice la página [!UICONTROL Hosts] en el navegador.
* Confirme que la variable [!DNL Target] es correcta, incluida la referencia a at.js.
* Intente ir a uno de los [!DNL Target] solicitudes en el host. Es posible que no [!DNL Target] La solicitud del host se ha procesado en un explorador.

**La lista [!UICONTROL Hosts] contiene dominios aleatorios o desconocidos.**

Si una solicitud a [!DNL Target] está hecho del dominio . Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. En caso de que el dominio incluido en la lista no sea uno de los que el equipo usa, puede hacer clic en [!UICONTROL Eliminar] para eliminarlo.

**My [!DNL Target] devoluciones de solicitud /&#42; sin visualización: host mbox sin autorización &#42;/.**

Si [!DNL Target] se realiza en un host no autorizado, la solicitud responde con /&#42; sin visualización: host mbox sin autorización &#42;/.
