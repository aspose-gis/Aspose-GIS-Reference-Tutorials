---
title: Escreva GeoJSON para transmitir
linktitle: Escreva GeoJSON para transmitir
second_title: API Aspose.GIS .NET
description: Explore o poder do Aspose.GIS para .NET! Escreva GeoJSON para transmitir sem esforço. Baixe agora para integração geoespacial perfeita.
type: docs
weight: 25
url: /pt/net/layer-data-operations/write-geojson-to-stream/
---
## Introdução
Você deseja aproveitar o poder do GeoJSON em seu aplicativo .NET usando Aspose.GIS? Bem, você está no lugar certo! Este guia passo a passo orientará você no processo de gravação de GeoJSON em um stream, aproveitando os recursos robustos do Aspose.GIS for .NET.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Biblioteca Aspose.GIS for .NET: Certifique-se de ter a biblioteca Aspose.GIS for .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/gis/net/).
2. Diretório de documentos: configure um diretório de documentos em seu projeto e anote seu caminho.
Agora vamos começar com o tutorial!
## Importar namespaces
Em primeiro lugar, certifique-se de incluir os namespaces necessários para acessar as funcionalidades do Aspose.GIS em seu código:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## Etapa 1: configurar o diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua “Seu diretório de documentos” pelo caminho real para o diretório de documentos.
## Etapa 2: crie um fluxo de memória
```csharp
using (var memoryStream = new MemoryStream())
{
    // O código para as próximas etapas vai aqui
}
```
## Etapa 3: Crie uma camada vetorial com driver GeoJSON
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // O código para as próximas etapas vai aqui
}
```
## Etapa 4: definir atributos de recursos
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## Etapa 5: construir e adicionar recursos
```csharp
// Primeiro recurso
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Segundo recurso
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## Etapa 6: exibir saída GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
Parabéns! Você gravou GeoJSON com sucesso em um stream usando Aspose.GIS for .NET.
## Conclusão
Neste tutorial, cobrimos as etapas fundamentais para integrar o Aspose.GIS for .NET ao seu projeto, focando especificamente na gravação de GeoJSON em um fluxo. Com essas etapas simples, porém poderosas, você pode aprimorar os recursos geoespaciais do seu aplicativo.
## perguntas frequentes
### Posso usar o Aspose.GIS for .NET em ambientes Windows e Linux?
Sim, Aspose.GIS for .NET é compatível com sistemas Windows e Linux.
### Existe um teste gratuito disponível?
 Absolutamente! Você pode explorar uma avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação detalhada?
 Confira a documentação[aqui](https://reference.aspose.com/gis/net/).
### Como posso obter licenciamento temporário?
 Licenças temporárias estão disponíveis[aqui](https://purchase.aspose.com/temporary-license/).
### Precisa de ajuda ou tem mais dúvidas?
 Visite nosso fórum de suporte[aqui](https://forum.aspose.com/c/gis/33).