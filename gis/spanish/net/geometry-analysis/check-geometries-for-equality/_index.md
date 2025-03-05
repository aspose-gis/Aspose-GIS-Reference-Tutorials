---
title: Verifique la igualdad de las geometrías
linktitle: Verifique la igualdad de las geometrías
second_title: Aspose.GIS API .NET
description: Aprenda a utilizar Aspose.GIS para .NET para verificar la igualdad de geometrías en sus aplicaciones .NET con este completo tutorial.
type: docs
weight: 10
url: /es/net/geometry-analysis/check-geometries-for-equality/
---
## Introducción
Aspose.GIS para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con datos geoespaciales de manera eficiente en sus aplicaciones .NET. Ya sea que esté creando aplicaciones de mapeo, herramientas de análisis espacial o integrando funcionalidad geoespacial en un software existente, Aspose.GIS proporciona las herramientas que necesita para realizar el trabajo.
## Requisitos previos
Antes de sumergirse en el uso de Aspose.GIS para .NET, asegúrese de tener implementados los siguientes requisitos previos:
### Marco .NET instalado
Asegúrese de tener .NET Framework instalado en su sistema. Puede descargarlo desde el sitio web de Microsoft.
### Aspose.GIS para la biblioteca .NET
 Descargue e instale la biblioteca Aspose.GIS para .NET desde[pagina de descarga](https://releases.aspose.com/gis/net/). Siga las instrucciones de instalación proporcionadas en la documentación.
### Entorno de desarrollo
Configure su entorno de desarrollo preferido, como Visual Studio, para el desarrollo .NET.

## Importar espacios de nombres
En su aplicación .NET, importe los espacios de nombres necesarios para utilizar la funcionalidad Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Paso 1: definir geometrías
Primero, defina las geometrías que desea comparar. En este ejemplo, tenemos dos geometrías:`geometry1` y`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Paso 2: Verifique la igualdad de las geometrías
 Ahora, verifique si las geometrías son espacialmente iguales usando el`SpatiallyEquals` método proporcionado por Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Verdadero
```
 Esto se imprimirá`True` a la consola desde`geometry1` y`geometry2` son espacialmente iguales.
## Paso 3: modificar la geometría
 A continuación, modifiquemos`geometry2` añadiendo un nuevo punto.
```csharp
geometry2.AddPoint(3, 3);
```
## Paso 4: Vuelva a verificar la igualdad
Ahora, vuelva a verificar la igualdad de las geometrías después de la modificación.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // FALSO
```
 Esta vez, la salida será`False` ya que las geometrías ya no son espacialmente iguales debido a la modificación realizada a`geometry2`.

## Conclusión
En conclusión, Aspose.GIS para .NET proporciona potentes herramientas para trabajar con datos geoespaciales en aplicaciones .NET. Siguiendo esta guía paso a paso, puede comprobar fácilmente la igualdad de las geometrías utilizando los métodos de Aspose.GIS.
## Preguntas frecuentes
### ¿Puedo usar Aspose.GIS para .NET con otros frameworks .NET?
Sí, Aspose.GIS para .NET es compatible con varios marcos .NET, incluidos .NET Core y .NET Standard.
### ¿Hay una prueba gratuita disponible para Aspose.GIS para .NET?
 Sí, puedes descargar una prueba gratuita desde[página de lanzamientos](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación para Aspose.GIS para .NET?
 Puede encontrar documentación detallada en el[Página de documentación de Aspose.GIS](https://reference.aspose.com/gis/net/).
### ¿Cómo puedo obtener soporte para Aspose.GIS para .NET?
 Puede obtener soporte en el foro de la comunidad Aspose.GIS.[aquí](https://forum.aspose.com/c/gis/33).
### ¿Puedo comprar una licencia temporal de Aspose.GIS para .NET?
 Sí, puede comprar una licencia temporal en el[pagina de compra](https://purchase.aspose.com/temporary-license/).