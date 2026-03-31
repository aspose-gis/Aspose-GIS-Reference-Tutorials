---
date: 2025-12-28
description: Aprenda como ler GeoJSON a partir de um stream usando Aspose.GIS para
  .NET. Este guia de leitura de GeoJSON em C# fornece um exemplo passo a passo para
  integrar dados geoespaciais.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Como ler GeoJSON de um fluxo com Aspose.GIS para .NET
url: /pt/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Ler GeoJSON de um Stream com Aspose.GIS para .NET

## Introdução
Se você está se perguntando **como ler geojson** em uma aplicação .NET, você chegou ao lugar certo. Neste tutorial, percorreremos um **exemplo c# geojson** completo que mostra como converter uma string GeoJSON, abrir uma camada GeoJSON a partir de um memory stream e extrair propriedades GeoJSON usando Aspose.GIS. Ao final, você terá um padrão reutilizável que pode ser inserido em qualquer projeto que precise trabalhar com dados geoespaciais.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.GIS for .NET  
- **Posso ler GeoJSON diretamente de um stream?** Sim – use `VectorLayer.Open` com `AbstractPath.FromStream`.  
- **Preciso de uma licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Extrair propriedades é simples?** Sim – chame `GetValue<T>(columnName)` em um feature.

## O que é “como ler geojson”?
Ler GeoJSON significa analisar o formato baseado em JSON que descreve recursos geográficos (pontos, linhas, polígonos) e tornar esses recursos disponíveis como objetos que você pode consultar, editar ou renderizar em sua aplicação.

## Por que usar Aspose.GIS para **abrir camada geojson**?
Aspose.GIS abstrai os detalhes de análise de baixo nível e fornece uma API consistente para muitos formatos GIS. Ele permite que você **abra camada geo de um stream, manipule arquivos grandes de forma eficiente e acesse atributos de recursos sem precisar escrever analisadores JSON personalizados.

## Pré-requisitos
1. **Conhecimento básico de C#** – você deve estar confortável com a sintaxe .NET e o IDE Visual Studio.  
2. **Aspose.GIS instalado** – faça o download da biblioteca [aqui](https://releases.aspose.com/gis/net/).  
3. **Um ambiente de desenvolvimento** – Visual Studio, Visual Studio Code ou JetBrains Rider funcionarão bem.  

## Importar Namespaces
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Etapa 1: **Converter string GeoJSON** – um **exemplo c# geojson**
Primeiro criamos uma string JSON que representa uma `FeatureCollection` simples. Esta é a parte de **converter string geojson** do fluxo de trabalho.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Etapa 2: **Abrir camada GeoJSON** a partir de stream e **extrair propriedades geojson**
Agora inserimos a string em um `MemoryStream`, abrimos como uma camada GIS e demonstramos como ler valores de atributos (a etapa de **extrair propriedades geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Dica profissional:** `VectorLayer.Open` detecta automaticamente o formato GeoJSON quando você passa `Drivers.GeoJson`. Você também pode abrir arquivos diretamente fornecendo um caminho de arquivo em vez de um stream.

## Problemas Comuns & Soluções
| Problema | Solução |
|----------|----------|
| **Formato JSON inválido** | Verifique se a string GeoJSON está bem‑formada; use um validador JSON. |
| **Problemas de codificação** | Certifique‑se de que o stream usa UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Propriedades ausentes** | Verifique se o nome da propriedade está escrito corretamente (`"name"` no exemplo). |
| **Exceção de licença** | Use uma licença de avaliação para testes; aplique uma licença permanente para produção. |

## Perguntas Frequentes
### O Aspose.GIS é compatível com outros formatos GIS?
Sim, Aspose.GIS suporta GeoJSON, Shapefile, KML, GML e muitos outros formatos.

### Posso experimentar o Aspose.GIS antes de comprar?
Sim, você pode baixar uma avaliação gratuita do Aspose.GIS [aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.GIS?
Você pode encontrar a documentação do Aspose.GIS [aqui](https://reference.aspose.com/gis/net/).

### Como posso obter suporte para o Aspose.GIS?
Você pode obter suporte para o Aspose.GIS nos fóruns da Aspose [aqui](https://forum.aspose.com/c/gis/33).

### Preciso de uma licença temporária para usar o Aspose.GIS?
Você pode obter uma licença temporária para o Aspose.GIS [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Neste guia, cobrimos **como ler geojson** de um memory stream usando Aspose.GIS para .NET, demonstramos um fluxo de trabalho **c# read geojson**, e mostramos como **extrair propriedades geojson** da camada aberta. Com essas etapas, você pode integrar perfeitamente o tratamento de dados geoespaciais em qualquer aplicação .NET.

---

**Última atualização:** 2025-12-28  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}