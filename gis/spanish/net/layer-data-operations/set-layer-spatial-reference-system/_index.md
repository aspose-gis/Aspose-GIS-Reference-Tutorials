---
date: 2025-12-31
description: Aprende a crear una capa vectorial y establecer el sistema de referencia
  espacial de la capa con Aspose.GIS para .NET. Domina la definición de la referencia
  espacial, la adición de una entidad puntual y la obtención del código EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Crear capa vectorial y establecer el sistema de referencia espacial de la capa
url: /es/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear capa vectorial y establecer el sistema de referencia espacial de la capa

## Introducción
En el amplio panorama de los Sistemas de Información Geográfica (GIS), **Aspose.GIS for .NET** se destaca como una herramienta robusta y versátil para desarrolladores. En este tutorial **creará una capa vectorial**, definirá su referencia espacial, añadirá una característica de punto y recuperará el código EPSG, todo con una guía clara paso a paso. Ya sea que sea un ingeniero GIS experimentado o que recién esté comenzando, estas técnicas le ayudarán a establecer correctamente el sistema de coordenadas del shapefile y a mejorar la fiabilidad de sus flujos de trabajo de datos espaciales.

## Respuestas rápidas
- **¿Qué significa “crear capa vectorial”?** Crea una nueva capa GIS (por ejemplo, un Shapefile) que puede almacenar geometrías como puntos, líneas o polígonos.  
- **¿Qué código EPSG se usa en el ejemplo?** EPSG 26918 (NAD83 / UTM zona 18N).  
- **¿Puedo añadir una característica de punto después de crear la capa?** Sí—utilice `ConstructFeature()` y asigne una geometría `Point`.  
- **¿Cómo recupero el CRS de la capa?** Lea `layer.SpatialReferenceSystem.EpsgCode` o `.Name`.  
- **¿Necesito una licencia para Aspose.GIS?** Hay una prueba gratuita disponible; se requiere una licencia para uso en producción.

## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:
- Conocimientos prácticos de programación .NET.  
- Visual Studio instalado en su sistema.  
- Biblioteca Aspose.GIS for .NET, que puede descargar [aquí](https://releases.aspose.com/gis/net/).  
- Comprensión básica de los sistemas de referencia espacial en GIS.

## Importar espacios de nombres
En su proyecto .NET, comience importando los espacios de nombres necesarios para acceder a las funcionalidades proporcionadas por Aspose.GIS. Use el siguiente fragmento de código:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Paso 1: Especificar el directorio de documentos
Comience especificando la ruta a su directorio de documentos. Esta será la ubicación donde se almacenarán sus archivos de datos espaciales.

```csharp
string dataDir = "Your Document Directory";
```

## Paso 2: Definir la referencia espacial y establecer el sistema de coordenadas del Shapefile
Defina la ruta para el Shapefile y **defina la referencia espacial** usando el código EPSG (26918 en este ejemplo). Este paso **establece el sistema de coordenadas del shapefile** para la capa.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Paso 3: Crear capa vectorial
Ahora **cree la capa vectorial** con la ruta del Shapefile especificada, el tipo de controlador (Shapefile) y el sistema de referencia espacial que acaba de definir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Paso 4: Añadir característica de punto a la capa
Construya una nueva característica y **añada la característica de punto** estableciendo su geometría (un `Point` con coordenadas 60, 24). Luego añada la característica a la capa vectorial.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Paso 5: Recuperar información del sistema de referencia espacial (Recuperar código EPSG)
Abra la capa vectorial y recupere información sobre el sistema de referencia espacial, como el código EPSG y el nombre legible por humanos. Esto demuestra cómo **recuperar el código EPSG** y **establecer el CRS de la capa**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Repita estos pasos según su caso de uso específico, y estará bien encaminado para dominar el arte de **crear capa vectorial** y gestionar referencias espaciales con Aspose.GIS for .NET.

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **La capa no se abre** | Controlador incorrecto o ruta de archivo corrupta | Verifique `Drivers.Shapefile` y asegúrese de que `path` apunte a un archivo `.shp` existente. |
| **Se muestra un CRS incorrecto** | Se está usando el código EPSG equivocado | Verifique el código EPSG con una fuente autorizada (p. ej., EPSG.io). |
| **La característica no se guarda** | No se llama a `layer.Add(feature)` dentro del bloque `using` | Asegúrese de que el método `Add` se ejecute antes de que la capa se libere. |

## Preguntas frecuentes
### ¿Aspose.GIS es compatible con otras bibliotecas GIS?
Sí, Aspose.GIS se integra bien con otras bibliotecas GIS y puede usarse en conjunto con ellas.

### ¿Puedo usar Aspose.GIS tanto para aplicaciones de escritorio como web?
¡Absolutamente! Aspose.GIS es versátil y puede utilizarse tanto en aplicaciones de escritorio como basadas en web.

### ¿Existen opciones de licencia disponibles para Aspose.GIS?
Sí, puede explorar las opciones de licencia y realizar una compra [aquí](https://purchase.aspose.com/buy).

### ¿Hay una prueba gratuita disponible para Aspose.GIS?
¡Claro! Puede descargar una versión de prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Dónde puedo buscar soporte para consultas relacionadas con Aspose.GIS?
Para cualquier soporte o consultas, visite el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Preguntas frecuentes adicionales
**P: ¿Cómo cambio el CRS de un Shapefile existente?**  
R: Abra la capa, cree un nuevo `SpatialReferenceSystem` con el código EPSG deseado y asígnelo a `layer.SpatialReferenceSystem` antes de guardar.

**P: ¿Puedo añadir otros tipos de geometría (p. ej., polígonos) usando el mismo enfoque?**  
R: Sí—reemplace `new Point(x, y)` por `new Polygon(...)` o `new LineString(...)` según sea necesario.

**P: ¿Es posible trabajar con conjuntos de datos grandes de manera eficiente?**  
R: Utilice las API de streaming (`VectorLayer.Create` con `FeatureCollection`) y libere las capas rápidamente para liberar recursos.

**P: ¿Aspose.GIS admite transformación de coordenadas?**  
R: Sí—use `Geometry.Transform(targetSrs)` para reproyectar geometrías entre diferentes referencias espaciales.

**P: ¿Qué versiones de .NET son compatibles?**  
R: Aspose.GIS funciona con .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Conclusión
En este tutorial exploramos cómo **crear una capa vectorial**, definir su referencia espacial, **añadir una característica de punto** y **recuperar el código EPSG** usando Aspose.GIS for .NET. Al dominar estos pasos, podrá establecer con confianza el sistema de coordenadas del shapefile, gestionar el CRS de la capa y crear aplicaciones GIS fiables.

---

**Última actualización:** 2025-12-31  
**Probado con:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}