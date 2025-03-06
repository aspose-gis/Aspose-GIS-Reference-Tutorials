---
title: Especifique a variante WKT na tradução usando Aspose.GIS
linktitle: Especifique a variante WKT na tradução
second_title: API Aspose.GIS .NET
description: Aprenda como especificar variantes WKT no Aspose.GIS for .NET para controlar o formato e a precisão da representação de dados espaciais de maneira eficaz.
weight: 19
url: /pt/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Especifique a variante WKT na tradução usando Aspose.GIS

## Introdução
Aspose.GIS for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com dados de sistemas de informações geográficas (GIS) em seus aplicativos .NET sem esforço. Um dos recursos essenciais fornecidos pelo Aspose.GIS é a capacidade de especificar a variante Well-Known Text (WKT) durante a tradução, permitindo aos usuários controlar o formato e a precisão das representações de dados espaciais. Neste tutorial, exploraremos como especificar variantes WKT passo a passo usando Aspose.GIS for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Aspose.GIS for .NET: Baixe e instale Aspose.GIS for .NET do[página de download](https://releases.aspose.com/gis/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET configurado.
3. Conhecimento Básico: Familiaridade com a linguagem de programação C# e framework .NET.

## Importar namespaces
Antes de usar a funcionalidade Aspose.GIS em seu código, importe os namespaces necessários:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Etapa 1: crie um objeto de ponto
 Primeiro, crie um`Point` objeto com valores de latitude, longitude e medida opcional (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Etapa 2: Definir Sistema de Referência Espacial (SRS)
Atribua um sistema de referência espacial (SRS) ao objeto pontual. Neste exemplo, usamos o sistema de referência espacial WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Etapa 3: Especifique a variante WKT
 Agora, especifique a variante WKT para tradução. Aspose.GIS suporta várias variantes WKT, incluindo`Iso`, `SimpleFeatureAccessOutdated` , e`ExtendedPostGis`. Escolha a variante apropriada com base em seus requisitos:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PONTO M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PONTO (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## Etapa 4: controlar o formato numérico
Você pode controlar o formato numérico das coordenadas na representação WKT. Aspose.GIS fornece opções para especificar a precisão decimal:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PONTO M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PONTO M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PONTO M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PONTO M (23.573 25.342 40.3)
```

## Conclusão
Neste tutorial, aprendemos como especificar variantes WKT na tradução usando Aspose.GIS for .NET. Seguindo as etapas descritas acima, os desenvolvedores podem controlar efetivamente o formato e a precisão das representações de dados espaciais em seus aplicativos .NET, aumentando a flexibilidade e a usabilidade dos sistemas de informação geográfica.
## Perguntas frequentes
### Aspose.GIS é compatível com todas as versões do .NET?
Sim, Aspose.GIS suporta .NET Framework 4.0 e superior.
### Posso usar Aspose.GIS para projetos comerciais?
Sim, o Aspose.GIS pode ser usado para projetos pessoais e comerciais.
### O Aspose.GIS fornece suporte para outros formatos de dados espaciais?
Sim, Aspose.GIS oferece suporte a uma ampla variedade de formatos de dados espaciais, incluindo ESRI Shapefile, GeoJSON e KML.
### Existe um teste gratuito disponível para Aspose.GIS?
 Sim, você pode baixar uma versão de teste gratuita do Aspose.GIS em[aqui](https://releases.aspose.com/).
### Onde posso obter ajuda ou suporte para Aspose.GIS?
 Você pode postar suas dúvidas ou buscar assistência da comunidade Aspose.GIS no[fórum](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
