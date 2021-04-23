---
keywords: kit de bienvenida;kit de bienvenida de target;introducción;introducción;introducción
description: Lea sugerencias de nuestro panel de expertos sobre el uso de Adobe [!DNL Target] como parte de sus esfuerzos de prueba y personalización.
title: ¿Dónde puedo encontrar consejos y trucos para usar Target?
feature: Información general
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2898'
ht-degree: 0%

---

# Capítulo 4: Sugerencias para usar Target

Basándonos en nuestro trabajo con muchos usuarios de [!DNL Target], hemos observado maneras de obtener más valor de su solución [!DNL Target]. Hemos resumido estos consejos en las muchas sugerencias que hemos incluido en este capítulo. Aunque puede que no esté listo para usar todas estas ideas de inmediato, manténgase en esta lista. Cuanto más experiencia adquiera con la solución y cuanto más madure su programa, más verá cómo estas sugerencias pueden ayudarle a lograr más con [!DNL Target].

## Sugerencia 1: Una personalización más profunda mediante el aumento del perfil del visitante con datos adicionales.

Puede personalizar experiencias con datos [!DNL Target] directamente de serie. Pero personalice más profundamente agregando sus propios datos a la mezcla. Puede aumentar el perfil con datos históricos de [!DNL Adobe Analytics] y datos en tiempo real de [!DNL Adobe Audience Manager]. También puede usar Atributos del cliente, una función del servicio principal Personas de [!DNL Adobe Experience Cloud], para incorporar fácilmente datos CRM, datos de socios de segundo nivel y datos comprados de terceros a [!DNL Target].

Por ejemplo, puede asociar datos de compra de su sistema de puntos de venta con un perfil del visitante. Para ello, simplemente cree un archivo CSV con hasta 200 variables sin conexión y cárguelo directamente en [!DNL Adobe Experience Cloud] a través de una carga de archivo, o utilice FTP para alojar y programar el archivo para que se actualice con regularidad. Una vez que los Atributos del cliente se encuentran en [!DNL Adobe Experience Cloud], puede asignarlos a soluciones de [!DNL Experience Cloud] como [!DNL Adobe Analytics] y [!DNL Target], donde estarán disponibles para análisis, pruebas y personalización.

Consulte [Atributos personalizados](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) para obtener instrucciones paso a paso.

**Es bueno saber**: Como  [!DNL Target] es una plataforma abierta y agnóstica que funciona bien con diferentes tecnologías, puede agregar CRM o datos comprados de muchas maneras diferentes. Esto significa que puede elegir un método que funcione mejor para su organización.

