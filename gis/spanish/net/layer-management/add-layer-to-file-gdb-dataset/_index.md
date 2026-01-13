---
date: 2026-01-13
description: Aprenda cómo agregar una capa a un conjunto de datos File GDB usando
  Aspose.GIS, con soporte de referencia espacial WGS84. Siga esta guía paso a paso
  para añadir una capa a GDB en .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Referencia espacial WGS84 – Añadir capa a GDB usando Aspose.GIS
url: /es/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Añadir capa a GDB usando Aspose.GIS

## Introducción
¿Listo para impulsar su flujo de trabajo GIS con Aspose.GIS para .NET? En este tutorial aprenderá **cómo añadir una capa a un conjunto de datos File GDB** mientras trabaja con el sistema de coordenadas **spatial reference wgs84**. Recorreremos cada paso, desde la preparación de su carpeta de datos hasta la validación de la capa recién creada, para que pueda comenzar a manipular datos geográficos con confianza.

## Respuestas rápidas
- **¿Cuál es el sistema de coordenadas principal utilizado?** spatial reference wgs84 (WGS 84)  
- **¿Qué biblioteca proporciona la API?** Aspose.GIS for .NET  
- **¿Necesito una licencia para pruebas?** Sí – una licencia temporal de Aspose está disponible.  
- **¿Puedo añadir atributos a la nueva capa?** Absolutamente, puede definir cualquier número de atributos de entidad.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## ¿Qué es spatial reference wgs84?
El spatial reference wgs84 (World Geodetic System 1984) es el sistema de coordenadas geográficas más utilizado. Define la latitud y longitud en grados y sirve como el CRS predeterminado para muchos conjuntos de datos GIS, incluido el que crearemos en esta guía.

## ¿Por qué usar Aspose.GIS para añadir una capa?
- **Sin dependencias externas:** Funciona listo para usar con código .NET puro.  
- **Control total sobre el esquema:** Puede definir atributos personalizados y tipos de geometría.  
- **Multiplataforma:** Compatible con entornos de ejecución Windows, Linux y macOS.  
- **Licenciamiento robusto:** Las licencias temporales le permiten evaluar rápidamente antes de comprometerse.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

- Biblioteca Aspose.GIS para .NET: Descargue e instale la biblioteca desde la [Documentación de Aspose.GIS para .NET](https://reference.aspose.com/gis/net/).  
- Directorio de documentos: Cree una carpeta dedicada en su máquina para almacenar archivos GIS.

## Importar espacios de nombres
Agregue las declaraciones `using` requeridas a su proyecto C# para poder acceder a las clases de Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Paso 1: Copiar directorio
Primero, duplique la carpeta que contiene el conjunto de datos GDB original. Mantener una copia protege los datos de origen mientras experimenta.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Paso 2: Abrir conjunto de datos y verificar capacidad de creación
Abra el conjunto de datos recién copiado y confirme que puede crear nuevas capas. La propiedad `CanCreateLayers` debe devolver **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Paso 3: Crear y poblar una nueva capa con spatial reference wgs84
Ahora creamos una capa llamada **data** y establecemos explícitamente su referencia espacial a **Wgs84**. También añadimos un atributo simple llamado **Name** e insertamos una entidad punto.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Paso 4: Abrir y validar la capa añadida
Finalmente, abra la capa que acaba de crear y verifique su contenido. La consola mostrará que la capa contiene una entidad y que el atributo **Name** coincide con lo que establecimos.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Problemas comunes y consejos
- **Ruta incorrecta:** Asegúrese de que `dataDir` termine con un separador de ruta (`/` o `\`) para que las cadenas concatenadas formen rutas de archivo válidas.  
- **Errores de licencia:** Si ve advertencias de licencia, aplique una licencia temporal desde el portal de Aspose antes de ejecutar el código.  
- **Desajuste de CRS:** Al abrir la capa más tarde en otra herramienta GIS, confirme que la herramienta reconoce WGS 84 (EPSG:4326) como el sistema de coordenadas.

## Preguntas frecuentes
### P: ¿Puedo usar Aspose.GIS para .NET con otras bibliotecas GIS?
Aspose.GIS para .NET está diseñado para funcionar de forma independiente, pero puede integrarse con otras bibliotecas para una funcionalidad mejorada.

### P: ¿Está disponible una licencia temporal para propósitos de prueba?
Sí, puede obtener una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/) para pruebas y evaluación.

### P: ¿Qué sistemas de referencia espacial admite Aspose.GIS para .NET?
Aspose.GIS para .NET admite una amplia gama de sistemas de referencia espacial, proporcionando flexibilidad en el manejo de datos geográficos.

### P: ¿Puedo contribuir a la comunidad de Aspose.GIS?
¡Absolutamente! Únase a las discusiones y comparta sus experiencias en el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33).

### P: ¿Dónde puedo encontrar documentación detallada de Aspose.GIS para .NET?
Explore la documentación completa [aquí](https://reference.aspose.com/gis/net/) para obtener información detallada sobre Aspose.GIS para .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose