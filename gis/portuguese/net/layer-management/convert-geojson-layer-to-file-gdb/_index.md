---
date: 2026-01-10
description: Aprenda a converter GeoJSON para File GDB com Aspose.GIS para .NET. Este
  guia passo a passo aborda a conversão de dados geoespaciais e a conversão do Aspose
  GIS.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: Como Converter GeoJSON para File GDB Usando Aspose.GIS para .NET
url: /pt/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Converter GeoJSON para File GDB Usando Aspose.GIS para .NET

## Introdução
Se você está se perguntando **como converter GeoJSON** em um File Geodatabase (File GDB) para fluxos de trabalho GIS robustos, chegou ao lugar certo. Neste tutorial, vamos guiá‑lo por todo o processo com Aspose.GIS para .NET, mostrando por que esta biblioteca é uma escolha de destaque para conversão de dados geoespaciais e como você pode criar rapidamente um file geodatabase a partir de uma camada GeoJSON.

## Respostas Rápidas
- **O que o tutorial aborda?** Conversão de uma camada GeoJSON para um File GDB usando Aspose.GIS para .NET.  
- **Qual palavra‑chave principal é alvo?** *how to convert geojson*.  
- **Preciso de licença?** Uma avaliação gratuita serve para testes; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para uma conversão básica.

## O que é GeoJSON e File GDB?
GeoJSON é um formato leve, baseado em texto, para codificar uma variedade de estruturas de dados geográficos. Um File Geodatabase (File GDB) é um formato baseado em pastas, de alto desempenho, usado por muitas aplicações GIS de desktop. Converter entre eles permite que você aproveite as vantagens de ambos os formatos em seus projetos.

## Por que usar Aspose.GIS para conversão de dados geoespaciais?
Aspose.GIS oferece uma API unificada que abstrai as complexidades do manuseio de formatos. Com suporte nativo para **geojson to file gdb**, você pode:

- Ler GeoJSON em C# sem analisadores de terceiros.  
- Criar programaticamente um file geodatabase.  
- Preservar automaticamente os dados de atributos e as informações de referência espacial.  

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Conhecimento prático de programação .NET.  
- Aspose.GIS para .NET instalado. Caso não tenha, faça o download [aqui](https://releases.aspose.com/gis/net/) e siga as instruções de instalação.

## Importar Namespaces
O primeiro passo é trazer os namespaces necessários para o escopo.

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

## Etapa 1: Configurar a Camada GeoJSON
Crie um arquivo GeoJSON temporário que contenha os atributos e recursos que você deseja converter. Este exemplo adiciona dois recursos de ponto simples.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Etapa 2: Copiar Conjunto de Dados de Teste
Para manter os dados de teste originais intactos, duplique o conjunto de dados File GDB existente. Isso garante um ambiente limpo para a conversão.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Etapa 3: Converter GeoJSON para File GDB
Abra a camada GeoJSON, crie uma nova camada dentro do File GDB copiado, copie os atributos e transfira cada recurso. Este é o núcleo do processo de **aspose gis conversion**.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Problemas Comuns e Soluções
- **Referência espacial ausente:** Certifique‑se de que o GeoJSON de origem inclui uma definição CRS ou defina explicitamente `SpatialReferenceSystem.Wgs84` ao criar a camada File GDB.  
- **Incompatibilidade de tipo de atributo:** Os tipos de dados de atributo no GeoJSON devem corresponder ao esquema de destino; caso contrário, o Aspose.GIS lançará uma exceção.  
- **Erros de acesso ao arquivo:** Verifique se a pasta de destino tem permissões de gravação e se nenhum outro processo está bloqueando os arquivos GDB.

## Perguntas Frequentes
### O Aspose.GIS é compatível com a versão mais recente do .NET?
Sim, o Aspose.GIS é compatível com as versões mais recentes do .NET framework.  

### Posso converter outros formatos geoespaciais usando Aspose.GIS?
Absolutamente! O Aspose.GIS suporta uma ampla variedade de formatos geoespaciais para manipulação versátil de dados.  

### Existe uma versão de avaliação disponível para o Aspose.GIS?
Sim, você pode explorar as funcionalidades do Aspose.GIS baixando a versão de avaliação [aqui](https://releases.aspose.com/).  

### Como obter suporte para dúvidas relacionadas ao Aspose.GIS?
Acesse o [forum](https://forum.aspose.com/c/gis/33) do Aspose.GIS para suporte dedicado.  

### Posso obter uma licença temporária para o Aspose.GIS?
Sim, você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).  

---

**Última atualização:** 2026-01-10  
**Testado com:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}