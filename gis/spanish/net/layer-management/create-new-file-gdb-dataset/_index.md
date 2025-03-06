---
title: Crear nuevo archivo de conjunto de datos GDB
linktitle: Crear nuevo archivo de conjunto de datos GDB
second_title: Aspose.GIS API .NET
description: Explore Aspose.GIS para .NET para crear y administrar conjuntos de datos SIG sin esfuerzo. Descárguelo ahora para un desarrollo geoespacial perfecto. #Aspose #SIG
weight: 10
url: /es/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear nuevo archivo de conjunto de datos GDB

## Introducción
En el ámbito del desarrollo geoespacial, Aspose.GIS para .NET se destaca como un poderoso conjunto de herramientas para administrar y manipular datos del Sistema de Información Geográfica (SIG). Si es un desarrollador experimentado o recién comienza su viaje hacia SIG, este tutorial lo guiará a través del proceso de creación de un nuevo conjunto de datos de geodatabase de archivos (GDB) utilizando Aspose.GIS para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.GIS para .NET: asegúrese de tener instalada la biblioteca Aspose.GIS para .NET. Puedes descargarlo desde el[Página de descarga de Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Entorno de desarrollo: configure su entorno de desarrollo con un IDE compatible, como Visual Studio, y tenga conocimientos básicos de programación .NET.
- Directorio de documentos: reemplace "Su directorio de documentos" en el fragmento de código con la ruta adecuada donde desea almacenar su conjunto de datos de GDB.
- Familiaridad con C#: este tutorial asume que está familiarizado con el lenguaje de programación C#.
## Importar espacios de nombres
En los pasos iniciales, importe los espacios de nombres necesarios para aprovechar la funcionalidad Aspose.GIS en su aplicación .NET:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Paso 1: crear un nuevo conjunto de datos GDB de archivos
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Salida: 0
    // Continúe con los pasos siguientes...
}
```
 Explicación: En este paso, creamos un nuevo conjunto de datos GDB usando el`Dataset.Create` método. Especificamos la ruta y el controlador (FileGdb) para crear una Geodatabase de Archivos. La salida de la consola muestra el recuento de capas inicial, que es cero en este punto.
## Paso 2: crear y completar la capa_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Explicación: Este paso implica crear una capa denominada "capa_1" dentro del conjunto de datos. Define un atributo llamado "valor" de tipo entero y llena la capa con diez entidades, cada una con una geometría de punto.
## Paso 3: Crear y completar Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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
Explicación: Aquí, creamos una segunda capa llamada "capa_2" y agregamos una única entidad con una geometría de cadena de líneas.
## Paso 4: verifique el recuento de capas actualizado
```csharp
Console.WriteLine(dataset.LayersCount); // Salida: 2
```
Explicación: Finalmente, verificamos el recuento de capas actualizadas después de agregar las dos capas. En este caso, la salida debería ser 2.
## Conclusión
¡Felicidades! Creó exitosamente un nuevo conjunto de datos File GDB y lo rellenó con capas usando Aspose.GIS para .NET. Este tutorial proporciona una comprensión fundamental del trabajo con datos geoespaciales en un entorno .NET.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.GIS para .NET con otras bibliotecas SIG?
Aspose.GIS para .NET es un conjunto de herramientas independiente; sin embargo, puede integrarlo con otras bibliotecas .NET para mejorar la funcionalidad.
### P: ¿Existe un foro comunitario para soporte de Aspose.GIS?
 Sí, puede encontrar apoyo y debates sobre el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33).
### P: ¿Cómo puedo obtener una licencia temporal para Aspose.GIS?
 Visita el[Licencia Temporal](https://purchase.aspose.com/temporary-license/) página para obtener información sobre cómo obtener una licencia temporal.
### P: ¿Hay ejemplos y documentación adicionales disponibles?
 Explorar el[Documentación de Aspose.GIS](https://reference.aspose.com/gis/net/) para más ejemplos e información detallada.
### P: ¿Dónde puedo comprar Aspose.GIS para .NET?
 Puede comprar Aspose.GIS para .NET en el[pagina de compra](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
