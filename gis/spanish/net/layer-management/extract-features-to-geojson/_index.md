---
date: 2026-07-05
description: Aprenda cómo convertir shapefile a geojson usando Aspose.GIS para .NET.
  La guía también cubre cómo copiar atributos entre capas y generar un archivo geojson
  con C#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Extraer características a GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Convertir Shapefile a GeoJSON con Aspose.GIS para .NET
url: /es/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir Shapefile a GeoJSON con Aspose.GIS para .NET

## Introducción
En este tutorial completo, paso a paso, aprenderás **cómo convertir shapefile a geojson** usando la poderosa biblioteca Aspose.GIS para .NET. Ya sea que estés construyendo un servicio web de mapas, preparando datos para una aplicación GIS móvil, o simplemente necesites intercambiar datos entre formatos, esta guía te muestra exactamente qué hacer, por qué cada paso es importante y cómo evitar errores comunes.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Convertir un Shapefile a un archivo GeoJSON, copiar atributos entre capas y generar la salida con C#.
- **¿Qué biblioteca se requiere?** Aspose.GIS para .NET.
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para producción; una prueba gratuita funciona para evaluación.
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para una conversión básica.
- **¿Puedo ejecutarlo en .NET Core/.NET 6?** Sí, el código funciona en todas las versiones compatibles de .NET.

## ¿Qué es convertir shapefile a geojson?
Convertir un Shapefile a GeoJSON significa leer características vectoriales del formato clásico ESRI Shapefile y escribirlas como un documento GeoJSON moderno y amigable para la web. Esta transformación te permite alimentar datos GIS directamente en bibliotecas de mapeo JavaScript como Leaflet o Mapbox GL, y simplifica el intercambio de datos entre herramientas GIS de escritorio y APIs web.

## ¿Por qué usar Aspose.GIS para esta conversión?
Aspose.GIS abstrae el análisis binario de bajo nivel, soporta más de 50 formatos de entrada y salida, y puede procesar conjuntos de datos de cientos de páginas sin cargar todo el archivo en memoria. La biblioteca también ofrece una API limpia y orientada a objetos que funciona en .NET Framework, .NET Core y .NET 5/6, de modo que pasas tiempo en la lógica de negocio en lugar de en peculiaridades de formato.

## Requisitos previos
Antes de comenzar, asegúrate de contar con lo siguiente:

- Aspose.GIS para .NET: Verifica que la biblioteca esté instalada. Si no, puedes descargarla desde la [página de Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Datos Shapefile: Ten un Shapefile listo para usar como entrada. Si necesitas datos de ejemplo, puedes encontrarlos en la [documentación de Aspose.GIS](https://reference.aspose.com/gis/net/).
- Entorno .NET: Configura un entorno .NET para ejecutar el código proporcionado.
- Directorio de documentos: Define la ruta a tu directorio de documentos en el fragmento de código.

¡Ahora que tienes todo listo, comencemos a convertir shapefile a geojson!

## Cómo convertir Shapefile a GeoJSON
Carga el Shapefile de origen, crea una capa GeoJSON de destino, copia el esquema de atributos, filtra los registros y escribe los resultados, todo en unos pocos pasos concisos. El flujo de trabajo completo cabe cómodamente en un solo bloque `using`, garantizando que los recursos se liberen automáticamente.

### Paso 1: Abrir Shapefile de entrada
El método `VectorLayer.Open` lee un Shapefile y devuelve una colección enumerable de objetos `Feature` que puedes iterar.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Paso 2: Crear GeoJSON de salida
`VectorLayer.Create` con el controlador `Drivers.GeoJson` crea un archivo GeoJSON vacío listo para recibir características.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Paso 3: Copiar atributos entre capas
`CopyAttributes` copia el esquema de atributos (nombres de campos y tipos de datos) del Shapefile de origen a la nueva capa GeoJSON en una sola llamada.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Paso 4: Procesar características
Itera a través de cada característica del Shapefile para que puedas aplicar lógica personalizada antes de escribirla.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Paso 5: Filtrar características por fecha
En este ejemplo omitimos los registros cuyo campo `dob` (fecha de nacimiento) falta o es anterior al 1 de ene de 1982. Ajusta el filtro según los requisitos de tus datos.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Paso 6: Construir una nueva característica (C# Generate GeoJSON File)
Una `Feature` representa un solo elemento espacial que contiene geometría y datos de atributos.  
Aquí construimos una nueva `Feature` para la capa GeoJSON, copiamos la geometría y los valores de atributos, y la añadimos a la salida. Este es el núcleo de *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

¡Felicidades! Has **convertido shapefile a geojson** con éxito y aprendido a **copiar atributos entre capas** en el proceso.

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El archivo de salida está vacío | `CopyAttributes` se llamó después de que la capa de salida se cerró | Asegúrate de que el bloque `using` para `outputLayer` permanezca abierto hasta después de agregar todas las características. |
| El filtro de fecha elimina todos los registros | Nombre de campo incorrecto o formato de fecha inesperado | Verifica el nombre del atributo (`dob`) y usa `GetValue<string>` si las fechas se almacenan como cadenas. |
| Excepción de licencia | Ejecutar sin una licencia válida de Aspose.GIS en producción | Aplica una licencia temporal o completa según lo descrito en la documentación de Aspose. |

## Preguntas frecuentes
**P: ¿Dónde puedo encontrar más documentación?**  
R: Visita la [documentación de Aspose.GIS](https://reference.aspose.com/gis/net/) para información detallada.

**P: ¿Cómo puedo obtener una licencia temporal?**  
R: Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo buscar soporte?**  
R: Únete al [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para soporte comunitario y discusiones.

**P: ¿Hay una prueba gratuita disponible?**  
R: Sí, puedes encontrar la prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo comprar Aspose.GIS para .NET?**  
R: Puedes adquirir el producto [aquí](https://purchase.aspose.com/buy).

## Conclusión
En este tutorial exploramos el proceso completo de **convertir shapefile a geojson** usando Aspose.GIS para .NET, demostramos cómo **copiar atributos entre capas** y mostramos una forma limpia de *c# generate geojson file*. Experimenta con diferentes filtros, conjuntos de datos más grandes o transformaciones geométricas adicionales para aprovechar al máximo las capacidades de la biblioteca.

---

**Última actualización:** 2026-07-05  
**Probado con:** Aspose.GIS para .NET (última versión estable)  
**Autor:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Tutoriales relacionados

- [Cómo convertir GeoJSON a File GDB usando Aspose.GIS para .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Cómo leer GeoJSON desde Stream con Aspose.GIS para .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cómo convertir GeoJSON a TopoJSON con Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}