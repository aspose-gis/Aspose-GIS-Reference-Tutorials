---
date: 2026-06-30
description: Aprenda cómo agregar una capa a un conjunto de datos File GDB usando
  Aspose.GIS con referencia espacial WGS84. Siga esta guía paso a paso para agregar
  una capa en .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Agregar capa a conjunto de datos File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cómo agregar capa a un conjunto de datos File GDB con referencia espacial WGS84
  usando Aspose.GIS
url: /es/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# cómo agregar una capa – referencia espacial wgs84 con Aspose.GIS

## Introducción
Listo para impulsar su flujo de trabajo GIS con Aspose.GIS para .NET? En este tutorial aprenderá **cómo agregar una capa** a un conjunto de datos File GDB mientras trabaja con el sistema de coordenadas **spatial reference WGS84**. Recorreremos cada paso, desde preparar su carpeta de datos hasta validar la capa recién creada, para que pueda comenzar a manipular datos geográficos con confianza y eficiencia.

## Respuestas rápidas
- **¿Cuál es el sistema de coordenadas principal utilizado?** spatial reference wgs84 (WGS 84)  
- **¿Qué biblioteca proporciona la API?** Aspose.GIS for .NET  
- **¿Necesito una licencia para pruebas?** Sí – una licencia temporal de Aspose está disponible.  
- **¿Puedo agregar atributos a la nueva capa?** Absolutamente, puede definir cualquier número de atributos de entidad.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## ¿Qué es spatial reference wgs84?
El spatial reference wgs84 (World Geodetic System 1984) es el sistema de coordenadas geográficas más utilizado. Define la latitud y longitud en grados y sirve como el CRS predeterminado para muchos conjuntos de datos GIS, incluido el que crearemos en esta guía.

## ¿Por qué usar Aspose.GIS para agregar una capa?
Cargue sus datos GIS sin binarios de terceros y mantenga el control total sobre la definición del esquema. Aspose.GIS admite **más de 40 sistemas de referencia espacial**, puede procesar archivos de más de **2 GB** sin cargar todo el conjunto de datos en memoria, y funciona en Windows, Linux y macOS. Esto lo convierte en una solución confiable y multiplataforma para la automatización GIS de nivel empresarial.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

- Aspose.GIS for .NET Library: Descargue e instale la biblioteca desde la [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Cree una carpeta dedicada en su máquina para almacenar archivos GIS.  
- Una licencia temporal de Aspose (opcional para evaluación) – consulte las preguntas frecuentes a continuación para el enlace de descarga.

## Importar espacios de nombres
Agregue las declaraciones `using` requeridas a su proyecto C# para que pueda acceder a las clases de Aspose.GIS:

*No se requiere bloque de código aquí; simplemente agregue las siguientes líneas al inicio de su archivo:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Paso 1: Copiar directorio
**Definition anchor:** Un conjunto de datos File GDB es una geodatabase ESRI basada en carpetas que almacena datos espaciales en un conjunto de archivos.  
Primero, duplique la carpeta que contiene el conjunto de datos GDB original. Mantener una copia protege los datos de origen mientras experimenta.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Paso 2: Abrir conjunto de datos y verificar capacidad de creación
`Dataset` representa una colección de capas GIS almacenadas en un File GDB. Abra el conjunto de datos recién copiado y confirme que puede crear nuevas capas. La propiedad `CanCreateLayers` debe devolver **True**. **`CanCreateLayers` es una propiedad booleana que indica si el conjunto de datos admite la creación de nuevas capas.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Paso 3: Crear y poblar una nueva capa con spatial reference wgs84
Ahora creamos una capa llamada **data** y establecemos explícitamente su referencia espacial a **Wgs84**. También añadimos un atributo simple llamado **Name** e insertamos una entidad de punto. **`CreateLayer` crea una nueva capa en el conjunto de datos con el nombre y la referencia espacial especificados.** **`SpatialReference` representa el sistema de coordenadas usado por una capa.** **`Feature` es un objeto geográfico individual (punto, línea o polígono) almacenado en una capa.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Paso 4: Abrir y validar la capa añadida
Finalmente, abra la capa que acaba de crear y verifique su contenido. La consola mostrará que la capa contiene una entidad y que el atributo **Name** coincide con lo que establecimos. **`Layer.Open` abre una capa existente para lectura o edición.** Esto confirma que la capa se añadió correctamente y que la referencia espacial es WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## ¿Cómo agregar una capa a un conjunto de datos File GDB?
Cargue el conjunto de datos, llame a `CreateLayer` con el nombre y la referencia espacial deseados, defina el esquema de atributos y luego inserte entidades. Todo esto se puede hacer con un puñado de llamadas a métodos de Aspose.GIS, y la API maneja el bloqueo de archivos y la validación del esquema automáticamente. El proceso garantiza que la nueva capa se ajuste a la referencia espacial del conjunto de datos, que las definiciones de atributos se almacenen en el esquema de la capa y que los datos puedan ser accedidos por cualquier software GIS que admita File GDB.

## Problemas comunes y consejos
- **Ruta incorrecta:** Asegúrese de que `dataDir` termine con un separador de ruta (`/` o `\`) para que las cadenas concatenadas formen rutas de archivo válidas.  
- **Errores de licencia:** Si ve advertencias de licencia, aplique una licencia temporal desde el portal de Aspose antes de ejecutar el código.  
- **Desajuste de CRS:** Al abrir la capa más tarde en otra herramienta GIS, confirme que la herramienta reconoce WGS 84 (EPSG:4326) como el sistema de coordenadas.  
- **Conjuntos de datos grandes:** Para conjuntos de datos que superen 1 GB, considere usar `Dataset.OpenReadOnly` para reducir el consumo de memoria.

## Preguntas frecuentes
### Q: ¿Puedo usar Aspose.GIS para .NET con otras bibliotecas GIS?
A: Sí, Aspose.GIS funciona de forma independiente pero puede combinarse con bibliotecas como GDAL o NetTopologySuite para procesamiento avanzado.

### Q: ¿Está disponible una licencia temporal para propósitos de prueba?
A: Sí, puede obtener una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/) para pruebas y evaluación.

### Q: ¿Qué sistemas de referencia espacial admite Aspose.GIS para .NET?
A: Aspose.GIS admite más de **40 códigos EPSG**, incluidos sistemas populares como WGS84 (EPSG:4326), Web Mercator (EPSG:3857) y NAD83 (EPSG:4269). Explore la documentación completa [aquí](https://reference.aspose.com/gis/net/).

### Q: ¿Puedo contribuir a la comunidad Aspose.GIS?
A: ¡Absolutamente! Únase a las discusiones y comparta sus experiencias en el [foro Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: ¿Dónde puedo encontrar documentación detallada para Aspose.GIS para .NET?
A: Explore la documentación completa [aquí](https://reference.aspose.com/gis/net/) para obtener información detallada sobre todas las clases, métodos y buenas prácticas.

---

**Última actualización:** 2026-06-30  
**Probado con:** Aspose.GIS for .NET (última versión estable)  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Tutoriales relacionados

- [Crear conjunto de datos File Geodatabase .NET con Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Crear capa vectorial en File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Crear conjunto de datos File GDB y establecer tolerancias para una capa](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}