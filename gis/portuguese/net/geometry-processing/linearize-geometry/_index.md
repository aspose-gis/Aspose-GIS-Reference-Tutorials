---
date: 2026-09-10
description: Aprenda a converter curvas em linhas (linearize geometry) usando Aspose.GIS
  for .NET, permitindo processamento e análise geoespaciais eficientes em seus aplicativos
  .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize a Geometry
og_description: Converter curvas em linhas (linearize geometry) usando Aspose.GIS
  for .NET. Aprenda passo a passo como simplificar geometrias para renderização mais
  rápida e maior compatibilidade.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Converter curvas em linhas com Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Como Converter Curvas em Linhas com Aspose.GIS for .NET
url: /pt/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter curvas em linhas (linearizar geometria) com Aspose.GIS para .NET

## Introdução
Se você precisa **converter curvas em linhas** para mapeamento, análise espacial ou tarefas de troca de dados, o Aspose.GIS para .NET oferece uma maneira limpa e programática de fazer isso. Neste tutorial, percorreremos um exemplo completo e real que mostra como pegar uma geometria complexa — contendo curvas e formas compostas — e transformá‑la em uma representação linear simples que funciona com qualquer sistema GIS.

## Respostas rápidas
- **O que significa “converter curvas em linhas”?** Ela transforma geometrias curvas em segmentos de linha reta.  
- **Por que escolher o Aspose.GIS?** A biblioteca suporta mais de 30 formatos GIS e lida com a conversão de geometria sem ferramentas externas.  
- **O que preciso ter antes?** .NET Framework ou .NET Core, Visual Studio (ou qualquer IDE C#), e o pacote NuGet Aspose.GIS.  
- **Quanto tempo o exemplo levará para ser executado?** Menos de cinco minutos após a instalação da biblioteca.  
- **Posso exportar para outros formatos?** Absolutamente — troque o driver KML por Shapefile, GeoJSON, etc.  
Você pode baixar a suíte completa de produtos no [site da Aspose](https://releases.aspose.com/).

## O que significa converter curvas em linhas?
Converter curvas em linhas (também chamado de **linearizar geometria**) substitui cada segmento curvo por uma série de pequenos trechos de linha reta, criando uma *geometria linear*. Isso torna a renderização até cinco vezes mais rápida, reduz o consumo de memória e garante que os dados possam ser consumidos por serviços GIS legados que aceitam apenas recursos lineares.

## Por que converter curvas em linhas?
Geometrias lineares são renderizadas e consultadas até **5× mais rápido** que suas contrapartes curvas, e **mais de 30 plataformas GIS** aceitam apenas recursos lineares. Simplificar a geometria também reduz o tamanho do arquivo para visualizações baseadas na web e habilita algoritmos — como análise de rede ou agrupamento — que requerem entrada de linhas retas.

## Como linearizar a geometria?
Use o método `ToLinearGeometry()` fornecido pelo Aspose.GIS. Ele tessela automaticamente cada curva em uma geometria em segmentos de linha reta, preservando quaisquer valores Z, de modo que você obtenha uma aproximação linear sem perder dados de elevação. Você também pode especificar uma tolerância para controlar o desvio máximo entre a curva original e os segmentos gerados, permitindo equilibrar precisão e tamanho do arquivo. O método funciona tanto para geometrias 2‑D quanto 3‑D.

## Pré-requisitos
Antes de mergulhar no código, certifique‑se de que você tem:

1. **Aspose.GIS for .NET** – faça o download no [site Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ou .NET Core) instalado na sua máquina de desenvolvimento.  
3. **Visual Studio** (ou qualquer IDE compatível com C#) para escrever e executar o exemplo.

## Importar namespaces
Para começar a usar a funcionalidade do Aspose.GIS, importe os namespaces necessários.

### Namespaces principais do Aspose.GIS
O namespace `Aspose.Gis` contém as classes principais de geometria, drivers e utilitários necessários para todas as operações GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Driver para o formato de destino
`Aspose.Gis.Drivers` fornece fábricas estáticas para cada formato de arquivo suportado; `Drivers.Kml` cria um gravador KML.  
```csharp
using Aspose.GIS.Kml;
```

## Guia passo a passo para converter curvas em linhas
A seguir está uma explicação detalhada de cada linha de código, explicando **como converter curvas em linhas** e por que cada passo é importante.

### Passo 1: Definir o caminho de saída
`Path.Combine` cria um caminho de arquivo independente de plataforma, lidando automaticamente com barras invertidas do Windows e barras normais do Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Substitua `"Your Document Directory"` pela pasta onde você deseja salvar o arquivo KML.

### Passo 2: Criar uma camada para o arquivo de saída
Uma *camada* agrupa recursos geográficos do mesmo tipo. Aqui instanciamos uma nova camada KML que armazenará a geometria linearizada.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Passo 3: Construir um novo recurso
Um *recurso* representa um único objeto geográfico (ponto, linha, polígono, etc.). Vamos anexar nossa geometria linear a este recurso.  
```csharp
var feature = layer.ConstructFeature();
```

### Passo 4: Definir a geometria complexa original
`Geometry.FromWkt` analisa uma string Well‑Known Text (WKT) em um objeto de geometria. O WKT de exemplo inclui um `LineString`, um `CompoundCurve` e um `CircularString` para demonstrar o tratamento de curvas.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Passo 5: Converter curvas em linhas
`ToLinearGeometry()` tessela cada curva na geometria de origem em segmentos de linha reta, retornando uma nova geometria linear que preserva quaisquer coordenadas Z.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Passo 6: Atribuir a geometria linear ao recurso
A propriedade `Geometry` do recurso agora contém a versão simplificada e linear da forma original.  
```csharp
feature.Geometry = linear;
```

### Passo 7: Adicionar o recurso à camada
Adicionar o recurso à camada KML o coloca na fila para gravação; quando o bloco `using` termina, a camada grava os dados no arquivo de saída.  
```csharp
layer.Add(feature);
```

## Armadilhas comuns e dicas profissionais
- **Separadores de caminho:** Use `Path.Combine` para evitar problemas no Windows vs. Linux.  
- **Geometrias muito grandes:** Linearizar formas intrincadas pode gerar milhares de vértices; considere chamar `Simplify()` após a linearização para reduzir a contagem de pontos.  
- **Seleção de driver:** Se precisar de um formato de saída diferente, substitua `Drivers.Kml` por `Drivers.Shapefile`, `Drivers.GeoJson`, etc., e altere a extensão do arquivo conforme necessário.  
- **Preservação de valores Z:** `ToLinearGeometry()` mantém coordenadas 3‑D (Z), portanto você não perde dados de elevação.

## Perguntas frequentes (FAQ)

**Q: O Aspose.GIS para .NET é compatível com .NET Core?**  
A: Sim, o Aspose.GIS funciona com .NET Core, permitindo aplicações multiplataforma.

**Q: Posso trabalhar com diferentes formatos de arquivo GIS usando o Aspose.GIS para .NET?**  
A: Absolutamente! A biblioteca suporta KML, Shapefile, GeoJSON e muitos outros formatos — mais de 30 no total.

**Q: O Aspose.GIS oferece operações e análises espaciais?**  
A: Sim, ele fornece uma ampla gama de funções espaciais, desde buffers até junções espaciais.

**Q: Existe uma versão de avaliação gratuita disponível?**  
A: Sim, você pode baixar uma avaliação gratuita no [site Aspose.GIS](https://releases.aspose.com/gis/net/).

**Q: Onde posso obter ajuda se encontrar problemas?**  
A: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade e da equipe.

### Consultas adicionais comuns

**Q: Posso linearizar geometrias que contêm coordenadas 3D (Z)?**  
A: Sim, `ToLinearGeometry()` funciona tanto com geometrias 2D quanto 3D; os valores Z são preservados.

**Q: Como a linearização afeta o tamanho do arquivo?**  
A: Converter curvas em muitos segmentos curtos pode aumentar o tamanho do arquivo; execute `Simplify()` após a linearização se o tamanho for uma preocupação.

**Q: Posso controlar o comprimento dos segmentos ao converter curvas em linhas?**  
A: O método padrão usa uma tolerância interna. Para segmentação personalizada, você pode tesselar manualmente as curvas antes de chamar `ToLinearGeometry()`.

## Conclusão
Neste tutorial, abordamos **como converter curvas em linhas** (linearizar geometria) usando o Aspose.GIS para .NET, desde a configuração do ambiente até a gravação do resultado linearizado em um arquivo KML. Agora você pode incorporar esse fluxo de trabalho em aplicativos de mapeamento, pipelines de processamento de dados ou qualquer projeto relacionado a GIS que exija geometrias simplificadas.

---

**Última atualização:** 2026-09-10  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Como criar GeoJSON com tolerância Aspose.GIS para .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Converter polígono em linha com Aspose.GIS para .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Aprenda como criar geometria LineString com Aspose.GIS para .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}