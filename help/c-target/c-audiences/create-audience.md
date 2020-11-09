---
keywords: audience;audience rules;create audience;creating audience
description: Puede crear audiencias personalizadas y guardarlas en la biblioteca de Target para usarlas en las actividades. Puede copiar una audiencia existente que después puede editar para crear una audiencia parecida y combinar varias.
title: Crear audiencias en Target
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 99%

---


# Crear audiencias en Target{#build-audiences-in-target}

Puede crear audiencias personalizadas y guardarlas en la biblioteca de Target para usarlas en las actividades. Puede copiar una audiencia existente que después puede editar para crear una audiencia parecida y combinar varias.

## Información general de audiencia

Las audiencias están definidas por reglas que determinan quién se incluye o excluye de una actividad de [!DNL Target]. Una definición de audiencia puede incluir varias reglas y cada regla puede incluir varios parámetros. Las definiciones de audiencias complejas usan operadores booleanos Y y O para combinar reglas y parámetros para otorgarle un control detallado sobre qué visitantes del sitio se cuentan como participantes de actividades.

Cuando se combinan reglas o parámetros con Y, cualquier miembro potencial de la audiencia debe cumplir *todas* las condiciones definidas para que se le incluya como participante. Por ejemplo, si define una regla de sistema operativo AND (y) una regla de navegador, solo se incluyen en la actividad los visitantes que usan el sistema operativo *y* el navegador especificados.

Cuando se combinan reglas o parámetros con O, cualquier miembro potencial de la audiencia solamente necesita cumplir cualquier condición única definida para que se lo incluya como participante. Por ejemplo, si se definen varias reglas móviles conectadas por O, se incluyen en la actividad los visitantes que cumplen *cualquiera* de los criterios definidos.

Puede combinar ambos operadores booleanos para crear reglas complejas; sin embargo, los operadores del mismo nivel de regla deben coincidir. La interfaz de usuario se aplica automáticamente al operador correcto.

Por ejemplo, la siguiente regla segmenta a los visitantes que usan Chrome *o* Firefox en un equipo Windows:

![Crear audiencia](assets/audience_create.png)

>[!NOTE]
>
>Tenga cuidado de evitar crear reglas que excluyen todos los miembros potenciales de la audiencia. Por ejemplo, no es posible visitar una página con los navegadores Chrome *y* Firefox simultáneamente.

## Creación de una nueva audiencia

1. Haga clic en **[!UICONTROL Audiencias]** en la barra de menú superior.

   ![](assets/audiences_list.png)

1. En la lista [!UICONTROL Audiencias], haga clic en **[!UICONTROL + Crear audiencia]**.

   O

   Para copiar una audiencia existente, en la lista [!UICONTROL Audiencias], pase el ratón sobre la audiencia que quiera y luego haga clic en el icono **[!UICONTROL Copiar]**. Luego puede editar la audiencia para crear otra parecida.

1. Escriba un nombre descriptivo y único para la audiencia.
1. Haga clic en **[!UICONTROL + Agregar regla]**.

   Las reglas permiten limitar la audiencia a un subconjunto de los visitantes del sitio.
1. Seleccione un tipo de regla.

   Cada tipo de regla tiene sus propios parámetros. Consulte [Categorías para audiencias](/help/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obtener más información sobre cómo configurar cada tipo de regla de audiencia.
1. Defina los parámetros de la regla.
1. Haga clic en **[!UICONTROL Guardar]**.

   Las audiencias recién creadas aparecen en la lista tras unos segundos de retraso en el procesamiento. Si la audiencia no aparece en la lista inmediatamente, pruebe a buscarla o actualice la lista.

## Vídeo de formación: Creación de audiencias ![Distintivo de información general](/help/assets/overview.png)

Este vídeo contiene información sobre la creación de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)