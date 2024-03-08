---
title: Conversão de GeoJSON para arquivo GDB desmistificada
linktitle: Converter camada GeoJSON em arquivo GDB
second_title: API Aspose.GIS .NET
description: Desbloqueie maravilhas geoespaciais com Aspose.GIS for .NET! Converta facilmente camadas GeoJSON em bancos de dados geográficos de arquivos. Tente agora! #Aspose #GIS
type: docs
weight: 17
url: /pt/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Introdução
No domínio dinâmico dos Sistemas de Informação Geográfica (GIS), a capacidade de converter dados perfeitamente entre diferentes formatos é crucial. Aspose.GIS for .NET surge como um aliado poderoso, oferecendo um conjunto abrangente de ferramentas para lidar com dados geoespaciais sem esforço. Neste tutorial, nos aprofundaremos no processo de conversão de uma camada GeoJSON em um arquivo geodatabase (arquivo GDB) usando Aspose.GIS for .NET.
## Pré-requisitos
Antes de embarcar nesta jornada geoespacial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de programação .NET.
-  Aspose.GIS para .NET instalado. Se não, baixe-o em[aqui](https://releases.aspose.com/gis/net/) e siga as instruções de instalação.
## Importar namespaces
Para iniciar o processo de conversão, comece importando os namespaces necessários:
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
Agora, vamos dividir o processo em um guia passo a passo:
## Etapa 1: configurar a camada GeoJSON
Comece criando uma camada GeoJSON com atributos e recursos relevantes. Aqui está um trecho para orientá-lo:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Adicionar atributos
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Construir e adicionar recursos
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
## Etapa 2: copiar conjunto de dados de teste
Para preservar a integridade dos seus dados de teste, crie uma cópia do conjunto de dados. Use o seguinte trecho de código:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Etapa 3: converter GeoJSON em arquivo GDB
Agora é hora de realizar a conversão. Utilize o seguinte código:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copiar atributos
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Adicionar recursos
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Conclusão
Neste tutorial, navegamos no terreno intrigante de converter uma camada GeoJSON em um arquivo geodatabase usando Aspose.GIS for .NET. Armado com esse conhecimento, agora você está equipado para manipular dados geoespaciais de maneira transparente em seus aplicativos .NET.
## Perguntas frequentes
### O Aspose.GIS é compatível com o framework .NET mais recente?
Sim, Aspose.GIS é compatível com as versões mais recentes do .NET framework.
### Posso converter outros formatos geoespaciais usando Aspose.GIS?
Absolutamente! Aspose.GIS oferece suporte a uma ampla variedade de formatos geoespaciais para manipulação versátil de dados.
### Existe uma versão de teste disponível para Aspose.GIS?
 Sim, você pode explorar as funcionalidades do Aspose.GIS baixando a versão de teste[aqui](https://releases.aspose.com/).
### Como posso obter suporte para consultas relacionadas ao Aspose.GIS?
 Vá para o Aspose.GIS[fórum](https://forum.aspose.com/c/gis/33) para suporte dedicado.
### Posso obter uma licença temporária para Aspose.GIS?
 Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).