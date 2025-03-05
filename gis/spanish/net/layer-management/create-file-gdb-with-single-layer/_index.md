---
title: Crear archivo GDB con una sola capa
linktitle: Crear archivo GDB con una sola capa
second_title: Aspose.GIS API .NET
description: Libere el potencial de la gestión de datos geoespaciales en .NET con Aspose.GIS. Aprenda a crear Geodatabases de Archivos y capas paso a paso. ¡Descargar ahora!
type: docs
weight: 11
url: /es/net/layer-management/create-file-gdb-with-single-layer/
---
## Introducción
¿Está listo para mejorar sus aplicaciones geoespaciales con capas y geodatabases de archivos sólidas? No busque más, Aspose.GIS para .NET. En este tutorial, lo guiaremos a través del proceso de creación de una geodatabase de archivos (GDB) con una sola capa usando Aspose.GIS para .NET. Aproveche el poder de la gestión y visualización de datos espaciales en sus aplicaciones .NET sin esfuerzo.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1.  Aspose.GIS para .NET: asegúrese de tener instalada la biblioteca Aspose.GIS. Puedes descargarlo desde el[Página de descarga de Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
2. Entorno de desarrollo: configure un entorno de desarrollo .NET que funcione en su máquina.
3. Directorio de documentos: elija o cree un directorio en su sistema donde almacenará sus archivos de datos geoespaciales.
## Importar espacios de nombres
Para comenzar, necesita importar los espacios de nombres necesarios en su proyecto .NET. Estos espacios de nombres proporcionarán acceso a las funcionalidades de Aspose.GIS. Agregue las siguientes líneas al comienzo de su archivo de código:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Paso 1: configure su directorio de documentos
```csharp
string dataDir = "Your Document Directory";
```
Reemplace "Su directorio de documentos" con la ruta al directorio donde desea almacenar sus archivos de datos geoespaciales.
## Paso 2: crear una geodatabase de archivos con una sola capa
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Este fragmento de código crea una geodatabase de archivos con una sola capa y le agrega una entidad de línea.
## Paso 3: abra la geodatabase de archivos y recupere la información de la capa
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Salida: Número de características: 1
}
```
En este paso, abrimos la geodatabase de archivos creada, recuperamos la capa denominada "capa" e imprimimos el recuento de entidades en la capa.
## Conclusión
¡Felicidades! Ha creado con éxito una geodatabase de archivos con una sola capa utilizando Aspose.GIS para .NET. Explore las amplias capacidades de gestión de datos espaciales en sus aplicaciones con facilidad.
## Preguntas frecuentes
### ¿Puedo usar Aspose.GIS para .NET en mis proyectos .NET existentes?
Sí, Aspose.GIS para .NET se puede integrar perfectamente en sus proyectos .NET existentes.
### ¿Existe una versión de prueba disponible de Aspose.GIS para .NET?
 Sí, puede explorar las características de Aspose.GIS para .NET descargando el[versión de prueba gratuita](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación detallada sobre Aspose.GIS para .NET?
 Referirse a[documentación](https://reference.aspose.com/gis/net/) para obtener información completa sobre Aspose.GIS para .NET.
### ¿Cómo puedo obtener soporte para Aspose.GIS para .NET?
 Visita el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33) para el apoyo y asistencia de la comunidad.
### ¿Hay licencias temporales disponibles para Aspose.GIS para .NET?
 Sí, puedes obtener un[licencia temporal](https://purchase.aspose.com/temporary-license/) para Aspose.GIS para .NET.