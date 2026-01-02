---
date: 2026-01-02
description: Aprenda a agregar una entidad puntual mientras establece nombres de campos
  y lee el ID del objeto usando Aspose.GIS para .NET. Guía paso a paso para desarrolladores.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Agregar característica de punto y especificar los nombres de los campos de
  ID de objeto y geometría
url: /es/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar entidad puntual y especificar los nombres de los campos Object ID y Geometry

## Introducción
Emprender un viaje al mundo de los Sistemas de Información Geográfica (GIS) usando Aspose.GIS para .NET abre un abanico de posibilidades para desarrolladores y entusiastas por igual. En este tutorial, **aprenderás a agregar una entidad puntual** mientras también **configuras los nombres de los campos** y **lees los valores del Object ID**, dándote control total sobre tus datos espaciales.

## Respuestas rápidas
- **¿Cuál es el propósito principal de esta guía?** Mostrar cómo agregar una entidad puntual y configurar los nombres de los campos Object ID y Geometry.  
- **¿Qué biblioteca se utiliza?** Aspose.GIS para .NET.  
- **¿Necesito una licencia?** Hay una versión de prueba gratuita; se requiere una licencia para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Puedo leer el Object ID después de la inserción?** Sí, el tutorial demuestra cómo leer el Object ID desde la capa.

## Requisitos previos
Antes de sumergirte en el tutorial, asegúrate de contar con lo siguiente:
- Aspose.GIS para .NET: Descarga e instala la biblioteca desde [aquí](https://releases.aspose.com/gis/net/).
- Directorio de documentos: Configura un directorio para tus documentos donde almacenar las geodatabases.
- Entorno .NET: Verifica que dispones de un entorno .NET funcional.

## Importar espacios de nombres
Para comenzar, necesitas importar los espacios de nombres necesarios en tu proyecto. Estos espacios de nombres proporcionan las clases y métodos esenciales para interactuar con Aspose.GIS para .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Paso 1: Agregar entidad puntual y especificar los nombres de los campos Object ID y Geometry
En este paso, aprenderás a configurar los nombres de los campos Object ID y Geometry para tus datos GIS. Esto es crucial para una gestión eficiente de los datos y para poder **leer el Object ID** más adelante.

### Paso 1.1: Establecer el directorio de documentos
Comienza definiendo la ruta a tu directorio de documentos:

```csharp
string dataDir = "Your Document Directory";
```

### Paso 1.2: Crear una GeoDatabase y definir opciones
Crea una GeoDatabase con los **nombres de campo** deseados para Object ID y Geometry:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Paso 1.3: Crear y agregar una capa
Crea una capa dentro de la GeoDatabase y agrega una entidad que represente una geometría puntual:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Paso 1.4: Abrir y recuperar datos de la capa
Abre la capa y recupera la entidad que acabas de agregar. Esto demuestra cómo **leer el Object ID** del conjunto de datos:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## ¿Por qué establecer nombres de campo personalizados?
Personalizar los nombres de los campos Object ID y Geometry te brinda flexibilidad al integrarte con bases de datos existentes o al adherirte a convenciones de nombres requeridas por aplicaciones posteriores. Además, hace que los datos sean más auto‑descriptivos, lo que simplifica el mantenimiento y la colaboración.

## Problemas comunes y solución de problemas
- **Directorio inexistente** – Asegúrate de que `dataDir` apunte a una carpeta existente; de lo contrario, `Dataset.Create` lanzará una excepción.
- **Conflictos de nombres de campo** – Si ya existe un campo con el mismo nombre en la geodatabase, la creación fallará. Elige nombres únicos.
- **Desajuste de referencia espacial** – Siempre coincide el sistema de referencia espacial (p. ej., WGS84) con los datos que pretendes almacenar.

## Conclusión
¡Felicidades! Has aprendido con éxito a **agregar una entidad puntual**, **configurar los nombres de los campos** y **leer el Object ID** usando Aspose.GIS para .NET. Esta base te permite crear aplicaciones GIS robustas y gestionar datos espaciales con confianza.

## Preguntas frecuentes
### P: ¿Puedo usar Aspose.GIS para .NET en mis aplicaciones web?
R: Sí, Aspose.GIS para .NET es adecuado tanto para aplicaciones de escritorio como web, ofreciendo capacidades geoespaciales versátiles.

### P: ¿Existe una versión de prueba disponible antes de comprar?
R: Sí, puedes explorar las funciones de Aspose.GIS para .NET con una prueba gratuita disponible [aquí](https://releases.aspose.com/).

### P: ¿Cómo puedo obtener una licencia temporal para Aspose.GIS para .NET?
R: Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para fines de evaluación.

### P: ¿Qué sistemas de referencia espacial soporta Aspose.GIS para .NET?
R: Aspose.GIS para .NET soporta varios sistemas de referencia espacial, proporcionando flexibilidad para diferentes conjuntos de datos geográficos.

### P: ¿Dónde puedo buscar ayuda o discutir consultas relacionadas con Aspose.GIS?
R: Visita el foro de Aspose.GIS [aquí](https://forum.aspose.com/c/gis/33) para soporte y discusiones.

## Preguntas frecuentes adicionales

**P: ¿Puedo cambiar el campo Object ID después de crear la capa?**  
R: No. El nombre del campo se define al crear la capa; debes recrear la capa con un nuevo objeto `FileGdbOptions` para modificarlo.

**P: ¿Cómo recupero otros valores de atributos además del Object ID?**  
R: Usa `feature.GetValue<T>("FieldName")` donde `FieldName` es el nombre del atributo que deseas leer.

**P: ¿Es posible agregar múltiples entidades puntuales en un solo lote?**  
R: Sí. Recorre tus datos, construye una entidad para cada punto, asigna su geometría y llama a `layer.Add(feature)` dentro del mismo bloque `using`.

**P: ¿Aspose.GIS soporta otros tipos de geometría?**  
R: Absolutamente. Puedes trabajar con `LineString`, `Polygon`, `MultiPoint`, y más creando los objetos de geometría correspondientes.

**P: ¿Qué ocurre si intento leer un Object ID que no existe?**  
R: Acceder a un índice fuera de rango (p. ej., `layer[10]` cuando solo hay una entidad) lanzará una `IndexOutOfRangeException`. Siempre verifica `layer.Count` primero.

---

**Última actualización:** 2026-01-02  
**Probado con:** Aspose.GIS para .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}