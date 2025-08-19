---
keywords: mvt; prueba multivariable; crear prueba multivariable; creación de prueba multivariable; crear mvt; creación de mvt, procedimiento de mvt; procedimiento de prueba multivariable
description: Aprenda a usar el [!UICONTROL Visual Experience Composer] (VEC) en  [!DNL Adobe Target] para crear un [!UICONTROL Multivariate Test] (MVT).
title: ¿Cómo creo un(a) [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 56%

---

# Crear una prueba multivariable

El [!UICONTROL Visual Experience Composer] (VEC) de [!DNL Adobe Target] facilita la creación de [!UICONTROL Multivariate Test] y la modificación de partes de la página en [!DNL Target].

El editor de apuntar y hacer clic [!DNL Target] le permite elegir cualquier ubicación y agregar varias ofertas.

[!UICONTROL Multivariate Test] (MVT) toma un informe centrado en una página. Es decir, la prueba se ejecuta en una determinada dirección URL, con las experiencias que diseño para esa página.

1. Haga clic en **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   ![Crear una prueba multivariada](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Para obtener más información sobre los distintos tipos de actividades disponibles en [!DNL Target] y sus diferencias, consulte [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/main/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad encaja con sus necesidades.

1. (Condicional) Elija el tipo de entrega: [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email] o [!UICONTROL Other/API].

1. (Condicional) Si es cliente de [Target Premium](/help/main/c-intro/intro.md#premium), [elija un espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique la dirección URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) para la página que desea probar y haga clic en **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >Utilice una dirección URL completa, incluido HTTP o HTTPS del principio.

   Si aparece un mensaje pidiendo que habilite el navegador para contenido mixto, siga las instrucciones del mensaje. Después de habilitar el navegador para contenido mixto, vuelva a comenzar por el Paso 1.

   Se abre [!UICONTROL Visual Experience Composer].

1. Escriba un nombre para la actividad.

   ![Campo Nombre de la actividad](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   El nombre de la actividad no puede comenzar con ninguno de los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

   El nombre de la actividad no puede contener ninguna de estas secuencias de caracteres:

   | Secuencia de caracteres | Descripción |
   |--- |--- |
   | ;= | Punto y coma, igual a |
   | ;+ | Punto y coma, más |
   | ;- | Punto y coma, menos |
   | ;@ | Punto y coma, signo de arroba |
   | ,= | Coma, igual a |
   | ,+ | Coma, más |
   | ,- | Coma, menos |
   | ,@ | Coma, Signo de arroba |
   | `[`&quot; | Corchete de apertura, comillas dobles |
   | &quot;`]` | Comillas tipográficas dobles, cerrar corchete |

1. [Cree las ofertas en cada ubicación](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Cuadro de diálogo Editar texto/HTML](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Puede añadir los siguientes tipos de oferta:

   * HTML
   * Imagen
   * Texto

1. Haga clic en **[!UICONTROL Preview]** para [obtener una vista previa de sus experiencias](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Previsualizar experiencias](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Puede ver cada experiencia y excluir aquellas que no quiere incluir en la prueba. Para excluir una o más experiencias, seleccione las casillas que desee y luego haga clic en **[!UICONTROL Exclude]**

   ![Excluir experiencias](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Utilice el estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para probar la viabilidad de su plan de prueba.

   ![Indicador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   La siguiente ilustración indica que la actividad no tiene tráfico suficiente.

   ![imagen del estimador](assets/estimator.png)

   La siguiente ilustración indica que la actividad no tiene tráfico suficiente.

   ![estimador2 imagen](assets/estimator2.png)

1. Haga clic en **[!UICONTROL Next]** para avanzar a la página [!UICONTROL Targeting].

1. Elija la audiencia y el porcentaje de visitantes correspondiente que desea que participen de la actividad.

   ![Página de segmentación en actividad MVT](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % de la audiencia de California.

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Revise el resumen de la prueba](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7), realice los cambios que desee y luego haga clic en **[!UICONTROL Next]**.

1. [Especifique los objetivos y la configuración](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) para la prueba.

1. Haga clic en **[!UICONTROL Save and Close]** para crear la actividad.

## Vídeo de formación: Creación de pruebas multivariable (9:25) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se muestra cómo planificar y crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/17395)