Consulte [Métodos para obtener los datos en Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obtener más información.

## Sugerencia 2: Personalice más profundamente mezclando audiencias [!DNL Target] con otras audiencias de Adobe Experience Cloud.

La combinación de audiencias que residen en diferentes soluciones [!DNL Adobe Experience Cloud] puede ofrecerle una comprensión mucho más amplia de sus clientes, así como la capacidad de personalizar más profundamente. Por ejemplo, aunque [!DNL Target] proporciona datos de audiencia en tiempo real, [!DNL Adobe Analytics] proporciona datos de audiencia históricos. La combinación de ambos puede ayudarle a identificar cuándo el comportamiento de un cliente es coherente y cuándo puede haber una oportunidad para actuar en un nuevo comportamiento. Simplemente haga clic en el menú desplegable situado junto a &quot;Todos los visitantes&quot; al crear una actividad. A continuación, marque las casillas de hasta veinte audiencias, haga clic en &quot;Combinar varias audiencias&quot; y haga clic en &quot;Guardar&quot;.

Consulte [Combinación de varias audiencias](/help/c-target/combining-multiple-audiences.md) para obtener instrucciones paso a paso.

**Es bueno saber**:  [!DNL Adobe Audience Manager] las audiencias están disponibles en  [!DNL Target] automáticamente. Sin embargo, el uso compartido de audiencias [!DNL Adobe Analytics] requiere un poco de configuración manual. Simplemente marque la casilla denominada &quot;Convertir en una audiencia Experience Cloud&quot; durante el proceso de creación de audiencias en [!DNL Analytics]. A continuación, en [!DNL Target], haga clic en &quot;Importar audiencias de Experience Cloud&quot;.

## Sugerencia 3: Exporte datos de [!DNL Target] para usarlos con herramientas de terceros.

Con los tokens de respuesta, los administradores pueden obtener datos fácilmente de [!DNL Target] y en herramientas de terceros. Esto puede resultar útil cuando desea agregar los datos a los datos recopilados en una herramienta de encuesta. Por ejemplo, si un estudio muestra una muestra de una población que obtuvo una experiencia como &quot;9&quot; y otro obtuvo una experiencia como &quot;4&quot;, puede utilizar los datos para ver quién vio la experiencia A y quién vio la experiencia B. También puede utilizar tokens de respuesta para exportar datos [!DNL Target] al almacén de datos interno. Simplemente haga clic en &quot;Administración&quot; y luego coloque el conmutador situado junto al token de respuesta deseado en la posición ON. A continuación, cree una actividad . Los datos están listos para transferirse al proveedor de terceros. Puede verificar que [!DNL Target] esté exportando los datos mediante herramientas de depuración.

Consulte [Tokens de respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Sugerencia** útil: Para que un administrador pueda activar un token de respuesta asociado a un tercero, un desarrollador debe configurar una asociación con esa empresa de terceros.

Consulte [Tokens de respuesta](/help/administrating-target/response-tokens.md) para obtener instrucciones paso a paso.

**Haga esto primero**: Asegúrese de que está utilizando la versión 1.1 o posterior de at.js . Si utiliza una versión anterior, verá los tokens de respuesta, pero at.js no podrá utilizarlos.

## Sugerencia 4: Cree audiencias a partir de estas variables clave para aumentar el valor de la actividad.

Al crear audiencias para segmentar o probar promociones y ofertas, considere primero estas variables:

* Comportamiento. Patrones de visita al sitio y patrones de compra
* Referrer. Sitios de referencia y campañas
* Temporal. Tiempos del día, días de la semana y factores de temporada
* Sin conexión. Patrones de visita y compra en tiendas físicas
* Entorno. País de origen, sistema operativo, tipo de navegador

## Sugerencia 5: Proporcione a los usuarios el nivel de acceso que necesitan para realizar su trabajo.

Facilite el trabajo con los datos de su organización y mantenerlos seguros. [!DNL Target Premium] permite a los administradores controlar el nivel de acceso dado a diferentes equipos internos y externos.

Consulte [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) para obtener más información.

**Sugerencia** útil: Al agregar usuarios, si el nombre de un miembro del equipo no se ha agregado previamente a su organización (como puede ser el caso de un empleado de una agencia de terceros), al introducir su dirección de correo electrónico y contraseña, se envía una invitación por correo electrónico para unirse al espacio de trabajo de un equipo.

¿Usar Target Standard? Aún puede [asignar tres niveles de acceso](/help/administrating-target/c-user-management/c-user-management/user-management.md) a los usuarios con funciones de solo lectura, editor y aprobador.

## Sugerencia 6: Descubra el rendimiento de una oferta en un recorrido de clientes probándolo en todas las páginas del recorrido.

Ver el rendimiento de una oferta, como envío gratuito, durante un recorrido con el cliente que se produce en varias páginas del sitio web.

Consulte [Actividad de varias páginas](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) para obtener instrucciones paso a paso.

**Sugerencia** útil: Si cambia la dirección URL después de especificar un intervalo de páginas, se restablecerá la experiencia. Esto significa que las variaciones que ha especificado ya no aparecerán. Si necesita cambiar la dirección URL, recuerde redefinir la experiencia.

## Sugerencia 7: Pruebe una oferta con distintas audiencias para descubrir si las audiencias tienen preferencias diferentes.

Con las versiones de experiencia, puede ejecutar una prueba con variaciones para tantas audiencias como desee. Por ejemplo, puede crear una publicidad tipo titular que ofrezca envío gratuito (con imágenes y variaciones de moneda para clientes de EE.UU., Reino Unido y EE.UU.) sin tener que ejecutar pruebas para tres audiencias diferentes.

Consulte para [Varias audiencias de experiencia en una prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) y [Versiones de experiencia en Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obtener instrucciones paso a paso.

## Sugerencia 8: Ahorre tiempo replicando experiencias de actividad en páginas similares.

Cree una variación en una página web, como un nuevo color de botón, y aplíquelo automáticamente a todas las páginas que compartan la misma plantilla. Puede especificar páginas o aplicar las variaciones a todas las páginas similares del sitio web.

Consulte [Incluir la misma experiencia en páginas similares](/help/c-experiences/c-visual-experience-composer/temtest.md) para obtener instrucciones paso a paso.

## Sugerencia 9: Reduzca el desorden en la biblioteca de audiencias creando audiencias únicas.

Si va a segmentar un segmento que sabe que no se volverá a dirigir (por ejemplo, clientes afectados por un evento meteorológico inesperado), la creación de una audiencia de un solo uso puede ayudarle a realizar el trabajo sin necesidad de agregar desorden a la biblioteca de audiencias. Esto facilita la búsqueda de audiencias que utiliza una y otra vez.

Consulte [Crear una audiencia solo de actividad](/help/c-target/creating-activity-only-audience.md) para obtener instrucciones paso a paso.

**Capacidad** muy solicitada: Nuestros clientes nos pidieron que permitiéramos evitar que las audiencias de un solo uso se guardaran automáticamente en la Biblioteca de audiencias. Ahora, ya no tienen que eliminar audiencias manualmente para mantener sus bibliotecas organizadas.

## Sugerencia 10: Ejecute pruebas simples más rápido, ya que no las somete al proceso de control de calidad estándar.

No hay nada peor que tener una actividad lista para ir y luego esperar semanas para que complete el proceso estándar de control de calidad. Puede realizar el control de calidad de la mayoría de las actividades simplemente pasando unos cuantos vínculos de control de calidad a compañeros para probarlos en varios navegadores. Lo más probable es que quiera realizar más pruebas de control de calidad para los esfuerzos que cambian drásticamente la función del sitio, pero en realidad, debería tener menos de esas actividades y muchas más de las más básicas. Añadir mejores controles de derechos para que menos personas puedan impulsar las cosas en su totalidad también añade límites significativos y le permite realizar lo que necesita sin sacrificar la velocidad y la eficiencia. Otra opción es disponer de un recurso de TI designado para supervisar oportunamente el proceso de control de calidad.

Consulte [Control de calidad de la actividad](/help/c-activities/c-activity-qa/activity-qa.md) para obtener instrucciones paso a paso.

## Sugerencia 11: Ejecute pruebas en páginas de alto tráfico para que alcancen la relevancia estadística más rápidamente.

Muchos especialistas en marketing inician programas de optimización para segmentación de audiencia y segmentación sin comprobar si los niveles de tráfico y las audiencias representadas proporcionarán resultados significativos dentro del marco temporal de prueba para sus objetivos de optimización y conversión. Para evitar este error común, responda a estas preguntas con antelación:

* ¿Cuántos visitantes únicos diarios tiene la página?
* ¿Cuál es la tasa de conversión de la página?
* ¿Cuánto tiempo espera que se ejecute la prueba antes de que pueda llamarla completa con seguridad?

**Sugerencia útil**: Utilice el  [calculador de tamaño de la ](https://docs.adobe.com/content/target-microsite/testcalculator.html) muestra de Target para determinar el tamaño de la muestra necesario para una prueba con éxito.

## Sugerencia 12: Diseñe pruebas más sencillas para asegurarse de que puede crearlas e implementarlas.

Después de considerar todos los aspectos de cómo diseñar una prueba, un plan puede ser muy complejo. En función de dónde esté su negocio con las pruebas y de la capacidad de su grupo para diseñar, codificar, ejecutar y analizar los resultados, determine si la prueba parece demasiado ambiciosa. En caso afirmativo, esté preparado para reducir su alcance y complejidad. Es mejor comenzar con un tamaño pequeño que no realizar la prueba en absoluto. No puede proporcionar un alza impactante si nunca inicia la prueba. Es importante equilibrar las aspiraciones del equipo con las realidades de sus recursos y capacidades.

## Sugerencia 13: Divida pruebas complejas en actividades de prueba más pequeñas para que sean alcanzables.

En lugar de desarrollar una prueba de gran tamaño con múltiples variables y desarrollo complejo, desarrolle una serie menos compleja de pruebas más pequeñas con variables mínimas. Esto permite una comprensión más profunda del rendimiento de las pruebas en función de variables específicas. También reduce los posibles problemas técnicos que conlleva el desarrollo de proyectos más grandes.

![Ilustración de pruebas complejas](/help/c-intro/assets/break-complex-tasks.png)

## Sugerencia 14: Maximice el impacto de la prueba realizando pruebas más cerca del final del canal de conversión.

Realizar pruebas tan cerca de la página en la que los visitantes hacen clic en Completar compra, Enviar solicitud o completar de otro modo una conversión tiende a ofrecer los resultados más impactantes. Los visitantes que llegan al final del canal están más cualificados, han invertido más tiempo y están listos para realizar compras, por lo que probar perspectivas sobre sus preferencias y acciones puede ayudarle a realizar cambios rentables. Dado que las páginas en la ruta de compra son críticas para las tasas de conversión, las pruebas que se realicen en esas páginas deben socializarse con las partes interesadas clave antes de implementarlas.

![Ilustración del canal de conversión](/help/c-intro/assets/conversion-funnel.png)

## Sugerencia 15: Actualice constantemente las pruebas para realizar mejoras iterativas.

Si la hipótesis no ha demostrado ser verdadera, piense en formas de mejorar la prueba. Recuerde que aunque ninguna de las experiencias probadas funcionara mejor, su experimento no era una pérdida de tiempo. Una prueba con éxito no siempre significa un aumento de ingresos o conversiones. Si la prueba realmente apoyó su hipótesis, entonces usted está en camino a desarrollar una teoría general. Pero incluso cuando tenga un claro resultado ganador, no se detenga allí. Con demasiada frecuencia, los especialistas en marketing cometen el error de probar de una vez y luego confiar en esos resultados sin comprender realmente qué llevó al éxito. En cambio, planee repetir esos resultados para averiguar por qué el favorito estaba por delante. Esto le llevará a perspectivas más profundas que puede usar en campañas futuras.

## Sugerencia 16: Compare pruebas y actividades de personalización para obtener ideas y mejorar la segmentación.

La comparación del rendimiento de conversión de distintas audiencias dentro de distintas pruebas en diferentes ubicaciones puede ayudar a enfocar y refinar la estrategia de optimización de una empresa. Utilice comparaciones de prueba para identificar qué audiencias son las más valiosas de probar, qué deben recibir experiencias segmentadas y qué tipos de experiencias tienen más probabilidades de generar una respuesta.

Por ejemplo, un cliente de servicios financieros dirigió una campaña promocional para una tarjeta de crédito que incluía incentivos profesionales para eventos deportivos. Mediante pruebas multivariable factoriales parciales de sus páginas de aterrizaje, el cliente pudo equilibrar de forma óptima la mensajería sobre los beneficios de las tarjetas de crédito con incentivos deportivos para dirigirse a distintas audiencias desde su base de clientes. Este método permitió a la empresa aprovechar y maximizar la conversión durante una ventana en la que el evento deportivo principal se encontraba en una situación de tiempo delicado.

## Sugerencia 17: Haga que las pruebas sean útiles al iniciarlas únicamente si sabe que puede actuar con los datos.

Una prueba no tiene sentido si no está claro cómo va a actuar en los datos. Esto incluye saber cuál es la métrica de éxito clave, qué debe suceder para impulsar a un ganador, cómo seguirá los resultados de las pruebas y qué hará con la información de audiencia. Para una prueba rápida y exitosa, es vital que todos los grupos involucrados en la prueba (desarrolladores, creativos, especialistas en pruebas y otros) conozcan su papel antes del inicio de la prueba.

## Sugerencia 18: Antes de iniciar una prueba, asegúrese de que la empresa admita el impulso del ganador.

Las organizaciones de optimización exitosas creen en el concepto de las pruebas y entienden que sus opiniones profesionales sobre qué experiencia ganará la prueba no siempre son ciertas. Determinan el ganador en función de una base de datos sólida y están ansiosos y dispuestos a impulsar la experiencia ganadora en vivo después de que los resultados se hayan obtenido, aunque no esté en línea con sus expectativas o parezca contrario a la intuición.

Por ejemplo, un cliente de servicios de atención médica de Adobe demostró recientemente el valor de las pruebas mostrando cómo un banner a pantalla completa que el equipo había considerado un dunk en realidad impactó negativamente en la conversión. Si su organización aún no ha adoptado plenamente las pruebas, es mejor realizar primero pruebas de ámbito más simples y más pequeñas para que los cambios de los resultados de las pruebas se puedan realizar gradualmente.

## Sugerencia 19: Comunique a todos que ha iniciado una prueba para evitar preocuparse cuando cambie el sitio.

Una de las ventajas de configurar las actividades para que utilicen parámetros de control de calidad es que puede compartir esos vínculos con todos los miembros de su equipo. Considere la actividad y asegúrese de que no supone que el sitio no funciona correctamente cuando visita una variante de prueba.

Una vez finalizadas las pruebas, la comunicación de los lanzamientos de las campañas, los resultados de las pruebas y, en especial, las lecciones aprendidas, le ayuda a crear conciencia de los resultados de las pruebas y a interesarse por ellos. Compartir los resultados con todos los miembros de la organización también evita volver a probar una hipótesis, educa a todos sobre lo que funciona y los ayuda a desafiar fundamentalmente sus propias ideas sobre lo que funciona basándose en lo que ha encontrado. Es aconsejable preparar una plantilla que utilice cada vez para compartir sus conclusiones y aprendizajes clave.
A continuación, considere la posibilidad de crear un libro que se pueda compartir o Microsoft PowerPoint que capture acumulativamente estos conocimientos.

## Sugerencia 20: Aproveche la funcionalidad móvil para crear actividades móviles más innovadoras.

Las experiencias de los usuarios de tableta y smartphones deben centrarse en los controles táctiles como la interacción principal del visitante en lugar de los clics del ratón y los controles de teclado. Aproveche los controles de visualización móviles, incluidos el desliz, el tacto, el arrastre, el pellizco y el zoom. Utilice botones grandes y simples para designar las interacciones y la navegación, como un carro de compras grande o un botón de reproducción de vídeo. Si diseña para minoristas móviles, incorpore una visualización de producto enriquecida que esté optimizada para el tipo de dispositivo. Siempre busque oportunidades para cambiar el enfoque de la experiencia del usuario a visores integrados, grandes o con zoom y panorámica interactivos de pantalla completa, giros de 360 grados y funciones de vídeo mejoradas.

## Sugerencia 21: Ayudar a los visitantes móviles a encontrar lo que desean optimizando la búsqueda móvil.

Los usuarios de móviles tienen una intención alta. La mayoría de ellos utilizan la búsqueda antes de hacer cualquier otra cosa en los sitios de comercio electrónico, lo que hace que la optimización de la búsqueda en sitios móviles sea crucial. Para mejorar la optimización de los motores de búsqueda (SEO) para móviles, utilice indicaciones de navegación explícitas para facilitar la navegación. Además, implemente la sugerencia automática y la corrección automática en los cuadros de entrada de búsqueda para resolver la dificultad de escribir en dispositivos móviles. Proporcionar resultados de búsqueda relevantes y convincentes optimizados para el tamaño y la ubicación de la pantalla.

## Sugerencia 22: Llegue a las audiencias móviles mejor mediante el targeting de hora del día para campañas SEM móviles.

Conozca cómo y cuándo llegar a su audiencia y cómo administrar mejor su gasto en publicidad diaria dividiendo sus campañas móviles en distintos segmentos a lo largo del día.

Muchos especialistas en marketing cometen el error de no asignar suficiente presupuesto para capturar esa parte de voz en las horas en que el uso de dispositivos particulares es más pesado, dejando así muchos ingresos y posibles clientes sobre la mesa.

Por ejemplo, el uso de tabletas suele aumentar en el horario nocturno y muchos usuarios navegan mientras ven la televisión. Por el contrario, los usuarios de smartphones suelen acceder al contenido sobre la marcha. Los tiempos de máxima conversión también varían según el sector, por lo que es importante comprender cuándo es más probable que actúen sus clientes únicos.

## Recuerde

Considere las siguientes ideas antes de pasar al siguiente capítulo: &quot;Inspiración para pruebas y actividades de personalización&quot;.

### Cuando cree las pruebas, no decore, sea intencional.

* Controle el flujo con rutas oculares intencionales centradas en los puntos de conversión.
* Asegúrese de usar su Inmobiliaria para su ventaja.
* Aproveche el enfoque de la imagen para asegurarse de que las imágenes no sean decorativas, sino que funcionan para usted.
* Reduzca el desorden, la fricción y la desenfoque con Copia simplificada.
* Asegúrese de que tiene Llamadas a acciones efectivas cuando necesite que el usuario tome medidas.
* Añada credibilidad a través del Contenido generado por el usuario siempre que sea posible.

### Simplifique el sitio web.

* No &quot;haga&quot; que los clientes lean. No lo harán.
* Facilitar el escaneo.
* Utilice bloques de copia con viñetas.
* Asegúrese de que su copia sigue un proceso de pensamiento claro y secuencial.

### Utilizar Llamada a acción efectiva

* Pónganse en los zapatos del cliente.
* Utilice un lenguaje orientado a la acción.
* Tenga en cuenta la motivación de la conversión.
* Abordar el resultado de la conversión.
* ¡Asegúrese de que se vean los CTA!
