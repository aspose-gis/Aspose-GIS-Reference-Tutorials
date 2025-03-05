---
title: Dominio GIS agregue capas a GDB con Aspose.GIS para .NET
linktitle: Agregar capa al archivo del conjunto de datos GDB
second_title: Aspose.GIS API .NET
description: ¡Desbloquee el poder de SIG con Aspose.GIS para .NET! Aprenda cómo agregar capas a conjuntos de datos de File GDB en este tutorial paso a paso. #datosgeográficos #Aspose #GIS
type: docs
weight: 16
url: /es/net/layer-management/add-layer-to-file-gdb-dataset/
---
## Introducción
¿Está listo para mejorar sus capacidades SIG utilizando Aspose.GIS para .NET? En esta guía paso a paso, lo guiaremos a través del proceso de agregar una capa a un conjunto de datos de geodatabase de archivos (GDB). Aspose.GIS para .NET proporciona potentes funciones para manipular información geográfica y, con este tutorial, podrá integrar sin problemas capas adicionales en sus conjuntos de datos.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Biblioteca Aspose.GIS para .NET: descargue e instale la biblioteca desde[Documentación de Aspose.GIS para .NET](https://reference.aspose.com/gis/net/).
- Directorio de documentos: cree un directorio de documentos dedicado en su máquina para almacenar y administrar archivos relacionados con SIG.
## Importar espacios de nombres
En su proyecto .NET, asegúrese de importar los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.GIS. Utilice el siguiente fragmento de código:
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
## Paso 1: copiar directorio
Antes de continuar, duplique el directorio que contiene su conjunto de datos GDB. Este paso garantiza que el conjunto de datos original permanezca intacto. Utilice el fragmento de código proporcionado:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Paso 2: abra el conjunto de datos y verifique la capacidad de creación
 Abra el conjunto de datos duplicado y compruebe si puede crear capas. Esto se confirma por la presencia de`True` en la salida de la consola.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // Verdadero
```
## Paso 3: crear y completar una nueva capa
Cree una nueva capa dentro del conjunto de datos, definiendo su sistema de referencia espacial, atributos y una entidad de muestra. Este fragmento de código demuestra el proceso:
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
## Paso 4: abra y valide la capa agregada
Abra la capa que acaba de crear y valide su contenido. Verifique el recuento y recupere los valores de los atributos usando el siguiente código:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Nombre_1"
}
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo agregar una capa a un conjunto de datos de File GDB usando Aspose.GIS para .NET. Con estas nuevas habilidades, podrá manipular eficientemente datos geográficos en sus proyectos SIG.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.GIS para .NET con otras bibliotecas SIG?
Aspose.GIS para .NET está diseñado para funcionar de forma independiente, pero se puede integrar con otras bibliotecas para mejorar la funcionalidad.
### P: ¿Hay una licencia temporal disponible para realizar pruebas?
 Sí, puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/) para pruebas y evaluación.
### P: ¿Qué sistemas de referencia espacial admite Aspose.GIS para .NET?
Aspose.GIS para .NET admite una amplia gama de sistemas de referencia espacial, lo que brinda flexibilidad en el manejo de datos geográficos.
### P: ¿Puedo contribuir a la comunidad Aspose.GIS?
 ¡Absolutamente! Únase a las discusiones y comparta sus experiencias sobre el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33).
### P: ¿Dónde puedo encontrar documentación detallada de Aspose.GIS para .NET?
 Explora la documentación completa[aquí](https://reference.aspose.com/gis/net/) para obtener información detallada sobre Aspose.GIS para .NET.