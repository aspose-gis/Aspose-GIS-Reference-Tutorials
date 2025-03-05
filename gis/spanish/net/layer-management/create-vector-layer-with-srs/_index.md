---
title: Crear capa vectorial con SRS
linktitle: Crear capa vectorial con SRS
second_title: Aspose.GIS API .NET
description: Explore Aspose.GIS para .NET su clave para una integración SIG perfecta. Cree capas vectoriales sin esfuerzo con sistemas de referencia espaciales específicos. ¡Descargar ahora!
type: docs
weight: 13
url: /es/net/layer-management/create-vector-layer-with-srs/
---
## Introducción
Aspose.GIS para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con datos del sistema de información geográfica (GIS) sin problemas en aplicaciones .NET. En este tutorial, nos centraremos en crear una capa vectorial con un sistema de referencia espacial (SRS). Al final de esta guía, podrá integrar sin esfuerzo capacidades SIG en sus proyectos .NET.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos de desarrollo C# y .NET.
-  Aspose.GIS para la biblioteca .NET instalada. Puedes descargarlo[aquí](https://releases.aspose.com/gis/net/).
- Un entorno de desarrollo configurado y listo.
## Importar espacios de nombres
Asegúrese de haber importado los espacios de nombres necesarios al principio de su archivo C#:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Paso 1: configurar el sistema de referencia espacial proyectado
Creemos un sistema de referencia espacial proyectado (SRS) usando la proyección World Mercator como ejemplo. Sigue estos pasos:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Paso 2: cree una capa vectorial y agregue funciones
Ahora, creemos un archivo de forma y agreguemos funciones con el SRS especificado:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Esto generará una excepción ya que la geometría tiene un SRS diferente.
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Paso 3: verificar el sistema de referencia espacial
Finalmente, abramos la capa y verifiquemos su sistema de referencia espacial:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84/Mercator Mundial"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Debería volver verdadero
}
```
Si sigue estos pasos, habrá creado con éxito una capa vectorial con un sistema de referencia espacial específico utilizando Aspose.GIS para .NET.
## Conclusión
Integrar la funcionalidad SIG en sus aplicaciones .NET nunca ha sido tan fácil gracias a Aspose.GIS. Con la capacidad de crear capas vectoriales sin esfuerzo y administrar sistemas de referencia espacial, puede mejorar sus proyectos con poderosas capacidades geoespaciales.
## Preguntas frecuentes
### ¿Aspose.GIS es compatible con todos los formatos de archivos SIG?
 Aspose.GIS admite varios formatos SIG, incluidos Shapefile, GeoJSON, KML y más. Comprobar el[documentación](https://reference.aspose.com/gis/net/) para la lista completa.
### ¿Puedo utilizar Aspose.GIS en una aplicación web?
¡Absolutamente! Aspose.GIS para .NET es versátil y se puede utilizar en aplicaciones web, aplicaciones de escritorio e incluso aplicaciones móviles.
### ¿Dónde puedo obtener soporte para Aspose.GIS?
 Puede encontrar una comunidad útil en el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33) para cualquier consulta o problema que pueda surgir.
### ¿Hay una prueba gratuita disponible?
 Sí, puede explorar las funciones de Aspose.GIS obteniendo una prueba gratuita[aquí](https://releases.aspose.com/).
### ¿Cómo puedo comprar una licencia para Aspose.GIS?
 Para comprar una licencia, visite el[pagina de compra](https://purchase.aspose.com/buy).