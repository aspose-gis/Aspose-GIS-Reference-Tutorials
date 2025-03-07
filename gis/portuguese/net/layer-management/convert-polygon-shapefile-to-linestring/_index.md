---
title: Converter Shapefile de polígono em cadeia de linha
linktitle: Converter Shapefile de polígono em cadeia de linha
second_title: API Aspose.GIS .NET
description: Explore o poder do Aspose.GIS para .NET e converta facilmente Polygon Shapefiles em Linestrings. Aumente o seu desenvolvimento GIS hoje!
weight: 18
url: /pt/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter Shapefile de polígono em cadeia de linha

## Introdução
Se você estiver trabalhando com sistemas de informação geográfica (GIS) em .NET, Aspose.GIS é uma biblioteca poderosa que pode simplificar suas tarefas. Neste tutorial, iremos guiá-lo através do processo de conversão de um Polygon Shapefile em uma Linestring usando Aspose.GIS. Isso pode ser particularmente útil quando você precisa extrair recursos lineares de dados poligonais para diversas aplicações, como planejamento de rotas ou análise de rede.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte em vigor:
-  Biblioteca Aspose.GIS: Baixe e instale a biblioteca Aspose.GIS do[local na rede Internet](https://releases.aspose.com/gis/net/).
- Dados Shapefile: Tenha um Shapefile Polygon pronto para conversão. Se não tiver um, você poderá encontrar dados de amostra ou criar os seus próprios.
- Ambiente de desenvolvimento: Configure seu ambiente de desenvolvimento .NET com as ferramentas necessárias.
## Importar namespaces
Em seu código C#, você precisa importar os namespaces Aspose.GIS para acessar as classes e métodos necessários. Adicione os seguintes namespaces no início do seu arquivo de código:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Etapa 1: definir o diretório de documentos
```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
```
Substitua “Your Document Directory” pelo caminho para o diretório onde seu Shapefile está localizado.
## Etapa 2: Abra o Shapefile de origem
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // O resto do código irá aqui
}
```
Esta etapa abre o Polygon Shapefile de origem para leitura.
## Etapa 3: Criar o Shapefile de Linestring de Destino
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // O resto do código irá aqui
}
```
Aqui, criamos um novo Linestring Shapefile para gravar os dados convertidos.
## Etapa 4: iterar por meio dos recursos de origem
```csharp
foreach (Feature sourceFeature in source)
{
    // O resto do código irá aqui
}
```
Este loop percorre cada recurso no Polygon Shapefile de origem.
## Etapa 5: converter polígono em cadeia de linha e gravar no destino
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Nesta etapa, cada recurso Polygon é convertido em um Linestring, e o recurso Linestring resultante é gravado no Shapefile de destino.
## Conclusão
Seguindo essas etapas, você pode converter facilmente um Polygon Shapefile em uma Linestring usando Aspose.GIS for .NET. Este processo abre novas possibilidades para análise e visualização de dados em aplicações GIS.

## Perguntas frequentes
### Aspose.GIS é compatível com todas as versões do .NET?
Sim, Aspose.GIS suporta diversas versões de .NET, garantindo compatibilidade com seu ambiente de desenvolvimento.
### Posso usar Aspose.GIS para projetos comerciais?
 Sim você pode. Para usar Aspose.GIS em projetos comerciais, considere adquirir uma licença[aqui](https://purchase.aspose.com/buy).
### Existem exemplos ou documentação disponíveis?
 Sim, você pode encontrar documentação abrangente e exemplos no[página de documentação](https://reference.aspose.com/gis/net/).
### Existe uma versão de teste disponível?
 Sim, você pode explorar o Aspose.GIS com uma avaliação gratuita visitando[esse link](https://releases.aspose.com/).
### Onde posso procurar ajuda ou suporte?
 Visite a[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para qualquer assistência ou dúvidas relacionadas ao suporte.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
