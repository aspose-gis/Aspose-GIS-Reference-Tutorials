---
date: 2026-01-05
description: Aprende a leer shapefiles en C# usando Aspose.GIS para .NET, a obtener
  todos los valores de atributos de las entidades y a volcar los atributos de manera
  eficiente.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Leer Shapefile C# – Obtener todos los valores de atributos de las entidades
url: /es/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtener todos los valores de atributos de características

## Introducción
Bienvenido al mundo del desarrollo geoespacial con Aspose.GIS para .NET! En este tutorial aprenderá **cómo leer shapefile C#** y recuperar cada valor de atributo de sus características. Ya sea que esté creando una aplicación de mapas o procesando datos espaciales por lotes, dominar la extracción de atributos es esencial. Vamos a sumergirnos y ver el código en acción.

## Respuestas rápidas
- **¿Qué hace este código?** Abre un Shapefile y lee todos, varios o los valores de atributos volcado de cada característica.  
- **¿Qué biblioteca se requiere?** Aspose.GIS para .NET (compatible con .NET Framework y .NET Core).  
- **¿Necesito una licencia?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Puedo leer otros formatos?** Sí – la misma API admite GeoJSON, KML y muchos más.  
- **¿Cómo volcar atributos?** Use `feature.GetValuesDump()` para obtener una matriz de objetos flexible.

## ¿Qué es “read shapefile C#”?
Leer un Shapefile en C# significa abrir el archivo .shp con una biblioteca GIS, iterar sobre sus características vectoriales y acceder a los datos de atributos almacenados en el archivo .dbf adjunto. Aspose.GIS abstrae el manejo de archivos de bajo nivel, permitiéndole centrarse en los valores de atributos que necesita.

## ¿Por qué usar Aspose.GIS para leer atributos?
- **API simple** – métodos intuitivos como `GetValues` y `GetValuesDump`.  
- **Multiplataforma** – funciona en Windows, Linux y macOS con .NET Core.  
- **Amplio soporte de formatos** – maneje Shapefile, GeoJSON, GML y más sin complementos adicionales.  
- **Optimizado para rendimiento** – iteración rápida sobre grandes conjuntos de datos.

## Requisitos previos
Antes de embarcarnos en este emocionante viaje, asegúrese de contar con los siguientes requisitos:
- Aspose.GIS para .NET: descargue e instale la biblioteca desde la [página de descarga de Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Entorno de desarrollo: configure un entorno de desarrollo .NET, como Visual Studio.
- Shapefile: tenga un Shapefile de ejemplo (p. ej., "InputShapeFile.shp") listo en su directorio de documentos.

## Importar espacios de nombres
En su código C#, comience importando los espacios de nombres necesarios para aprovechar las funcionalidades de Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Paso 1: Establecer el directorio de documentos
```csharp
string dataDir = "Your Document Directory";
```
Reemplace "Your Document Directory" con la ruta real donde se encuentra su Shapefile.

## Paso 2: Abrir el VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Este paso implica abrir el Shapefile usando Aspose.GIS, especificando la ruta del archivo y el formato (en este caso, Shapefile).

## Paso 3: Recuperar todos los valores de atributos de las características
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
El fragmento muestra **cómo leer atributos** para cada característica cargándolos en una matriz de tamaño fijo.

## Paso 4: Recuperar varios valores de atributos de características
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Aquí demostramos **cómo leer valores de atributos específicos** cuando solo necesita un subconjunto de campos.

## Paso 5: Recuperar valores de atributos como volcado de objetos
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Este paso final muestra **cómo volcar atributos** usando `GetValuesDump()`, que devuelve una colección flexible que puede inspeccionar o serializar.

## Problemas comunes y soluciones
- **Desajuste del tamaño de la matriz** – Asegúrese de que la matriz que pasa a `GetValues` coincida con el número de atributos que espera; de lo contrario obtendrá entradas `null`.  
- **Archivo no encontrado** – Verifique que `dataDir` apunte a la carpeta correcta y que el nombre del Shapefile esté escrito exactamente.  
- **Excepción de licencia** – Si ve un error de licencia, aplique una licencia temporal o completa antes de llamar a cualquier método de la API.

## Preguntas frecuentes
### ¿Aspose.GIS es compatible con .NET Core?
Sí, Aspose.GIS es totalmente compatible con .NET Core, lo que le permite crear aplicaciones multiplataforma.

### ¿Puedo trabajar con diferentes formatos de archivos GIS usando Aspose.GIS?
¡Absolutamente! Aspose.GIS admite varios formatos, incluidos Shapefile, GeoJSON y más.

### ¿Existe un foro comunitario para soporte de Aspose.GIS?
Sí, puede encontrar asistencia y participar con la comunidad de Aspose.GIS en el [foro de soporte](https://forum.aspose.com/c/gis/33).

### ¿Cómo puedo obtener una licencia temporal para Aspose.GIS?
Puede adquirir una licencia temporal para propósitos de prueba [aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo encontrar documentación detallada de Aspose.GIS?
La documentación completa está disponible [aquí](https://reference.aspose.com/gis/net/).

### ¿Cómo recupero solo el atributo “Name” de cada característica?
Use `GetValues` con una matriz de un solo elemento y pase el índice del campo “Name”, o llame directamente a `feature["Name"]`.

### ¿Cuál es la diferencia entre `GetValues` y `GetValuesDump`?
`GetValues` llena una matriz preasignada con valores crudos, mientras que `GetValuesDump` devuelve una matriz de objetos que puede enumerarse sin conocer el esquema de antemano.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-05  
**Probado con:** Aspose.GIS para .NET (última versión)  
**Autor:** Aspose  

---