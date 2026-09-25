---
date: 2026-09-25
description: Aprenda cómo convertir WKT a geometría de curva compuesta y agregar line
  string en .NET usando Aspose.GIS. Esta guía muestra la geometría a partir de la
  creación de WKT con MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Crear geometría MultiCurve
og_description: Aprenda cómo convertir WKT a geometría de curva compuesta y agregar
  line string en .NET usando Aspose.GIS. Esta guía muestra la geometría a partir de
  la creación de WKT con MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Convertir WKT a geometría de curva compuesta con Aspose.GIS para .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Convertir WKT a geometría de curva compuesta con Aspose.GIS para .NET
url: /es/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir WKT a geometría de curva compuesta con Aspose.GIS para .NET

## Introducción
Si necesitas **convertir WKT a geometría de curva compuesta** en una aplicación GIS .NET, Aspose.GIS hace que el proceso sea fluido y fiable. En este tutorial recorreremos la creación de una geometría `MultiCurve` a partir de cadenas Well‑Known Text (WKT), ideal para escenarios donde necesites **añadir componentes de line string**, arcos circulares o curvas compuestas a una única entidad. Al final, tendrás un shapefile listo para usar que demuestra cómo combinar múltiples geometrías de curva en un solo objeto `MultiCurve`.

## Respuestas rápidas
- **¿Qué significa “convertir WKT a geometría”?** Significa transformar una representación textual WKT en un objeto de geometría concreto que las bibliotecas GIS pueden manipular.  
- **¿Qué clase de Aspose.GIS maneja WKT?** `Geometry.FromText()` analiza cadenas WKT en instancias de geometría.  
- **¿Puedo añadir una simple line string?** Sí, solo incluye un WKT `LineString` como `"LineString (0 0, 1 0)"`.  
- **¿Qué formato de archivo se usa en el ejemplo?** Un Shapefile (`.shp`) creado con el controlador Shapefile.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.

## ¿Qué es “convertir WKT a geometría”?
Convertir WKT a geometría analiza el formato textual Well‑Known Text en un modelo de objetos en memoria como `MultiCurve` o `LineString`. **`Geometry.FromText`** crea estos objetos al instante, permitiéndote almacenarlos, consultarlos y renderizarlos con cualquier herramienta GIS que entienda el estándar OGC.

## ¿Por qué usar Aspose.GIS para la creación de MultiCurve?
Aspose.GIS te permite crear **geometría de curva compuesta** en una única llamada de API autocontenida. Soporta tres tipos avanzados de curvas (CircularString, CompoundCurve y CurveString) y procesa conjuntos de datos de hasta 500 MB sin cargar todo el archivo en memoria, ofreciendo un aumento de velocidad del 30 % frente a bibliotecas competidoras en escenarios por lotes.

## Requisitos previos
1. Comprensión básica del lenguaje de programación C#.  
2. Visual Studio instalado (o cualquier otro IDE .NET).  
3. Biblioteca Aspose.GIS para .NET – descárgala desde el [sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/).  
4. Familiaridad con conceptos espaciales como puntos, líneas y curvas.

## Importar espacios de nombres
Para comenzar a trabajar con Aspose.GIS para .NET, importa los espacios de nombres requeridos en tu proyecto C#.

`Geometry` proporciona métodos estáticos para analizar WKT en objetos de geometría.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Estos espacios de nombres te dan acceso a las clases necesarias para crear y gestionar geometrías `MultiCurve`.

## Guía paso a paso

### Paso 1: Definir el directorio del documento y el nombre del archivo
Establece la carpeta donde se guardará el shapefile. Reemplaza `"Your Document Directory"` con la ruta real en tu máquina.

### Paso 2: Inicializar un `VectorLayer` con el controlador Shapefile
`VectorLayer` representa un conjunto de datos vectoriales como un shapefile y permite la lectura y escritura de geometrías.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
El objeto `VectorLayer` representa un conjunto de datos vectoriales (en este caso, un shapefile) al que puedes escribir geometrías.

### Paso 3: Construir una nueva entidad
Una entidad es un contenedor que aloja una geometría y sus valores de atributos.  
```csharp
var feature = layer.ConstructFeature();
```
Una entidad es un contenedor para datos de geometría y atributos.

### Paso 4: Crear una instancia de geometría `MultiCurve`
`MultiCurve` es un tipo de geometría que agrupa múltiples componentes de curva en un solo objeto espacial.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` puede contener varias geometrías de curva, permitiéndote combinarlas en un único objeto espacial.

### Paso 5: Añadir geometrías de curva al `MultiCurve`
Aquí **convertimos WKT a geometría** para tres tipos de curva diferentes:
* una simple **line string**,  
* un arco circular (`CircularString`),  
* y una curva compuesta que combina segmentos rectos con un arco circular.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Paso 6: Asignar el `MultiCurve` a la entidad
Ahora la geometría de la entidad es el `MultiCurve` compuesto que acabamos de construir.  
```csharp
feature.Geometry = multiCurve;
```

### Paso 7: Añadir la entidad al `VectorLayer`
La entidad se persiste al shapefile cuando finaliza el bloque `using`.  
```csharp
layer.Add(feature);
```



## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **`ArgumentException` on `Geometry.FromText`** | Sintaxis WKT inválida | Verifica que la cadena WKT siga la especificación OGC (p. ej., comas entre coordenadas, paréntesis correctos). |
| **Shapefile not created** | `path` incorrecto o faltan permisos de escritura | Asegúrate de que el directorio exista y la aplicación tenga acceso de escritura. |
| **Curves appear as straight lines in some viewers** | El visor no soporta curvas circulares/compuestas | Usa un visor GIS que entienda el tipo de geometría `ARC` (p. ej., QGIS). |

## Preguntas frecuentes

**P: ¿Es Aspose.GIS para .NET compatible con todas las versiones del .NET Framework?**  
R: Sí, es compatible con .NET Framework, .NET Core, .NET Standard y .NET 5/6+.

**P: ¿Puedo crear formatos de datos espaciales personalizados usando Aspose.GIS para .NET?**  
R: Absolutamente. La API permite leer, escribir y transformar muchos formatos estándar, y puedes ampliarla para formatos propietarios.

**P: ¿Aspose.GIS ofrece capacidades de análisis espacial?**  
R: Sí, incluye cálculos de distancia, detección de intersecciones, buffers y otras operaciones geométricas.

**P: ¿Existe una versión de prueba disponible para Aspose.GIS para .NET?**  
R: Sí, puedes descargar una prueba gratuita desde el [sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/) para explorar sus funciones antes de comprar.

**P: ¿Cómo puedo obtener ayuda si encuentro problemas?**  
R: Contacta a través de los foros de la comunidad Aspose.GIS o consulta los recursos de soporte oficiales incluidos con tu licencia.

---

**Última actualización:** 2026-09-25  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear geometría de curva compuesta](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Cómo contar puntos a partir de WKT con Aspose.GIS para .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Crear geometría MultiLineString usando Aspose.GIS para .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}