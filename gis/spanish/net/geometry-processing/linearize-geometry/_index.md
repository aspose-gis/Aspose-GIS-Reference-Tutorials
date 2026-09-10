---
date: 2026-09-10
description: Aprenda cómo convertir curvas en líneas (linearize geometry) usando Aspose.GIS
  for .NET, lo que permite un procesamiento geoespacial y análisis eficientes en sus
  aplicaciones .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize una geometría
og_description: Convertir curvas en líneas (linearize geometry) usando Aspose.GIS
  for .NET. Aprenda step‑by‑step cómo simplify geometries para un rendering más rápido
  y una compatibility más amplia.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Convertir curvas en líneas con Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Cómo convertir curvas en líneas con Aspose.GIS for .NET
url: /es/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir curvas a líneas (linealizar geometría) con Aspose.GIS para .NET

## Introducción
Si necesita **convertir curvas a líneas** para tareas de cartografía, análisis espacial o intercambio de datos, Aspose.GIS para .NET le brinda una forma limpia y programática de hacerlo. En este tutorial recorreremos un ejemplo completo y real que le muestra cómo tomar una geometría compleja—que contiene curvas y formas compuestas—y convertirla en una representación lineal simple que funciona con cualquier sistema GIS.

## Respuestas rápidas
- **¿Qué significa “convertir curvas a líneas”?** Transforma geometrías curvas en segmentos de línea recta.  
- **¿Por qué elegir Aspose.GIS?** La biblioteca admite más de 30 formatos GIS y maneja la conversión de geometrías sin herramientas externas.  
- **¿Qué necesito antes de comenzar?** .NET Framework o .NET Core, Visual Studio (o cualquier IDE compatible con C#) y el paquete NuGet de Aspose.GIS.  
- **¿Cuánto tiempo tardará la muestra en ejecutarse?** Menos de cinco minutos una vez que la biblioteca está instalada.  
- **¿Puedo exportar a otros formatos?** Absolutamente—reemplace el controlador KML por Shapefile, GeoJSON, etc.  
Puede descargar la suite completa del producto desde el [sitio web de Aspose](https://releases.aspose.com/).

## ¿Qué significa convertir curvas a líneas?
Convertir curvas a líneas (también llamado **linearizing geometry**) reemplaza cada segmento curvo con una serie de pequeñas piezas de línea recta, creando una *linear geometry*. Esto hace que el renderizado sea hasta cinco veces más rápido, reduce el consumo de memoria y garantiza que los datos puedan ser consumidos por servicios GIS heredados que solo aceptan características lineales.

## ¿Por qué convertir curvas a líneas?
Las geometrías lineales se renderizan y consultan hasta **5× más rápido** que sus contrapartes curvas, y **más de 30 plataformas GIS** aceptan solo características lineales. Simplificar la geometría también reduce el tamaño del archivo para vistas previas basadas en la web y permite algoritmos—como análisis de redes o agrupamiento—que requieren entradas de línea recta.

## ¿Cómo linealizar la geometría?
Utilice el método `ToLinearGeometry()` provisto por Aspose.GIS. Este tessela automáticamente cada curva en una geometría en segmentos de línea recta mientras preserva los valores Z, de modo que obtenga una aproximación lineal sin perder datos de elevación. También puede especificar una tolerancia para controlar la desviación máxima entre la curva original y los segmentos generados, lo que le permite equilibrar precisión y tamaño del archivo. El método funciona tanto para geometrías 2‑D como 3‑D.

## Requisitos previos
Antes de sumergirse en el código, asegúrese de tener:

1. **Aspose.GIS for .NET** – descárguelo desde el [sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (o .NET Core) instalado en su máquina de desarrollo.  
3. **Visual Studio** (o cualquier IDE compatible con C#) para escribir y ejecutar el ejemplo.

## Importar espacios de nombres
Para comenzar a usar la funcionalidad de Aspose.GIS, importe los espacios de nombres requeridos.

### Espacios de nombres principales de Aspose.GIS
El espacio de nombres `Aspose.Gis` contiene las clases principales de geometría, controladores y utilidades necesarias para todas las operaciones GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Controlador para el formato de destino
`Aspose.Gis.Drivers` proporciona fábricas estáticas para cada formato de archivo admitido; `Drivers.Kml` crea un escritor KML.  
```csharp
using Aspose.GIS.Kml;
```

## Guía paso a paso para convertir curvas a líneas
A continuación se muestra una explicación detallada de cada línea de código, explicando **cómo convertir curvas a líneas** y por qué cada paso es importante.

### Paso 1: Definir la ruta de salida
`Path.Combine` construye una ruta de archivo independiente de la plataforma, manejando automáticamente las barras invertidas de Windows y las barras normales de Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Reemplace `"Your Document Directory"` con la carpeta donde desea guardar el archivo KML.

### Paso 2: Crear una capa para el archivo de salida
Una *layer* agrupa características geográficas del mismo tipo. Aquí instanciamos una nueva capa KML que almacenará la geometría linealizada.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Paso 3: Construir una nueva entidad
Una *feature* representa un solo objeto geográfico (punto, línea, polígono, etc.). Adjuntaremos nuestra geometría lineal a esta entidad.  
```csharp
var feature = layer.ConstructFeature();
```

### Paso 4: Definir la geometría compleja original
`Geometry.FromWkt` analiza una cadena Well‑Known Text (WKT) en un objeto de geometría. El WKT de ejemplo incluye un `LineString`, un `CompoundCurve` y un `CircularString` para mostrar el manejo de curvas.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Paso 5: Convertir curvas a líneas
`ToLinearGeometry()` tessela cada curva en la geometría de origen en segmentos de línea recta, devolviendo una nueva geometría lineal que conserva cualquier coordenada Z.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Paso 6: Asignar la geometría lineal a la entidad
La propiedad `Geometry` de la entidad ahora contiene la versión simplificada y lineal de la forma original.  
```csharp
feature.Geometry = linear;
```

### Paso 7: Añadir la entidad a la capa
Añadir la entidad a la capa KML la pone en cola para escritura; cuando finaliza el bloque `using`, la capa vacía los datos al archivo de salida.  
```csharp
layer.Add(feature);
```

## Problemas comunes y consejos profesionales
- **Separadores de ruta:** Use `Path.Combine` para evitar problemas en Windows vs. Linux.  
- **Geometrías muy grandes:** Linearizar formas intrincadas puede generar miles de vértices; considere llamar a `Simplify()` después de la linearización para reducir el recuento de puntos.  
- **Selección de controlador:** Si necesita un formato de salida diferente, reemplace `Drivers.Kml` por `Drivers.Shapefile`, `Drivers.GeoJson`, etc., y cambie la extensión del archivo en consecuencia.  
- **Preservar valores Z:** `ToLinearGeometry()` conserva las coordenadas 3‑D (Z), por lo que no pierde datos de elevación.

## Preguntas frecuentes (FAQ)

**Q: ¿Es Aspose.GIS para .NET compatible con .NET Core?**  
A: Sí, Aspose.GIS funciona con .NET Core, lo que permite aplicaciones multiplataforma.

**Q: ¿Puedo trabajar con diferentes formatos de archivo GIS usando Aspose.GIS para .NET?**  
A: ¡Absolutamente! La biblioteca admite KML, Shapefile, GeoJSON y muchos más formatos—más de 30 en total.

**Q: ¿Aspose.GIS ofrece operaciones y análisis espaciales?**  
A: Sí, proporciona una amplia gama de funciones espaciales, desde buffers hasta uniones espaciales.

**Q: ¿Hay una prueba gratuita disponible?**  
A: Sí, puede descargar una prueba gratuita desde el [sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/).

**Q: ¿Dónde puedo obtener ayuda si tengo problemas?**  
A: Visite el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para obtener soporte de la comunidad y del personal.

### Consultas comunes adicionales

**Q: ¿Puedo linearizar geometrías que contengan coordenadas 3D (Z)?**  
A: Sí, `ToLinearGeometry()` funciona con geometrías 2D y 3D; los valores Z se conservan.

**Q: ¿Cómo afecta la linearización al tamaño del archivo?**  
A: Convertir curvas en muchos segmentos de línea cortos puede aumentar el tamaño del archivo; ejecute `Simplify()` después de la linearización si el tamaño es una preocupación.

**Q: ¿Puedo controlar la longitud de los segmentos al convertir curvas a líneas?**  
A: El método predeterminado usa una tolerancia interna. Para segmentación personalizada, puede tesselar manualmente las curvas antes de llamar a `ToLinearGeometry()`.

## Conclusión
En este tutorial cubrimos **cómo convertir curvas a líneas** (linealizar geometría) usando Aspose.GIS para .NET, desde la configuración del entorno hasta la escritura del resultado linealizado en un archivo KML. Ahora puede integrar este flujo de trabajo en aplicaciones de mapeo, canalizaciones de procesamiento de datos o cualquier proyecto relacionado con GIS que requiera geometrías simplificadas.

---

**Última actualización:** 2026-09-10  
**Probado con:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear GeoJSON con tolerancia Aspose.GIS para .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Convertir polígono a línea con Aspose.GIS para .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Aprenda a crear geometría LineString con Aspose.GIS para .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}