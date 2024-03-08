---
title: Crie uma camada vetorial com SRS
linktitle: Crie uma camada vetorial com SRS
second_title: API Aspose.GIS .NET
description: Explore o Aspose.GIS for .NET - sua chave para integração perfeita com GIS. Crie camadas vetoriais sem esforço com sistemas de referência espacial especificados. Baixe Agora!
type: docs
weight: 13
url: /pt/net/layer-management/create-vector-layer-with-srs/
---
## Introdução
Aspose.GIS for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com dados de sistemas de informações geográficas (GIS) perfeitamente em aplicativos .NET. Neste tutorial, focaremos na criação de uma camada vetorial com um sistema de referência espacial (SRS). Ao final deste guia, você será capaz de integrar facilmente recursos GIS em seus projetos .NET.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico de desenvolvimento em C# e .NET.
-  Biblioteca Aspose.GIS para .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/gis/net/).
- Um ambiente de desenvolvimento configurado e pronto.
## Importar namespaces
Certifique-se de ter os namespaces necessários importados no início do seu arquivo C#:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Etapa 1: Configurar o Sistema de Referência Espacial Projetado
Vamos criar um sistema de referência espacial projetado (SRS) usando a projeção World Mercator como exemplo. Siga esses passos:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Etapa 2: crie uma camada vetorial e adicione recursos
Agora, vamos criar um shapefile e adicionar recursos com o SRS especificado:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Isso lançará uma exceção, pois a geometria tem um SRS diferente
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Etapa 3: verificar o sistema de referência espacial
Por fim, vamos abrir a camada e verificar seu sistema de referência espacial:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Mercado Mundial"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Deve retornar verdadeiro
}
```
Seguindo essas etapas, você criou com sucesso uma camada vetorial com um sistema de referência espacial especificado usando Aspose.GIS for .NET.
## Conclusão
Integrar a funcionalidade GIS em seus aplicativos .NET nunca foi tão fácil, graças ao Aspose.GIS. Com a capacidade de criar facilmente camadas vetoriais e gerenciar sistemas de referência espacial, você pode aprimorar seus projetos com poderosos recursos geoespaciais.
## Perguntas frequentes
### O Aspose.GIS é compatível com todos os formatos de arquivo GIS?
 Aspose.GIS suporta vários formatos GIS, incluindo Shapefile, GeoJSON, KML e muito mais. Verifica a[documentação](https://reference.aspose.com/gis/net/) para a lista completa.
### Posso usar Aspose.GIS em uma aplicação web?
Absolutamente! Aspose.GIS for .NET é versátil e pode ser usado em aplicativos da web, aplicativos de desktop e até mesmo aplicativos móveis.
### Onde posso obter suporte para Aspose.GIS?
 Você pode encontrar uma comunidade útil no[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para quaisquer dúvidas ou problemas que você possa encontrar.
### Existe um teste gratuito disponível?
 Sim, você pode explorar os recursos do Aspose.GIS obtendo uma avaliação gratuita[aqui](https://releases.aspose.com/).
### Como posso adquirir uma licença para Aspose.GIS?
 Para adquirir uma licença, visite o[página de compra](https://purchase.aspose.com/buy).