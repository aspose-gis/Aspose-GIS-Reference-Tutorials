---
date: 2026-01-13
description: Aprende cómo convertir shapefile a geojson usando Aspose.GIS para .NET.
  La guía también cubre la copia de atributos entre capas y la generación de archivos
  geojson con C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Cómo convertir Shapefile a GeoJSON usando Aspose.GIS para .NET
url: /es/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir Shapefile a GeoJSON con Aspose.GIS para .NET

## Introducción
En este tutorial completo, paso a paso, aprenderás **cómo convertir shapefile a geojson** usando la potente biblioteca Aspose.GIS para .NET. Ya sea que estés construyendo un servicio web de mapas, preparando datos para una aplicación GIS móvil, o simplemente necesites intercambiar datos entre formatos, esta guía te muestra exactamente qué hacer, por qué cada paso es importante y cómo evitar errores comunes.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Convertir un Shapefile a un archivo GeoJSON, copiar atributos entre capas y generar la salida con C#.
- **¿Qué biblioteca se requiere?** Aspose.GIS para .NET.
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para producción; una prueba gratuita funciona para evaluación.
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para una conversión básica.
- **¿Puedo ejecutarlo en .NET Core/.NET 6?** Sí, el código funciona en todas las versiones compatibles de .NET.

## Requisitos previos
Antes de comenzar, asegúrate de contar con lo siguiente:

- Aspose.GIS para .NET: Asegúrate de tener la biblioteca instalada. Si no, puedes descargarla desde la [página de Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Datos Shapefile: Ten un Shapefile listo para usar como entrada. Si necesitas datos de ejemplo, puedes encontrarlos en la [documentación de Aspose.GIS](https://reference.aspose.com/gis/net/).
- Entorno .NET: Configura un entorno .NET para ejecutar el código proporcionado.
- Directorio de documentos: Define la ruta a tu directorio de documentos en el fragmento de código.

¡Ahora que tienes todo listo, comencemos a convertir shapefile a geojson!

## ¿Qué es “convertir shapefile a geojson”?
Convertir un Shapefile a GeoJSON significa leer características vectoriales del formato clásico ESRI Shapefile y escribirlas como un documento GeoJSON moderno y amigable para la web. GeoJSON se usa ampliamente en bibliotecas de mapeo JavaScript (Leaflet, Mapbox GL) y APIs, lo que hace que la conversión sea una tarea frecuente en el desarrollo GIS.

## ¿Por qué usar Aspose.GIS para esta conversión?
Aspose.GIS abstrae los detalles de bajo nivel de los formatos de archivo, permite copiar tablas de atributos sin esfuerzo y proporciona una API limpia y orientada a objetos que funciona en .NET Framework, .NET Core y .NET 5/6. Esto significa que puedes centrarte en la lógica de negocio en lugar de analizar archivos binarios.

## Importar espacios de nombres
Primero, incluye los espacios de nombres necesarios en tu código:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Estos espacios de nombres son esenciales para trabajar con las funcionalidades de Aspose.GIS.

## Cómo convertir Shapefile a GeoJSON
A continuación se muestra el flujo de trabajo completo dividido en pasos claros. Cada paso incluye una breve explicación seguida del bloque de código exacto que debes copiar a tu proyecto.

### Paso 1: Abrir Shapefile de entrada
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Abre el Shapefile de entrada usando el método `VectorLayer.Open`. Esto te brinda una colección enumerable de objetos `Feature`.

### Paso 2: Crear GeoJSON de salida
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Crea el archivo de salida con el método `VectorLayer.Create`, especificando el controlador `Drivers.GeoJson`.

### Paso 3: Copiar atributos entre capas
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Esta única línea copia el esquema de atributos (nombres de campos, tipos) del Shapefile origen a la nueva capa GeoJSON, exactamente lo que describe la palabra clave secundaria *copy attributes between layers*.

### Paso 4: Procesar características
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Itera sobre cada característica del Shapefile para que puedas aplicar lógica personalizada antes de escribirla.

### Paso 5: Filtrar características por fecha
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
En este ejemplo omitimos los registros cuyo campo `dob` (fecha de nacimiento) falta o es anterior al 1 de enero de 1982. Siéntete libre de ajustar el filtro según los requisitos de tus datos.

### Paso 6: Construir una nueva característica (C# generar archivo GeoJSON)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Aquí construimos una nueva `Feature` para la capa GeoJSON, copiamos la geometría y los valores de atributos, y la añadimos a la salida. Este es el núcleo de *c# generate geojson file*.

¡Felicidades! Has **convertido shapefile a geojson** con éxito y aprendido cómo copiar atributos entre capas en el proceso.

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El archivo de salida está vacío | `CopyAttributes` se llamó después de que la capa de salida se cerró | Asegúrate de que el bloque `using` para `outputLayer` permanezca abierto hasta después de agregar todas las características. |
| El filtro de fecha elimina todos los registros | Nombre de campo incorrecto o formato de fecha inesperado | Verifica el nombre del atributo (`dob`) y usa `GetValue<string>` si las fechas se almacenan como cadenas. |
| Excepción de licencia | Ejecutar sin una licencia válida de Aspose.GIS en producción | Aplica una licencia temporal o completa como se describe en la documentación de Aspose. |

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
En este tutorial exploramos el proceso completo de **convertir shapefile a geojson** usando Aspose.GIS para .NET, demostramos cómo copiar atributos entre capas y mostramos una forma limpia de *c# generate geojson file*. Experimenta con diferentes filtros, conjuntos de datos más grandes o transformaciones geométricas adicionales para aprovechar al máximo las capacidades de la biblioteca.

---

**Última actualización:** 2026-01-13  
**Probado con:** Aspose.GIS para .NET (última versión estable)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}