---
title: Verifique a igualdade das geometrias
linktitle: Verifique a igualdade das geometrias
second_title: API Aspose.GIS .NET
description: Aprenda como usar Aspose.GIS for .NET para verificar a igualdade de geometrias em seus aplicativos .NET com este tutorial abrangente.
weight: 10
url: /pt/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verifique a igualdade das geometrias

## Introdução
Aspose.GIS for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com dados geoespaciais de forma eficiente em seus aplicativos .NET. Esteja você construindo aplicativos de mapeamento, ferramentas de análise espacial ou integrando funcionalidades geoespaciais em software existente, o Aspose.GIS fornece as ferramentas de que você precisa para realizar o trabalho.
## Pré-requisitos
Antes de começar a usar o Aspose.GIS for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
### .NET Framework instalado
Certifique-se de ter o .NET Framework instalado em seu sistema. Você pode baixá-lo no site da Microsoft.
### Biblioteca Aspose.GIS para .NET
 Baixe e instale a biblioteca Aspose.GIS for .NET do[página de download](https://releases.aspose.com/gis/net/). Siga as instruções de instalação fornecidas na documentação.
### Ambiente de desenvolvimento
Configure seu ambiente de desenvolvimento preferido, como Visual Studio, para desenvolvimento .NET.

## Importar namespaces
Em seu aplicativo .NET, importe os namespaces necessários para usar a funcionalidade Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passo 1: Definir Geometrias
Primeiro, defina as geometrias que deseja comparar. Neste exemplo, temos duas geometrias:`geometry1` e`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Etapa 2: verificar a igualdade das geometrias
 Agora, verifique se as geometrias são espacialmente iguais usando o`SpatiallyEquals` método fornecido por Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Verdadeiro
```
 Isto irá imprimir`True` para o console desde`geometry1` e`geometry2` são espacialmente iguais.
## Etapa 3: modificar a geometria
 A seguir, vamos modificar`geometry2` adicionando um novo ponto.
```csharp
geometry2.AddPoint(3, 3);
```
## Etapa 4: verificar novamente a igualdade
Agora, verifique novamente a igualdade das geometrias após a modificação.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Falso
```
 Desta vez, a saída será`False` já que as geometrias não são mais iguais espacialmente devido à modificação feita`geometry2`.

## Conclusão
Concluindo, Aspose.GIS for .NET fornece ferramentas poderosas para trabalhar com dados geoespaciais em aplicativos .NET. Seguindo este guia passo a passo, você pode facilmente verificar a igualdade das geometrias usando os métodos Aspose.GIS.
## Perguntas frequentes
### Posso usar o Aspose.GIS for .NET com outras estruturas .NET?
Sim, Aspose.GIS for .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET Standard.
### Existe uma avaliação gratuita disponível para Aspose.GIS for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita no site[página de lançamentos](https://releases.aspose.com/).
### Onde posso encontrar documentação para Aspose.GIS for .NET?
 Você pode encontrar documentação detalhada no[Página de documentação do Aspose.GIS](https://reference.aspose.com/gis/net/).
### Como posso obter suporte para Aspose.GIS for .NET?
 Você pode obter suporte no fórum da comunidade Aspose.GIS[aqui](https://forum.aspose.com/c/gis/33).
### Posso adquirir uma licença temporária do Aspose.GIS for .NET?
 Sim, você pode comprar uma licença temporária no[página de compra](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
