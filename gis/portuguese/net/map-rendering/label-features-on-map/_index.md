---
date: 2026-01-15
description: Aprenda a rotular recursos de mapa usando Aspose.GIS para .NET, com opções
  de estilo de rótulo personalizadas para rotulagem de grandes conjuntos de dados.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Rotular recursos do mapa com Aspose.GIS para .NET
url: /pt/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rotulando recursos de mapa com Aspose.GIS para .NET

## Introdução
Rotular recursos de mapa é essencial para transformar dados geoespaciais brutos em visualizações claras e fáceis de usar. Neste tutorial você descobrirá **como rotular recursos de mapa** (a palavra‑chave principal) usando Aspose.GIS para .NET, explorará estilos de rótulo personalizados e verá técnicas que funcionam mesmo com grandes conjuntos de dados. Ao final, você será capaz de adicionar texto informativo diretamente aos seus mapas, tornando‑os mais perspicazes para analistas e usuários finais.

## Respostas rápidas
- **Qual é a classe principal para renderização?** `Map` (Aspose.Gis.Rendering)
- **Qual classe de rotulagem adiciona texto simples?** `SimpleLabeling`
- **Posso estilizar rótulos (halo, fonte, rotação)?** Sim – via propriedades como `HaloSize`, `FontStyle` e `Placement`
- **Como lidar com grandes conjuntos de dados?** Use `FeatureBasedConfiguration` para priorizar rótulos com base em valores de atributos
- **Preciso de uma licença?** Uma versão de avaliação funciona para desenvolvimento; uma licença comercial é necessária para produção

## O que são recursos de mapa rotulados?
`label map features` significa anexar texto legível (como nomes de cidades, números de população ou identificadores personalizados) a objetos geométricos — pontos, linhas ou polígonos — de modo que o mapa transmita tanto informações espaciais quanto atributos de forma instantânea.

## Por que usar Aspose.GIS para rotular recursos de mapa?
- **Zero dependências externas** – biblioteca pura .NET, sem binários GIS nativos necessários.  
- **Opções de estilo avançadas** – halos, fontes personalizadas, rotação e pontos de ancoragem permitem ajustar finamente a aparência.  
- **Consciente de desempenho** – rotulagem baseada em recursos integrada permite priorizar os rótulos mais importantes ao renderizar grandes conjuntos de dados.  
- **Vários formatos de saída** – SVG, PNG, PDF, etc., com resultados de rotulagem consistentes.

## Pré‑requisitos
Antes de começar, assegure‑se de que você tem:

- Um conhecimento prático de C# e do framework .NET.  
- Aspose.GIS para .NET instalado. Você pode baixá‑lo **[aqui](https://releases.aspose.com/gis/net/)**.  
- Um arquivo GeoJSON contendo dados de ponto (ou qualquer formato vetorial suportado).  

## Importar namespaces
Em seu código C#, importe os namespaces necessários:

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

Agora percorreremos vários cenários de rotulagem, cada um construído sobre o anterior.

## Rotulagem de Pontos – Como rotular pontos
### Passo 1: Defina o caminho para o diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```

### Passo 2: Crie um mapa com um símbolo de marcador simples
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

Neste exemplo básico, nós **como rotular pontos** usando o atributo `name` do arquivo GeoJSON.

## Rotulagem de Pontos Estilizada – Estilo de rótulo personalizado
Siga os passos 1 e 2 do exemplo anterior, então personalize o estilo de rotulagem:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

O halo adicionado e a fonte itálica dão aos rótulos um **estilo de rótulo personalizado** que se destaca em fundos movimentados.

## Rotulagem de Pontos Posicionada – Opções avançadas de posicionamento
Novamente, comece com os passos 1 e 2 do primeiro exemplo, então ajuste o posicionamento:

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
// Rest of the steps remain the same
```

Aqui controlamos pontos de ancoragem, deslocamentos e rotação, oferecendo controle detalhado sobre **como rotular pontos** em áreas de mapa congestionadas.

## Rotulagem de Pontos Baseada em Recursos – Rotulagem de grandes conjuntos de dados
Ao lidar com muitos pontos, você pode querer priorizar rótulos com base em um atributo como população. Siga os passos 1 e 2 do primeiro exemplo, então implemente a rotulagem baseada em recursos:

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
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Esta estratégia de **rotulagem de grandes conjuntos de dados** garante que as cidades mais importantes (por população) sejam mostradas primeiro, enquanto pontos menos críticos podem ser omitidos quando o espaço é limitado.

## Conclusão
Parabéns! Agora você conhece várias maneiras de **rotular recursos de mapa** com Aspose.GIS para .NET — desde rotulagem simples de pontos até estilos sofisticados baseados em recursos para grandes conjuntos de dados. Experimente halos, rotações e regras de prioridade para criar mapas que comunicam exatamente o que seu público precisa ver.

## Perguntas Frequentes

**Q: Posso rotular recursos usando fontes personalizadas?**  
A: Sim. Defina `FontFamily` e `FontStyle` na configuração `SimpleLabeling` para usar qualquer fonte instalada.

**Q: O Aspose.GIS é compatível com outros formatos de dados GIS?**  
A: Absolutamente. Ele suporta GeoJSON, Shapefile, KML, GML e muitos outros formatos.

**Q: Como posso lidar com grandes conjuntos de dados para rotulagem?**  
A: Use `FeatureBasedConfiguration` para atribuir prioridades e ajustar dinamicamente o tamanho da fonte com base nos valores dos atributos, como mostrado no exemplo baseado em recursos.

**Q: Existem opções avançadas de posicionamento de rótulos disponíveis?**  
A: Sim. Você pode ajustar finamente o posicionamento com `PointLabelPlacement`, ajustando pontos de ancoragem, deslocamentos e rotação.

**Q: Posso automatizar a geração de rótulos em um processo em lote?**  
A: Certamente. Envolva o código de renderização do mapa em um loop ou serviço em segundo plano para processar várias camadas ou arquivos automaticamente.

---

**Última atualização:** 2026-01-15  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}