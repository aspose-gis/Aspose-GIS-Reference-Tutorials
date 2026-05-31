---
date: 2026-05-31
description: Aprenda a limitar a precisão ao gravar geometrias com Aspose.GIS para
  .NET, reduzindo o tamanho do GeoJSON e mantendo o controle das coordenadas.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Limitar a precisão ao gravar geometrias
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Como limitar a precisão ao gravar geometrias com Aspose.GIS
url: /pt/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Limitar a Precisão ao Gravar Geometrias com Aspose.GIS

Se você está se perguntando **como limitar a precisão** ao gravar geometrias em uma aplicação GIS .NET, o Aspose.GIS para .NET oferece uma maneira simples e de alto desempenho para controlar o arredondamento de coordenadas. Neste tutorial, percorreremos todo o processo — desde a configuração do ambiente até a verificação de que a saída respeita as regras de precisão que você definir.

## Respostas Rápidas
- **O que significa “limitar a precisão”?** Ele arredonda os valores das coordenadas para um número definido de dígitos fracionários ao gravar um arquivo espacial.  
- **Qual formato é usado no exemplo?** GeoJSON, mas as mesmas opções se aplicam a outros formatos suportados.  
- **Preciso de uma licença para experimentar isso?** Um teste gratuito funciona para desenvolvimento e testes; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso controlar a precisão da coordenada Z separadamente?** Sim — use `ZPrecisionModel` para definir valores exatos ou arredondados.

## Como Limitar a Precisão ao Gravar Geometrias

Carregue seu gravador GeoJSON com um objeto `GeoJsonOptions` que especifica a precisão desejada para X/Y e Z, então grave a geometria e leia-a novamente — todo esse fluxo cabe em menos de dez linhas de código e garante que todas as coordenadas sejam arredondadas exatamente como você definiu.

Limitar a precisão é essencial quando você precisa de representação consistente de coordenadas entre diferentes ferramentas GIS, reduzir o tamanho do arquivo ou cumprir padrões de intercâmbio de dados. A seguir, definiremos opções de precisão, gravaremos uma geometria e então a leremos novamente para confirmar o arredondamento.

## O que é Limitação de Precisão?

Limitação de precisão é o processo de arredondar a parte fracionária dos valores de coordenadas para um número fixo de dígitos antes de persistir a geometria em um formato de arquivo. Isso garante que todo consumidor do arquivo veja os mesmos valores numéricos, ajudando a evitar pequenas discrepâncias que podem causar erros de topologia.

## Por que Usar Aspose.GIS para Controle de Precisão?

Aspose.GIS suporta **50+** formatos de entrada e saída — incluindo GeoJSON, Shapefile, KML e GML — e pode processar arquivos com **centenas de milhares de recursos** sem carregar todo o conjunto de dados na memória. Seus modelos de precisão incorporados permitem arredondar coordenadas em uma única chamada, eliminando a necessidade de scripts de pós‑processamento manuais.

## Pré‑requisitos

### 1. Download e Instalação
Obtenha o pacote mais recente do Aspose.GIS para .NET no site oficial: [download link](https://releases.aspose.com/gis/net/). Siga o guia de instalação para adicionar o pacote NuGet ao seu projeto.

### 2. Importação de Namespace
Adicione os namespaces necessários para que você possa acessar as classes GIS e utilitários auxiliares.

## Guia Passo a Passo

### Etapa 1: Definir Opções de Precisão
A classe `GeoJsonOptions` permite especificar quantos dígitos fracionários manter para as coordenadas X/Y e Z.  
`PrecisionModel` define como os valores das coordenadas são arredondados ou mantidos exatos durante a gravação.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Etapa 2: Definir Caminho de Saída
Especifique onde o arquivo GeoJSON resultante será salvo.  
`VectorLayer` é o contêiner do Aspose.GIS para uma coleção de recursos que compartilham o mesmo esquema; ele grava no caminho que você fornece usando as opções definidas anteriormente.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Etapa 3: Criar e Popular a Geometria
Abra um novo `VectorLayer` com as opções definidas acima, construa uma geometria `Point` e adicione-a à camada.  
`Point` representa uma única coordenada (X, Y, Z opcional) em um sistema de referência espacial. É o tipo de geometria mais simples e é usado aqui para demonstrar o arredondamento de precisão.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Etapa 4: Ler e Verificar a Precisão
Abra o arquivo que você acabou de criar e imprima as coordenadas. Você deve ver os valores X/Y arredondados para três casas decimais, enquanto o valor Z permanece exato.  
Ao ler o arquivo novamente, o Aspose.GIS analisa os valores arredondados diretamente, de modo que o `Point` em memória reflete a precisão que você definiu durante a gravação.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Problemas Comuns & Dicas

- **Erros de Caminho:** Certifique‑se de que o diretório em `path` exista ou use `Path.Combine` com `Environment.CurrentDirectory` para construir um caminho de arquivo seguro.  
- **Precisão Não Aplicada:** Verifique se você passa o objeto `GeoJsonOptions` ao criar a camada; caso contrário, a precisão padrão (double completo) é usada.  
- **Conjuntos de Dados Grandes:** Para operações em lote, considere reutilizar uma única instância de `VectorLayer` e adicionar recursos em lote para melhorar o desempenho.

## Perguntas Frequentes

**Q: O Aspose.GIS para .NET é compatível com outros formatos GIS?**  
A: Sim, ele suporta **50+** formatos — incluindo Shapefile, GeoJSON, KML, GML e CSV — permitindo conversão perfeita entre eles.  

**Q: Posso experimentar o Aspose.GIS para .NET antes de comprar?**  
A: Absolutamente. Um teste gratuito está disponível na página de download, oferecendo acesso total a todos os recursos para avaliação.  

**Q: Como obtenho uma licença temporária para testes?**  
A: Licenças de avaliação temporárias podem ser geradas através do portal de licenças da Aspose; são válidas por 30 dias.  

**Q: Onde posso obter ajuda se encontrar problemas?**  
A: O fórum Aspose.GIS e a tag do Stack Overflow `aspose-gis` são ótimos lugares para fazer perguntas e encontrar soluções da comunidade.  

**Q: A biblioteca funciona tanto para pequenos scripts quanto para aplicações em escala empresarial?**  
A: Sim, o Aspose.GIS foi projetado para lidar com tudo, desde protótipos rápidos até cargas de trabalho de servidor de alta taxa, processando conjuntos de dados de vários gigabytes com baixo consumo de memória.  

---

**Última Atualização:** 2026-05-31  
**Testado Com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Camada Vetorial, Limitar Precisão com Aspose.GIS para .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Como Converter GeoJSON – Aspose.GIS para .NET](/gis/net/geo-data-conversion/)
- [Como Verificar Geometria com Aspose.GIS para .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}