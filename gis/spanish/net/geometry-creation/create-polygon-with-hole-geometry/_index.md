---
title: Cree un polígono con geometría de agujero usando Aspose.GIS
linktitle: Crear polígono con geometría de agujero
second_title: Aspose.GIS API .NET
description: Aprenda a crear un polígono con geometría de agujero usando Aspose.GIS para .NET. Tutorial paso a paso con ejemplos de código.
weight: 13
url: /es/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cree un polígono con geometría de agujero usando Aspose.GIS

## Introducción
En este tutorial, recorreremos el proceso de creación de un polígono con una geometría de agujero usando Aspose.GIS para .NET. Aspose.GIS es una poderosa biblioteca que permite a los desarrolladores trabajar con datos geoespaciales en sus aplicaciones .NET. 
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Aspose.GIS para la biblioteca .NET: puede descargarlo desde[aquí](https://releases.aspose.com/gis/net/).
2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo configurado con Visual Studio o cualquier otro IDE .NET instalado.
## Importar espacios de nombres
En primer lugar, debe importar los espacios de nombres necesarios para trabajar con las funcionalidades de Aspose.GIS. He aquí cómo hacerlo:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ahora, procedamos a crear un polígono con una geometría de agujero usando Aspose.GIS para .NET.
## Paso 1: crear un objeto poligonal
```csharp
Polygon polygon = new Polygon();
```
## Paso 2: definir el anillo exterior
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Paso 3: Definir el anillo interior (agujero)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Paso 4: asignar un anillo exterior y agregar un anillo interior al polígono
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo crear un polígono con una geometría de agujero usando Aspose.GIS para .NET. Este conocimiento será beneficioso para diversas aplicaciones geoespaciales donde dichas geometrías son esenciales.
## Preguntas frecuentes
### 1. ¿Qué es Aspose.GIS?
Aspose.GIS es una biblioteca .NET que permite a los desarrolladores trabajar con datos geoespaciales, permitiéndoles crear, leer y manipular varios formatos de archivos geoespaciales.
### 2. ¿Puedo utilizar Aspose.GIS para proyectos comerciales?
 Sí, puede utilizar Aspose.GIS tanto para proyectos personales como comerciales comprando una licencia. Visita[aquí](https://purchase.aspose.com/buy) para más detalles.
### 3. ¿Existe una prueba gratuita disponible para Aspose.GIS?
 Sí, puede aprovechar una prueba gratuita de Aspose.GIS desde[aquí](https://releases.aspose.com/).
### 4. ¿Dónde puedo encontrar soporte para Aspose.GIS?
 Puede encontrar soporte para Aspose.GIS en el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. ¿Cómo puedo obtener una licencia temporal para Aspose.GIS?
 Puede obtener una licencia temporal para Aspose.GIS en[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
