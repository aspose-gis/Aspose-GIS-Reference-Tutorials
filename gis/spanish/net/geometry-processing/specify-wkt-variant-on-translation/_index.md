---
date: 2025-12-23
description: Aprenda cómo convertir geometría a WKT con opciones variantes, establecer
  el formato numérico y ajustar la precisión decimal usando Aspose.GIS para .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Convertir geometría a opciones de variante WKT usando Aspose.GIS
url: /es/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir geometría a opciones de variante WKT usando Aspose.GIS

## Introducción
En aplicaciones .NET modernas, **convertir geometría a WKT** es un paso común cuando necesita intercambiar datos espaciales con otros sistemas o almacenarlos en un formato basado en texto. Aspose.GIS para .NET hace que esta conversión sea sencilla mientras le brinda control total sobre la variante WKT, el formato numérico y la precisión decimal. En este tutorial aprenderá cómo convertir geometría a WKT, elegir la variante correcta y ajustar finamente la salida para cumplir con los requisitos exactos de su proyecto.

## Respuestas rápidas
- **¿Qué significa “convertir geometría a WKT”?** Transforma objetos geométricos (puntos, líneas, polígonos) en la representación Well‑Known Text.  
- **¿Qué variantes de WKT son compatibles?** `Iso`, `SimpleFeatureAccessOutdated` y `ExtendedPostGis`.  
- **¿Cómo puedo controlar la precisión decimal?** Use las opciones `NumericFormat` como `General`, `RoundTrip` o `Flat`.  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial para uso que no sea de prueba.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.0+ y .NET 5/6/7.

## ¿Qué es “convertir geometría a WKT”?
Convertir geometría a WKT produce una cadena legible por humanos que describe objetos espaciales. Este formato es ampliamente aceptado por herramientas GIS, bases de datos y servicios web, lo que lo hace ideal para el intercambio de datos.

## ¿Por qué usar Aspose.GIS para esta conversión?
- **Control de precisión** – Elija cuántos decimales se emiten.  
- **Flexibilidad de variante** – Coincida con el dialecto WKT exacto requerido por su sistema downstream.  
- **Sin dependencias externas** – Biblioteca .NET pura, sin binarios nativos.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Aspose.GIS for .NET** – Descárguelo e instálelo desde la [download page](https://releases.aspose.com/gis/net/).  
2. **Entorno de desarrollo** – Cualquier versión reciente de Visual Studio o VS Code con .NET SDK.  
3. **Conocimientos básicos de C#** – Familiaridad con clases, objetos y el framework .NET.

## Importar espacios de nombres
Primero, importe los espacios de nombres requeridos al alcance:

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

## Paso 1: Crear un objeto Point
Cree un `Point` que luego **convertirá geometría a WKT**. El punto incluye latitud, longitud y un valor de medida (M) opcional:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Paso 2: Establecer el Sistema de Referencia Espacial (SRS)
Asigne un sistema de referencia espacial para que la salida WKT sepa a qué sistema de coordenadas referirse. Aquí usamos el sistema común WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Paso 3: Especificar la variante WKT
Elija la variante WKT apropiada cuando **convierta geometría a WKT**. Cada variante formatea la salida de forma ligeramente diferente:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Paso 4: Controlar el formato numérico (Establecer formato numérico y ajustar precisión decimal)
Ajuste finamente la representación numérica de las coordenadas. La clase `NumericFormat` le permite **establecer el formato numérico** y **ajustar la precisión decimal** según sus necesidades:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Problemas comunes y consejos
- **Valor M ausente** – Si no necesita una medida, omita la propiedad `M`; la variante ISO la eliminará automáticamente.  
- **Precisión inesperada** – Verifique que está usando el `NumericFormat` correcto; `General` conserva la precisión completa de doble, mientras que `Flat` redondea al número especificado de decimales.  
- **SRID no mostrado** – Sólo la variante `ExtendedPostGis` antepone `SRID=` a la salida. Elija esta variante cuando su sistema de destino espere un SRID.

## Conclusión
Al seguir estos pasos ahora sabe cómo **convertir geometría a WKT**, seleccionar la variante correcta y controlar con precisión la salida numérica. Esto le brinda la flexibilidad de integrar Aspose.GIS con cualquier flujo de trabajo GIS, base de datos o servicio web que consuma WKT.

## Preguntas frecuentes
### ¿Es Aspose.GIS compatible con todas las versiones de .NET?
Sí, Aspose.GIS soporta .NET Framework 4.0 y superiores.

### ¿Puedo usar Aspose.GIS para proyectos comerciales?
Sí, Aspose.GIS puede usarse tanto para proyectos personales como comerciales.

### ¿Aspose.GIS ofrece soporte para otros formatos de datos espaciales?
Sí, Aspose.GIS soporta una amplia gama de formatos de datos espaciales, incluidos ESRI Shapefile, GeoJSON y KML.

### ¿Hay una versión de prueba gratuita disponible para Aspose.GIS?
Sí, puede descargar una versión de prueba gratuita de Aspose.GIS desde [here](https://releases.aspose.com/).

### ¿Dónde puedo obtener ayuda o soporte para Aspose.GIS?
Puede publicar sus preguntas o buscar asistencia en la comunidad de Aspose.GIS en el [forum](https://forum.aspose.com/c/gis/33).

## Preguntas frecuentes
**P: ¿Cómo exporto una colección de Geometry a una única cadena WKT?**  
R: Itere sobre cada geometría en la colección y concatene sus resultados `AsText`, opcionalmente separándolos con comas o saltos de línea.

**P: ¿Puedo cambiar el SRID sin alterar las coordenadas?**  
R: Sí, establezca la propiedad `SpatialReferenceSystem` al SRID deseado; los valores de coordenadas permanecen sin cambios.

**P: ¿Qué ocurre si utilizo una variante WKT no soportada?**  
R: Aspose.GIS lanzará una `ArgumentException`. Siempre valide la variante contra los valores del enum `WktVariant`.

---

**Última actualización:** 2025-12-23  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}