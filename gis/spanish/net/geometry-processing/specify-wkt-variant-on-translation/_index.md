---
date: 2026-04-09
description: Aprenda cómo asignar la referencia espacial y establecer la precisión
  decimal al crear puntos en C# con Aspose.GIS para .NET en sus aplicaciones .NET.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Especificar variante WKT en la traducción
second_title: Aspose.GIS .NET API
title: Asignar referencia espacial y establecer variante WKT usando Aspose.GIS
url: /es/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Asignar referencia espacial y establecer variante WKT usando Aspose.GIS

## Introducción
En este tutorial aprenderá cómo **asignar referencia espacial** a una geometría y controlar el formato exacto de salida WKT con Aspose.GIS para .NET. Ya sea que necesite **crear point C#** objetos para mapeo, análisis o intercambio de datos, poder elegir la variante WKT adecuada y la precisión numérica hace que sus datos espaciales sean interoperables y fáciles de leer. Repasemos el proceso paso a paso.

## Respuestas rápidas
- **¿Qué significa “assign spatial reference”?** Vincula una geometría a un sistema de coordenadas específico como WGS‑84.  
- **¿Qué variantes de WKT son compatibles?** Iso, SimpleFeatureAccessOutdated y ExtendedPostGis.  
- **¿Cómo puedo controlar la precisión decimal?** Use las opciones `NumericFormat` como `General`, `RoundTrip` o `Flat`.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.0+ y .NET Core/5/6+.

## ¿Qué es “assign spatial reference”?
Asignar una referencia espacial (o sistema de referencia espacial, SRS) indica al software GIS cómo interpretar los valores de coordenadas de una geometría. Sin un SRS, los números de latitud‑longitud de un punto no tienen significado en el mundo real.

## ¿Por qué controlar la variante WKT y el formato numérico?
Diferentes herramientas GIS esperan sintaxis WKT ligeramente distintas. Seleccionar la variante adecuada garantiza un intercambio de datos sin problemas, mientras que establecer la precisión decimal evita errores de redondeo o números excesivamente largos que saturan registros y archivos.

## Requisitos previos
1. Aspose.GIS para .NET – descargue desde la [página de descarga](https://releases.aspose.com/gis/net/).  
2. Un entorno de desarrollo .NET (Visual Studio, VS Code o Rider).  
3. Familiaridad básica con C# y el framework .NET.

## Importar espacios de nombres
Antes de usar cualquier clase de Aspose.GIS, importe los espacios de nombres requeridos:

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

## Paso 1: Crear un objeto Point (create point C#)
Comenzamos construyendo un `Point` con latitud, longitud y un valor de medida (M) opcional:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Paso 2: Asignar sistema de referencia espacial (SRS)
Ahora **asignamos referencia espacial** al punto. Aquí usamos el sistema ampliamente soportado WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Paso 3: Especificar la variante WKT deseada
Elija la variante WKT que coincida con su aplicación posterior:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Paso 4: Establecer la precisión decimal para la salida WKT
Controle cuántos dígitos aparecen en la cadena final usando `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Problemas comunes y consejos
- **Problema:** Olvidar establecer el SRS antes de llamar a `AsText` puede resultar en información SRID faltante.  
- **Consejo:** Use `NumericFormat.RoundTrip` cuando necesite un viaje de ida y vuelta sin pérdida de coordenadas.  
- **Consejo:** La variante `Iso` es la más portable; elija `ExtendedPostGis` solo cuando necesite SRID incrustado.

## Conclusión
Ahora sabe cómo **asignar referencia espacial**, elegir la variante WKT apropiada y **establecer la precisión decimal** al **crear point C#** objetos con Aspose.GIS. Estos controles le brindan la flexibilidad para cumplir con los requisitos exactos de cualquier flujo de trabajo GIS, desde visualizaciones simples hasta análisis espacial de alta precisión.

## Preguntas frecuentes

**Q:** ¿Es Aspose.GIS compatible con todas las versiones de .NET?  
**A:** Sí, Aspose.GIS soporta .NET Framework 4.0 y superiores, así como .NET Core/5/6.

**Q:** ¿Puedo usar Aspose.GIS para proyectos comerciales?  
**A:** Absolutamente. Se requiere una licencia comercial para uso en producción, pero hay una prueba gratuita disponible para evaluación.

**Q:** ¿Aspose.GIS soporta otros formatos de datos espaciales?  
**A:** Sí, funciona con ESRI Shapefile, GeoJSON, KML y muchos más formatos.

**Q:** ¿Dónde puedo descargar una prueba gratuita?  
**A:** Puede descargar una versión de prueba gratuita de Aspose.GIS desde [aquí](https://releases.aspose.com/).

**Q:** ¿Cómo obtener ayuda si tengo problemas?  
**A:** Publique sus preguntas en el [foro](https://forum.aspose.com/c/gis/33) de la comunidad Aspose.GIS donde tanto el personal de Aspose como los miembros de la comunidad pueden ayudar.

---

**Última actualización:** 2026-04-09  
**Probado con:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}