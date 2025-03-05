---
title: Crear nuevo archivo de forma
linktitle: Crear nuevo archivo de forma
second_title: Aspose.GIS API .NET
description: Aprenda a crear un nuevo archivo de forma usando Aspose.GIS para .NET. Siga nuestra guía paso a paso y libere el poder de la manipulación de datos espaciales.
type: docs
weight: 12
url: /es/net/layer-management/create-new-shapefile/
---
## Introducción
Si está profundizando en el desarrollo de sistemas de información geográfica (SIG) con .NET, Aspose.GIS es su solución preferida. Esta poderosa biblioteca permite a los desarrolladores trabajar sin problemas con datos espaciales y, en este tutorial, lo guiaremos a través del proceso de creación de un nuevo archivo de forma usando Aspose.GIS para .NET.
## Requisitos previos
Antes de pasar al tutorial, asegúrese de cumplir los siguientes requisitos previos:
- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio instalado en su máquina.
-  Aspose.GIS para la biblioteca .NET. Puedes descargarlo[aquí](https://releases.aspose.com/gis/net/).
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios para aprovechar la funcionalidad de Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Paso 1: configura tu proyecto
Comience creando un nuevo proyecto C# en Visual Studio e incluya la biblioteca Aspose.GIS.
## Paso 2: definir el directorio de documentos
```csharp
string dataDir = "Your Document Directory";
```
Reemplace "Su directorio de documentos" con la ruta real donde desea guardar su nuevo archivo de forma.
## Paso 3: crear una capa vectorial
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //agregar atributos antes de agregar características
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Este segmento de código configura la capa vectorial y define atributos para sus características.
## Paso 4: agregar funciones
### Caso 1: Establece valores individualmente
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Caso 2: establece nuevos valores para todos los atributos
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Conclusión
 ¡Felicidades! Ha creado con éxito un nuevo archivo de forma utilizando Aspose.GIS para .NET. Este tutorial cubrió los conceptos básicos para configurar su proyecto, definir atributos y agregar funciones. A medida que explores más, consulta la[documentación](https://reference.aspose.com/gis/net/) para características y funcionalidades avanzadas.
## Preguntas frecuentes
### P: ¿Puedo utilizar Aspose.GIS con otros lenguajes de programación?
Aspose.GIS admite principalmente .NET, pero también hay versiones disponibles para Java.
### P: ¿Hay una prueba gratuita disponible?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo encontrar soporte para Aspose.GIS?
 Visita el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoyo y debates de la comunidad.
### P: ¿Cómo puedo obtener una licencia temporal?
 Obtenga su licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo comprar Aspose.GIS para .NET?
 Puedes comprar la biblioteca.[aquí](https://purchase.aspose.com/buy).