---
date: 2026-07-05
description: Aprenda cómo recortar características de capa con Aspose.GIS for .NET,
  incluyendo cómo recortar raster con polygon, extraer raster cell size y recuperar
  raster extent. Descargue su free trial ahora.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Cómo recortar características de capa
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cómo recortar características de capa con Aspose.GIS for .NET
url: /es/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo recortar características de capa

## Introducción
En este tutorial aprenderá **cómo recortar capas** utilizando Aspose.GIS para .NET, una biblioteca potente que le permite **recortar ráster con polígono**, **extraer el tamaño de celda del ráster** y **recuperar la extensión del ráster** para un análisis geoespacial preciso. Ya sea que esté preparando datos para un mapa web, recortando imágenes satelitales o aislando una región de interés, esta guía paso a paso le muestra exactamente cómo realizar la tarea de forma rápida y fiable.

## Respuestas rápidas
- **¿Qué significa “recortar capa”?** Recorta una capa ráster o vectorial a los límites de una geometría suministrada, descartando todo lo que está fuera.  
- **¿Qué geometría se usa en este ejemplo?** Un polígono definido en formato WKT (Well‑Known Text).  
- **¿Puedo extraer el tamaño de celda después de recortar?** Sí – la propiedad `CellSize` devuelve el ancho y la altura de una celda ráster.  
- **¿Necesito una licencia para ejecutar el código?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es “recortar capa”?
**Recortar una capa significa restringir el conjunto de datos a un área geográfica específica, descartando todo lo que está fuera.** Esta operación reduce el tamaño del archivo, acelera el procesamiento posterior y centra el análisis en la región que le interesa. Al limitar los datos al área de interés, también simplifica flujos de trabajo posteriores como el estilo, el análisis y la publicación, mientras se preserva el sistema de referencia de coordenadas y los metadatos originales.

## ¿Por qué usar Aspose.GIS para recortar?
**Aspose.GIS procesa archivos ráster de hasta 2 GB sin cargar la imagen completa en memoria y soporta más de 30 formatos ráster, incluidos GeoTIFF, JPEG2000 y PNG.** La biblioteca ofrece una llamada de una sola línea `Crop`, manejo automático de CRS y rendimiento multihilo que puede recortar un GeoTIFF de 500 MB en menos de un segundo en un servidor típico.

## Requisitos previos
Antes de adentrarse en la magia de la manipulación geoespacial, asegúrese de contar con los siguientes requisitos:

- Biblioteca Aspose.GIS para .NET: Asegúrese de que la biblioteca Aspose.GIS esté instalada en su proyecto .NET. Puede descargarla [aquí](https://releases.aspose.com/gis/net/).  
- Directorio de documentos: Configure un directorio para almacenar sus documentos. Reemplace `"Your Document Directory"` en el código proporcionado con la ruta real a su directorio de documentos.

Ahora, profundicemos en la guía paso a paso.

## Importar espacios de nombres
El espacio de nombres `Aspose.Gis` contiene todos los tipos centrales para el manejo de ráster y vectores. Importe este espacio para acceder a `Layer`, `Geometry` y clases relacionadas.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ¿Cómo recorto una capa con un polígono?
`Crop` es un método de la clase `Layer` que extrae un subconjunto ráster definido por una geometría.  
Cargue el ráster de origen, defina una geometría poligonal y llame al método `Crop`; toda la operación se realiza en una sola línea de código. El método devuelve un nuevo ráster que contiene solo los píxeles dentro del polígono, preservando automáticamente la referencia espacial original.

## Paso 1: Abrir y recortar la capa (recortar ráster con polígono)
`Layer` representa un conjunto de datos ráster que puede abrirse, consultarse y editarse.  
La clase `Layer` representa un conjunto de datos ráster que puede abrirse, consultarse y editarse. Abrir un GeoTIFF y recortarlo con un polígono aísla el área de interés en solo unas pocas instrucciones.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Paso 2: Recuperar información del ráster (extraer tamaño de celda del ráster y recuperar extensión del ráster)
`CellSize` proporciona el ancho y la altura de cada celda ráster en unidades de coordenadas.  
`Extent` devuelve el cuadro delimitador geográfico del ráster.  
La propiedad `CellSize` brinda el ancho y la altura de cada celda ráster en unidades de coordenadas, mientras que la propiedad `Extent` devuelve el cuadro delimitador geográfico del ráster recortado. Ambas piezas de información son esenciales para cálculos posteriores, como la medición de áreas o la reproyección.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Paso 3: Mostrar información
Imprima la información extraída para comprender el impacto del proceso de recorte en sus datos geoespaciales.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Repita estos pasos según sea necesario para refinar y adaptar sus datos geoespaciales a los requisitos específicos del proyecto.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Orientación incorrecta del polígono** | Asegúrese de que el polígono WKT siga la regla de la mano derecha (sentido antihorario para anillos externos). |
| **Falta de referencia espacial** | Verifique que el GeoTiff de origen contenga un CRS; de lo contrario, establezca uno manualmente antes de recortar. |
| **Ralentización del rendimiento en rásters enormes** | Use `layer.Crop` en una copia reducida o procese el ráster en mosaicos. |

## Preguntas frecuentes
**P: ¿Existe una licencia temporal disponible para Aspose.GIS para .NET?**  
R: Sí, puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo encontrar documentación completa para Aspose.GIS para .NET?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/gis/net/).

**P: ¿Cómo puedo buscar soporte o conectar con la comunidad de Aspose.GIS para .NET?**  
R: Visite el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para soporte y participación comunitaria.

**P: ¿Puedo descargar una prueba gratuita de Aspose.GIS para .NET?**  
R: Sí, puede descargar una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo comprar Aspose.GIS para .NET?**  
R: Puede adquirir la biblioteca [aquí](https://purchase.aspose.com/buy).

**P: ¿Puedo recortar múltiples capas en una sola ejecución?**  
R: Sí—itere sobre cada capa y aplique la misma llamada `Crop` con la geometría deseada.

**P: ¿La API admite otros formatos ráster (p. ej., JPEG2000)?**  
R: Aspose.GIS admite todos los formatos expuestos por los controladores GDAL subyacentes, incluidos JPEG2000, PNG y más.

## Conclusión
Al seguir esta guía ahora sabe **cómo recortar capas** de manera eficiente con Aspose.GIS para .NET. Puede **recortar ráster con polígono**, **extraer el tamaño de celda del ráster** y **recuperar la extensión del ráster** para adaptarse a cualquier necesidad del proyecto. Explore APIs adicionales para reproyección, estilo de ráster y análisis vectorial para desbloquear todo el potencial de sus flujos de trabajo geoespaciales.

---

**Última actualización:** 2026-07-05  
**Probado con:** Aspose.GIS 24.10 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [How to Create Polygon Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}