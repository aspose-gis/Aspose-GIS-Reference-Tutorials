---
date: 2026-07-05
description: Aprenda como crop layer features com Aspose.GIS for .NET, incluindo como
  crop raster com polygon, extrair raster cell size e recuperar raster extent. Baixe
  sua versão de avaliação gratuita agora.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Como Crop Layer Features
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como Crop Layer Features com Aspose.GIS for .NET
url: /pt/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Recortar Recursos de Camada

## Introdução
Neste tutorial você aprenderá **como recortar recursos de camada** usando Aspose.GIS para .NET, uma biblioteca poderosa que permite **recortar raster com polígono**, **extrair o tamanho da célula raster**, e **recuperar a extensão do raster** para análises geoespaciais precisas. Seja preparando dados para um mapa web, aparando imagens de satélite ou isolando uma região de interesse, este guia passo a passo mostra exatamente como concluir a tarefa de forma rápida e confiável.

## Respostas Rápidas
- **O que significa “recortar camada”?** Ele corta um raster ou camada vetorial aos limites de uma geometria fornecida, descartando tudo que está fora.  
- **Qual geometria é usada neste exemplo?** Um polígono definido em formato WKT (Well‑Known Text).  
- **Posso extrair o tamanho da célula após o recorte?** Sim – a propriedade `CellSize` devolve a largura e altura de uma célula raster.  
- **Preciso de licença para executar o código?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “como recortar camada”?
**Recortar uma camada significa restringir o conjunto de dados a uma área geográfica específica, descartando tudo que está fora.** Esta operação reduz o tamanho do arquivo, acelera o processamento subsequente e foca a análise na região de interesse. Ao limitar os dados à área desejada, você também simplifica fluxos de trabalho posteriores, como estilização, análise e publicação, preservando o sistema de referência de coordenadas original e os metadados.

## Por que usar Aspose.GIS para recortar?
**Aspose.GIS processa arquivos raster de até 2 GB sem carregar a imagem inteira na memória e suporta mais de 30 formatos raster, incluindo GeoTIFF, JPEG2000 e PNG.** A biblioteca oferece uma chamada única `Crop`, tratamento automático de CRS e desempenho multithread que pode recortar um GeoTIFF de 500 MB em menos de um segundo em um servidor típico.

## Pré-requisitos
Antes de mergulhar na magia da manipulação geoespacial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

- Biblioteca Aspose.GIS para .NET: Garanta que a biblioteca Aspose.GIS esteja instalada em seu projeto .NET. Você pode baixá‑la [aqui](https://releases.aspose.com/gis/net/).  
- Diretório de Documentos: Configure um diretório para armazenar seus documentos. Substitua `"Your Document Directory"` no código fornecido pelo caminho real do seu diretório de documentos.

Agora, vamos ao guia passo a passo.

## Importar Namespaces
O namespace `Aspose.Gis` contém todos os tipos principais para manipulação de raster e vetor. Importe‑o para ter acesso à `Layer`, `Geometry` e classes relacionadas.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Como recortar uma camada com um polígono?
`Crop` é um método da classe `Layer` que extrai um subconjunto raster definido por uma geometria.  
Carregue o raster de origem, defina uma geometria poligonal e chame o método `Crop` – toda a operação é executada em uma única linha de código. O método devolve um novo raster que contém apenas os pixels dentro do polígono, preservando automaticamente a referência espacial original.

## Etapa 1: Abrir e Recortar a Camada (recortar raster com polígono)
`Layer` representa um conjunto de dados raster que pode ser aberto, consultado e editado.  
A classe `Layer` representa um conjunto de dados raster que pode ser aberto, consultado e editado. Abrir um GeoTIFF e recortá‑lo com um polígono isola a área de interesse em apenas algumas instruções.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Etapa 2: Recuperar Informações do Raster (extrair tamanho da célula raster & recuperar extensão do raster)
`CellSize` fornece a largura e altura de cada célula raster em unidades de coordenada.  
`Extent` devolve a caixa delimitadora geográfica do raster.  
A propriedade `CellSize` fornece a largura e altura de cada célula raster em unidades de coordenada, enquanto a propriedade `Extent` devolve a caixa delimitadora geográfica do raster recortado. Ambas as informações são essenciais para cálculos posteriores, como medição de área ou reprojeção.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Etapa 3: Exibir Informações
Imprima as informações extraídas para entender o impacto do processo de recorte nos seus dados geoespaciais.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Repita estas etapas conforme necessário para refinar e adaptar seus dados geoespaciais às exigências específicas do projeto.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| **Orientação incorreta do polígono** | Certifique‑se de que o polígono WKT segue a regra da mão direita (sentido anti‑horário para anéis externos). |
| **Referência espacial ausente** | Verifique se o GeoTiff de origem contém um CRS; caso contrário, defina‑a manualmente antes do recorte. |
| **Desempenho lento em rasters muito grandes** | Use `layer.Crop` em uma cópia reduzida ou processe o raster em blocos (tiles). |

## Perguntas Frequentes
**Q: Existe uma licença temporária disponível para Aspose.GIS para .NET?**  
A: Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso encontrar documentação completa para Aspose.GIS para .NET?**  
A: A documentação está disponível [aqui](https://reference.aspose.com/gis/net/).

**Q: Como posso obter suporte ou conectar‑me com a comunidade do Aspose.GIS para .NET?**  
A: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte e interação com a comunidade.

**Q: Posso baixar uma versão de avaliação gratuita do Aspose.GIS para .NET?**  
A: Sim, você pode baixar a avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso comprar o Aspose.GIS para .NET?**  
A: Você pode adquirir a biblioteca [aqui](https://purchase.aspose.com/buy).

**Q: Posso recortar múltiplas camadas em uma única execução?**  
A: Sim—faça um loop sobre cada camada e aplique a mesma chamada `Crop` com a geometria desejada.

**Q: A API suporta outros formatos raster (por exemplo, JPEG2000)?**  
A: Aspose.GIS suporta todos os formatos expostos pelos drivers GDAL subjacentes, incluindo JPEG2000, PNG e muitos outros.

## Conclusão
Seguindo este guia, você agora sabe **como recortar recursos de camada** de forma eficiente com Aspose.GIS para .NET. É fácil **recortar raster com polígono**, **extrair o tamanho da célula raster** e **recuperar a extensão do raster** para atender a qualquer necessidade de projeto. Explore APIs adicionais para reprojeção, estilização de raster e análise vetorial para desbloquear todo o potencial dos seus fluxos de trabalho geoespaciais.

---

**Última atualização:** 2026-07-05  
**Testado com:** Aspose.GIS 24.10 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [How to Create Polygon Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}