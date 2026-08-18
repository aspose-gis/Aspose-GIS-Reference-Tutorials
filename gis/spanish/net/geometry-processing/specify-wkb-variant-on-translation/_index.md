---
date: 2026-06-10
description: Aprenda cómo crear geometría linestring en .NET y convertir la geometría
  a WKB usando Aspose.GIS para .NET con la variante ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Especificar variante WKB en la traducción
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Crear geometría Linestring y variante WKB en Aspose.GIS para .NET
url: /es/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear geometría Linestring y variante WKB en Aspose.GIS para .NET

## Introducción
Si necesitas **create linestring geometry .NET** y luego traducir esa geometría a una forma binaria, Aspose.GIS para .NET te ofrece una API limpia y de alto rendimiento que funciona en .NET Framework, .NET Core y .NET 5/6+. En este tutorial recorreremos cada paso—desde la importación de espacios de nombres hasta la escritura de un archivo EWKB—para que puedas preservar la información del SRID e integrar datos GIS en PostgreSQL/PostGIS o cualquier flujo de trabajo basado en binarios sin complicaciones.

## Respuestas rápidas
- **¿Qué significa WKB?** Well‑Known Binary, una representación binaria compacta de objetos geométricos.  
- **¿Qué variante de WKB almacena el SRID?** La variante `ExtendedPostGis` (EWKB) inserta el SRID directamente en el binario.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa de Aspose.GIS para implementaciones en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, y .NET 5/6+.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para un ejemplo básico.

## ¿Qué es una geometría Linestring?
Una geometría linestring es una forma simple compuesta por una lista ordenada de puntos conectados por segmentos de línea recta. Es la representación preferida para características lineales como carreteras, tuberías o cauces de ríos en bases de datos espaciales.

## ¿Por qué especificar una variante WKB?
Usar la variante WKB correcta garantiza que los metadatos críticos—especialmente el Identificador del Sistema de Referencia Espacial (SRID)—viajen con tu geometría. La variante `ExtendedPostGis` (EWKB) almacena el SRID dentro de la carga binaria, lo que permite una ida y vuelta sin problemas con PostGIS, Oracle Spatial o cualquier sistema que espere binarios con conocimiento del SRID.

## Requisitos previos
Antes de comenzar, asegúrate de contar con lo siguiente:

### Instalación de Aspose.GIS para .NET
1. Descargar Aspose.GIS: Visita el [download link](https://releases.aspose.com/gis/net/) para obtener el paquete más reciente.  
2. Agrega el paquete NuGet a tu proyecto (p.ej., `Install-Package Aspose.GIS`).  

### Familiaridad con la programación en C#
- Comprensión básica de la sintaxis de C# y la estructura del proyecto.  
- Capacidad para ejecutar un proyecto de consola .NET o de biblioteca de clases.

## Importar espacios de nombres
El espacio de nombres `Aspose.GIS` te brinda acceso a todas las clases relacionadas con geometría.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Estos espacios de nombres proporcionan la funcionalidad central de GIS, incluyendo la creación de geometrías, transformación y serialización binaria.

## ¿Cómo crear una geometría linestring?
Para crear un linestring, instancia un objeto `Linestring` con una lista ordenada de pares de coordenadas, establece su SRID si es necesario y luego serialízalo a la variante WKB deseada. El proceso implica tres pasos: construir la geometría, elegir la variante `ExtendedPostGis` para conservar el SRID y escribir el arreglo de bytes resultante en un archivo.

### Paso 1: Crear un objeto Geometry
La clase `Geometry` es el tipo base de Aspose.GIS que representa cualquier objeto espacial en memoria. Linestring representa una serie de puntos conectados que forman una geometría lineal.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
En este paso instanciamos un `Linestring` con una colección de pares de coordenadas que modelan un segmento de carretera simple.

### Paso 2: Generar la representación WKB
`WkbVariant.ExtendedPostGis` es el valor del enumerado que indica a Aspose.GIS que incluya el SRID en el binario de salida.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Aquí llamamos al método `AsBinary`, pasando la variante EWKB, lo que devuelve un `byte[]` que contiene la representación binaria completa.

### Paso 3: Escribir en archivo
`File.WriteAllBytes` escribe el arreglo binario en el disco.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
El archivo resultante (`EWkbFile.ewkb`) puede importarse directamente a una tabla PostGIS usando la función `ST_GeomFromEWKB`.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Archivo vacío** | `Path.Combine` apunta a un directorio que no existe. | Asegúrate de que el directorio de destino exista o créalo con `Directory.CreateDirectory`. |
| **SRID incorrecto** | Usar el valor predeterminado `WkbVariant.Standard` elimina el SRID. | Siempre usa `WkbVariant.ExtendedPostGis` cuando se requiera preservar el SRID. |
| **Excepción de licencia** | Ejecutar sin una licencia válida en producción. | Aplica una licencia temporal o completa antes de ejecutar el código en un entorno de producción. |

## Preguntas frecuentes
**Q: ¿Puedo usar el archivo EWKB con PostGIS?**  
A: Sí, la variante `ExtendedPostGis` produce EWKB que incluye el SRID, el cual PostGIS lee directamente mediante `ST_GeomFromEWKB`.  

**Q: ¿Es posible leer un archivo WKB de nuevo en un objeto geometría?**  
A: Por supuesto. Usa `Geometry.FromBinary(byteArray)` para reconstruir la geometría a partir de su forma binaria.  

**Q: ¿La biblioteca admite otros tipos de geometría como polígonos?**  
A: Sí, Aspose.GIS maneja puntos, linestrings, polígonos, multipolígonos y muchos más tipos espaciales.  

**Q: ¿Cómo especifico un SRID diferente al crear la geometría?**  
A: Establece la propiedad `SRID` en el objeto de geometría antes de llamar a `AsBinary`, por ejemplo, `linestring.SRID = 4326;`.  

**Q: ¿Este código funciona en .NET Core?**  
A: Sí, la misma API funciona en .NET Framework, .NET Core y .NET 5/6 sin modificaciones.

---

**Última actualización:** 2026-06-10  
**Probado con:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Traducir geometría al formato WKB con Aspose.GIS para .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Especificar variante WKT en la traducción usando Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Crear geometría MultiLineString usando Aspose.GIS para .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}