---
title: Conversión de coordenadas con Aspose.GIS
linktitle: Convertir coordenadas
second_title: Aspose.GIS API .NET
description: Aprenda a convertir coordenadas con Aspose.GIS para .NET. Se proporcionan guía paso a paso, requisitos previos y preguntas frecuentes.
weight: 25
url: /es/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Conversión de coordenadas con Aspose.GIS

## Introducción
En este tutorial, profundizaremos en el mundo de los sistemas de información geográfica (SIG) utilizando la poderosa biblioteca Aspose.GIS para .NET. Aspose.GIS es un conjunto de herramientas integral que permite a los desarrolladores trabajar con datos espaciales sin esfuerzo. Si es un desarrollador experimentado o recién está comenzando, este tutorial lo guiará a través del proceso de utilización de Aspose.GIS para convertir coordenadas de manera efectiva.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Conocimientos básicos de C#: la familiaridad con el lenguaje de programación C# es esencial para comprender e implementar los ejemplos de código proporcionados.
  
2.  Instalación de Aspose.GIS: asegúrese de haber descargado e instalado la biblioteca Aspose.GIS para .NET. Puedes descargarlo desde el[Sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importar espacios de nombres
Antes de comenzar, importemos los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Dividamos el ejemplo proporcionado en varios pasos para una comprensión clara:
## Paso 1: inicie el proceso de conversión
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Esta línea simplemente muestra un mensaje que indica el inicio del proceso de conversión de coordenadas.
## Paso 2: convertir a grados decimales
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Aquí, convertimos las coordenadas (25,5, 45,5) al formato de grados decimales usando el`AsPointText` método con el`PointFormats.DecimalDegrees` parámetro. Luego, el resultado se imprime en la consola.
## Paso 3: Convertir a grados decimales y minutos
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Este paso convierte las coordenadas al formato de minutos decimales en grados e imprime el resultado.
## Paso 4: Convertir a Grados Minutos Segundos
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
De manera similar, convertimos las coordenadas al formato de grados minutos segundos y mostramos la salida.
## Paso 5: Convertir a GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Finalmente, convertimos las coordenadas al formato GeoRef e imprimimos el resultado.

## Conclusión
En este tutorial, exploramos el proceso de conversión de coordenadas usando Aspose.GIS para .NET. Si sigue la guía paso a paso y utiliza la biblioteca Aspose.GIS, puede manipular eficientemente datos espaciales dentro de sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Aspose.GIS es compatible con otros lenguajes de programación?
Aspose.GIS está dirigido principalmente a desarrolladores .NET, pero ofrece interoperabilidad con Java a través de Aspose.GIS para Java.
### ¿Puedo probar Aspose.GIS antes de comprarlo?
 Sí, puede acceder a una prueba gratuita de Aspose.GIS desde[sitio web](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.GIS?
 Puede buscar ayuda en el foro de la comunidad Aspose.GIS.[aquí](https://forum.aspose.com/c/gis/33).
### ¿Hay licencias temporales disponibles para Aspose.GIS?
 Sí, se pueden obtener licencias temporales del[página de licencia temporal](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar Aspose.GIS?
 Puede comprar Aspose.GIS desde el[pagina de compra](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
