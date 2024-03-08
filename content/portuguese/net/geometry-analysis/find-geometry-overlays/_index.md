---
title: Dominando sobreposições de geometria com Aspose.GIS para .NET
linktitle: Encontre sobreposições de geometria
second_title: API Aspose.GIS .NET
description: Aprenda como realizar operações de sobreposição geométrica usando Aspose.GIS for .NET. Operações mestres de interseção, união, diferença e diferença simétrica.
type: docs
weight: 16
url: /pt/net/geometry-analysis/find-geometry-overlays/
---
## Introdução
No âmbito dos Sistemas de Informação Geográfica (SIG), as operações de sobreposição são fundamentais para a análise espacial. Eles permitem a comparação e combinação de diferentes conjuntos de dados espaciais para obter informações valiosas. Aspose.GIS for .NET fornece funcionalidades robustas para realizar sobreposições geométricas com eficiência. Neste tutorial, nos aprofundaremos em várias operações de sobreposição, como interseção, união, diferença e diferença simétrica usando Aspose.GIS for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
### 1. Ambiente de desenvolvimento .NET
Certifique-se de ter um ambiente de desenvolvimento .NET configurado em sua máquina. Você pode baixar e instalar o SDK do .NET no site do .NET.
### 2. Biblioteca Aspose.GIS para .NET
 Baixe e instale a biblioteca Aspose.GIS for .NET do[local na rede Internet](https://releases.aspose.com/gis/net/).
## Importar namespaces
Antes de começar a usar o Aspose.GIS for .NET, você precisa importar os namespaces necessários para o seu projeto.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 1: criar objetos poligonais
Primeiro, definiremos dois objetos poligonais que representam regiões espaciais.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## Passo 2: Execute a operação de intersecção
A seguir, vamos encontrar a intersecção dos dois polígonos.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polígono
```
## Etapa 3: Imprimir pontos de interseção
Imprimiremos os pontos do polígono de interseção.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Passo 4: Execute a Operação Sindical
Agora, vamos encontrar a união dos dois polígonos.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polígono
```
## Etapa 5: imprimir pontos de união
Imprima os pontos do polígono de união.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Etapa 6: Execute a operação de diferença
A seguir, vamos encontrar a diferença entre os dois polígonos.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polígono
```
## Etapa 7: Imprimir pontos de diferença
Imprima os pontos do polígono de diferença.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Etapa 8: Execute a operação de diferença simétrica
Por último, vamos encontrar a diferença simétrica entre os dois polígonos.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Multipolígono
```
## Etapa 9: Imprimir polígonos de diferença simétrica
Imprima os pontos de cada polígono na diferença simétrica.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Conclusão
Dominar as sobreposições geométricas é crucial na análise espacial e o Aspose.GIS for .NET fornece um conjunto abrangente de ferramentas para realizar essas operações com eficiência. Seguindo este tutorial, você aprendeu como utilizar Aspose.GIS for .NET para realizar operações de interseção, união, diferença e diferença simétrica em formas geométricas.
## Perguntas frequentes
### P: Posso usar Aspose.GIS for .NET em meus projetos comerciais?
Sim, o Aspose.GIS for .NET pode ser usado em projetos comerciais e não comerciais.
### P: Existe uma versão de teste disponível para Aspose.GIS for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte para Aspose.GIS for .NET?
 Você pode obter suporte no fórum da comunidade Aspose.GIS[aqui](https://forum.aspose.com/c/gis/33).
### P: Há alguma licença temporária disponível para Aspose.GIS for .NET?
 Sim, licenças temporárias estão disponíveis para fins de teste e avaliação. Você pode obtê-los em[aqui](https://purchase.aspose.com/temporary-license/).
### P: Posso comprar Aspose.GIS for .NET diretamente?
 Sim, você pode comprar Aspose.GIS para .NET no site[aqui](https://purchase.aspose.com/buy).