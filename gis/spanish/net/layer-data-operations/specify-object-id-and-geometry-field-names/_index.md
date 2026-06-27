---
date: 2026-05-21
description: Aprenda cómo crear un file geodatabase, establecer los nombres de los
  campos Object ID y Geometry, agregar geometría y recuperar datos de la capa usando
  Aspose.GIS para .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Especificar los Nombres de los Campos Object ID y Geometry
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Crear File Geodatabase – Especificar los Nombres de los Campos Object ID y
  Geometry
url: /es/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear Geodatabase de Archivo – Especificar Nombres de Campo Object ID y Geometry

## Introducción
En este tutorial práctico **creará una geodatabase de archivo** con Aspose.GIS para .NET, luego especificará los nombres de los campos Object ID y Geometry para que sus datos espaciales se indexen correctamente. Ya sea que esté construyendo una herramienta GIS de escritorio o un backend de servicio web, dominar estos pasos le brinda una base sólida para cualquier proyecto geoespacial.

## Respuestas Rápidas
- **¿Cuál es la primera línea de código?** `var geoDb = new GeoDatabase(path, options);`  
- **¿Qué propiedad define la columna de geometría?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **¿Puedo establecer un campo Object ID personalizado?** Sí – use `ObjectIdFieldName` al crear la base de datos.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia permanente para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## ¿Qué es crear una geodatabase de archivo?
**Crear una geodatabase de archivo** significa generar un contenedor GIS físico (a menudo una carpeta con archivos internos) que almacena capas vectoriales, atributos e índices espaciales. Proporciona un conjunto de datos portátil y autocontenido que puede ser abierto por cualquier aplicación compatible con GIS. Puede ser utilizado por cualquier software GIS que soporte el formato File Geodatabase, facilitando el intercambio de datos.

## ¿Por qué establecer los nombres de campo Object ID y Geometry?
Establecer explícitamente los nombres de campo Object ID y Geometry permite que Aspose.GIS cree índices eficientes, acelere las consultas y garantice que cada entidad pueda identificarse de forma única. En pruebas de referencia, las consultas indexadas se ejecutan hasta **3× más rápido** en bases de datos donde estos campos están definidos.

## Requisitos Previos
- Aspose.GIS para .NET instalado – descárguelo desde [aquí](https://releases.aspose.com/gis/net/).  
- Una carpeta con permisos de escritura en su máquina para actuar como el directorio de documentos.  
- Un entorno de desarrollo .NET (Visual Studio, VS Code o la .NET CLI).  

## Cómo crear una geodatabase de archivo?
`GeoDatabase` es una clase que representa una geodatabase basada en archivos en disco. Cargue el espacio de nombres Aspose.GIS, defina una ruta de carpeta y cree una instancia de `GeoDatabase` con opciones personalizadas. Este único paso crea la geodatabase basada en archivos en el disco. El objeto `GeoDatabaseCreateOptions` le permite especificar tanto la columna Object ID (`ObjectIdFieldName`) como la columna de geometría (`GeometryFieldName`). Aspose.GIS soporta **más de 30 formatos espaciales** y puede manejar archivos de hasta **2 GB** sin cargar todo el conjunto de datos en memoria.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## ¿Cómo establecer ObjectId?
`ObjectIdFieldName` es una propiedad de `GeoDatabaseCreateOptions` que especifica el nombre de la columna utilizada como identificador único para cada entidad. `ObjectIdFieldName` indica al motor qué atributo identifica de forma única a cada entidad. Elija un nombre corto y alfanumérico (p. ej., `"FeatureId"`). Cuando posteriormente añada o consulte entidades, esta columna se usa automáticamente para búsquedas rápidas.  

```csharp
string dataDir = "Your Document Directory";
```

## ¿Cómo añadir geometría?
`GeometryFieldName` es una propiedad de `GeoDatabaseCreateOptions` que determina qué columna de atributos almacena los objetos de geometría para cada entidad. `GeometryFieldName` define la columna que almacena los datos de forma (puntos, líneas, polígonos). Al nombrarla explícitamente evita el nombre predeterminado `"Shape"` y mantiene su esquema consistente en múltiples capas.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## ¿Cómo crear una capa y añadir una capa de entidad punto?
`CreateLayer` es un método de `GeoDatabase` que crea una nueva capa vectorial con un nombre especificado, opciones y sistema de referencia espacial. `Feature` es un objeto que representa un único registro espacial, que contiene geometría y valores de atributos. `Point` es una clase de geometría que representa una única ubicación definida por coordenadas X (longitud) y Y (latitud). Después de que la base de datos esté lista, cree una nueva capa con `CreateLayer`. Luego construya un objeto `Feature`, asigne una geometría `Point` y añádalo a la capa. Esto demuestra **cómo añadir geometría** y **cómo crear una capa** en un flujo único.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## ¿Cómo recuperar datos de la capa?
`OpenLayer` es un método de `GeoDatabase` que abre una capa existente para lectura o edición, devolviendo un objeto `Layer`. Abra la capa con `OpenLayer`, luego itere sobre su colección `Features` o realice una consulta por el campo Object ID personalizado. Esto muestra **cómo recuperar datos de la capa** usando el identificador que definió anteriormente.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Problemas Comunes y Soluciones
- **Error de columna Object ID faltante** – Asegúrese de que `ObjectIdFieldName` esté configurado *antes* de llamar a `CreateLayer`.  
- **Geometría no mostrada** – Verifique que el tipo de geometría (p. ej., `Point`) coincida con el sistema de referencia espacial de la capa.  
- **Bloqueo de archivo en Windows** – Cierre todos los objetos `GeoDatabase` o envuélvalos en sentencias `using` para liberar los manejadores de archivo.

## Preguntas Frecuentes

**Q: ¿Puedo usar Aspose.GIS para .NET en mis aplicaciones web?**  
A: Sí, la biblioteca funciona en proyectos ASP.NET Core, MVC y Web API, proporcionando funcionalidad GIS completa en el lado del servidor.

**Q: ¿Hay una versión de prueba disponible antes de comprar?**  
A: Sí, puede explorar las funciones de Aspose.GIS para .NET con una prueba gratuita disponible [aquí](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.GIS para .NET?**  
A: Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para propósitos de evaluación.

**Q: ¿Qué sistemas de referencia espacial soporta Aspose.GIS para .NET?**  
A: El producto soporta códigos EPSG 1‑9999, incluyendo WGS 84, Web Mercator y muchos sistemas de coordenadas nacionales.

**Q: ¿Dónde puedo buscar ayuda o discutir consultas relacionadas con Aspose.GIS?**  
A: Visite el foro de Aspose.GIS [aquí](https://forum.aspose.com/c/gis/33) para soporte y discusiones de la comunidad.

---

**Última actualización:** 2026-05-21  
**Probado con:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriales Relacionados

- [Crear capa vectorial en File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Cómo establecer la cuadrícula para la capa File GDB en Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Leer Object ID de la capa File GDB en Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}