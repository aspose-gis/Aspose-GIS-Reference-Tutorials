---
date: 2026-10-05
description: Aprenda como ler geojson de um stream usando Aspose.GIS for .NET. Este
  guia passo a passo mostra como carregar o stream de geojson, analisá‑lo e extrair
  propriedades em C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: Ler GeoJSON de Stream
og_description: Aprenda como ler geojson de um stream usando Aspose.GIS for .NET,
  incluindo análise, abertura de camada geojson e extração de propriedades em C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Como ler geojson de um stream com Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Como ler geojson de um stream com Aspose.GIS for .NET
url: /pt/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler geojson a partir de um stream com Aspose.GIS para .NET

## Introdução
Se você está se perguntando **como ler geojson** em uma aplicação .NET, você chegou ao lugar certo. Neste tutorial, percorreremos um **exemplo completo de C# GeoJSON** que mostra como converter uma string GeoJSON, **carregar stream geojson** em um memory stream, abrir uma camada GeoJSON e extrair propriedades GeoJSON usando Aspose.GIS. Ao final, você terá um padrão reutilizável que pode ser inserido em qualquer projeto que precise trabalhar com dados geoespaciais.

## Respostas rápidas
- **Qual biblioteca devo usar?** Aspose.GIS para .NET – lida com mais de 30 formatos GIS prontamente.  
- **Posso ler GeoJSON diretamente de um stream?** Sim – chame `VectorLayer.Open` com `AbstractPath.FromStream`.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Extrair propriedades é simples?** Absolutamente – use `GetValue<T>(columnName)` em um feature.

**VectorLayer.Open** abre uma camada GIS a partir de uma fonte de dados, como um arquivo ou stream. **AbstractPath.FromStream** cria um objeto de caminho abstrato que representa o stream fornecido para o driver GIS. **GetValue<T>(columnName)** lê o valor do atributo especificado de um feature e o retorna como tipo T.

## O que é como ler geojson?
Ler geojson é o processo de converter uma string ou stream formatada em GeoJSON em objetos de recursos geográficos em memória. Esse formato codifica pontos, linhas e polígonos usando JSON, facilitando a troca de dados espaciais entre serviços web, bancos de dados e aplicações cliente. Uma vez analisado, você pode consultar, editar ou renderizar os recursos com qualquer biblioteca .NET compatível com GIS, como Aspose.GIS.

## Por que usar Aspose.GIS para abrir camada geojson?
Aspose.GIS permite abrir uma camada GeoJSON diretamente de um stream, eliminando a necessidade de arquivos temporários e reduzindo a sobrecarga de I/O. A biblioteca suporta mais de 30 formatos GIS e pode processar arquivos de até 2 GB sem carregar todo o documento na memória, o que é ideal para conjuntos de dados grandes. Também normaliza sistemas de referência de coordenadas automaticamente, permitindo que você se concentre na lógica de negócios em vez de parsing de baixo nível.

## Quando você carregaria um stream geojson?
Você carregaria um stream GeoJSON quando receber dados espaciais de uma API, precisar manipular arquivos enviados por usuários sem persistí‑los em disco, ou gerar GeoJSON dinamicamente a partir de uma consulta ao banco de dados. O streaming evita gravações desnecessárias em disco, melhora o desempenho em cenários de alto volume e mantém sua aplicação sem estado, o que é especialmente valioso em microsserviços nativos da nuvem.

## Pré-requisitos
Antes de mergulharmos, certifique‑se de que você tem:

1. **Conhecimento básico de C#** – você deve estar confortável com a sintaxe .NET e o IDE Visual Studio.  
2. **Aspose.GIS instalado** – faça o download da biblioteca na [página de download do Aspose.GIS .NET](https://releases.aspose.com/gis/net/).  
3. **Um ambiente de desenvolvimento** – Visual Studio, Visual Studio Code ou JetBrains Rider funcionarão bem.  

## Importar namespaces
O namespace `Aspose.GIS` fornece as classes principais de GIS. `System.IO` fornece `MemoryStream`, e `System.Text` oferece utilitários de codificação UTF‑8. Importar esses namespaces torna o código subsequente conciso e legível.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Etapa 1: converter string geojson – um exemplo C# GeoJSON
Primeiro criamos uma string JSON que representa um `FeatureCollection` simples. Esta é a parte **converter string geojson** do fluxo de trabalho.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Etapa 2: carregar stream geojson e extrair propriedades geojson
Agora alimentamos a string em um `MemoryStream`, abrimos como uma camada GIS e demonstramos como ler valores de atributos (a etapa **extrair propriedades geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Dica profissional:** `VectorLayer.Open` detecta automaticamente o formato GeoJSON quando você passa `Drivers.GeoJson`. Você também pode abrir arquivos diretamente fornecendo um caminho de arquivo em vez de um stream.

## Problemas comuns e soluções
| Problema | Solução |
|----------|----------|
| **Invalid JSON format** | Verifique se a string GeoJSON está bem‑formada; use um validador JSON. |
| **Encoding problems** | Certifique‑se de que o stream usa UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | Verifique se o nome da propriedade está escrito corretamente (`"name"` no exemplo). |
| **License exception** | Use uma licença de teste para testes; aplique uma licença permanente para produção. |

## Perguntas frequentes
### O Aspose.GIS é compatível com outros formatos GIS?
Sim, o Aspose.GIS suporta GeoJSON, Shapefile, KML, GML e mais de 20 formatos adicionais, permitindo que você troque entre fontes de dados sem alterar o código.

### Posso experimentar o Aspose.GIS antes de comprar?
Você pode baixar uma versão de teste gratuita do Aspose.GIS na [página de download da versão de teste gratuita do Aspose.GIS](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.GIS?
Você pode encontrar a documentação do Aspose.GIS na [referência da API .NET do Aspose.GIS](https://reference.aspose.com/gis/net/).

### Como posso obter suporte para o Aspose.GIS?
Você pode obter suporte para o Aspose.GIS no fórum Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Preciso de uma licença temporária para usar o Aspose.GIS?
Você pode obter uma licença temporária para o Aspose.GIS na [página de solicitação de licença temporária](https://purchase.aspose.com/temporary-license/).

## Conclusão
Neste guia, abordamos **como ler geojson** a partir de um memory stream usando Aspose.GIS para .NET, demonstramos um fluxo de trabalho **C# read geojson**, e mostramos como **extrair propriedades geojson** da camada aberta. Com essas etapas, você pode integrar perfeitamente o tratamento de dados geoespaciais em qualquer aplicação .NET.

---

**Última atualização:** 2026-10-05  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Como escrever GeoJSON para stream com Aspose.GIS para .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Como converter GeoJSON para GDB usando Aspose.GIS para .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Converter Shapefile para GeoJSON com Aspose.GIS para .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}