---
date: 2026-05-21
description: Aprenda como escrever GeoJSON em um fluxo usando Aspose.GIS para .NET.
  Este tutorial geojson .net mostra a conversão passo a passo de pontos e a geração
  de código GeoJSON em C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Escrever GeoJSON em fluxo
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como escrever GeoJSON em fluxo com Aspose.GIS para .NET
url: /pt/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escrever GeoJSON em Stream

## Introdução
Neste tutorial você aprenderá **como escrever GeoJSON em um stream** em uma aplicação .NET usando Aspose.GIS. Vamos percorrer cada etapa, desde a configuração do ambiente até a geração de um documento GeoJSON válido, para que você possa integrar dados geoespaciais perfeitamente em seus serviços.

## Respostas Rápidas
- **Qual é a classe principal para saída GeoJSON?** `VectorLayer` com o `GeoJsonDriver`.
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Posso converter coleções de pontos para GeoJSON?** Sim – use a classe `Feature` e defina a geometria do ponto.
- **O streaming é suportado para grandes conjuntos de dados?** Absolutamente; `MemoryStream` permite escrever sem arquivos intermediários.

## O que é GeoJSON?
GeoJSON é um formato padrão aberto para codificar uma variedade de estruturas de dados geográficos usando JSON. Ele define objetos como FeatureCollection, Feature e tipos de geometria (Point, LineString, Polygon). Essa representação leve e amigável à web permite a troca e visualização fáceis de dados espaciais em diversas plataformas e linguagens de programação.

## Por que usar Aspose.GIS para geração de GeoJSON?
Aspose.GIS suporta mais de 30 formatos de arquivos espaciais e pode processar arquivos maiores que 2 GB sem carregar todo o documento na memória. Seu mecanismo de streaming de alto desempenho grava GeoJSON diretamente em streams, reduzindo a sobrecarga de I/O. Isso o torna ideal para cargas de trabalho geoespaciais em escala empresarial, serviços em nuvem e aplicações em tempo real.

## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de que você tem os seguintes pré-requisitos em vigor:
1. Aspose.GIS for .NET Library: Garanta que a biblioteca Aspose.GIS for .NET esteja instalada. Você pode baixá‑la [aqui](https://releases.aspose.com/gis/net/).
2. Document Directory: Tenha um diretório de documentos configurado em seu projeto e anote seu caminho.

Agora, vamos começar o tutorial!

## Como escrever GeoJSON em um stream?
`VectorLayer` representa um conjunto de dados vetoriais que pode ser salvo em vários formatos, incluindo GeoJSON.  
`GeoJsonDriver` é o driver usado pelo Aspose.GIS para ler e gravar arquivos GeoJSON.  
`layer.Save` grava o conteúdo da camada no stream fornecido usando as opções de salvamento especificadas.  

Carregue um `VectorLayer` com o `GeoJsonDriver`, adicione recursos que contenham geometria de ponto e, em seguida, chame `layer.Save(stream, new GeoJsonSaveOptions())`. Isso grava um documento GeoJSON completo e compatível com padrões diretamente no `MemoryStream` fornecido em apenas algumas linhas de código. O método serializa a coleção de recursos, manipulando dados de atributos e conversão de geometria automaticamente, de modo que você obtenha um payload JSON pronto para uso sem manipulação manual de strings.

## Importar Namespaces
Primeiro de tudo, certifique‑se de incluir os namespaces necessários para acessar as funcionalidades do Aspose.GIS em seu código:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Etapa 1: Configurar o Diretório de Documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua "Your Document Directory" pelo caminho real do seu diretório de documentos.

## Etapa 2: Criar um Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Etapa 3: Criar um Vector Layer com o Driver GeoJSON
A classe `VectorLayer` representa um conjunto de dados vetoriais que pode ser salvo em vários formatos, incluindo GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Etapa 4: Definir Atributos da Feature
Defina o esquema de atributos para suas features (por exemplo, ID, Nome).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Etapa 5: Construir e Adicionar Features
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

## Etapa 6: Exibir a Saída GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Parabéns! Você escreveu GeoJSON em um stream com sucesso usando Aspose.GIS para .NET.

## Problemas Comuns e Soluções
- **Stream de saída vazio:** Certifique‑se de redefinir a posição do stream (`stream.Position = 0`) antes de ler.
- **Ordem de coordenadas incorreta:** GeoJSON espera a ordem longitude‑latitude; verifique os valores dos seus pontos.
- **Grandes conjuntos de dados:** Use `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` para transmitir recursos incrementalmente.

## Perguntas Frequentes
### Posso usar Aspose.GIS para .NET em ambientes Windows e Linux?
Sim, Aspose.GIS para .NET é compatível com sistemas Windows e Linux.

### Existe um teste gratuito disponível?
Absolutamente! Você pode explorar um teste gratuito [aqui](https://releases.aspose.com/).

### Onde posso encontrar documentação detalhada?
Confira a documentação [aqui](https://reference.aspose.com/gis/net/).

### Como posso obter licenciamento temporário?
Licenças temporárias estão disponíveis [aqui](https://purchase.aspose.com/temporary-license/).

### Precisa de assistência ou tem mais perguntas?
Visite nosso fórum de suporte [aqui](https://forum.aspose.com/c/gis/33).

**Q: Posso gerar GeoJSON a partir de uma coleção de pontos latitude/longitude?**  
A: Sim – crie uma `Feature` para cada ponto, atribua uma geometria `Point` e adicione‑a ao `VectorLayer`.

**Q: O Aspose.GIS suporta gravação de GeoJSON compactado (gzip)?**  
A: Você pode envolver o `MemoryStream` em um `GZipStream` antes de salvar para produzir um payload compactado.

**Q: Qual é o tamanho máximo de um arquivo GeoJSON que o Aspose.GIS pode manipular?**  
A: A biblioteca pode transmitir arquivos superiores a 2 GB; o uso de memória permanece baixo porque os dados são gravados incrementalmente.

---

**Last Updated:** 2026-05-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Ler GeoJSON de um Stream com Aspose.GIS para .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Como Converter GeoJSON para TopoJSON com Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Como Converter Shapefile para GeoJSON usando Aspose.GIS para .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}