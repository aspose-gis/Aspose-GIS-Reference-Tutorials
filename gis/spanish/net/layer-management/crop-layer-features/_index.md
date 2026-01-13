---
date: 2026-01-13
description: Aprenda a recortar características de capas con Aspose.GIS para .NET,
  incluyendo cómo recortar un ráster con un polígono, extraer el tamaño de celda del
  ráster y obtener la extensión del ráster. Descargue su prueba gratuita ahora.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Cómo recortar características de capa con Aspose.GIS para .NET
url: /es/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo recortar características de capa

## Introducción
En este tutorial aprenderá **cómo recortar capas** usando Aspose.GIS para .NET, un enfoque potente que le permite **recortar ráster con un polígono**, **extraer el tamaño de celda del ráster** y **obtener la extensión del ráster** para un análisis geoespacial preciso. Ya sea que esté preparando datos para un mapa web, recortando imágenes satelitales o aislando una región de interés, esta guía paso a paso le muestra exactamente cómo realizar la tarea.

## Respuestas rápidas
- **¿Qué significa “recortar capa”?** Recorta una capa ráster o vectorial a los límites de una geometría suministrada.  
- **¿Qué geometría se usa en este ejemplo?** Un polígono definido en formato WKT.  
- **¿Puedo extraer el tamaño de celda después de recortar?** Sí, la propiedad `CellSize` proporciona esa información.  
- **¿Necesito una licencia para ejecutar el código?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es “cómo recortar capa”?
Recortar una capa significa restringir el conjunto de datos a un área geográfica específica, descartando todo lo que está fuera de la forma definida. Esto reduce el tamaño del archivo, acelera el procesamiento y centra el análisis en la región que le interesa.

## ¿Por qué usar Aspose.GIS para recortar?
- **Manejo de ráster de alto rendimiento** – ideal para archivos GeoTiff grandes.  
- **API sencilla** – llamada `Crop` de una sola línea con cualquier geometría.  
- **Compatibilidad total con .NET** – funciona en aplicaciones de escritorio, servidor y nube.  
- **Manejo preciso de referencias espaciales** – conserva la información del CRS automáticamente.

## Requisitos previos
Antes de adentrarse en la magia de la manipulación geoespacial, asegúrese de contar con los siguientes requisitos:

- Biblioteca Aspose.GIS para .NET: Verifique que tenga la biblioteca Aspose.GIS instalada en su proyecto .NET. Puede descargarla [aquí](https://releases.aspose.com/gis/net/).  
- Directorio de documentos: Configure un directorio para almacenar sus documentos. Reemplace `"Your Document Directory"` en el código proporcionado con la ruta real a su directorio de documentos.

Ahora, vamos a sumergirnos en la guía paso a paso.

## Importar espacios de nombres
Comience importando los espacios de nombres necesarios para aprovechar todo el poder de Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Paso 1: Abrir y recortar la capa (recortar ráster con polígono)
Comience abriendo la capa GeoTiff y recortándola en función de un polígono definido. Esto garantiza que sus datos geoespaciales se refinen a un área de interés específica.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Paso 2: Obtener información del ráster (extraer tamaño de celda del ráster y obtener la extensión del ráster)
Una vez recortada la capa, extraiga información esencial sobre los datos ráster, como el tamaño de celda, el sistema de referencia espacial y los límites.

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
### P: ¿Existe una licencia temporal disponible para Aspose.GIS para .NET?
R: Sí, puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### P: ¿Dónde puedo encontrar documentación completa para Aspose.GIS para .NET?
R: La documentación está disponible [aquí](https://reference.aspose.com/gis/net/).

### P: ¿Cómo puedo obtener soporte o conectar con la comunidad de Aspose.GIS para .NET?
R: Visite el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para soporte y participación comunitaria.

### P: ¿Puedo descargar una prueba gratuita de Aspose.GIS para .NET?
R: Sí, puede descargar una prueba gratuita [aquí](https://releases.aspose.com/).

### P: ¿Dónde puedo comprar Aspose.GIS para .NET?
R: Puede adquirir la biblioteca [aquí](https://purchase.aspose.com/buy).

### P: ¿Puedo recortar múltiples capas en una sola ejecución?
R: Sí, itere sobre cada capa y aplique la misma llamada `Crop` con la geometría deseada.

### P: ¿La API admite otros formatos de ráster (p. ej., JPEG2000)?
R: Aspose.GIS admite todos los formatos que los controladores GDAL subyacentes exponen, incluidos JPEG2000, PNG y más.

## Conclusión
Al seguir esta guía ahora sabe **cómo recortar capas** de manera eficiente con Aspose.GIS para .NET. Puede **recortar ráster con polígono**, **extraer el tamaño de celda del ráster** y **obtener la extensión del ráster** para adaptarse a cualquier necesidad del proyecto. Explore más APIs para reproyección, estilo de ráster y análisis vectorial para desbloquear todo el potencial de sus flujos de trabajo geoespaciales.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-13  
**Probado con:** Aspose.GIS 24.10 para .NET  
**Autor:** Aspose  

---