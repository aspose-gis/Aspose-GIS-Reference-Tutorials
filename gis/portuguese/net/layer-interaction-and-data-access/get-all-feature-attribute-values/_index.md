---
date: 2026-01-05
description: Aprenda a ler shapefile em C# usando Aspose.GIS para .NET, recuperar
  todos os valores de atributos de recursos e exportar atributos de forma eficiente.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Ler Shapefile C# – Obter Todos os Valores de Atributos das Feições
url: /pt/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obter Todos os Valores de Atributos das Features

## Introduction
Bem-vindo ao mundo do desenvolvimento geoespacial com Aspose.GIS para .NET! Neste tutorial você aprenderá **como ler shapefile C#** e recuperar cada valor de atributo de suas features. Seja construindo um aplicativo de mapeamento ou processando dados espaciais em lote, dominar a extração de atributos é essencial. Vamos mergulhar e ver o código em ação.

## Quick Answers
- **O que este código faz?** Ele abre um Shapefile e lê todos, vários ou os valores de atributos despejados de cada feature.  
- **Qual biblioteca é necessária?** Aspose.GIS para .NET (compatível com .NET Framework e .NET Core).  
- **Preciso de uma licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.  
- **Posso ler outros formatos?** Sim – a mesma API suporta GeoJSON, KML e muitos outros.  
- **Como despejar atributos?** Use `feature.GetValuesDump()` para obter um array de objetos flexível.

## What is “read shapefile C#”?
Ler um Shapefile em C# significa abrir o arquivo .shp com uma biblioteca GIS, iterar sobre suas features vetoriais e acessar os dados de atributos armazenados no arquivo .dbf associado. Aspose.GIS abstrai o manuseio de arquivos de baixo nível, permitindo que você se concentre nos valores de atributos que precisa.

## Why use Aspose.GIS to read attributes?
- **API simples** – métodos intuitivos como `GetValues` e `GetValuesDump`.  
- **Multiplataforma** – funciona no Windows, Linux e macOS com .NET Core.  
- **Suporte rico a formatos** – manipula Shapefile, GeoJSON, GML e mais sem plugins adicionais.  
- **Desempenho otimizado** – iteração rápida em grandes conjuntos de dados.

## Prerequisites
Before we embark on this exciting journey, ensure you have the following prerequisites in place:
- Aspose.GIS for .NET: Baixe e instale a biblioteca a partir da [página de download do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento .NET, como o Visual Studio.
- Shapefile: Tenha um Shapefile de exemplo (por exemplo, "InputShapeFile.shp") pronto no diretório de documentos.

## Import Namespaces
No seu código C#, comece importando os namespaces necessários para aproveitar as funcionalidades do Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Step 1: Set the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
Substitua "Your Document Directory" pelo caminho real onde seu Shapefile está localizado.

## Step 2: Open the VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Esta etapa envolve abrir o Shapefile usando Aspose.GIS, especificando o caminho do arquivo e o formato (neste caso, Shapefile).

## Step 3: Retrieve All Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
O trecho mostra **como ler atributos** de cada feature carregando-os em um array de tamanho fixo.

## Step 4: Retrieve Several Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Aqui demonstramos **como ler valores de atributos específicos** quando você precisa apenas de um subconjunto de campos.

## Step 5: Retrieve Attribute Values as Objects Dump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Esta etapa final demonstra **como despejar atributos** usando `GetValuesDump()`, que retorna uma coleção flexível que você pode inspecionar ou serializar.

## Common Issues and Solutions
- **Incompatibilidade de tamanho de array** – Certifique‑se de que o array passado para `GetValues` corresponda ao número de atributos esperados; caso contrário, você obterá entradas `null`.  
- **Arquivo não encontrado** – Verifique se `dataDir` aponta para a pasta correta e se o nome do Shapefile está escrito exatamente.  
- **Exceção de licença** – Se você vir um erro de licença, aplique uma licença temporária ou completa antes de chamar quaisquer métodos da API.

## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
Sim, Aspose.GIS é totalmente compatível com .NET Core, permitindo que você crie aplicações multiplataforma.

### Can I work with different GIS file formats using Aspose.GIS?
Absolutamente! Aspose.GIS suporta vários formatos, incluindo Shapefile, GeoJSON e mais.

### Is there a community forum for Aspose.GIS support?
Sim, você pode encontrar assistência e interagir com a comunidade Aspose.GIS no [forum de suporte](https://forum.aspose.com/c/gis/33).

### How can I obtain a temporary license for Aspose.GIS?
Você pode obter uma licença temporária para fins de teste [aqui](https://purchase.aspose.com/temporary-license/).

### Where can I find detailed documentation for Aspose.GIS?
A documentação completa está disponível [aqui](https://reference.aspose.com/gis/net/).

### How do I retrieve only the “Name” attribute from each feature?
Use `GetValues` com um array de tamanho um elemento e passe o índice do campo “Name”, ou chame `feature["Name"]` diretamente.

### What is the difference between `GetValues` and `GetValuesDump`?
`GetValues` preenche um array pré‑alocado com valores brutos, enquanto `GetValuesDump` retorna um array de objetos que pode ser enumerado sem conhecer o esquema previamente.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-05  
**Testado com:** Aspose.GIS for .NET (última versão)  
**Autor:** Aspose  

---