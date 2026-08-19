---
date: 2026-06-15
description: Aprenda como criar vector layer e definir layer spatial reference system
  com Aspose.GIS for .NET. Domine a definição de spatial reference, a adição de point
  feature e a recuperação do código EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Definir Layer Spatial Reference System
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Criar Vector Layer e Definir Layer Spatial Reference System
url: /pt/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial e Definir o Sistema de Referência Espacial da Camada

## Introdução
No vasto cenário dos Sistemas de Informação Geográfica (GIS), **Aspose.GIS for .NET** destaca‑se como uma biblioteca robusta e de alto desempenho que suporta **mais de 70** formatos vetoriais e raster e pode processar arquivos maiores que **10 GB** sem carregar todo o conjunto de dados na memória. Neste tutorial você **criará uma camada vetorial**, definirá sua referência espacial, **adicionará um recurso de ponto** e recuperará o código EPSG — tudo com orientação clara, passo a passo. Seja construindo um serviço de mapeamento, um pipeline de conversão de dados ou um motor de análise espacial, dominar esses fundamentos manterá o sistema de coordenadas do seu shapefile preciso e seu fluxo de trabalho GIS confiável.

## Respostas Rápidas
- **O que significa “criar camada vetorial”?** Cria uma nova camada GIS (por exemplo, um Shapefile) que pode armazenar geometrias como pontos, linhas ou polígonos.  
- **Qual código EPSG é usado no exemplo?** EPSG 26918 (NAD83 / UTM zona 18N).  
- **Posso adicionar um recurso de ponto após criar a camada?** Sim — use `ConstructFeature()` e atribua uma geometria `Point`.  
- **Como recupero o CRS da camada?** Leia `layer.SpatialReferenceSystem.EpsgCode` ou `.Name`.  
- **Preciso de licença para o Aspose.GIS?** Um teste gratuito está disponível; uma licença é necessária para uso em produção.

## O que é criar camada vetorial?
A operação **criar camada vetorial** cria um novo conjunto de dados vetoriais (como um Shapefile) que pode conter recursos geométricos e dados de atributos. No Aspose.GIS, isso é feito instanciando um objeto `VectorLayer` com um driver e um sistema de referência espacial.

## Por que definir corretamente o sistema de coordenadas da camada (CRS)?
Definir o sistema de referência de coordenadas (CRS) correto garante que cada geometria armazenada se alinhe com outros conjuntos de dados espaciais. Com o Aspose.GIS você pode definir o CRS usando um código EPSG padrão, o que assegura interoperabilidade com softwares GIS em todo o mundo. Por exemplo, o EPSG 26918 define NAD83 / UTM zona 18N, uma projeção comum para dados na costa leste dos Estados Unidos.

## Pré‑requisitos
- Experiência em desenvolvimento .NET (C# ou VB.NET).  
- Visual Studio 2022 ou posterior.  
- Biblioteca Aspose.GIS for .NET – faça o download **[aqui](https://releases.aspose.com/gis/net/)**.  
- Familiaridade básica com sistemas de referência espacial (CRS/EPSG).

## Importar Namespaces
O namespace `Aspose.Gis` fornece as classes centrais de GIS, enquanto `Aspose.Gis.Geometries` oferece tipos de geometria como `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Como criar uma camada vetorial no Aspose.GIS para .NET?
`VectorLayer` representa um conjunto de dados vetoriais como um Shapefile e fornece métodos para criar, ler e editar recursos.  
`SpatialReferenceSystem` define o sistema de referência de coordenadas usando um código EPSG.  

Carregue a pasta de destino, defina um `SpatialReferenceSystem` codificado em EPSG e chame `VectorLayer.Create` com o driver Shapefile. Essa chamada única aloca um novo arquivo `.shp`, grava os arquivos auxiliares `.shx` e `.dbf` e incorpora os metadados do CRS, pronto para inserção de recursos de forma eficiente.

### Etapa 1: Especificar o Diretório do Documento
Comece especificando o caminho para o diretório de documentos. Este será o local onde seus arquivos de dados espaciais serão armazenados.

```csharp
string dataDir = "Your Document Directory";
```

### Etapa 2: Definir Referência Espacial e Definir o Sistema de Coordenadas do Shapefile
`SpatialReferenceSystem` representa o CRS de uma camada, identificado por um código EPSG.  

Defina o caminho para o Shapefile e **defina a referência espacial** usando o código EPSG (26918 neste exemplo). Esta etapa **define o sistema de coordenadas do shapefile** para a camada.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Como adicionar um recurso de ponto a uma camada vetorial?
`Point` é um tipo de geometria que representa um par único de coordenadas X/Y.  

Construa um novo recurso, atribua uma geometria `Point` com as coordenadas X/Y desejadas e adicione o recurso ao `VectorLayer` aberto. A operação grava a geometria no arquivo `.shp` e o registro de atributos no arquivo `.dbf` em uma única transação.

### Etapa 3: Criar Camada Vetorial
`ConstructFeature` cria um novo objeto de recurso que pode conter geometria e dados de atributos.  

Agora **crie a camada vetorial** com o caminho do Shapefile especificado, o tipo de driver (Shapefile) e o sistema de referência espacial que você acabou de definir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Etapa 4: Adicionar Recurso de Ponto à Camada
Construa um novo recurso e **adicione o recurso de ponto** definindo sua geometria (um `Point` com coordenadas 60, 24). Em seguida, adicione o recurso à camada vetorial.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Etapa 5: Recuperar Informações do Sistema de Referência Espacial (Recuperar Código EPSG)
Abra a Camada Vetorial e recupere informações sobre o sistema de referência espacial, como o código EPSG e o nome legível. Isso demonstra como **recuperar o código EPSG** e **definir o CRS da camada**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Problemas Comuns e Soluções
| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **Falha ao abrir a camada** | Driver errado ou caminho de arquivo corrompido | Verifique `Drivers.Shapefile` e assegure que `path` aponta para um arquivo `.shp` existente. |
| **CRS incorreto exibido** | Uso do código EPSG errado | Verifique novamente o código EPSG em uma fonte autoritária (ex.: EPSG.io). |
| **Recurso não salvo** | Não chamar `layer.Add(feature)` dentro do bloco `using` | Garanta que o método `Add` seja executado antes que a camada seja descartada. |

## Perguntas Frequentes
**Q: Como altero o CRS de um Shapefile existente?**  
R: Abra a camada, crie um novo `SpatialReferenceSystem` com o código EPSG desejado, atribua‑o a `layer.SpatialReferenceSystem` e, em seguida, salve a camada.

**Q: Posso adicionar outros tipos de geometria (por exemplo, polígonos) usando a mesma abordagem?**  
R: Sim — substitua `new Point(x, y)` por `new Polygon(...)` ou `new LineString(...)` conforme necessário.

**Q: É possível trabalhar com grandes conjuntos de dados de forma eficiente?**  
R: Use APIs de streaming (`VectorLayer.Create` com `FeatureCollection`) e descarte as camadas prontamente para liberar recursos.

**Q: O Aspose.GIS suporta transformação de coordenadas?**  
R: Sim — use `Geometry.Transform(targetSrs)` para reprojetar geometrias entre diferentes referências espaciais.

**Q: Quais versões do .NET são suportadas?**  
R: O Aspose.GIS funciona com .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Última atualização:** 2026-06-15  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar Camada Vetorial e Definir Tolerância de Linearização usando Aspose.GIS para .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Criar Camada Vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [referência espacial wgs84 – Adicionar Camada ao GDB usando Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}