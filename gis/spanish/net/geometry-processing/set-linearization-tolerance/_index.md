---
date: 2025-12-21
description: Aprende a crear una capa vectorial, establecer la tolerancia de linealización
  y agregar una entidad a la capa usando Aspose.GIS para .NET. Sigue esta guía paso
  a paso para exportar archivos GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Crear capa vectorial y establecer la tolerancia de linealización usando Aspose.GIS
  para .NET
url: /es/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear capa vectorial y establecer tolerancia de linealización usando Aspose.GIS para .NET

## Introducción
Si necesitas **crear capa vectorial**, controlar la precisión de curvas y exportar el resultado como un documento GeoJSON, Aspose.GIS para .NET lo hace sencillo. En este tutorial aprenderás a configurar las opciones de GeoJSON, establecer la tolerancia de linealización y **agregar entidad a la capa** — todo manteniendo el código limpio y listo para producción.

## Respuestas rápidas
- **¿Qué significa “crear capa vectorial”?** Crea un nuevo conjunto de datos GIS vectorial (p. ej., un archivo GeoJSON) que puede almacenar geometrías y atributos.  
- **¿Cómo establecer la tolerancia?** Usa la propiedad `LinearizationTolerance` de `GeoJsonOptions`.  
- **¿Puedo exportar un archivo GeoJSON?** Sí, simplemente crea un `VectorLayer` con el controlador `Drivers.GeoJson`.  
- **¿Necesito una licencia?** Una licencia válida de Aspose.GIS desbloquea todas las funciones; una licencia temporal funciona para evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es “crear capa vectorial”?
Crear una capa vectorial significa inicializar un nuevo contenedor GIS (como un archivo GeoJSON) que puede contener entidades geométricas como puntos, líneas y polígonos. Esta capa se convierte en el destino para cualquier geometría que construyas y cualquier atributo que adjuntes.

## ¿Por qué configurar las opciones de GeoJSON?
Configurar las opciones de GeoJSON—especialmente la **tolerancia de linealización**—garantiza que las geometrías curvas (p. ej., `CircularString`) se aproximen con una precisión que cumpla los requisitos de exactitud de tu aplicación. Este paso es crucial cuando luego **exportas el archivo GeoJSON** para usarlo en mapas web o análisis espaciales.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Visual Studio** instalado (cualquier versión reciente).  
2. **Licencia de Aspose.GIS** (o una clave de evaluación temporal).  
3. Biblioteca **Aspose.GIS para .NET** descargada y referenciada en tu proyecto.  
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
Crearemos un objeto `GeoJsonOptions` y le indicaremos a Aspose.GIS cuán cerca debe estar la geometría linealizada de la curva original.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Paso 2: Definir la ruta de salida (cómo exportar GeoJSON)
Especifica dónde se guardará el archivo resultante. Reemplaza el marcador de posición con tu carpeta real.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Paso 3: **Crear capa vectorial** con las opciones configuradas
Ahora realmente **creamos la capa vectorial** usando el método `VectorLayer.Create`. El bloque `using` garantiza la correcta liberación de recursos.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Paso 4: Construir una geometría (p. ej., una cadena circular)
Aquí construimos una geometría de ejemplo—un `CircularString`. Puedes reemplazarla con cualquier WKT válido.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Paso 5: **Agregar entidad a la capa** y guardar
Finalmente, creamos una entidad, asignamos la geometría y la añadimos a la capa. Este es el núcleo de la operación **agregar entidad a la capa**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Cuando el bloque `using` finaliza, la capa se escribe automáticamente en el archivo definido en `path`, proporcionándote un archivo GeoJSON listo para usar.

## Problemas comunes y consejos
- **Ruta incorrecta** – Asegúrate de que el directorio exista y tengas permisos de escritura.  
- **Tolerancia demasiado baja** – Establecer `LinearizationTolerance` a un valor muy pequeño puede aumentar drásticamente el tamaño del archivo. Ajústalo según tus necesidades de precisión.  
- **Errores de licencia** – Si ves advertencias de licencia, verifica que el archivo de licencia se haya cargado correctamente antes de cualquier llamada a Aspose.GIS.

## Preguntas frecuentes

**P: ¿Aspose.GIS para .NET es compatible con otros frameworks de .NET?**  
R: Sí, funciona con .NET Framework, .NET Core y .NET 5/6/7.

**P: ¿Puedo usar Aspose.GIS en proyectos comerciales?**  
R: Por supuesto. Una licencia comercial elimina todas las restricciones de evaluación.

**P: ¿Aspose.GIS admite otros formatos GIS además de GeoJSON?**  
R: Sí, admite Shapefile, KML, GML y muchos más.

**P: ¿Existe una versión de prueba disponible?**  
R: Puedes descargar una prueba gratuita desde el sitio web de Aspose.

**P: ¿Dónde puedo obtener soporte?**  
R: Usa los foros de Aspose o el enlace de soporte en la sección de recursos.

## Conclusión
Al seguir estos pasos ahora sabes cómo **crear capa vectorial**, configurar la tolerancia de linealización y **agregar entidad a la capa** para una creación fluida de **exportar archivo GeoJSON**. Explora tipos de geometría adicionales y el manejo de atributos para aprovechar al máximo Aspose.GIS en tus proyectos GIS con .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

---