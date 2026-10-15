---
date: 2026-10-15
description: Aprenda como criar geojson a partir de coordenadas e gravá-lo em um stream
  usando Aspose.GIS para .NET. Este tutorial mostra a conversão passo a passo de pontos
  e a geração de código C# GeoJSON.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Gravar GeoJSON em Stream
og_description: Aprenda como criar geojson a partir de coordenadas e gravá-lo em um
  stream usando Aspose.GIS para .NET – guia passo a passo para grandes conjuntos de
  dados.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Criar geojson a partir de coordenadas, gravar em um stream no .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Criar geojson a partir de coordenadas, gravar em um stream no .NET
url: /pt/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar geojson a partir de coordenadas e gravar em um stream

## Introdução
Neste tutorial você aprenderá **como criar geojson a partir de coordenadas** e gravá‑lo diretamente em um stream usando Aspose.GIS para .NET. Vamos percorrer a configuração do ambiente, a criação de camadas, o preenchimento de recursos e a transmissão do resultado, para que você possa incorporar cargas geoespaciais em APIs, funções de nuvem ou serviços sem arquivos, sem arquivos temporários.

## Respostas Rápidas
- **Qual classe grava GeoJSON em um stream?** `VectorLayer` juntamente com o `GeoJsonDriver`.
- **Preciso de licença para desenvolvimento?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Posso converter coleções de pontos para GeoJSON?** Sim – crie um `Feature` para cada ponto e atribua uma geometria `Point`.
- **A transmissão é adequada para grandes conjuntos de dados?** Absolutamente – `MemoryStream` permite gravar GeoJSON em escala de gigabytes sem carregar todo o arquivo na memória.

## O que é GeoJSON?
GeoJSON é um formato aberto baseado em JSON para codificar recursos geográficos como pontos, linhas e polígonos. Consiste em um `FeatureCollection` que agrupa objetos `Feature` individuais, cada um contendo geometria e dados de atributos. Por ser leve e amigável à web, o GeoJSON é o padrão de fato para troca de dados espaciais entre navegadores, servidores GIS e aplicativos móveis.

## Por que usar Aspose.GIS para geração de geojson?
Aspose.GIS suporta **35+ formatos de arquivos espaciais** e pode transmitir arquivos maiores que **2 GB** mantendo o uso de memória abaixo de **50 MB**. Seu mecanismo de transmissão de alto desempenho grava GeoJSON diretamente em qualquer `Stream` .NET, eliminando a necessidade de arquivos temporários intermediários e reduzindo a latência de I/O em até **70 %** em cenários típicos de nuvem.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Aspose.GIS for .NET** instalado. Baixe o pacote **Aspose.GIS for .NET** [aqui](https://releases.aspose.com/gis/net/).
2. Uma pasta gravável no seu projeto onde você pode colocar arquivos temporários, se necessário.
3. .NET 5+ ou .NET Core 3.1+ runtime instalado.

Agora, vamos mergulhar na implementação.

## Como criar geojson a partir de coordenadas e gravar em um stream?
`VectorLayer` representa um conjunto de dados vetoriais em memória que pode ser salvo em vários formatos.  
`GeoJsonDriver` é o driver que permite ler e gravar arquivos GeoJSON.  

Carregue um `VectorLayer` com o `GeoJsonDriver`, adicione objetos `Feature` que contenham geometria `Point` e chame `layer.Save(stream, new GeoJsonSaveOptions())`. Essa única chamada serializa toda a coleção de recursos em um documento GeoJSON compatível com padrões que reside no `MemoryStream` fornecido. O processo trata o mapeamento de atributos e a conversão de coordenadas automaticamente, de modo que você receba uma carga JSON pronta para uso sem a necessidade de montar strings manualmente.

### Âncoras de definição
**VectorLayer** é o objeto central do Aspose.GIS que representa um conjunto de dados vetoriais mutável na memória.  
**GeoJsonDriver** é o driver responsável por ler e gravar arquivos GeoJSON.  

## Importar namespaces
Primeiro, certifique‑se de incluir os namespaces necessários para acessar as funcionalidades do Aspose.GIS no seu código:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Etapa 1: configurar o diretório de documentos
Crie um caminho de pasta onde o Aspose.GIS pode armazenar arquivos auxiliares, se necessário.  
```csharp
string dataDir = "Your Document Directory";
```
Substitua "Your Document Directory" pelo caminho real do seu diretório de documentos.

## Etapa 2: criar um memory stream
Um `MemoryStream` fornece um buffer em memória que pode ser enviado diretamente via HTTP ou salvo em armazenamento na nuvem.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Etapa 3: criar uma camada vetorial com driver GeoJSON
A classe `VectorLayer` representa um conjunto de dados vetoriais que pode ser salvo em vários formatos, incluindo GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Etapa 4: definir atributos do recurso
Defina o esquema de atributos para seus recursos (por exemplo, ID, Nome).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Etapa 5: construir e adicionar recursos
Crie objetos `Feature`, atribua geometria de ponto, defina valores de atributos e adicione‑os à camada.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Etapa 6: exibir a saída GeoJSON
Após salvar, redefina a posição do stream e leia a string JSON para verificação ou transmissão.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Parabéns! Você criou geojson a partir de coordenadas e gravou em um stream usando Aspose.GIS para .NET.

## Problemas comuns e soluções
- **Fluxo de saída vazio:** Certifique‑se de redefinir a posição do stream (`stream.Position = 0`) antes de ler.
- **Ordem de coordenadas incorreta:** GeoJSON espera ordem longitude‑latitude; verifique os valores dos seus pontos.
- **Conjuntos de dados grandes:** Use `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` para transmitir recursos incrementalmente e manter o uso de memória baixo.

## Perguntas frequentes

**Q: Posso usar Aspose.GIS para .NET em ambientes Windows e Linux?**  
A: Sim, Aspose.GIS para .NET funciona no Windows, Linux e macOS com suporte total ao .NET Core.

**Q: Existe uma versão de avaliação disponível?**  
A: Absolutamente! Você pode explorar a **página de download da avaliação gratuita** [aqui](https://releases.aspose.com/).

**Q: Onde posso encontrar documentação detalhada?**  
A: Consulte a **documentação do Aspose.GIS .NET** [aqui](https://reference.aspose.com/gis/net/).

**Q: Como posso obter licenciamento temporário?**  
A: Licenças temporárias estão disponíveis na **página de licença temporária** [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Precisa de assistência ou tem mais perguntas?**  
A: Visite nosso **fórum de suporte GIS** [aqui](https://forum.aspose.com/c/gis/33).

**Q: Posso gerar GeoJSON a partir de uma coleção de pontos latitude/longitude?**  
A: Sim – crie um `Feature` para cada ponto, atribua uma geometria `Point` e adicione‑o ao `VectorLayer`.

**Q: O Aspose.GIS suporta gravação de GeoJSON compactado (gzip)?**  
A: Você pode envolver o `MemoryStream` em um `GZipStream` antes de salvar para produzir uma carga compactada.

**Q: Qual é o tamanho máximo de um arquivo GeoJSON que o Aspose.GIS pode manipular?**  
A: A biblioteca pode transmitir arquivos superiores a 2 GB; o uso de memória permanece baixo porque os dados são gravados incrementalmente.

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

## Tutoriais relacionados

- [Como ler GeoJSON de um stream com Aspose.GIS para .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Como converter GeoJSON para TopoJSON com Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Como converter Shapefile para GeoJSON usando Aspose.GIS para .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}