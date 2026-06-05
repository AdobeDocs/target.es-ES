---
keywords: público;reglas de público;crear público;creación de público
description: Aprenda a crear audiencias personalizadas y a guardarlas en la biblioteca  [!DNL Adobe Target] [!UICONTROL Audiencias] para usarlas en las actividades.
title: ¿Cómo Se Generan Audiencias?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
TQID: https://experienceleague.adobe.com/-t5UqbGCl2EwCyScCq1B8X9bWxQQYWSd0e7RBoUoYQg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 538
ht-degree: 50%

---

# Generar audiencias en [!DNL Target]

Cree audiencias personalizadas y guárdelas en la biblioteca [!DNL Adobe Target] [!UICONTROL Audiencias] para usarlas en sus actividades. También puede copiar una audiencia existente y editarla para crear una similar y combinar varias audiencias.

## Información general de público

Los públicos están definidos por reglas que determinan quién se incluye o excluye de una actividad de [!DNL Target]. Una definición de audiencia puede incluir varias reglas y cada regla puede incluir varios parámetros. Las definiciones de audiencias complejas usan operadores booleanos Y y O para combinar reglas y parámetros para otorgarle un control detallado sobre qué visitantes del sitio se cuentan como participantes de actividades.

Cuando combina reglas o parámetros con AND, cualquier posible miembro de la audiencia debe cumplir *todas* las condiciones definidas para que se incluya como participante. Por ejemplo, si define una regla de sistema operativo AND (y) una regla de navegador, solo se incluyen en la actividad los visitantes que usan el sistema operativo *y* el navegador especificados.

Cuando se combinan reglas o parámetros con O, cualquier miembro potencial de la audiencia solamente necesita cumplir cualquier condición única definida para que se lo incluya como participante. Por ejemplo, si se definen varias reglas móviles conectadas por O, se incluyen en la actividad los visitantes que cumplen *cualquiera* de los criterios definidos.

Puede combinar ambos operadores booleanos para crear reglas complejas; sin embargo, los operadores del mismo nivel de regla deben coincidir. La interfaz de usuario se aplica automáticamente al operador correcto.

Por ejemplo, la siguiente regla segmenta a los visitantes que usan [!DNL Chrome] *o* [!DNL Firefox] en un equipo [!DNL Windows]:

![Crear público](assets/audience_create.png)

>[!NOTE]
>
>Tenga cuidado de evitar crear reglas que excluyen todos los miembros potenciales del público. Por ejemplo, no es posible visitar una página con [!DNL Chrome] *y* [!DNL Firefox] simultáneamente.

## Creación de audiencias

1. Haga clic en **[!UICONTROL Audiencias]** en la barra de menús superior.

   ![imagen audiences_list](assets/audiences_list.png)

1. En la lista [!UICONTROL Audiencias], haga clic en **[!UICONTROL Crear audiencia]**.

   O

   Para copiar una audiencia existente, en la lista [!UICONTROL Audiencias], haga clic en el icono **[!UICONTROL Más acciones]** ( ![Más acciones](/help/main/assets/icons/MoreSmallListVert.svg) ) de la audiencia que desee copiar y, a continuación, haga clic en **[!UICONTROL Duplicar]**. Luego puede editar el público para crear otra parecida.

1. Escriba un nombre descriptivo y único para la audiencia, así como una descripción opcional.

   Los nombres de audiencia no pueden comenzar con los siguientes caracteres:

   `=  +  -  !  @`

   Los nombres de audiencia no pueden contener ninguna de las siguientes secuencias de caracteres:

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  ['  ]'`

1. Arrastre y suelte los atributos deseados de la lista **[!UICONTROL Atributos]** de la izquierda al panel Generador de audiencias.

   ![Arrastrar y soltar atributos](assets/drag-attribute.png)

   Cada tipo de regla tiene sus propios parámetros. Consulte [Categorías para públicos](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obtener más información sobre cómo configurar cada tipo de regla de público.

1. Defina los parámetros de la regla.

   Por ejemplo, la siguiente audiencia identifica visitantes de Utah que usan el sistema operativo [!DNL Macintosh].

   ![Audiencia de Utah/Macintosh](assets/adience-builder.png)

1. (Condicional) Siga agregando y definiendo los atributos deseados.

   Para crear otro contenedor, haga clic en **[!UICONTROL Agregar contenedor]** o simplemente arrastre otro atributo al panel Generador de audiencias. A continuación, se puede ajustar el operador (AND u OR) mediante la lista desplegable.

1. Haga clic en **[!UICONTROL Finalizado]**.

   Los públicos recién creados aparecen en la lista tras unos segundos de retraso en el procesamiento. Si la audiencia no aparece en la lista inmediatamente, pruebe a buscarla o actualice la lista.

## Vídeo de formación: Creación de audiencias ![Distintivo de información general](/help/main/assets/overview.png)

Este vídeo contiene información sobre la creación de audiencias.

* Crear públicos
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
