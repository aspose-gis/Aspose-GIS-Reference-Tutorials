---
date: 2026-05-31
description: Aprenda cómo crear GeoJSON, configurar opciones de GeoJSON y agregar
  una entidad a la capa usando Aspose.GIS para .NET. Siga esta guía paso a paso.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Establecer tolerancia de linealización
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cómo crear GeoJSON con tolerancia Aspose.GIS para .NET
url: /es/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear GeoJSON con tolerancia Aspose.GIS para .NET

## Introducción
Si deseas **aprender a crear GeoJSON** archivos, controlar la precisión de las curvas y exportar el resultado como un documento listo‑para‑usar, Aspose.GIS para .NET lo hace sencillo. En este tutorial descubrirás cómo configurar las opciones de GeoJSON, establecer la tolerancia de linealización y **add feature to layer** objetos manteniendo el código limpio y listo para producción.

## Respuestas rápidas
- **¿Qué significa “create vector layer”?** Crea un nuevo conjunto de datos vectorial GIS (p. ej., un archivo GeoJSON) que puede almacenar geometrías y atributos.  
- **¿Cómo establezco la tolerancia de linealización?** Establece la propiedad `LinearizationTolerance` en una instancia de `GeoJsonOptions` antes de crear la capa.  
- **¿Puedo exportar un archivo GeoJSON directamente?** Sí—usa `VectorLayer.Create` con el controlador `Drivers.GeoJson` y las opciones configuradas.  
- **¿Necesito una licencia?** Una licencia válida de Aspose.GIS desbloquea todas las funciones; una clave de evaluación temporal funciona para pruebas.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qué es “create vector layer”?
Crear una capa vectorial significa inicializar un nuevo contenedor GIS (como un archivo GeoJSON) que puede contener puntos, líneas, polígonos y datos de atributos asociados. Esta capa se convierte en el objetivo para cualquier geometría que construyas y cualquier atributo que adjuntes.

## Por qué configurar opciones de GeoJSON?
Configurar las opciones de GeoJSON—especialmente la **linearization tolerance**—garantiza que las geometrías curvadas (p. ej., `CircularString`) se aproximen con una precisión que cumpla los requisitos de exactitud de tu aplicación. Una configuración adecuada reduce el tamaño del archivo mientras preserva la fidelidad visual, lo cual es crítico cuando el GeoJSON es consumido por mapas web o herramientas de análisis espacial.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Visual Studio** (cualquier versión reciente).  
2. **Licencia Aspose.GIS** (o una clave de evaluación temporal).  
3. Biblioteca **Aspose.GIS for .NET** referenciada en tu proyecto.  
4. Familiaridad básica con **C#**.

## Importar espacios de nombres
Primero, importa los espacios de nombres requeridos para que el compilador sepa dónde encontrar las clases GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guía paso a paso

### Paso 1: Configurar opciones de GeoJSON (cómo establecer la tolerancia)
`GeoJsonOptions` especifica la configuración de serialización utilizada al escribir archivos GeoJSON.  
`GeoJsonOptions` define cómo Aspose.GIS serializa GeoJSON, incluyendo la tolerancia de linealización, la precisión de coordenadas y otras configuraciones de salida.  
Crearemos un objeto `GeoJsonOptions` y le indicaremos a Aspose.GIS cuán cerca debe estar la geometría linealizada de la curva original.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Paso 2: Definir la ruta de salida (cómo exportar GeoJSON)
Especifica la ruta completa del archivo donde se guardará el GeoJSON resultante. Asegúrate de que la carpeta exista y de que la aplicación tenga permisos de escritura.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Paso 3: **Create Vector Layer** con las opciones configuradas
La clase `VectorLayer` representa un contenedor GIS que puede leer y escribir datos espaciales.  
`Drivers.GeoJson` es el identificador del controlador para escribir archivos en formato GeoJSON.  
Usar `VectorLayer.Create` junto con el controlador `Drivers.GeoJson` y las `GeoJsonOptions` previamente configuradas crea un nuevo archivo GeoJSON listo para la inserción de características.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Paso 4: Construir una geometría (p. ej., una cadena circular)
`CircularString` es una geometría de línea curva que Aspose.GIS puede linealizar según la tolerancia que establezcas. Puedes reemplazarla con cualquier representación WKT válida como `POINT`, `LINESTRING` o `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Paso 5: **Add Feature to Layer** y guardar
`Feature` es el objeto que combina una geometría con datos de atributos. Después de crear una instancia de `Feature`, asigna la geometría, opcionalmente agrega valores de atributos y llama a `layer.Add(feature)` para persistirla. Cuando finaliza el bloque `using`, la capa se escribe automáticamente en el archivo definido en `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Cuando finaliza el bloque `using`, la capa se escribe automáticamente en el archivo definido en `path`, proporcionándote un archivo GeoJSON listo‑para‑usar.

## Problemas comunes y consejos
- **Ruta incorrecta** – Verifica que el directorio exista y que tengas permisos de escritura.  
- **Tolerancia demasiado baja** – Establecer `LinearizationTolerance` a un valor muy pequeño puede aumentar drásticamente el tamaño del archivo; una tolerancia de 0.001 suele equilibrar precisión y tamaño.  
- **Errores de licencia** – Si ves advertencias de licencia, asegúrate de que el archivo de licencia se cargue antes de cualquier llamada a Aspose.GIS.  
- **Nota de rendimiento** – Aspose.GIS soporta el procesamiento de archivos de hasta 2 GB sin cargar todo el documento en memoria, gracias a su arquitectura de streaming.

## Preguntas frecuentes

**P: ¿Aspose.GIS para .NET es compatible con otros frameworks .NET?**  
R: Sí, funciona con .NET Framework 4.5+, .NET Core 3.1+, y .NET 5/6/7.

**P: ¿Puedo usar Aspose.GIS en proyectos comerciales?**  
R: Absolutamente. Una licencia comercial elimina todas las restricciones de evaluación y brinda soporte técnico completo.

**P: ¿Aspose.GIS admite otros formatos GIS además de GeoJSON?**  
R: Sí, admite más de 30 formatos—including Shapefile, KML, GML y CSV—permitiendo conversiones sin problemas entre ellos.

**P: ¿Existe una versión de prueba disponible?**  
R: Puedes descargar una prueba gratuita de 30 días desde el sitio web de Aspose; incluye todas las funciones.

**P: ¿Dónde puedo obtener soporte?**  
R: Utiliza los foros de Aspose, el portal de soporte dedicado o el enlace “Contact Support” en el panel de control del producto.

## Conclusión
Al seguir estos pasos ahora sabes **cómo crear GeoJSON**, configurar la tolerancia de linealización y **add feature to layer** para una exportación fluida de GeoJSON. Explora tipos de geometría adicionales, manejo de atributos y escenarios de procesamiento masivo para aprovechar al máximo Aspose.GIS en tus proyectos GIS con .NET.

---

**Última actualización:** 2026-05-31  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create Vector Layer, Limit Precision with Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}