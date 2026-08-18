---
date: 2026-08-18
description: Convierta grados decimales a DMS usando Aspose.GIS for .NET. Esta guía
  paso a paso en C# muestra cómo convertir latitud/longitud, grados decimales a DMS
  y más.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Convertir coordenadas
og_description: Conversión de grados decimales a DMS facilitada con Aspose.GIS for
  .NET. Aprenda a transformar valores de latitud‑longitud al formato DMS en minutos.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Convertir grados decimales a DMS con Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Cómo convertir grados decimales a DMS con Aspose.GIS for .NET
url: /es/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo convertir grados decimales a dms con Aspose.GIS

## Introducción
En este tutorial aprenderás **cómo convertir grados decimales a dms** usando la potente biblioteca Aspose.GIS para .NET. Ya sea que necesites **c# convert lat long**, generar cadenas de ubicación legibles para informes, o simplemente explorar diferentes formatos de coordenadas, esta guía te acompaña paso a paso con explicaciones claras y fragmentos de C# listos para ejecutar.

## Respuestas rápidas
- **¿Qué significa “convert coordinates to dms”?** Transforma los valores numéricos de latitud/longitud en la notación tradicional de grados‑minutos‑segundos.  
- **¿Qué biblioteca realiza la conversión?** Aspose.GIS para .NET proporciona la clase `GeoConvert` con soporte integrado de formatos.  
- **¿Necesito una licencia para probarlo?** Hay una prueba gratuita disponible; se requiere una licencia comercial para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, y .NET 5/6+.  
- **¿Puedo usar el mismo código para otros formatos?** Sí, simplemente cambia el valor del enumerado `PointFormats` (p. ej., `DecimalDegrees`, `GeoRef`).  

## ¿Qué es la conversión de coordenadas a dms?
Convertir coordenadas a DMS reescribe los valores decimales de latitud y longitud en un formato como `25°30'00"N 45°30'00"E`. El proceso divide cada grado decimal en grados enteros, minutos (una sesentava parte de un grado) y segundos (una sesentava parte de un minuto), y luego agrega el indicador hemisférico correspondiente (N, S, E, W). Esta forma legible es esencial para muchos conjuntos de datos heredados y para comunicar ubicaciones precisas sin depender de notación decimal.

## ¿Por qué usar Aspose.GIS para la conversión de coordenadas?
Aspose.GIS admite **más de 50 formatos de entrada y salida** y puede procesar archivos GIS de cientos de páginas sin cargar todo el conjunto de datos en memoria. La API ofrece precisión sub‑milimétrica para casos extremos como valores negativos y designadores hemisféricos, y funciona de manera consistente en entornos .NET de Windows, Linux y macOS.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Conocimientos básicos de C#** – familiaridad con variables, llamadas a métodos y salida en consola.  
2. **Aspose.GIS instalado** – descarga el paquete más reciente desde el [sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/). También puedes explorar el sitio principal de lanzamientos de Aspose en el [sitio web de lanzamientos de Aspose](https://releases.aspose.com/).  

## Importar espacios de nombres
Primero, importa los espacios de nombres requeridos para operaciones GIS:

Import Namespaces placeholder remains unchanged.

## Guía paso a paso

### ¿Qué es la clase GeoConvert?
La clase `GeoConvert` proporciona métodos estáticos para convertir entre formatos de coordenadas como grados decimales, DMS y GeoRef. Incluye sobrecargas que aceptan valores numéricos crudos o objetos `Point` y devuelven cadenas formateadas o nuevas instancias de `Point`. Al manejar casos extremos como coordenadas negativas y redondeos, la clase garantiza que la salida cumpla con las especificaciones GIS estándar, simplificando la integración en cualquier aplicación de mapeo .NET.

### Paso 1: iniciar el proceso de conversión
Imprimimos un mensaje amigable para que sepas que la demostración ha comenzado.

```csharp
using System;
using Aspose.Gis;
```

### Paso 2: convertir a grados decimales
Aunque el objetivo final es DMS, empezamos mostrando la representación decimal original. Esto también demuestra la ruta **decimal degrees to dms** que seguirás más adelante.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Paso 3: convertir a minutos decimales de grado
Este formato (`DD°MM.m'`) es un paso intermedio común cuando necesitas **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Paso 4: convertir a grados minutos segundos (dms)
Aquí está el núcleo de nuestro tutorial—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Paso 5: convertir a GeoRef
Para mayor completitud, también demostramos el formato `GeoRef`, útil en flujos de trabajo de teledetección.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Problemas comunes y soluciones
- **Letras de hemisferio incorrectas** – Asegúrate de pasar valores positivos para norte/este y negativos para sur/oeste; la API agrega automáticamente el sufijo correcto.  
- **Salida en blanco inesperada** – Verifica que el ensamblado `Aspose.Gis` esté referenciado correctamente y que el proyecto apunte a una versión .NET compatible.  
- **Licencia no encontrada** – Coloca tu archivo de licencia en la raíz de la aplicación o configúralo programáticamente con `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Preguntas frecuentes

**P: ¿Aspose.GIS es compatible con otros lenguajes de programación?**  
R: Aspose.GIS está dirigido principalmente a desarrolladores .NET, pero también existe una versión Java.

**P: ¿Puedo probar Aspose.GIS antes de comprar?**  
R: Sí, puedes acceder a una prueba gratuita de Aspose.GIS desde el [sitio web](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener soporte para Aspose.GIS?**  
R: Puedes buscar ayuda en el foro de la comunidad Aspose.GIS [aquí](https://forum.aspose.com/c/gis/33).

**P: ¿Hay licencias temporales disponibles para Aspose.GIS?**  
R: Sí, las licencias temporales se pueden obtener en la [página de licencias temporales](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo comprar Aspose.GIS?**  
R: Puedes adquirir Aspose.GIS en la [página de compra](https://purchase.aspose.com/buy).

## Conclusión
Al seguir estos pasos, ahora sabes cómo **convertir grados decimales a dms** y a otros formatos GIS comunes usando Aspose.GIS para .NET. Esta capacidad te permite integrar sin problemas cadenas de ubicación legibles en aplicaciones de mapeo, informes o cualquier flujo de trabajo de datos espaciales. Siéntete libre de experimentar con diferentes valores de latitud/longitud y explorar los demás formatos que ofrece la clase `GeoConvert`.

---

**Última actualización:** 2026-08-18  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Tutoriales relacionados

- [Cómo crear geometría de punto y obtener el tipo de geometría con Aspose.GIS para .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Cómo convertir GeoJSON – Aspose.GIS para .NET](/gis/net/geo-data-conversion/)
- [Crear geometría MultiPoint .NET con Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}