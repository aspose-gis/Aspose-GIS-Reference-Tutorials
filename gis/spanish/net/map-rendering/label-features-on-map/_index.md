---
title: Dominar el etiquetado de funciones con Aspose.GIS para .NET
linktitle: Etiquetar características en el mapa
second_title: Aspose.GIS API .NET
description: Explore Aspose.GIS para .NET y domine el arte del etiquetado de funciones en mapas. Mejore sus visualizaciones geoespaciales sin esfuerzo. #Aspose #SIG
weight: 11
url: /es/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar el etiquetado de funciones con Aspose.GIS para .NET

## Introducción
En el mundo de la visualización de datos geoespaciales, etiquetar características en un mapa desempeña un papel crucial a la hora de transmitir información de forma eficaz. Aspose.GIS para .NET proporciona un potente conjunto de herramientas para lograr esto sin problemas. En este tutorial, exploraremos varios métodos para etiquetar puntos en un mapa usando Aspose.GIS, mejorando las visualizaciones de su mapa con etiquetas informativas.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Un conocimiento práctico de C# y el marco .NET.
-  Aspose.GIS para .NET instalado. Puedes descargarlo[aquí](https://releases.aspose.com/gis/net/).
- Un archivo GeoJSON que contiene datos de puntos. Si no tiene uno, puede utilizar un archivo de muestra para realizar pruebas.
## Importar espacios de nombres
En su código C#, asegúrese de importar los espacios de nombres necesarios para trabajar con Aspose.GIS:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Ahora, dividamos cada ejemplo en varios pasos en un formato de guía paso a paso.
##  Etiquetado de puntos

### Paso 1: establezca la ruta a su directorio de documentos:
```csharp
string dataDir = "Your Document Directory";
```
### Paso 2: crea un mapa con un símbolo de marcador simple:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Agregue una capa vectorial y aplique etiquetado.
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Renderice el mapa en un archivo SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Etiquetado de puntos con estilo

Siga los pasos 1 y 2 del ejemplo anterior.

### Paso 1: personaliza el estilo de etiquetado:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// El resto de pasos siguen igual.
```
## Etiquetado de puntos colocados

Siga los pasos 1 y 2 del primer ejemplo.
### Paso 2: personaliza la ubicación de la etiqueta:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// El resto de pasos siguen igual.
```
## Función de etiquetado de puntos basada

Siga los pasos 1 y 2 del primer ejemplo.

### Paso 1: implementar el etiquetado basado en características:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Recuperar población de la característica.
        var population = feature.GetValue<int>("population");
        // El tamaño de fuente se calcula y se basa en la población.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // La prioridad de la etiqueta también se basa en la población.
        // Cuanto mayor sea la prioridad, es más probable que aparezca una etiqueta en la imagen de salida.
        labeling.Priority = population;
    }
};
// El resto de pasos siguen igual.
```
## Conclusión
¡Felicidades! Ha aprendido cómo mejorar las visualizaciones de sus mapas etiquetando características usando Aspose.GIS para .NET. Experimente con diferentes estilos y ubicaciones para crear mapas atractivos adaptados a sus datos.
## Preguntas frecuentes
### ¿Puedo etiquetar funciones usando fuentes personalizadas?
Sí, puedes personalizar el estilo y el tamaño de fuente en la configuración de etiquetado.
### ¿Aspose.GIS es compatible con otros formatos de datos SIG?
Aspose.GIS admite varios formatos geoespaciales, incluidos GeoJSON, Shapefile y más.
### ¿Cómo puedo manejar grandes conjuntos de datos para etiquetar?
Aspose.GIS está optimizado para el rendimiento, pero considere usar configuraciones basadas en funciones para priorizar etiquetas según los atributos de los datos.
### ¿Hay opciones avanzadas de colocación de etiquetas disponibles?
Sí, puede ajustar la ubicación de las etiquetas utilizando opciones como rotación, puntos de anclaje y desplazamientos.
### ¿Puedo automatizar la generación de etiquetas en un proceso por lotes?
Por supuesto, puede integrar Aspose.GIS en sus flujos de trabajo automatizados para la generación de etiquetas por lotes.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
