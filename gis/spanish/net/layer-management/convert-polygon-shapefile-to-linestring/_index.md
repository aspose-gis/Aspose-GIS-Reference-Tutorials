---
title: Convertir un archivo de forma de polígono a una cadena de líneas
linktitle: Convertir un archivo de forma de polígono a una cadena de líneas
second_title: Aspose.GIS API .NET
description: Explore el poder de Aspose.GIS para .NET y convierta sin esfuerzo archivos de formas poligonales en cadenas de líneas. ¡Impulse su desarrollo SIG hoy!
weight: 18
url: /es/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir un archivo de forma de polígono a una cadena de líneas

## Introducción
Si trabaja con sistemas de información geográfica (SIG) en .NET, Aspose.GIS es una biblioteca poderosa que puede simplificar sus tareas. En este tutorial, lo guiaremos a través del proceso de convertir un archivo de forma de polígono en una cadena de líneas usando Aspose.GIS. Esto puede resultar particularmente útil cuando necesita extraer características lineales de datos poligonales para diversas aplicaciones, como planificación de rutas o análisis de redes.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente en su lugar:
-  Biblioteca Aspose.GIS: descargue e instale la biblioteca Aspose.GIS desde[sitio web](https://releases.aspose.com/gis/net/).
- Datos de Shapefile: tenga un archivo de forma de polígono listo para la conversión. Si no tiene uno, puede buscar datos de muestra o crear los suyos propios.
- Entorno de desarrollo: configure su entorno de desarrollo .NET con las herramientas necesarias.
## Importar espacios de nombres
En su código C#, debe importar los espacios de nombres de Aspose.GIS para acceder a las clases y métodos necesarios. Agregue los siguientes espacios de nombres al comienzo de su archivo de código:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Paso 1: configurar el directorio de documentos
```csharp
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
```
Reemplace "Su directorio de documentos" con la ruta al directorio donde se encuentra su Shapefile.
## Paso 2: abra el archivo Shapefile de origen
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // El resto del código irá aquí.
}
```
Este paso abre el archivo Polygon Shapefile de origen para su lectura.
## Paso 3: crear el archivo Shapefile de cadena de líneas de destino
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // El resto del código irá aquí.
}
```
Aquí, creamos un nuevo Linestring Shapefile para escribir los datos convertidos.
## Paso 4: iterar a través de las funciones de origen
```csharp
foreach (Feature sourceFeature in source)
{
    // El resto del código irá aquí.
}
```
Este bucle recorre en iteración cada característica en el archivo de forma de polígono de origen.
## Paso 5: convertir el polígono en una cadena lineal y escribir en el destino
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
En este paso, cada característica de polígono se convierte en una cadena de líneas y la característica de cadena de líneas resultante se escribe en el Shapefile de destino.
## Conclusión
Siguiendo estos pasos, puede convertir fácilmente un archivo de forma de polígono en una cadena de líneas usando Aspose.GIS para .NET. Este proceso abre nuevas posibilidades para el análisis y visualización de datos en aplicaciones SIG.

## Preguntas frecuentes
### ¿Aspose.GIS es compatible con todas las versiones de .NET?
Sí, Aspose.GIS admite varias versiones de .NET, lo que garantiza la compatibilidad con su entorno de desarrollo.
### ¿Puedo utilizar Aspose.GIS para proyectos comerciales?
 Sí tu puedes. Para utilizar Aspose.GIS en proyectos comerciales, considere comprar una licencia[aquí](https://purchase.aspose.com/buy).
### ¿Hay algún ejemplo o documentación disponible?
 Sí, puede encontrar documentación completa y ejemplos en el[página de documentación](https://reference.aspose.com/gis/net/).
### ¿Hay una versión de prueba disponible?
 Sí, puedes explorar Aspose.GIS con una prueba gratuita visitando[este enlace](https://releases.aspose.com/).
### ¿Dónde puedo buscar ayuda o apoyo?
 Visita el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33) para cualquier consulta relacionada con asistencia o soporte.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
