---
title: Conversión de GeoJSON a File GDB desmitificada
linktitle: Convertir capa GeoJSON a archivo GDB
second_title: Aspose.GIS API .NET
description: ¡Desbloquee maravillas geoespaciales con Aspose.GIS para .NET! Convierta sin esfuerzo capas GeoJSON en geodatabases de archivos. ¡Pruebalo ahora! #Aspose #SIG
weight: 17
url: /es/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Conversión de GeoJSON a File GDB desmitificada

## Introducción
En el ámbito dinámico de los Sistemas de Información Geográfica (SIG), la capacidad de convertir datos sin problemas entre diferentes formatos es crucial. Aspose.GIS para .NET surge como un poderoso aliado, que ofrece un conjunto completo de herramientas para manejar datos geoespaciales sin esfuerzo. En este tutorial, profundizaremos en el proceso de conversión de una capa GeoJSON a una Geodatabase de archivos (Archivo GDB) usando Aspose.GIS para .NET.
## Requisitos previos
Antes de embarcarse en este viaje geoespacial, asegúrese de cumplir con los siguientes requisitos previos:
- Un conocimiento práctico de la programación .NET.
-  Aspose.GIS para .NET instalado. Si no, descárgalo de[aquí](https://releases.aspose.com/gis/net/) y siga las instrucciones de instalación.
## Importar espacios de nombres
Para iniciar el proceso de conversión, comience importando los espacios de nombres necesarios:
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
Ahora, analicemos el proceso en una guía paso a paso:
## Paso 1: configurar la capa GeoJSON
Comience creando una capa GeoJSON con atributos y características relevantes. Aquí hay un fragmento para guiarte:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Agregar atributos
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Construir y agregar características
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Paso 2: copiar el conjunto de datos de prueba
Para preservar la integridad de sus datos de prueba, cree una copia del conjunto de datos. Utilice el siguiente fragmento de código:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Paso 3: convertir GeoJSON a archivo GDB
Ahora es el momento de realizar la conversión. Utilice el siguiente código:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copiar atributos
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Agrega características
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Conclusión
En este tutorial, navegamos por el intrigante terreno de convertir una capa GeoJSON en una geodatabase de archivos usando Aspose.GIS para .NET. Armado con este conocimiento, ahora está equipado para manipular sin problemas datos geoespaciales en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Aspose.GIS es compatible con el último marco .NET?
Sí, Aspose.GIS es compatible con las últimas versiones de .NET framework.
### ¿Puedo convertir otros formatos geoespaciales usando Aspose.GIS?
¡Absolutamente! Aspose.GIS admite una amplia gama de formatos geoespaciales para una manipulación de datos versátil.
### ¿Existe una versión de prueba disponible para Aspose.GIS?
 Sí, puedes explorar las funcionalidades de Aspose.GIS descargando la versión de prueba.[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para consultas relacionadas con Aspose.GIS?
 Dirígete a Aspose.GIS[foro](https://forum.aspose.com/c/gis/33) para soporte dedicado.
### ¿Puedo obtener una licencia temporal para Aspose.GIS?
 Sí, puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
