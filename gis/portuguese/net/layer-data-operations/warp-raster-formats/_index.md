---
date: 2026-10-10
description: Aprenda como obter o tamanho da célula raster e alterar a resolução raster
  ao transformar formatos raster usando Aspose.GIS para .NET – um guia passo a passo
  para visualização de dados espaciais.
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: Transformar formatos raster
og_description: Obtenha o tamanho da célula raster após transformar rasters usando
  Aspose.GIS para .NET. Este tutorial mostra como alterar a resolução raster, converter
  arquivos GeoTIFF e extrair metadados raster detalhados em algumas etapas simples.
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: Obter tamanho da célula raster e transformar rasters com Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: Obter tamanho da célula raster – transformar formatos raster
url: /pt/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obter tamanho da célula raster – warp formatos de raster

## Introdução
Neste tutorial você **obterá o tamanho da célula raster** após executar uma operação de warp e descobrirá como **alterar a resolução raster** para qualquer GeoTIFF usando Aspose.GIS para .NET. Seja preparando dados para um serviço de mapa web, alinhando camadas para análise espacial ou simplesmente precisando verificar se uma reprojeção manteve o detalhe pretendido, estas etapas lhe darão controle total sobre a geometria raster e seus metadados. Vamos percorrer o processo, desde o carregamento do raster até a extração do tamanho da célula e outras propriedades chave.

## Respostas rápidas
- **Qual é o objetivo principal?** Obter o tamanho da célula raster após executar uma operação de warp.  
- **Qual biblioteca é usada?** Aspose.GIS para .NET.  
- **Preciso de licença?** Existe uma versão de avaliação gratuita; uma licença é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo o exemplo leva para ser executado?** Menos de um minuto em uma máquina típica.

## Pré-requisitos
Antes de embarcarmos nesta jornada, certifique‑se de que você tem os seguintes pré‑requisitos:
- Aspose.GIS para .NET: Se ainda não o fez, baixe e instale a biblioteca Aspose.GIS. Você pode encontrar a versão mais recente [aqui](https://releases.aspose.com/gis/net/).
- Seu Diretório de Documentos: Configure um diretório para armazenar seus documentos. Isso será crucial para o gerenciamento de arquivos durante o processo de warp do raster.

Agora que estamos equipados, vamos mergulhar no código.

## Importar namespaces
O namespace `Aspose.GIS` fornece as classes principais para operações raster e vetor. Importe os namespaces necessários para iniciar sua aventura geoespacial.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## Etapa 1: inicializar o caminho
Comece definindo o caminho para o seu diretório de documentos. É aqui que toda a mágica acontecerá:

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: abrir camada raster
A classe `RasterLayer` representa um único conjunto de dados raster carregado na memória. Abrir o GeoTIFF o prepara para transformações subsequentes.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## Etapa 3: warp do raster
O método `Warp` reprojeta e reamostra um raster para um novo sistema de referência de coordenadas e resolução. Ele abstrai matemática complexa, permitindo que você especifique as dimensões alvo e o sistema de referência espacial alvo em uma única chamada.  
`WarpOptions` permite definir parâmetros como largura de saída, altura e sistema de referência espacial alvo para a operação de warp.

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## Etapa 4: extrair informações do raster
Após o warp, você pode consultar o raster resultante para obter metadados essenciais, como tamanho da célula, sistema de referência espacial, limites e contagem de bandas. Essas propriedades permitem validar se a transformação se comportou como esperado.

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## Etapa 5: imprimir detalhes do raster
Vamos exibir os detalhes principais que extraímos, fornecendo a você uma visão rápida da geometria e do conteúdo do raster warpado.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## Etapa 6: explorar bandas raster
`RasterBand` representa uma banda individual (camada) de dados raster, como vermelho, verde, azul ou valores de elevação. Cada banda contém um canal de dados separado que pode ser inspecionado quanto ao tipo de dado, estatísticas e tratamento de NoData.

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## Por que obter o tamanho da célula raster?
Obter o tamanho da célula raster após um warp informa a distância no solo representada por cada pixel. Esta informação é essencial quando você precisa alinhar múltiplas camadas, executar análises baseadas em distância ou confirmar que o warp preservou a resolução espacial requerida.

## Como warp formatos raster de forma eficiente
O método `Warp` abstrai a lógica complexa de reprojeção, permitindo que você se concentre nos parâmetros de entrada, como dimensões alvo e sistema de referência espacial alvo. Isso simplifica a conversão de dados entre sistemas de coordenadas, o reamostramento para uma resolução diferente ou o recorte para uma área específica.

## Benefícios quantificados do Aspose.GIS
Aspose.GIS suporta **mais de 30 formatos raster** e pode processar arquivos de até **2 GB** sem carregar a imagem inteira na memória, proporcionando transformações rápidas e eficientes em termos de memória em hardware de servidor típico.

## Problemas comuns e soluções
- **Valores inesperados de tamanho de célula:** Certifique‑se de que os parâmetros `Height` e `Width` correspondam à resolução de saída desejada.  
- **Referência espacial ausente:** Se `spatialRefSys` retornar null, verifique se o GeoTIFF de origem contém metadados CRS adequados.  
- **Tratamento de NoData:** Use `warped.NoDataValues.IsNull()` para detectar dados ausentes; você também pode atribuir um valor NoData personalizado antes do warp.

## Perguntas frequentes

**Q: O Aspose.GIS é compatível com todos os formatos raster?**  
A: Sim, o Aspose.GIS suporta uma ampla gama de formatos raster, oferecendo flexibilidade no manuseio de diversos conjuntos de dados espaciais.

**Q: Posso realizar warp de raster em imagens não georreferenciadas?**  
A: O Aspose.GIS foi projetado para lidar com dados georreferenciados, garantindo transformações precisas. Certifique‑se de que suas imagens raster possuam informações de referência espacial adequadas.

**Q: Como posso contribuir para a comunidade Aspose.GIS?**  
A: Participe da discussão no [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para compartilhar suas experiências, fazer perguntas e colaborar com outros desenvolvedores.

**Q: Existe uma avaliação gratuita disponível para o Aspose.GIS?**  
A: Sim, você pode explorar as capacidades do Aspose.GIS baixando uma avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Licenças temporárias estão disponíveis para o Aspose.GIS?**  
A: Sim, se precisar de uma licença temporária, você pode obtê‑la [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-10-10  
**Testado com:** Aspose.GIS para .NET (última versão)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Layer Data Operations](/gis/net/layer-data-operations/)
- [How to Add Layer to File GDB Dataset with spatial reference WGS84 using Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}