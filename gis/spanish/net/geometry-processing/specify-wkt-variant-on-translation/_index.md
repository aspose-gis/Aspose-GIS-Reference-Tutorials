---
title: Especifique la variante WKT en la traducción usando Aspose.GIS
linktitle: Especificar la variante WKT en la traducción
second_title: Aspose.GIS API .NET
description: Aprenda a especificar variantes de WKT en Aspose.GIS para .NET para controlar el formato y la precisión de la representación de datos espaciales de manera efectiva.
weight: 19
url: /es/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Especifique la variante WKT en la traducción usando Aspose.GIS

## Introducción
Aspose.GIS para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con datos del sistema de información geográfica (GIS) en sus aplicaciones .NET sin esfuerzo. Una de las características esenciales proporcionadas por Aspose.GIS es la capacidad de especificar la variante de texto conocido (WKT) durante la traducción, lo que permite a los usuarios controlar el formato y la precisión de las representaciones de datos espaciales. En este tutorial, exploraremos cómo especificar variantes de WKT paso a paso usando Aspose.GIS para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener implementados los siguientes requisitos previos:
1. Aspose.GIS para .NET: Descargue e instale Aspose.GIS para .NET desde[pagina de descarga](https://releases.aspose.com/gis/net/).
2. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo .NET.
3. Conocimientos básicos: familiaridad con el lenguaje de programación C# y el framework .NET.

## Importar espacios de nombres
Antes de usar la funcionalidad Aspose.GIS en su código, importe los espacios de nombres necesarios:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Paso 1: crear un objeto de punto
 Primero, crea un`Point` objeto con valores de latitud, longitud y medida opcional (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Paso 2: configurar el sistema de referencia espacial (SRS)
Asigne un sistema de referencia espacial (SRS) al objeto puntual. En este ejemplo, utilizamos el sistema de referencia espacial WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Paso 3: especificar la variante WKT
 Ahora, especifique la variante WKT para la traducción. Aspose.GIS admite varias variantes de WKT, incluidas`Iso`, `SimpleFeatureAccessOutdated` , y`ExtendedPostGis`. Elija la variante adecuada según sus necesidades:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PUNTO M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PUNTO (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;PUNTO (23.5732, 25.3421, 40.3)
```
## Paso 4: Controlar el formato numérico
Puede controlar el formato numérico de las coordenadas en la representación WKT. Aspose.GIS proporciona opciones para especificar la precisión decimal:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PUNTO M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PUNTO M (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PUNTO M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PUNTO M (23,573 25,342 40,3)
```

## Conclusión
En este tutorial, aprendimos cómo especificar variantes de WKT en la traducción usando Aspose.GIS para .NET. Siguiendo los pasos descritos anteriormente, los desarrolladores pueden controlar eficazmente el formato y la precisión de las representaciones de datos espaciales en sus aplicaciones .NET, mejorando la flexibilidad y usabilidad de los sistemas de información geográfica.
## Preguntas frecuentes
### ¿Aspose.GIS es compatible con todas las versiones de .NET?
Sí, Aspose.GIS es compatible con .NET Framework 4.0 y superior.
### ¿Puedo utilizar Aspose.GIS para proyectos comerciales?
Sí, Aspose.GIS se puede utilizar tanto para proyectos personales como comerciales.
### ¿Aspose.GIS proporciona soporte para otros formatos de datos espaciales?
Sí, Aspose.GIS admite una amplia gama de formatos de datos espaciales, incluidos ESRI Shapefile, GeoJSON y KML.
### ¿Hay una prueba gratuita disponible para Aspose.GIS?
 Sí, puede descargar una versión de prueba gratuita de Aspose.GIS desde[aquí](https://releases.aspose.com/).
### ¿Dónde puedo obtener ayuda o soporte para Aspose.GIS?
 Puede publicar sus consultas o buscar ayuda de la comunidad Aspose.GIS en el[foro](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
