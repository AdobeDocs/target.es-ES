---
keywords: host;hosts;grupo de hosts;solución de problemas;prácticas recomendadas;ubox;redirecciones;redireccionamiento;lista blanca;lista de permitidos;lista negra;lista de bloqueados
description: Aprenda a organizar sus sitios web y entornos de preproducción para facilitar la administración y la creación de informes separados en Adobe Target.
title: ¿Qué son los hosts y cómo los utilizo?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 22%

---

# Hosts

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes separados en [!DNL Adobe Target].

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. La administración de hosts también permite separar los datos del informe mediante [entorno](/help/main/administrating-target/environments.md).

Un host es cualquier dominio del que [!DNL Target] se ha realizado la solicitud. En un sitio web, suele ser el `location.hostname` propiedad de la dirección URL que hace que [!DNL Target] solicitud.

De forma predeterminada, [!DNL Target] no limita un host que puede realizar [!DNL Target] solicitudes y recepción [!DNL Target] respuestas. Cuando los nuevos hosts realizan solicitudes, funcionan automáticamente. Este proceso también permite realizar pruebas en dominios diferentes que no conoce o no puede anticipar. Si desea anular este comportamiento predeterminado, puede configurar una lista de permitidos o lista de bloqueados para limitar los hosts con los que trabaja [!DNL Target].

Para administrar hosts, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

![imagen hosts_list](assets/hosts_list.png)

## Reconocer hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconocer un host y agregarlo al [!UICONTROL Hosts] lista, se deben cumplir las siguientes condiciones:

* Al menos uno [!DNL Target] la solicitud debe existir en el host
* Una página del host debe tener   lo siguiente:

   * Una referencia precisa de at.js
   * A [!DNL Target] para una solicitud global generada automáticamente [!DNL Target] solicitud

* La página con el [!DNL Target] la solicitud debe verse en un navegador

Una vez vista la página, el host se enumera en la variable [!UICONTROL Hosts] , lo que le permite administrarla en un entorno y previsualizar e iniciar actividades y pruebas.

>[!NOTE]
>
>Esto engloba todos los servidores de desarrollo personal.

Cuando un host se añada a la lista [!UICONTROL Hosts], compruebe si se reconoce.

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador. 


   De forma predeterminada, un host recién reconocido se coloca en la [!UICONTROL Producción] entorno. El [!UICONTROL Producción] El entorno es el entorno más seguro, ya que no permite que se vean actividades inactivas desde estos hosts.

1. (Condicional) Haga clic en **[!UICONTROL Mover]** icono ( ![icono de mover](/help/main/administrating-target/assets/icon-move.png) ) para mover el host a [!UICONTROL Desarrollo], [!UICONTROL Ensayo]u otro entorno.

>[!NOTE]
>
>El [!UICONTROL Producción] El entorno no se puede eliminar aunque se le cambie el nombre. Se da por hecho que en este entorno es donde se proporcionan las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Ordenar o buscar en la lista Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para ordenar los [!UICONTROL Hosts] , haga clic en cualquier encabezado de columna ([!UICONTROL Nombre], [!UICONTROL Entorno], o [!UICONTROL Última solicitud]) para ordenar la lista en orden ascendente o descendente.

Para buscar en [!UICONTROL Hosts] , escriba un término de búsqueda en la lista [!UICONTROL Buscar hosts] cuadro.

## Crear listas de permitidos que especifiquen hosts con autorización para enviar [!DNL Target] solicitudes a [!DNL Target]. {#allowlist}

Puede crear una lista de permitidos que especifique los hosts (dominios) con autorización para enviar [!DNL Target] solicitudes a [!DNL Target]. Todos los demás hosts que generan solicitudes obtienen una respuesta de error de autorización comentada. De forma predeterminada, cualquier host que contenga un [!DNL Target] solicitar registros con [!DNL Target] en el [!UICONTROL Producción] y tiene acceso a todas las actividades activas y aprobadas. Si no desea este método, puede utilizar la lista de permitidos para registrar los hosts específicos que pueden realizar [!DNL Target] solicitudes y recepción [!DNL Target] contenido. Todos los hosts seguirán mostrándose en la [!UICONTROL Hosts] Los entornos y se pueden seguir utilizando para agrupar estos hosts y asignar niveles diferentes a cada uno, como si el host puede ver actividades activas o inactivas.

Para crear una lista de permitidos:

1. Desde el [!UICONTROL Hosts] , haga clic en **[!UICONTROL Autorizar hosts]**.
1. Habilite la **[!UICONTROL Habilitar hosts autorizados para la entrega de contenido]** alternar.
1. Añada los hosts que desee en **[!UICONTROL El host contiene]** , como desee.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Añada los hosts que desee en **[!UICONTROL El host no contiene]** , como desee.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Guardar]**.

Si un [!DNL Target] la solicitud se realiza en un host no autorizado, la llamada responde con `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Prácticas recomendadas de seguridad**: Si utiliza la funcionalidad ubox de [!DNL Target], esta lista de permitidos también controla la lista de dominios a los que se [redirectores](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank} puede navegar. Asegúrese de agregar los dominios a los que desee redirigir al utilizar ubox como parte de la implementación. Si no se especifica la lista de permitidos, [!DNL Adobe] no puede verificar las direcciones URL de redireccionamiento y protegerlo de posibles redireccionamientos malintencionados.
>
>La lista de permitidos tiene prioridad sobre los entornos. Borre todos los hosts antes de utilizar la función de lista de permitidos y, a continuación, en la lista de hosts solo aparecerán los hosts permitidos por la lista de permitidos. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Si el dominio llama a at.js, aparecerá un dominio en la lista. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. Si no se pasa ningún entorno, el valor predeterminado del host de la llamada será [!UICONTROL Producción].

También puede crear una lista de bloqueados de que especifique los hosts (dominios) que no pueden enviar [!DNL Target] solicitudes a [!DNL Target] añadiendo los hosts deseados en [!UICONTROL El host no contiene] cuadro.

>[!NOTE]
>
>El [!UICONTROL Hosts autorizados] La lista se utiliza para [!DNL Target] hosts y hosts de redireccionamiento predeterminados. Añadir todos los dominios existentes aprobados para utilizar el [!DNL Adobe Target] SDK de JavaScript (at.js) *Y* todos los dominios utilizados en las URL de redireccionamiento predeterminadas de ubox. Añada nuevos dominios similares a la lista de permitidos en el futuro.

## Eliminación de un host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. Desde el [!UICONTROL Hosts] , haga clic en **[!UICONTROL Eliminar]** icono.
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>El host vuelve a aparecer en la lista si alguien abre una página que contiene un [!DNL Target] en el host.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de su cuenta.**

* Actualice la página [!UICONTROL Hosts] en el navegador.
* Confirme que la variable [!DNL Target] la solicitud es correcta, incluida la referencia de at.js.
* Intente navegar a uno de los [!DNL Target] solicitudes en el host. Es posible que no [!DNL Target] La solicitud del host se ha procesado alguna vez en un explorador.

**La lista [!UICONTROL Hosts] contiene dominios aleatorios o desconocidos.**

Si una solicitud a aparece un dominio en esta lista [!DNL Target] se crea desde el dominio. Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. En caso de que el dominio incluido en la lista no sea uno de los que el equipo usa, puede hacer clic en [!UICONTROL Eliminar] para eliminarlo.

**Mis [!DNL Target] solicitar devoluciones /&#42; sin visualización: host de mbox no autorizado &#42;/.**

Si un [!DNL Target] la solicitud se realiza en un host no autorizado, la solicitud responde con /&#42; sin visualización: host de mbox no autorizado &#42;/.
