---
title: Converter GeoJSON em TopoJSON com nome de objeto específico
linktitle: Converter GeoJSON em TopoJSON com nome de objeto específico
second_title: API Aspose.GIS .NET
description: Aprenda como converter GeoJSON em TopoJSON com um nome de objeto específico usando Aspose.GIS for .NET. Este tutorial fornece um guia passo a passo para manipulação eficiente de dados geográficos.
type: docs
weight: 12
url: /pt/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---
## Introdução
Aspose.GIS for .NET é uma ferramenta poderosa para trabalhar com dados geográficos em aplicativos .NET. Esteja você desenvolvendo um aplicativo de mapeamento, analisando dados espaciais ou manipulando arquivos geojson, o Aspose.GIS fornece um conjunto abrangente de recursos para agilizar seu fluxo de trabalho.
## Pré-requisitos
Antes de começarmos a converter GeoJSON em TopoJSON com um nome de objeto específico usando Aspose.GIS for .NET, certifique-se de ter o seguinte:
### 1. Instale Aspose.GIS para .NET
 Vá para o[página de download](https://releases.aspose.com/gis/net/) e pegue a versão mais recente do Aspose.GIS for .NET.
### 2. Configure seu ambiente de desenvolvimento
Certifique-se de ter o Visual Studio ou qualquer outro ambiente de desenvolvimento .NET configurado em seu sistema.
### 3. Prepare seu arquivo GeoJSON
Tenha um arquivo GeoJSON que deseja converter em TopoJSON. Se você não tiver um, poderá usar qualquer arquivo GeoJSON de amostra para este tutorial.

## Importar namespaces
Antes de iniciarmos o processo de conversão, vamos importar os namespaces necessários:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 1: definir caminhos de arquivo
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
 Substituir`"Your Document Directory"`com o caminho real do diretório onde seu arquivo GeoJSON está localizado e onde você deseja salvar o arquivo TopoJSON convertido.
## Etapa 2: definir opções de conversão
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // especifique o nome do objeto onde os recursos devem ser escritos
        DefaultObjectName = "name_of_the_object",
    }
};
```
 Nesta etapa, criamos um`ConversionOptions` objeto e especifique`DefaultObjectName`, que é o nome do objeto onde os recursos devem ser gravados no arquivo TopoJSON resultante.
## Etapa 3: realizar a conversão
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
 Por fim, chamamos o`Convert` método de`VectorLayer` class, passando o caminho do arquivo GeoJSON de entrada, drivers de entrada e saída e opções de conversão.

## Conclusão
Neste tutorial, aprendemos como converter GeoJSON em TopoJSON com um nome de objeto específico usando Aspose.GIS for .NET. Seguindo essas etapas, você pode gerenciar e manipular dados geográficos com eficiência em seus aplicativos .NET.
## Perguntas frequentes
### Posso usar Aspose.GIS for .NET em meus projetos comerciais?
Sim, você pode usar Aspose.GIS for .NET em projetos comerciais e pessoais.
### Existe uma avaliação gratuita disponível para Aspose.GIS for .NET?
Sim, você pode obter um teste gratuito em[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte para Aspose.GIS for .NET?
 Você pode obter suporte do[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Como posso adquirir uma licença do Aspose.GIS for .NET?
 Você pode comprar uma licença de[aqui](https://purchase.aspose.com/buy).
### Preciso de uma licença temporária para avaliação?
 Sim, você pode obter uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/).