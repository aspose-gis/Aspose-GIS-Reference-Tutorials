---
title: Contar geometrias em geometria com Aspose.GIS
linktitle: Contar geometrias em geometria
second_title: API Aspose.GIS .NET
description: Aprenda como contar geometrias em uma geometria usando Aspose.GIS for .NET. Tutorial passo a passo com exemplos de código para desenvolvedores.
weight: 23
url: /pt/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contar geometrias em geometria com Aspose.GIS

## Introdução
Aspose.GIS for .NET é uma ferramenta poderosa para desenvolvedores que buscam incorporar funcionalidades geoespaciais em seus aplicativos .NET. Esteja você construindo software de mapeamento, serviços baseados em localização ou ferramentas de análise espacial, o Aspose.GIS fornece um conjunto abrangente de recursos para atender às suas necessidades. Neste tutorial, exploraremos como contar geometrias dentro de uma geometria usando Aspose.GIS for .NET.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.
2. Aspose.GIS for .NET: Baixe e instale Aspose.GIS for .NET do[página de download](https://releases.aspose.com/gis/net/).
3. Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#.

## Importar namespaces
Antes de iniciar a codificação, você precisa importar os namespaces necessários para acessar a funcionalidade Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 2: Criar geometria de ponto
```csharp
Point point = new Point(40.7128, -74.006);
```
 Aqui, criamos um`Point` geometria com latitude 40.7128 e longitude -74.006.
## Etapa 3: criar geometria LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Esta etapa cria um`LineString` geometria e adiciona dois pontos a ela.
## Etapa 4: criar uma coleção de geometria
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Criamos então um`GeometryCollection` e adicione a ele as geometrias de ponto e linha criadas anteriormente.
## Etapa 5: contar geometrias
```csharp
int geometriesCount = geometryCollection.Count;
```
 Esta etapa conta o número de geometrias dentro do`GeometryCollection`.
## Etapa 6: exibir a contagem
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Por fim, imprimimos a contagem de geometrias, que neste caso é`2`.

## Conclusão
Neste tutorial, aprendemos como contar geometrias dentro de uma geometria usando Aspose.GIS for .NET. Seguindo essas etapas, você pode incorporar funcionalidade geoespacial em seus aplicativos .NET com facilidade.
## Perguntas frequentes
### O Aspose.GIS for .NET é adequado para aplicativos desktop e web?
Sim, o Aspose.GIS for .NET pode ser usado perfeitamente em aplicativos desktop e web.
### Posso realizar consultas espaciais usando Aspose.GIS for .NET?
Com certeza, Aspose.GIS for .NET fornece suporte robusto para realizar consultas espaciais em geometrias.
### O Aspose.GIS for .NET suporta vários formatos de arquivo GIS?
Sim, Aspose.GIS for .NET oferece suporte a uma ampla variedade de formatos de arquivo GIS, incluindo SHP, KML e GeoJSON.
### Existe uma avaliação gratuita disponível para Aspose.GIS for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita no site[local na rede Internet](https://releases.aspose.com/).
### Onde posso encontrar suporte para Aspose.GIS for .NET?
 Você pode encontrar suporte no[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
