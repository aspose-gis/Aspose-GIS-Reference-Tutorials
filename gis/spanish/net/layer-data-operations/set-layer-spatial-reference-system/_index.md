---
date: 2026-06-15
description: Aprenda cómo crear una capa vectorial y establecer el sistema de referencia
  espacial de la capa con Aspose.GIS para .NET. Domine la definición de la referencia
  espacial, la adición de una entidad de punto y la obtención del código EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Establecer el sistema de referencia espacial de la capa
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
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
En el amplio panorama de los Sistemas de Información Geográfica (GIS), **Aspose.GIS for .NET** se destaca como una biblioteca robusta y de alto rendimiento que admite **más de 70** formatos vectoriales y raster y puede procesar archivos de más de **10 GB** sin cargar todo el conjunto de datos en memoria. En este tutorial **creará una capa vectorial**, definirá su referencia espacial, **añadirá una entidad puntual** y recuperará el código EPSG, todo con una guía clara paso a paso. Ya sea que esté construyendo un servicio de mapeo, una canalización de conversión de datos o un motor de análisis espacial, dominar estos fundamentos mantendrá el sistema de coordenadas de su shapefile preciso y su flujo de trabajo GIS confiable.

## Respuestas rápidas
- **¿Qué significa “create vector layer”?** Crea una nueva capa GIS (por ejemplo, un Shapefile) que puede almacenar geometrías como puntos, líneas o polígonos.  
- **¿Qué código EPSG se usa en el ejemplo?** EPSG 26918 (NAD83 / UTM zona 18N).  
- **¿Puedo añadir una entidad puntual después de crear la capa?** Sí—use `ConstructFeature()` y asigne una geometría `Point`.  
- **¿Cómo recupero el CRS de la capa?** Lea `layer.SpatialReferenceSystem.EpsgCode` o `.Name`.  
- **¿Necesito una licencia para Aspose.GIS?** Hay una prueba gratuita disponible; se requiere una licencia para uso en producción.

## ¿Qué es crear capa vectorial?
La operación **create vector layer** crea un nuevo conjunto de datos vectorial (como un Shapefile) que puede contener entidades geométricas y datos de atributos. En Aspose.GIS, esto se realiza instanciando un objeto `VectorLayer` con un controlador y un sistema de referencia espacial.

## ¿Por qué establecer correctamente el sistema de coordenadas (CRS) de la capa?
Establecer el sistema de referencia de coordenadas (CRS) correcto garantiza que cada geometría que almacene se alinee con otros conjuntos de datos espaciales. Con Aspose.GIS puede definir el CRS mediante un código EPSG estándar, lo que garantiza la interoperabilidad con software GIS en todo el mundo. Por ejemplo, EPSG 26918 define NAD83 / UTM zona 18N, una proyección común para datos en el este de los Estados Unidos.

## Requisitos previos
- Experiencia en desarrollo .NET (C# o VB.NET).  
- Visual Studio 2022 o posterior.  
- Biblioteca Aspose.GIS para .NET – descárguela **[aquí](https://releases.aspose.com/gis/net/)**.  
- Familiaridad básica con los sistemas de referencia espacial (CRS/EPSG).

## Importar espacios de nombres
El espacio de nombres `Aspose.Gis` proporciona las clases GIS centrales, mientras que `Aspose.Gis.Geometries` le brinda tipos de geometría como `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## ¿Cómo crear una capa vectorial en Aspose.GIS para .NET?
VectorLayer representa un conjunto de datos vectorial como un Shapefile y proporciona métodos para crear, leer y editar entidades.  
SpatialReferenceSystem define el sistema de referencia de coordenadas mediante un código EPSG.  

Cargue la carpeta de destino, defina un `SpatialReferenceSystem` codificado con EPSG y llame a `VectorLayer.Create` con el controlador Shapefile. Esta única llamada crea un nuevo archivo `.shp`, escribe los archivos acompañantes `.shx` y `.dbf`, e incrusta los metadatos del CRS, listo para la inserción de entidades de manera eficiente.

### Paso 1: Especificar el directorio del documento
Comience especificando la ruta a su directorio de documentos. Este será el lugar donde se almacenarán sus archivos de datos espaciales.

```csharp
string dataDir = "Your Document Directory";
```

### Paso 2: Definir la referencia espacial y establecer el sistema de coordenadas del Shapefile
`SpatialReferenceSystem` representa el CRS de una capa, identificado por un código EPSG.  

Defina la ruta para el Shapefile y **defina la referencia espacial** utilizando el código EPSG (26918 en este ejemplo). Este paso **establece el sistema de coordenadas del shapefile** para la capa.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## ¿Cómo añadir una entidad puntual a una capa vectorial?
`Point` es un tipo de geometría que representa un par único de coordenadas X/Y.  

Construya una nueva entidad, asigne una geometría `Point` con las coordenadas X/Y deseadas y añada la entidad a la `VectorLayer` abierta. La operación escribe la geometría en el archivo `.shp` y el registro de atributos en el archivo `.dbf` en una única transacción.

### Paso 3: Crear capa vectorial
`ConstructFeature` crea un nuevo objeto de entidad que puede contener datos de geometría y atributos.  

Ahora **cree la capa vectorial** con la ruta del Shapefile especificada, el tipo de controlador (Shapefile) y el sistema de referencia espacial que acaba de definir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Paso 4: Añadir entidad puntual a la capa
Construya una nueva entidad y **añada la entidad puntual** estableciendo su geometría (un `Point` con coordenadas 60, 24). Luego añada la entidad a la capa vectorial.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Paso 5: Recuperar información del sistema de referencia espacial (recuperar código EPSG)
Abra la capa vectorial y recupere información sobre el sistema de referencia espacial, como el código EPSG y el nombre legible por humanos. Esto demuestra cómo **recuperar el código EPSG** y **establecer el CRS de la capa**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **La capa no se abre** | Controlador incorrecto o ruta de archivo corrupta | Verifique `Drivers.Shapefile` y asegúrese de que `path` apunte a un archivo `.shp` existente. |
| **CRS incorrecto mostrado** | Uso del código EPSG incorrecto | Verifique nuevamente el código EPSG con una fuente autorizada (p.ej., EPSG.io). |
| **Entidad no guardada** | No se llama a `layer.Add(feature)` dentro del bloque `using` | Asegúrese de que el método `Add` se ejecute antes de que la capa se libere. |

## Preguntas frecuentes
**P: ¿Cómo cambio el CRS de un Shapefile existente?**  
R: Abra la capa, cree un nuevo `SpatialReferenceSystem` con el código EPSG deseado, asígnelo a `layer.SpatialReferenceSystem` y luego guarde la capa.

**P: ¿Puedo añadir otros tipos de geometría (p.ej., polígonos) usando el mismo enfoque?**  
R: Sí—reemplace `new Point(x, y)` por `new Polygon(...)` o `new LineString(...)` según sea necesario.

**P: ¿Es posible trabajar con conjuntos de datos grandes de manera eficiente?**  
R: Use APIs de transmisión (`VectorLayer.Create` con `FeatureCollection`) y libere las capas rápidamente para liberar recursos.

**P: ¿Aspose.GIS admite la transformación de coordenadas?**  
R: Sí—use `Geometry.Transform(targetSrs)` para reproyectar geometrías entre diferentes referencias espaciales.

**P: ¿Qué versiones de .NET son compatibles?**  
R: Aspose.GIS funciona con .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Última actualización:** 2026-06-15  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Crear capa vectorial y establecer tolerancia de linealización usando Aspose.GIS para .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Crear capa vectorial en File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [referencia espacial wgs84 – Añadir capa a GDB usando Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}