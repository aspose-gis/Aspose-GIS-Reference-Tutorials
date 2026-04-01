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

# Obter todos os valores de atributos das características

## Introdução
Bem-vindo ao mundo do desenvolvimento geoespacial com Aspose.GIS para .NET! Neste tutorial você aprenderá **como ler shapefile C#** e recuperar cada valor de atributo de seus recursos. Seja construindo um aplicativo de mapeamento ou processamento de dados espaciais em lote, capturar a extração de atributos é essencial. Vamos mergulhar e ver o código em ação.

## Respostas rápidas
- **O que este código faz?** Ele abre um Shapefile e lê todos, vários ou os valores de atributos descartados de cada feature.
- **Qual biblioteca é necessária?** Aspose.GIS para .NET (compatível com .NET Framework e .NET Core).
- **Preciso de uma licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.
- **Posso ler outros formatos?** Sim – a mesma API suporta GeoJSON, KML e muitos outros.
- **Como descartar atributos?** Use `feature.GetValuesDump()` para obter um array de objetos flexível.

## O que é “ler shapefile C#”?
Ler um Shapefile em C# significa abrir o arquivo .shp com uma biblioteca GIS, iterar sobre seus recursos aleatórios e acessar os dados de atributos armazenados no arquivo .dbf associado. Aspose.GIS abstrai ou contém arquivos de baixo nível, permitindo que você se concentre nos valores de atributos que precisam.

## Por que usar Aspose.GIS para ler atributos?
- **API simples** – métodos intuitivos como `GetValues` e `GetValuesDump`.
- **Multiplataforma** – funciona no Windows, Linux e macOS com .NET Core.
- **Suporte rico a formatos** – manipula Shapefile, GeoJSON, GML e mais sem plugins adicionais.
- **Desempenho otimizado** – iteração rápida em grandes conjuntos de dados.

## Pré-requisitos
Antes de embarcarmos nesta jornada emocionante, certifique-se de ter os seguintes pré-requisitos em vigor:
- Aspose.GIS for .NET: Baixe e instale a biblioteca na [página de download do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento .NET, como o Visual Studio.
- Shapefile: Tenha um Shapefile de exemplo (por exemplo, "InputShapeFile.shp") imediatamente no diretório de documentos.

## Importar Namespaces
No seu código C#, comece importando os namespaces necessários para aproveitar as funcionalidades do Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Etapa 1: Defina o diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua "Your Document Directory" pelo caminho real onde seu Shapefile está localizado.

## Etapa 2: Abra o VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Esta etapa envolve abrir o Shapefile usando Aspose.GIS, especificando o caminho do arquivo e o formato (neste caso, Shapefile).

## Etapa 3: Recuperar todos os valores dos atributos da feição
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

## Etapa 4: Recuperar vários valores de atributos da feição
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

## Etapa 5: Recuperar os valores dos atributos como um despejo de objetos
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

## Problemas e soluções comuns
- **Incompatibilidade de tamanho de array** – Certifique-se de que o array passado para `GetValues` corresponde ao número de atributos esperados; Caso contrário, você obterá entradas `null`.
- **Arquivo não encontrado** – Verifique se `dataDir` aponta para a pasta correta e se o nome do Shapefile está escrito corretamente.
- **Exceção de licença** – Se você cometer um erro de licença, aplique uma licença temporária ou completa antes de chamar quaisquer métodos da API.

## Perguntas frequentes
### O Aspose.GIS é compatível com o .NET Core?
Sim, Aspose.GIS é totalmente compatível com .NET Core, permitindo que você crie aplicações multiplataforma.

### Posso trabalhar com diferentes formatos de arquivo GIS usando Aspose.GIS?
Absolutamente! Aspose.GIS suporta vários formatos, incluindo Shapefile, GeoJSON e mais.

### Existe um fórum da comunidade para suporte do Aspose.GIS?
Sim, você pode encontrar assistência e interagir com a comunidade Aspose.GIS no [fórum de suporte](https://forum.aspose.com/c/gis/33).

### Como posso obter uma licença temporária para Aspose.GIS?
Você pode obter uma licença temporária para fins de teste [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso encontrar documentação detalhada para Aspose.GIS?
A documentação completa está disponível [aqui](https://reference.aspose.com/gis/net/).

### Como recupero apenas o atributo “Nome” de cada recurso?
Use `GetValues` com um array de tamanho de um elemento e passe o índice do campo “Name”, ou chame `feature["Name"]` diretamente.

### Qual é a diferença entre `GetValues` e `GetValuesDump`?
`GetValues` preenche um array pré-alocado com valores brutos, enquanto `GetValuesDump` retorna um array de objetos que podem ser enumerados sem conhecer o esquema anteriormente.

---

**Última atualização:** 05/01/2026
**Testado com:** Aspose.GIS for .NET (última versão)
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
