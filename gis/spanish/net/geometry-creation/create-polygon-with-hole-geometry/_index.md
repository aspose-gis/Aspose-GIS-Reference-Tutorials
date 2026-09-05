---
date: 2026-09-05
description: Aprenda cómo crear un anillo interior de polígono con un agujero usando
  Aspose.GIS para .NET. Esta guía le muestra cómo agregar un agujero a un polígono
  y trabajar con datos.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Crear Polígono con Geometría de Agujero
og_description: Aprenda cómo crear un anillo interior de polígono con un agujero usando
  Aspose.GIS para .NET. Esta guía le muestra cómo agregar un agujero a un polígono
  y trabajar con datos.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Crear un anillo interior de polígono con un agujero usando Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Crear un anillo interior de polígono con un agujero usando Aspose.GIS
url: /es/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear un anillo interior de polígono con un agujero usando Aspose.GIS

## Introducción
En este tutorial aprenderás a **crear un anillo interior de polígono** que contiene un agujero usando Aspose.GIS para .NET. Ya sea que estés construyendo una aplicación de mapeo, realizando análisis espacial o preparando datos para servicios GIS, incrustar un agujero dentro de un polígono es una habilidad esencial. Recorreremos todo el flujo de trabajo, desde la configuración del entorno de desarrollo hasta la generación de un objeto polígono válido que pueda guardarse en cualquier formato geoespacial compatible.

## Respuestas rápidas
- **¿Qué significa “crear polígono con agujero”?** Significa construir un polígono que contiene uno o más anillos interiores (agujeros) que se excluyen del área.  
- **¿Qué biblioteca maneja esto?** Aspose.GIS para .NET ofrece soporte completo para anillos exteriores e interiores.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Cuánto tiempo lleva?** Normalmente menos de 10 minutos para implementar y probar.

## Cómo agregar un agujero a un polígono usando Aspose.GIS
Carga tu entorno GIS, define un anillo exterior y luego adjunta uno o más anillos interiores. Aspose.GIS orienta automáticamente los anillos y valida la geometría, de modo que puedes concentrarte en las coordenadas que representan el vacío que necesitas.

## ¿Qué es un anillo interior de polígono?
Un **anillo interior de polígono** es una frontera interna que resta área de la forma exterior del polígono.  
Lo creas definiendo una secuencia cerrada de puntos que Aspose.GIS trata como un agujero, el cual se excluye al calcular el área o al renderizar la forma.

## ¿Por qué crear un anillo interior de polígono usando Aspose.GIS?
Aspose.GIS valida y corrige la orientación de los anillos en menos de 5 ms para polígonos típicos de 200 puntos, eliminando la necesidad de código de validación personalizado. También soporta **más de 30 formatos de archivo geoespacial** (Shapefile, GeoJSON, GML, KML, etc.) y puede procesar polígonos con hasta 10 000 puntos sin cargar todo el archivo en memoria, brindándote velocidad y escalabilidad.

## Escenarios del mundo real para polígonos con agujeros
1. **Parcela de tierra con un lago interno** – el lago se modela como un agujero para que no se cuente en el área de la parcela.  
2. **Huella de edificios con patios** – el patio se excluye de la huella del edificio.  
3. **Zonas protegidas dentro de un área de conservación mayor** – puedes excluir secciones restringidas sin crear capas separadas.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. Aspose.GIS for .NET Library: Puedes descargarla desde la **Aspose.GIS for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Entorno de desarrollo: Asegúrate de tener un entorno de desarrollo configurado con Visual Studio o cualquier otro IDE de .NET instalado.

## Importar espacios de nombres
El espacio de nombres `Aspose.Gis` contiene todos los tipos de geometría que necesitarás, incluidos `Polygon`, `LinearRing` y métodos auxiliares para la validación.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ahora, procedamos a crear una geometría de polígono con un agujero usando Aspose.GIS para .NET.

## Paso 1: crear objeto polígono
`Polygon` es el tipo de geometría de Aspose.GIS que representa un polígono plano con anillos interiores opcionales. Comenzamos instanciando un objeto `Polygon` vacío que luego contendrá tanto el anillo exterior como los interiores.

```csharp
Polygon polygon = new Polygon();
```

## Paso 2: definir anillo exterior
`LinearRing` es la clase utilizada para los límites exteriores e interiores. El anillo exterior define la frontera externa del polígono. Añade puntos en orden horario para formar una forma cerrada.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Paso 3: definir anillo interior (agujero)
`LinearRing` también representa anillos interiores. El anillo interior es el **agujero** que se excluirá del área del polígono. Los puntos se añaden típicamente en orden antihorario, pero Aspose.GIS maneja la orientación automáticamente.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Paso 4: asignar anillo exterior y agregar anillo interior al polígono
El método `AddInteriorRing` adjunta uno o más anillos interiores a un `Polygon`. Llamalo después de establecer la propiedad `ExteriorRing`; puedes repetir la llamada para agregar varios agujeros.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Consejos y mejores prácticas
- **La orientación importa para la legibilidad** – aunque Aspose.GIS corrige automáticamente la orientación, mantener los anillos exteriores en sentido horario y los interiores en sentido antihorario facilita la inspección de la geometría en visores GIS.  
- **Cierra cada anillo** – siempre repite la primera coordenada como el último punto; esto garantiza una forma cerrada válida.  
- **Valida después de crear** – puedes llamar a `polygon.IsValid` para asegurar que la geometría cumple con los estándares OGC antes de guardarla.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| El agujero no se muestra en el visor GIS | Orientación del anillo interior invertida | Asegúrate de que los puntos se añadan en la dirección opuesta al anillo exterior (antihorario). |
| Error de polígono inválido | Anillos no cerrados (primer ≠ último punto) | Repite el primer punto como último punto en cada anillo (como se muestra arriba). |
| Geometría vacía inesperada | Olvidaste asignar `ExteriorRing` antes de agregar anillos interiores | Establece `polygon.ExteriorRing` primero, luego llama a `AddInteriorRing`. |

## Preguntas frecuentes
### 1. ¿Qué es Aspose.GIS?
Aspose.GIS es una biblioteca .NET que permite a los desarrolladores trabajar con datos geoespaciales, facilitando la creación, lectura y manipulación de varios formatos de archivo geoespacial.

### 2. ¿Puedo usar Aspose.GIS para proyectos comerciales?
Sí, puedes usar Aspose.GIS tanto en proyectos personales como comerciales adquiriendo una licencia. Visita la **Aspose.GIS purchase page**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) para más detalles.

### 3. ¿Hay una versión de prueba gratuita disponible para Aspose.GIS?
Sí, puedes obtener una prueba gratuita de Aspose.GIS desde la **Aspose.GIS free trial download page**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. ¿Dónde puedo encontrar soporte para Aspose.GIS?
Puedes encontrar soporte para Aspose.GIS en el [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. ¿Cómo puedo obtener una licencia temporal para Aspose.GIS?
Puedes obtener una licencia temporal para Aspose.GIS desde la **Aspose.GIS temporary license page**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Last Updated:** 2026-09-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Tutoriales relacionados

- [Cómo crear geometría de polígono con Aspose.GIS para .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aprenda cómo crear geometría MultiPolygon con Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Convertir polígono a línea con Aspose.GIS para .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}