---
date: 2026-06-30
description: Aprenda cómo crear un shapefile usando Aspose.GIS para .NET. Esta guía
  paso a paso le muestra cómo definir una capa vectorial, agregar un atributo de fecha
  y gestionar datos espaciales de manera eficiente.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Crear nuevo shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cómo crear un shapefile con Aspose.GIS para .NET
url: /es/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear un nuevo Shapefile

## Introducción
Si te estás adentrando en el desarrollo de sistemas de información geográfica (GIS) con .NET, Aspose.GIS es tu solución preferida para **how to create shapefile** de forma programática. Esta biblioteca te brinda control total sobre capas vectoriales, esquemas de atributos y cumplimiento del formato de archivo, de modo que puedas automatizar canalizaciones de datos o generar conjuntos de datos de prueba en minutos.

## Respuestas rápidas
- **¿Qué enseña este tutorial?** Cómo crear un nuevo shapefile, definir una capa vectorial y agregar atributos (incluido un campo de fecha).  
- **¿Qué biblioteca se requiere?** Aspose.GIS for .NET.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para aprendizaje; se requiere una licencia comercial para producción.  
- **¿Qué IDE debo usar?** Visual Studio (cualquier versión reciente).  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para el ejemplo básico.

## Cómo crear shapefile con Aspose.GIS para .NET?
Cargue la biblioteca Aspose.GIS, establezca la carpeta de salida, cree un `VectorLayer`, defina atributos y añada características—todo este flujo de trabajo se puede escribir en menos de 30 líneas de C#. La biblioteca maneja la creación de geometrías, la tipificación de atributos y la escritura del archivo automáticamente, por lo que no tiene que gestionar las especificaciones de bajo nivel de Shapefile usted mismo.

## Requisitos previos
Antes de comenzar el tutorial, asegúrese de que tiene los siguientes requisitos previos:
- Comprensión básica del lenguaje de programación C#.  
- Visual Studio instalado en su máquina.  
- Biblioteca Aspose.GIS para .NET. Puede descargarla [aquí](https://releases.aspose.com/gis/net/).

## Importar espacios de nombres
Start by importing the necessary namespaces to leverage the functionality of Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Paso 1: Configurar su proyecto
Comience creando un nuevo proyecto C# en Visual Studio e incluya la biblioteca Aspose.GIS.

## Paso 2: Definir el directorio del documento
```csharp
string dataDir = "Your Document Directory";
```
Reemplace *Your Document Directory* con la ruta real donde desea guardar su nuevo shapefile.

## Paso 3: Crear un VectorLayer
La clase `VectorLayer` representa una única capa shapefile que almacena datos de geometría y atributos.  
En este paso definimos una capa vectorial y declaramos tres atributos: un campo de texto (`name`), un campo entero (`age`) y un campo de fecha‑hora (`dob`). Añadir el atributo de fecha es crucial para los análisis de **temporal GIS shapefile**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Paso 4: Añadir características
### Caso 1: Establece valores individualmente
El método `SetValues` asigna valores de atributos a una característica en el orden en que fueron definidos.  
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
Aquí creamos dos puntos, establecemos cada atributo por separado y añadimos las características a la capa.

### Caso 2: Establece nuevos valores para todos los atributos
Alternativamente, puede proporcionar todos los valores de atributos a la vez usando `SetValues` con una matriz de objetos.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
En este enfoque rellenamos todos los valores de atributos en una sola llamada usando una matriz de objetos—útil cuando tiene muchos atributos.

## ¿Por qué es importante?
Crear un shapefile de forma programática le permite automatizar canalizaciones de datos, generar conjuntos de datos de prueba o incrustar la salida GIS directamente en servicios web. Aspose.GIS soporta **30+ formatos vectoriales y raster** y puede escribir shapefiles de cientos de páginas sin cargar todo el archivo en memoria, ofreciendo tanto velocidad como escalabilidad.

## Errores comunes y consejos
- **Separadores de ruta:** Use `Path.Combine` para compatibilidad multiplataforma en lugar de concatenar cadenas.  
- **Orden de atributos:** El orden de los valores en `SetValues` debe coincidir con el orden en que añadió los atributos.  
- **Manejo de fechas:** Siempre use `DateTimeKind.Utc` si sus datos GIS se compartirán entre zonas horarias.

## Conclusión
¡Felicidades! Ha creado con éxito un nuevo shapefile usando Aspose.GIS para .NET. Este tutorial cubrió los conceptos básicos para configurar su proyecto, definir una capa vectorial y añadir características—incluido un atributo de fecha. A medida que explore más, consulte la [documentación](https://reference.aspose.com/gis/net/) para funciones y funcionalidades avanzadas.

## Preguntas frecuentes
**Q: ¿Puedo usar Aspose.GIS con otros lenguajes de programación?**  
A: Aspose.GIS principalmente soporta .NET, pero también hay versiones disponibles para Java.

**Q: ¿Hay una prueba gratuita disponible?**  
A: Sí, puede acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar soporte para Aspose.GIS?**  
A: Visite el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para soporte comunitario y discusiones.

**Q: ¿Cómo puedo obtener una licencia temporal?**  
A: Obtenga su licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo comprar Aspose.GIS para .NET?**  
A: Puede adquirir la biblioteca [aquí](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-06-30  
**Probado con:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Obtener atributos de capa – Recuperar información de atributos de capa con Aspose.GIS para .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Crear capa vectorial y establecer el sistema de referencia espacial de la capa](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Crear capa vectorial en File GDB – Tutorial de Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}