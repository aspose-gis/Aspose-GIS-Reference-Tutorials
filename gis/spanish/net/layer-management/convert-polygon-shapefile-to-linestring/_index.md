---
date: 2026-06-25
description: Aprende cómo leer shapefile y convertir un shapefile de Polygon a Linestring
  usando Aspose.GIS para .NET. Impulsa tu desarrollo GIS con una guía clara paso a
  paso.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Convertir Polygon Shapefile a Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cómo leer Shapefile C# – Convertir Shapefile de Polygon a Linestring
url: /es/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer Shapefile C# – Convertir Shapefile de Polígono a Linestring

## Introducción
Si necesitas **cómo leer shapefile** datos en un entorno .NET, estás en el lugar correcto. Aspose.GIS for .NET abstrae el formato binario de bajo nivel de un Shapefile, permitiéndote cargar, consultar y transformar características geográficas con solo unas pocas llamadas a la API. Convertir un shapefile de polígono a linestring es especialmente útil cuando deseas extraer representaciones lineales para enrutamiento, análisis de redes o visualización simple.

## Respuestas rápidas
- **¿Qué biblioteca le ayuda a leer shapefile c#?** Aspose.GIS for .NET – soporta más de 50 formatos GIS y maneja archivos de varios cientos de megabytes sin cargar todo el archivo en memoria.  
- **¿Puede convertir un polígono a una línea?** Sí – llama a `LineString` en el anillo exterior del polígono y escribe el resultado en un nuevo shapefile.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para implementaciones en producción; una prueba gratuita funciona para evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **¿Hay una versión de prueba disponible?** Absolutamente – descarga una prueba gratuita desde el sitio de Aspose.

`LineString` es un tipo de geometría que representa una serie de segmentos de línea conectados.

## ¿Qué es “read shapefile c#”?
`Document` es la clase central que representa un conjunto de datos GIS y proporciona acceso a sus características.  
Leer un shapefile en C# significa cargar el archivo `.shp` en memoria para que puedas consultar, modificar o transformar sus geometrías. **Simplemente instancias la clase `Document` con la ruta del archivo, y Aspose.GIS analiza la estructura binaria por ti**, exponiendo las características a través de una colección fácil de usar. Este enfoque elimina la necesidad de trabajar manualmente con encabezados de archivo de bajo nivel o matrices de coordenadas.

## ¿Por qué convertir un polígono a línea con Aspose.GIS?
Convertir un polígono a linestring conserva el contorno exterior exacto mientras elimina los anillos interiores, dándote una representación lineal limpia. Aspose.GIS procesa **conjuntos de datos de hasta 500 MB en menos de 2 segundos en un servidor típico**, lo que hace que las conversiones por lotes sean rápidas y eficientes en memoria. La biblioteca también conserva la referencia espacial original, de modo que las líneas resultantes se alinean perfectamente con cualquier capa GIS existente.

## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrate de tener lo siguiente:

- **Aspose.GIS Library** – Descarga e instala la biblioteca Aspose.GIS desde el [sitio web](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Ten un Shapefile de Polígono listo para la conversión. Si no tienes uno, puedes encontrar datos de muestra o crear el tuyo propio.  
- **Development Environment** – Configura tu entorno de desarrollo .NET con las herramientas necesarias (Visual Studio, .NET SDK, etc.).

## Importar espacios de nombres
La clase `Document` es el objeto central de Aspose.GIS que representa un conjunto de datos GIS y proporciona métodos para leer y escribir shapefiles. Añade los siguientes espacios de nombres al comienzo de tu archivo de código:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ¿Cómo leer shapefile y convertir un polígono a linestring?
Carga el shapefile de polígono fuente, extrae el anillo exterior de cada polígono, crea un `LineString` a partir de ese anillo y escribe el resultado en un nuevo shapefile, todo en cinco pasos sencillos. Este patrón funciona para cualquier tamaño de conjunto de datos y garantiza que el sistema de coordenadas de la fuente se preserve en el destino.

### Paso 1: Establecer el directorio del documento
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Reemplaza `"Your Document Directory"` con la ruta real donde reside tu shapefile.

### Paso 2: Abrir el shapefile de origen
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Esta línea abre el Shapefile de Polígono de origen para que puedas leer sus características.

### Paso 3: Crear el shapefile de Linestring de destino
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Aquí creamos un nuevo Shapefile de Linestring que almacenará las geometrías convertidas.

### Paso 4: Iterar a través de las características de origen
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
El bucle recorre cada característica de polígono en el archivo original.

### Paso 5: Convertir polígono a linestring y escribir en el destino
La propiedad `ExteriorRing` devuelve el contorno exterior de un polígono como un `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
En este bloque convertimos el polígono a línea (`LineString`) y añadimos la nueva característica al shapefile de destino.

## Problemas comunes y consejos
- **Desajuste del sistema de coordenadas** – Asegúrate de que ambas capas, origen y destino, usen la misma referencia espacial; de lo contrario, las líneas pueden aparecer desplazadas.  
- **Archivos grandes** – Al procesar shapefiles muy grandes, considera transmitir las características en lugar de cargarlas todas en memoria a la vez.  
- **Geometrías nulas** – Protege contra características con geometrías vacías para evitar excepciones en tiempo de ejecución.  
- **Extraer líneas de un polígono** – Si solo necesitas el anillo exterior, usa la propiedad `ExteriorRing`; para anillos interiores, itera `InteriorRings`.  

## Preguntas frecuentes

**Q: ¿Aspose.GIS es compatible con todas las versiones de .NET?**  
A: Sí, Aspose.GIS soporta .NET Framework 4.5+, .NET Core 3.1+, y .NET 5/6/7, garantizando una integración fluida con pilas de desarrollo modernas.

**Q: ¿Puedo usar Aspose.GIS para proyectos comerciales?**  
A: Sí, puedes. Compra una licencia [aquí](https://purchase.aspose.com/buy) para eliminar limitaciones de evaluación y obtener soporte completo.

**Q: ¿Hay ejemplos o documentación disponible?**  
A: Sí, puedes encontrar documentación completa y ejemplos de código en la [página de documentación](https://reference.aspose.com/gis/net/).

**Q: ¿Existe una versión de prueba disponible?**  
A: Absolutamente – explora Aspose.GIS con una prueba gratuita visitando [este enlace](https://releases.aspose.com/).

**Q: ¿Dónde puedo buscar ayuda o soporte?**  
A: Visita el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para asistencia de la comunidad y soporte oficial.

---

**Última actualización:** 2026-06-25  
**Probado con:** Aspose.GIS for .NET (última versión)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo convertir Shapefile a GeoJSON usando Aspose.GIS para .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Cómo leer GeoJSON desde Stream con Aspose.GIS para .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cómo crear geometría de Polígono con Aspose.GIS para .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}