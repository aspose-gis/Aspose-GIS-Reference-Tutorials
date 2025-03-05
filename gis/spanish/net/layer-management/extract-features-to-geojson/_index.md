---
title: Extraer características a GeoJSON
linktitle: Extraer características a GeoJSON
second_title: Aspose.GIS API .NET
description: Explore la guía paso a paso sobre el uso de Aspose.GIS para .NET para extraer funciones a GeoJSON. ¡Aproveche el poder de SIG con facilidad! #Aspose #SIG
type: docs
weight: 23
url: /es/net/layer-management/extract-features-to-geojson/
---
## Introducción
¡Bienvenido a nuestro tutorial paso a paso sobre cómo extraer funciones a GeoJSON usando Aspose.GIS para .NET! Si es un desarrollador experimentado o recién comienza su viaje en la programación SIG, esta guía lo guiará a través del proceso, asegurándose de que aproveche todo el poder de Aspose.GIS para .NET.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:
-  Aspose.GIS para .NET: asegúrese de tener la biblioteca instalada. Si no, puedes descargarlo desde[Página Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
-  Datos de Shapefile: tenga un Shapefile listo para ingresar. Si necesita datos de muestra, puede encontrarlos en el[Documentación de Aspose.GIS](https://reference.aspose.com/gis/net/).
- Entorno .NET: configure un entorno .NET para ejecutar el código proporcionado.
- Directorio de documentos: defina la ruta a su directorio de documentos en el fragmento de código.
Ahora que tiene todo en su lugar, ¡comencemos a extraer funciones a GeoJSON!
## Importar espacios de nombres
En primer lugar, incluya los espacios de nombres necesarios en su código:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Estos espacios de nombres son esenciales para trabajar con las funcionalidades de Aspose.GIS.
## Paso 1: abrir el archivo Shapefile de entrada
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Su código para procesar el archivo de forma de entrada va aquí
}
```
 Abra el Shapefile de entrada usando el`VectorLayer.Open` método.
## Paso 2: crear GeoJSON de salida
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Su código para crear la salida GeoJSON va aquí
}
```
 Cree el GeoJSON de salida usando el`VectorLayer.Create` método.
## Paso 3: copiar atributos
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Copie los atributos de la capa de entrada a la capa de salida usando el`CopyAttributes` método.
## Paso 4: Características del proceso
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Su código para procesar cada característica de entrada va aquí
}
```
Itere a través de cada característica en la capa de entrada y procéselas individualmente.
## Paso 5: Filtrar funciones por fecha
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtrar funciones según una condición de fecha. En este ejemplo, omite funciones con una fecha de nacimiento anterior a 1982.
## Paso 6: construir una nueva característica
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Construya una nueva entidad para la capa de salida, copiando la geometría y los valores de la entidad de entrada.
¡Felicidades! Ha extraído con éxito funciones a GeoJSON utilizando Aspose.GIS para .NET.
## Conclusión
En este tutorial, exploramos el proceso de extracción de funciones a GeoJSON usando Aspose.GIS para .NET. Esta poderosa biblioteca abre un mundo de posibilidades para el desarrollo de SIG. Experimente con diferentes conjuntos de datos y funcionalidades para desbloquear todo el potencial de Aspose.GIS.
## Preguntas frecuentes
### P: ¿Dónde puedo encontrar más documentación?
 Visita el[Documentación de Aspose.GIS](https://reference.aspose.com/gis/net/) para obtener información detallada.
### P: ¿Cómo puedo obtener una licencia temporal?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo buscar ayuda?
 Disfruta el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoyo y debates de la comunidad.
### P: ¿Hay una prueba gratuita disponible?
 Sí, puedes encontrar la prueba gratuita.[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo comprar Aspose.GIS para .NET?
 Puedes comprar el producto.[aquí](https://purchase.aspose.com/buy).