---
date: 2026-01-15
description: Explore Aspose.GIS para .NET para criar camada vetorial com um sistema
  de referência espacial. Aprenda como definir SRS, criar camada e gerenciar dados
  GIS. Baixe agora!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Criar camada vetorial com SRS
url: /pt/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial com SRS

## Introdução
Aspose.GIS for .NET é uma biblioteca poderosa que permite aos desenvolvedores **create vector layer** objetos e trabalhar com dados de sistemas de informação geográfica (GIS) de forma fluida em aplicações .NET. Neste tutorial, vamos percorrer como criar uma camada vetorial com um sistema de referência espacial (SRS), por que você pode querer definir a referência espacial e quais benefícios isso traz para projetos do mundo real. Ao final deste guia, você será capaz de integrar recursos GIS em suas soluções .NET com confiança.

## Respostas Rápidas
- **Qual é o objetivo principal deste tutorial?** Mostrar como criar vector layer com um SRS especificado usando Aspose.GIS for .NET.  
- **Qual projeção é usada no exemplo?** World Mercator (EPSG:3395).  
- **Preciso de uma licença para executar o código?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso usar a mesma abordagem com outros formatos GIS?** Sim, o mesmo tratamento de SRS se aplica a Shapefile, GeoJSON, KML, etc.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é uma camada vetorial e por que definir sua referência espacial?
Uma **vector layer** armazena recursos geométricos (pontos, linhas, polígonos) juntamente com dados de atributos. Atribuir uma **spatial reference** (SRS) informa ao software GIS como interpretar essas coordenadas na superfície da Terra. Definir o SRS correto garante medições precisas, sobreposição adequada com outras camadas e visualizações de mapa confiáveis.

## Pré-requisitos
- Conhecimento básico de C# e desenvolvimento .NET.  
- Biblioteca Aspose.GIS for .NET instalada. Você pode baixá‑la **[aqui](https://releases.aspose.com/gis/net/)**.  
- Um ambiente de desenvolvimento (Visual Studio, VS Code ou qualquer IDE C#).  

## Importar Namespaces
Certifique‑se de que os namespaces necessários estejam importados no topo do seu arquivo C#:

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

## Como definir a referência espacial (SRS) – Etapa 1
Vamos criar um **projected spatial reference system** usando a projeção World Mercator como exemplo. Isso demonstra **how to set srs** para uma camada.

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

## Como criar camada – Etapa 2
Agora vamos **create a vector layer** (um Shapefile) e adicionar recursos que usam o SRS que acabamos de definir. Esta parte responde **how to create layer** com Aspose.GIS.

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro tip:** Sempre verifique se o `SpatialReferenceSystem` da geometria corresponde ao SRS da camada antes de adicioná‑la. Valores de SRS incompatíveis geram um `GisException`, como mostrado acima.

## Verificar Sistema de Referência Espacial – Etapa 3
Finalmente, abra a camada e confirme que o SRS foi aplicado corretamente.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Se a chamada `IsEquivalent` retornar `true`, você criou com sucesso **create vector layer** com a referência espacial desejada.

## Problemas Comuns & Soluções
| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| `GisException` ao adicionar um recurso | A geometria usa um SRS diferente da camada | Defina `feature.Geometry.SpatialReferenceSystem` para o SRS da camada antes de adicionar |
| A camada aparece vazia no software GIS | O shapefile foi criado sem um arquivo `.prj` adequado | Garanta que o objeto `projectedSrs` seja passado ao criar a camada |
| Valores de coordenadas inesperados | Parâmetros de projeção incorretos (ex.: meridiano central) | Verifique novamente os parâmetros passados para `AddProjectionParameter` |

## Perguntas Frequentes
### O Aspose.GIS é compatível com todos os formatos de arquivo GIS?
Aspose.GIS suporta vários formatos GIS, incluindo Shapefile, GeoJSON, KML e mais. Consulte a **[documentação](https://reference.aspose.com/gis/net/)** para a lista completa.

### Posso usar Aspose.GIS em uma aplicação web?
Absolutamente! Aspose.GIS for .NET é versátil e pode ser usado em aplicações web, aplicações desktop e até aplicativos móveis.

### Onde posso obter suporte para Aspose.GIS?
Você pode encontrar uma comunidade útil no **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** para quaisquer dúvidas ou problemas que encontrar.

### Existe uma versão de teste gratuita disponível?
Sim, você pode explorar os recursos do Aspose.GIS obtendo um teste gratuito **[aqui](https://releases.aspose.com/)**.

### Como posso comprar uma licença para Aspose.GIS?
Para comprar uma licença, visite a **[página de compra](https://purchase.aspose.com/buy)**.

## Perguntas Frequentes (Adicionais)

**Q: O que acontece se eu tentar adicionar uma geometria com um SRS diferente?**  
A: Aspose.GIS lança um `GisException`. Você deve reprojetar a geometria ou garantir que ela compartilhe o SRS da camada.

**Q: Posso mudar o SRS de uma camada existente?**  
A: Sim, você pode criar uma nova camada com o SRS desejado e copiar os recursos, reprojetando‑os conforme necessário.

**Q: É possível trabalhar com coordenadas 3D?**  
A: Aspose.GIS suporta coordenadas Z; basta usar construtores de geometria que aceitam um valor Z.

**Q: A biblioteca lida com transformações de datum automaticamente?**  
A: Ao reprojetar geometrias usando `Geometry.Transform`, Aspose.GIS realiza a mudança de datum necessária.

**Q: Quais versões do .NET são oficialmente testadas?**  
A: A biblioteca é testada com .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7.

## Conclusão
Agora você aprendeu como **create vector layer** com um sistema de referência espacial personalizado usando Aspose.GIS for .NET. Ao definir o SRS correto, manipular a geometria de forma consistente e verificar os metadados da camada, você pode construir aplicações robustas habilitadas para GIS que interoperam com qualquer software GIS padrão.

---

**Última atualização:** 2026-01-15  
**Testado com:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}