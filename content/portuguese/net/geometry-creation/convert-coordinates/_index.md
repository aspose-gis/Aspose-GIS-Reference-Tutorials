---
title: Coordenar conversão com Aspose.GIS
linktitle: Converter coordenadas
second_title: API Aspose.GIS .NET
description: Aprenda como converter coordenadas com Aspose.GIS for .NET. Guia passo a passo, pré-requisitos e perguntas frequentes fornecidas.
type: docs
weight: 25
url: /pt/net/geometry-creation/convert-coordinates/
---
## Introdução
Neste tutorial, mergulharemos no mundo dos sistemas de informação geográfica (GIS) usando a poderosa biblioteca Aspose.GIS para .NET. Aspose.GIS é um kit de ferramentas abrangente que permite aos desenvolvedores trabalhar com dados espaciais sem esforço. Quer você seja um desenvolvedor experiente ou apenas começando, este tutorial irá guiá-lo através do processo de utilização do Aspose.GIS para converter coordenadas de forma eficaz.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# é essencial para compreender e implementar os exemplos de código fornecidos.
  
2.  Instalação do Aspose.GIS: Certifique-se de ter baixado e instalado a biblioteca Aspose.GIS para .NET. Você pode baixá-lo no[Site Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importar namespaces
Antes de começar, vamos importar os namespaces necessários para acessar as funcionalidades do Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Vamos dividir o exemplo fornecido em várias etapas para uma compreensão clara:
## Etapa 1: inicie o processo de conversão
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Esta linha simplesmente exibe uma mensagem indicando o início do processo de conversão de coordenadas.
## Etapa 2: converter para graus decimais
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Aqui, convertemos as coordenadas (25,5, 45,5) para o formato de graus decimais usando o`AsPointText` método com o`PointFormats.DecimalDegrees` parâmetro. O resultado é então impresso no console.
## Etapa 3: converter em minutos decimais em graus
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Esta etapa converte as coordenadas para o formato de graus decimais e minutos e imprime o resultado.
## Etapa 4: converter para graus-minutos-segundos
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Da mesma forma, convertemos as coordenadas para o formato graus minutos segundos e exibimos a saída.
## Etapa 5: converter para GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Por fim, convertemos as coordenadas para o formato GeoRef e imprimimos o resultado.

## Conclusão
Neste tutorial, exploramos o processo de conversão de coordenadas usando Aspose.GIS for .NET. Seguindo o guia passo a passo e utilizando a biblioteca Aspose.GIS, você pode manipular dados espaciais com eficiência em seus aplicativos .NET.
## Perguntas frequentes
### O Aspose.GIS é compatível com outras linguagens de programação?
O Aspose.GIS é voltado principalmente para desenvolvedores .NET, mas oferece interoperabilidade com Java por meio do Aspose.GIS for Java.
### Posso experimentar o Aspose.GIS antes de comprar?
 Sim, você pode acessar uma avaliação gratuita do Aspose.GIS no[local na rede Internet](https://releases.aspose.com/).
### Como posso obter suporte para Aspose.GIS?
 Você pode buscar ajuda no fórum da comunidade Aspose.GIS[aqui](https://forum.aspose.com/c/gis/33).
### As licenças temporárias estão disponíveis para Aspose.GIS?
 Sim, licenças temporárias podem ser obtidas no[página de licença temporária](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar o Aspose.GIS?
 Você pode comprar Aspose.GIS no[página de compra](https://purchase.aspose.com/buy).