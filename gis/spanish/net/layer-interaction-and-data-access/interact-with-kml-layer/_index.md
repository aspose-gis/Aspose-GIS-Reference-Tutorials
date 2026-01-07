---
date: 2026-01-07
description: Aprenda a escribir archivos KML usando Aspose.GIS para .NET, cómo crear
  KML, agregar un atributo booleano y crear una cadena de líneas en sus aplicaciones.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Cómo escribir un archivo KML con Aspose.GIS para .NET
url: /es/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo escribir un archivo KML con Aspose.GIS para .NET

## Introducción
En el mundo actual impulsado por los datos, la capacidad de **escribir archivos KML** programáticamente le brinda el poder de compartir información geográfica entre plataformas, visualizar rutas en mapas e integrar datos de ubicación en aplicaciones web o móviles. Aspose.GIS para .NET hace que este proceso sea sencillo, permitiéndole centrarse en la lógica en lugar de las complejidades del formato de archivo. En este tutorial recorreremos la creación de una capa KML, la adición de atributos (incluido un atributo booleano) y la construcción de una geometría de línea—todo con código claro paso a paso.

## Respuestas rápidas
- **¿Qué significa “escribir un archivo KML”?** Generar un documento KML (Keyhole Markup Language) que describe características geográficas como puntos, líneas y polígonos.  
- **¿Qué biblioteca es la mejor para .NET?** Aspose.GIS para .NET proporciona una API fluida para crear y editar archivos KML.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita sirve para evaluación; se requiere una licencia para uso en producción.  
- **¿Puedo agregar atributos personalizados?** Sí, puede agregar atributos de tipo cadena, entero, booleano y doble a cada entidad.  
- **¿Se admite la creación de geometrías?** Absolutamente, puede crear puntos, líneas, polígonos y más.

## Requisitos previos
Antes de embarcarnos en este viaje, asegúrese de contar con los siguientes requisitos:
- Aspose.GIS para .NET: Descargue e instale la biblioteca desde la [página de descarga de Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Entorno de desarrollo: Configure un entorno de desarrollo adecuado, como Visual Studio, para integrar Aspose.GIS sin problemas en sus proyectos .NET.

## Importar espacios de nombres
Antes de comenzar a interactuar con capas KML, asegúrese de incluir los espacios de nombres necesarios en su proyecto. Este paso garantiza que tenga acceso a las clases y métodos requeridos para la manipulación de datos geoespaciales.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Paso 1: Establecer el directorio del documento
Defina la ruta a su directorio de documentos donde se almacenarán los archivos KML.

```csharp
string dataDir = "Your Document Directory";
```

## Paso 2: Crear una capa KML
Inicialice una capa KML usando Aspose.GIS, especificando la ruta para el archivo KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Paso 3: Definir atributos (agregar atributo booleano)
Agregue atributos a la capa KML para representar diferentes tipos de datos como cadena, entero, **boolean**, y doble. Aquí es donde “agrega atributo booleano” a cada entidad.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Paso 4: Construir y poblar entidades (crear línea)
Construya entidades que representen objetos geoespaciales y establezca valores para los atributos definidos. Aquí **creamos una línea** para ilustrar una ruta simple.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Paso 5: Agregar otra entidad
Repita el proceso para agregar una segunda entidad con valores de atributos diferentes y una geometría nula.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Cómo escribir un archivo KML – Todo junto
Al seguir los pasos anteriores ahora tiene un archivo KML completamente funcional que contiene atributos personalizados (incluido un indicador booleano) y una geometría de línea. Puede abrir el `Kml_File_out.kml` resultante en Google Earth, ArcGIS o cualquier visor GIS que admita KML.

## Problemas comunes y solución de errores
- **Errores de ruta de archivo** – Asegúrese de que `dataDir` termine con un separador de ruta (`\` o `/`) apropiado para su SO.  
- **Licencia faltante** – La prueba funciona para evaluación, pero se requiere una versión con licencia para escribir archivos KML sin restricciones.  
- **Geometría nula** – Establecer `Geometry.Null` es intencional para entidades sin datos espaciales; omítalo si siempre necesita geometría.

## Preguntas frecuentes
### ¿Aspose.GIS es compatible con otros formatos GIS?
Sí, Aspose.GIS admite varios formatos GIS, incluidos shapefile, GeoJSON y KML.

### ¿Puedo visualizar los datos geoespaciales creados con Aspose.GIS?
¡Absolutamente! Aspose.GIS se integra sin problemas con bibliotecas de mapeo, permitiéndole visualizar sus datos geoespaciales.

### ¿Existe una versión de prueba disponible para Aspose.GIS?
Sí, puede explorar las funciones de Aspose.GIS descargando la [versión de prueba gratuita](https://releases.aspose.com/).

### ¿Cómo puedo obtener soporte para Aspose.GIS?
Visite el [foro de Aspose.GIS](https://forum.aspose.com/c/gis/33) para soporte comunitario o explore opciones de soporte premium [aquí](https://purchase.aspose.com/buy).

### ¿Hay licencias temporales disponibles para Aspose.GIS?
Sí, puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

## Preguntas frecuentes adicionales

**Q: ¿Cómo crear archivos **KML** con estilo personalizado?**  
A: Use el espacio de nombres `Aspose.Gis.Formats.Kml.Styles` para definir íconos, colores de línea y estilos de etiqueta antes de agregar entidades.

**Q: ¿Puedo escribir archivos KML grandes de manera eficiente?**  
A: Escriba entidades en lotes y vacíe la capa periódicamente para mantener bajo el uso de memoria.

**Q: ¿Aspose.GIS admite .NET Core y .NET 6+?**  
A: Sí, la biblioteca es totalmente compatible con .NET Core, .NET 5 y .NET 6.

---

**Última actualización:** 2026-01-07  
**Probado con:** Aspose.GIS 24.10 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}