---
date: 2026-01-13
description: Aprenda como recortar recursos de camada com Aspose.GIS para .NET, incluindo
  como recortar raster com polígono, extrair o tamanho da célula raster e recuperar
  a extensão do raster. Baixe sua avaliação gratuita agora.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Como recortar recursos de camada com Aspose.GIS para .NET
url: /pt/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Recortar Recursos de Camada

## Introdução
Neste tutorial você aprenderá **como recortar recursos de camada** usando Aspose.GIS para .NET, uma abordagem poderosa que permite **recortar raster com polígono**, **extrair o tamanho da célula do raster** e **recuperar a extensão do raster** para análises geoespaciais precisas. Seja preparando dados para um mapa web, aparando imagens de satélite ou isolando uma região de interesse, este guia passo a passo mostra exatamente como concluir a tarefa.

## Respostas Rápidas
- **O que significa “recortar camada”?** Ele corta uma camada raster ou vetorial aos limites de uma geometria fornecida.  
- **Qual geometria é usada neste exemplo?** Um polígono definido no formato WKT.  
- **Posso extrair o tamanho da célula após o recorte?** Sim – a propriedade `CellSize` fornece essa informação.  
- **Preciso de licença para executar o código?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “como recortar camada”?
Recortar uma camada significa restringir o conjunto de dados a uma área geográfica específica, descartando tudo que está fora da forma definida. Isso reduz o tamanho do arquivo, acelera o processamento e foca a análise na região de interesse.

## Por que usar Aspose.GIS para recortar?
- **Manipulação de raster de alto desempenho** – ideal para arquivos GeoTiff grandes.  
- **API simples** – chamada `Crop` de uma linha com qualquer geometria.  
- **Compatibilidade total com .NET** – funciona em aplicativos desktop, servidor e nuvem.  
- **Manuseio preciso de referência espacial** – preserva automaticamente as informações de CRS.

## Pré‑requisitos
Antes de mergulhar na magia da manipulação geoespacial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

- Biblioteca Aspose.GIS para .NET: Garanta que a biblioteca Aspose.GIS esteja instalada no seu projeto .NET. Você pode baixá‑la [aqui](https://releases.aspose.com/gis/net/).  
- Diretório de Documentos: Configure um diretório para armazenar seus documentos. Substitua `"Your Document Directory"` no código fornecido pelo caminho real do seu diretório de documentos.

Agora, vamos ao guia passo a passo.

## Importar Namespaces
Comece importando os namespaces necessários para aproveitar todo o poder do Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Etapa 1: Abrir e Recortar a Camada (recortar raster com polígono)
Inicie abrindo a camada GeoTiff e recortando‑a com base em um polígono definido. Isso garante que seus dados geoespaciais sejam refinados para uma área de interesse específica.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Etapa 2: Recuperar Informações do Raster (extrair tamanho da célula do raster & recuperar extensão do raster)
Depois que a camada for recortada, extraia informações essenciais sobre os dados raster, como tamanho da célula, sistema de referência espacial e limites.

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
|----------|---------|
| **Orientação incorreta do polígono** | Certifique‑se de que o polígono WKT siga a regra da mão direita (sentido anti‑horário para anéis externos). |
| **Referência espacial ausente** | Verifique se o GeoTiff de origem contém um CRS; caso contrário, defina um manualmente antes de recortar. |
| **Desempenho lento em rasters muito grandes** | Use `layer.Crop` em uma cópia reduzida ou processe o raster em blocos (tiles). |

## Perguntas Frequentes
### Q: Existe uma licença temporária disponível para Aspose.GIS para .NET?
A: Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q: Onde posso encontrar a documentação completa para Aspose.GIS para .NET?
A: A documentação está disponível [aqui](https://reference.aspose.com/gis/net/).

### Q: Como posso obter suporte ou conectar‑me com a comunidade do Aspose.GIS para .NET?
A: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte e engajamento da comunidade.

### Q: Posso baixar uma versão de avaliação gratuita do Aspose.GIS para .NET?
A: Sim, você pode baixar a avaliação gratuita [aqui](https://releases.aspose.com/).

### Q: Onde posso comprar o Aspose.GIS para .NET?
A: Você pode adquirir a biblioteca [aqui](https://purchase.aspose.com/buy).

### Q: Posso recortar múltiplas camadas em uma única execução?
A: Sim—faça um loop sobre cada camada e aplique a mesma chamada `Crop` com a geometria desejada.

### Q: A API suporta outros formatos raster (por exemplo, JPEG2000)?
A: Aspose.GIS suporta todos os formatos que os drivers GDAL subjacentes expõem, incluindo JPEG2000, PNG e mais.

## Conclusão
Seguindo este guia, você agora sabe **como recortar recursos de camada** de forma eficiente com Aspose.GIS para .NET. Você pode facilmente **recortar raster com polígono**, **extrair o tamanho da célula do raster** e **recuperar a extensão do raster** para atender a qualquer necessidade de projeto. Explore APIs adicionais para reprojeção, estilização de raster e análise vetorial para desbloquear todo o potencial dos seus fluxos de trabalho geoespaciais.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-13  
**Testado com:** Aspose.GIS 24.10 para .NET  
**Autor:** Aspose  

---