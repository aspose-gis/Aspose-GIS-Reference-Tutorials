---
date: 2026-09-15
description: Aprenda cómo asignar coordinate system, establecer WKT variant y controlar
  decimal precision al crear point geometry en C# con Aspose.GIS para .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Especificar WKT Variant en la traducción
og_description: Aprenda cómo asignar coordinate system, establecer WKT variant y controlar
  decimal precision al crear point geometry en C# con Aspose.GIS para .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Asignar coordinate system, establecer WKT variant usando Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Asignar coordinate system, establecer WKT variant usando Aspose.GIS
url: /es/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Asignar sistema de coordenadas, establecer variante WKT usando Aspose.GIS

## Introducción
En este tutorial aprenderá cómo **asignar sistema de coordenadas**, elegir la variante WKT adecuada y controlar la precisión decimal al **crear geometría de punto** en C# con Aspose.GIS para .NET. Ya sea que esté construyendo un servicio de mapas, realizando análisis espacial o intercambiando datos entre plataformas GIS, estas configuraciones garantizan que su salida sea interoperable y fácil de leer. Repasemos el proceso paso a paso.

## Respuestas rápidas
- **¿Qué significa “asignar sistema de coordenadas”?** Vincula una geometría a un sistema de referencia de coordenadas específico, como WGS‑84.  
- **¿Qué variantes WKT son compatibles?** Iso, SimpleFeatureAccessOutdated y ExtendedPostGis.  
- **¿Cómo puedo controlar la precisión decimal?** Use el enum `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **¿Necesito una licencia para Aspose.GIS?** Hay una prueba gratuita disponible; se requiere una licencia comercial para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.0+ y .NET Core/5/6+.

## ¿Qué es “asignar sistema de coordenadas”?
Asignar una referencia espacial (o sistema de referencia espacial, SRS) indica al software GIS cómo interpretar los valores de coordenadas de una geometría, vinculando los números a un sistema de coordenadas del mundo real como WGS‑84. Sin un SRS, los valores de latitud‑longitud de un punto no tienen significado en el mundo real.

## ¿Por qué controlar la variante WKT y el formato numérico?
Más de 30 herramientas GIS esperan sintaxis WKT específicas, por lo que seleccionar la variante adecuada previene errores de importación. Configurar el formato numérico reduce el ruido de redondeo y mantiene la salida concisa, lo cual es especialmente importante cuando los registros o archivos se analizan programáticamente.

## Requisitos previos
1. Aspose.GIS para .NET – descargar desde la [página de descarga](https://releases.aspose.com/gis/net/).  
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

## ¿Cómo asignar sistema de coordenadas a un punto?
Cargue una instancia de `Point`, luego adjunte un sistema de referencia espacial (SRS) usando la clase `SpatialReference`. Este patrón de dos pasos asegura que la geometría lleve su metadato de sistema de coordenadas al exportarse, permitiendo que las herramientas posteriores interpreten correctamente las coordenadas. La clase `Point` representa una ubicación única definida por coordenadas X (longitud) y Y (latitud).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Paso 2: asignar sistema de referencia espacial (SRS)
Ahora **asignamos la referencia espacial** al punto. `SpatialReference` representa un sistema de referencia de coordenadas identificado por un SRID. Aquí usamos el sistema WGS‑84 ampliamente soportado (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Paso 3: especificar la variante WKT deseada
Elija la variante WKT que coincida con su aplicación posterior:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## ¿Cómo establecer la precisión decimal para la salida WKT?
Controle cuántos dígitos aparecen en la cadena final usando el enum `NumericFormat`, que define reglas de formato como `General`, `RoundTrip` o `Flat`. Seleccionar `RoundTrip` preserva la fidelidad completa de las coordenadas para escenarios de ida y vuelta, mientras que `General` ofrece una representación concisa adecuada para la mayoría de las tareas de visualización. El enum `NumericFormat` controla cómo se formatean los números de coordenadas en la salida WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Problemas comunes y consejos
- **Problema:** Olvidar establecer el SRS antes de llamar a `AsText` puede resultar en información de SRID ausente.  
- **Consejo:** Use `NumericFormat.RoundTrip` cuando necesite una ida y vuelta sin pérdida de coordenadas.  
- **Consejo:** La variante `Iso` es la más portable; elija `ExtendedPostGis` solo cuando necesite que el SRID esté incrustado.

## Conclusión
Ahora sabe cómo **asignar sistema de coordenadas**, elegir la variante WKT adecuada y **establecer la precisión decimal** al **crear geometría de punto** con Aspose.GIS. Estos controles le brindan la flexibilidad para cumplir con los requisitos exactos de cualquier flujo de trabajo GIS, desde visualizaciones simples hasta análisis espacial de alta precisión.

## Preguntas frecuentes

**Q:** ¿Es Aspose.GIS compatible con todas las versiones de .NET?  
**A:** Sí, Aspose.GIS soporta .NET Framework 4.0 y superiores, así como .NET Core/5/6.

**Q:** ¿Puedo usar Aspose.GIS para proyectos comerciales?  
**A:** Por supuesto. Se requiere una licencia comercial para uso en producción, pero hay una prueba gratuita disponible para evaluación.

**Q:** ¿Aspose.GIS soporta otros formatos de datos espaciales?  
**A:** Sí, funciona con más de 30 formatos, incluidos ESRI Shapefile, GeoJSON, KML, CSV y muchos más.

**Q:** ¿Dónde puedo descargar una prueba gratuita?  
**A:** Puede descargar una versión de prueba gratuita de Aspose.GIS desde la [página de descarga de prueba gratuita de Aspose.GIS](https://releases.aspose.com/).

**Q:** ¿Cómo obtengo ayuda si encuentro problemas?  
**A:** Publique sus preguntas en el [foro](https://forum.aspose.com/c/gis/33) de la comunidad Aspose.GIS, donde tanto el personal de Aspose como los miembros de la comunidad pueden ayudar.

---

**Última actualización:** 2026-09-15  
**Probado con:** Aspose.GIS para .NET (última versión)  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear una capa vectorial y establecer su sistema de referencia espacial](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Cómo traducir geometría a WKT con Aspose.GIS para .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Cómo limitar la precisión al escribir geometrías con Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}