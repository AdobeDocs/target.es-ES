---
keywords: Script de perfil;atributos de script de perfil;actividades mutuamente excluyentes
description: Aprenda a utilizar atributos de perfil para configurar pruebas en Adobe [!DNL Target] que comparen varias actividades pero no permitan que los mismos visitantes participen en cada actividad.
title: ¿Puedo usar scripts de perfil para probar actividades mutuamente exclusivas?
feature: Audiencias
exl-id: b0b23887-3339-411e-9f5c-64f9d1ba778c
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 74%

---

# Uso de scripts de perfil para probar actividades mutuamente exclusivas

Puede usar atributos de perfil en [!DNL Adobe Target] para configurar pruebas que comparen dos o más actividades pero no permitan que los mismos visitantes participen en cada actividad.

La prueba de actividades mutuamente exclusivas evita que un visitante de una campaña afecte a los resultados de la prueba para el resto de actividades. Cuando un visitante participa en diversas actividades, puede resultar difícil determinar si se ha producido un alza positiva o negativa de la experiencia del visitante con una actividad o si interacciones entre varias actividades han afectado a los resultados de una o más actividades.

Por ejemplo, puede probar dos áreas del sistema de comercio electrónico. Puede que desee probar a hacer que el botón &quot;Agregar al carro&quot; aparezca rojo en lugar de azul. También puede desear probar un nuevo proceso de cierre de compra que reduzca el número de pasos de cinco a dos. Si ambas actividades tienen el mismo evento de éxito (una compra completada), puede resultar difícil determinar si el botón rojo mejora las conversiones o si las mismas conversiones también aumentan debido al proceso de cierre de compra mejorado. Al separar las pruebas en actividades mutuamente exclusivas, puede probar cada fase de forma independiente.

Tenga en cuenta la siguiente información cuando utilice uno de los siguientes scripts de perfil:

* La secuencia de comandos de perfil debe ejecutarse antes de que la actividad se inicie y la secuencia de comandos no debe modificarse mientras dure la actividad.
* Esta técnica reduce la cantidad de tráfico en la actividad, lo que puede requerir que la actividad se ejecute durante más tiempo. Debe tener en cuenta este hecho cuando calcule la duración de la actividad.

## Configuración de dos actividades

Para clasificar los visitantes en grupos para que cada uno de ellos vea una actividad diferente, debe crear un atributo de perfil. Un atributo de perfil puede clasificar a un visitante en uno de dos o más grupos. Para definir un atributo de perfil denominado “twogroups”, cree la secuencia de comandos siguiente:

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` determina si el atributo de perfil *twogroups* se establece para el visitante actual. Si es así, no es necesario realizar ninguna otra acción.

* `var ran_number=Math.floor(Math.random() *99)` declara una nueva variable denominada ran_number, configura su valor en un decimal aleatorio entre 0 y 1 y, a continuación, lo multiplica por 99 y lo redondea a la baja para crear un rango de 100 (0-99) que resulta útil para especificar el porcentaje de visitantes que ven la actividad.

* `if (ran_number <= 49)` comienza una rutina que determina el grupo al que pertenece el visitante. Si el número devuelto está entre 0 y 49, el visitante se asigna a GrupoA. Si el número devuelto está entre 50 y 99, el visitante se asigna a GrupoB. El grupo determina qué actividad ve el visitante.

Después de crear el atributo de perfil, configure la primera actividad para que se dirija a la población deseada. Para ello, es necesario que el parámetro de perfil de usuario `user.twogroups` coincida con el valor especificado para GrupoA.

>[!NOTE]
>
>Seleccione uno de los primeros mbox de la página. Este código determina si un visitante experimenta la actividad. Siempre que el navegador encuentre primero un mbox, se puede utilizar para definir este valor.

Defina la segunda campaña de forma que el parámetro de perfil de usuario `user.twogroups` coincida con el valor especificado para GrupoB.

## Configuración de tres o más actividades

La configuración de tres o más actividades mutuamente exclusivas es similar a la configuración de dos, pero debe modificar el atributo de perfil de JavaScript para crear un grupo independiente para cada actividad y determinar quién ve cada una de ellas. La generación de números aleatorios es diferente en función de si crea un número par o impar de grupos.

Por ejemplo, para crear cuatro grupos, use el siguiente JavaScript:

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

En este ejemplo, la coincidencia que se utiliza para generar el número aleatorio que asigna un visitante a un grupo es la misma que con solo dos grupos. Se genera un decimal aleatorio y, a continuación, se redondea a la baja para crear un número entero.

Si crea un número impar de grupos, o cualquier número que no se divida por 100 de forma equitativa, no deberá redondear el decimal a la baja para obtener un número entero. La falta de redondeo del decimal permite especificar rangos de números no enteros. Para ello, cambie esta línea:

`var ran_number=Math.floor(Math.random()*99);`

a:

`var ran_number=Math.random()*99;`

Por ejemplo, para colocar a los visitantes en tres grupos iguales, use el siguiente código:

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
