---
title: Dominando a rotulagem de recursos com Aspose.GIS para .NET
linktitle: Rotular recursos no mapa
second_title: API Aspose.GIS .NET
description: Explore o Aspose.GIS for .NET e domine a arte da rotulagem de recursos em mapas. Aprimore suas visualizações geoespaciais sem esforço. #Aspose #GIS
weight: 11
url: /pt/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando a rotulagem de recursos com Aspose.GIS para .NET

## Introdução
No mundo da visualização de dados geoespaciais, rotular recursos em um mapa desempenha um papel crucial na transmissão eficaz de informações. Aspose.GIS for .NET fornece um kit de ferramentas poderoso para conseguir isso perfeitamente. Neste tutorial, exploraremos vários métodos de rotulagem de pontos em um mapa usando Aspose.GIS, aprimorando as visualizações do seu mapa com rótulos informativos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de C# e do framework .NET.
-  Aspose.GIS para .NET instalado. Você pode baixá-lo[aqui](https://releases.aspose.com/gis/net/).
- Um arquivo GeoJSON contendo dados de ponto. Se não tiver um, você pode usar um arquivo de amostra para teste.
## Importar namespaces
Em seu código C#, certifique-se de importar os namespaces necessários para trabalhar com Aspose.GIS:
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
Agora, vamos dividir cada exemplo em várias etapas em um formato de guia passo a passo.
##  Rotulagem de pontos

### Passo 1: Defina o caminho para o diretório de documentos:
```csharp
string dataDir = "Your Document Directory";
```
### Passo 2: Crie um mapa com um símbolo de marcador simples:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Adicione uma camada vetorial e aplique rotulagem
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Renderize o mapa em um arquivo SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Estilo de rotulagem de pontos

Siga as etapas 1 e 2 do exemplo anterior.

### Etapa 1: personalize o estilo de rotulagem:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// O resto das etapas permanecem as mesmas
```
## Rotulagem de pontos colocada

Siga as etapas 1 e 2 do primeiro exemplo.
### Etapa 2: personalize o posicionamento da etiqueta:
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
// O resto das etapas permanecem as mesmas
```
## Baseado em recurso de rotulagem de pontos

Siga as etapas 1 e 2 do primeiro exemplo.

### Etapa 1: Implementar rotulagem baseada em recursos:
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
        // Recuperar a população do recurso.
        var population = feature.GetValue<int>("population");
        // O tamanho da fonte é calculado e baseado na população.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // A prioridade do rótulo também se baseia na população.
        // Quanto maior for a prioridade, maior será a probabilidade de o rótulo aparecer na imagem de saída.
        labeling.Priority = population;
    }
};
// O resto das etapas permanecem as mesmas
```
## Conclusão
Parabéns! Você aprendeu como aprimorar as visualizações do seu mapa rotulando recursos usando Aspose.GIS for .NET. Experimente diferentes estilos e posicionamentos para criar mapas atraentes e adaptados aos seus dados.
## Perguntas frequentes
### Posso rotular recursos usando fontes personalizadas?
Sim, você pode personalizar o estilo e o tamanho da fonte na configuração da etiqueta.
### Aspose.GIS é compatível com outros formatos de dados GIS?
Aspose.GIS suporta vários formatos geoespaciais, incluindo GeoJSON, Shapefile e muito mais.
### Como posso lidar com grandes conjuntos de dados para rotulagem?
Aspose.GIS é otimizado para desempenho, mas considere usar configurações baseadas em recursos para priorizar rótulos com base em atributos de dados.
### Existem opções avançadas de posicionamento de etiquetas disponíveis?
Sim, você pode ajustar o posicionamento da etiqueta usando opções como rotação, pontos de ancoragem e deslocamentos.
### Posso automatizar a geração de etiquetas em um processo em lote?
Com certeza, você pode integrar Aspose.GIS em seus fluxos de trabalho automatizados para geração de etiquetas em lote.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
