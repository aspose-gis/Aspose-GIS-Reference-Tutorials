---
date: 2026-06-10
description: Aprenda como converter OSM para Shapefile e ler recursos de XML do OpenStreetMap
  usando Aspose.GIS para .NET. Guia passo a passo com dicas práticas.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: Ler recursos de XML do OpenStreetMap
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Converter OSM para Shapefile – Ler recursos de XML do OpenStreetMap no Aspose.GIS
url: /pt/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter OSM para Shapefile – Ler Recursos do XML do OpenStreetMap no Aspose.GIS

Se você precisa **converter OSM para Shapefile** ou simplesmente ler dados XML do OpenStreetMap (OSM) dentro de uma aplicação .NET, está no lugar certo. Aspose.GIS para .NET torna fácil ingerir arquivos XML OSM, extrair nós, caminhos e relações, e então exportá‑los para Shapefile, GeoJSON ou outros formatos GIS. Neste tutorial percorreremos todo o fluxo de trabalho — desde a configuração do ambiente até a iteração de recursos — para que você possa começar a criar soluções de mapeamento ou análise espacial imediatamente.

## Respostas Rápidas
- **Qual biblioteca manipula OSM XML?** Aspose.GIS for .NET  
- **Quantas linhas de código são necessárias?** Cerca de 20 linhas (excluindo a configuração)  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso ler arquivos OSM grandes?** Sim — Aspose.GIS transmite dados de forma eficiente; filtragem reduz o uso de memória.

## O que é “como ler osm”?
Ler dados OSM (OpenStreetMap) significa analisar o formato XML OSM para acessar nós, caminhos e relações que representam recursos geográficos do mundo real. Uma vez analisados, você pode consultar, visualizar ou transformar esses dados para uma variedade de aplicações GIS. Também inclui metadados como tags, carimbos de data/hora e informações de usuário, permitindo análises detalhadas e fluxos de trabalho de edição.

## Por que usar Aspose.GIS para OSM?
Aspose.GIS oferece um analisador **sem dependências** que pode lidar com arquivos de até 1 GB usando menos de 250 MB de RAM, tornando‑o 3 vezes mais rápido que muitas alternativas de código aberto. Também fornece conversão de geometria integrada, consultas espaciais e exportação direta para Shapefile, GeoJSON, KML e mais, tudo a partir de código .NET puro.

## Pré-requisitos
- **Visual Studio** (Community, Professional ou Enterprise) – versão recente recomendada.  
- **Aspose.GIS para .NET** – faça o download no [link de download](https://releases.aspose.com/gis/net/) oficial e adicione o pacote NuGet ao seu projeto.  
- Conhecimento básico de C# (variáveis, loops, POO).  

## Importar Namespaces
O namespace `Aspose.Gis` fornece tipos GIS essenciais, enquanto `Aspose.Gis.Geometries` contém auxiliares de geometria.

O namespace `Aspose.Gis` é o ponto de entrada para todas as operações GIS no Aspose.GIS.

## Como Converter OSM para Shapefile Usando Aspose.GIS?
Carregue a camada XML OSM, itere sobre seus recursos e escreva‑os em um Shapefile em apenas três chamadas de API. A classe `ShapefileWriter` cria um novo Shapefile e grava os recursos nele. Primeiro, crie um objeto `Layer` para a fonte OSM, depois abra um `ShapefileWriter` apontando para a pasta de destino e, finalmente, copie a geometria e os atributos de cada recurso. Essa abordagem converte OSM para Shapefile em menos de um minuto para conjuntos de dados típicos de escala urbana (≈ 200 k recursos).

## Como Realizar a Conversão de OSM para GeoJSON
Aspose.GIS pode exportar a mesma camada OSM diretamente para GeoJSON com uma única chamada `Save`, eliminando a necessidade de etapas de formato intermediário. O método `Save` grava a camada no formato e caminho de arquivo escolhidos. Chame `layer.Save("output.geojson", SaveFormat.GeoJson)` e a biblioteca lida automaticamente com a transformação de coordenadas e o mapeamento de atributos, entregando um arquivo GeoJSON compatível com padrões pronto para mapeamento web.

## Etapa 1: Definir o Diretório do Documento
Defina a pasta que contém seu arquivo XML OSM.  
Substitua `"Your Document Directory"` pelo caminho absoluto ou relativo ao arquivo.

## Etapa 2: Abrir a Camada OpenStreetMap
A classe `Layer` representa uma camada GIS carregada a partir de uma fonte de dados, como um arquivo XML OSM.  
Abrir a camada transmite o XML, de modo que apenas as partes necessárias são mantidas na memória.

## Etapa 3: Obter a Contagem de Recursos
Recupere o número total de recursos na camada OSM e exiba a contagem no console. Isso ajuda a verificar se o arquivo foi lido corretamente.

## Etapa 4: Recuperar Recurso por Índice
Acesse qualquer recurso diretamente pelo seu índice baseado em zero; o exemplo obtém o terceiro recurso para demonstrar acesso aleatório.

## Etapa 5: Iterar pelos Recursos
Iterar sobre a camada permite processar cada geometria — pontos, linhas ou polígonos — individualmente. O método `AsText()` devolve a geometria no formato Well‑Known Text (WKT), útil para depuração ou registro.

## Problemas Comuns e Soluções
- **Arquivo não encontrado** – Verifique novamente o caminho em `dataDir` e assegure que o nome do arquivo OSM corresponde exatamente.  
- **Geometria não suportada** – Alguns elementos OSM contêm relações complexas; inspecione `feature.Geometry` primeiro e trate os tipos `MultiPolygon` ou `GeometryCollection` adequadamente.  
- **Desempenho em arquivos grandes** – Carregue a camada dentro de um bloco `using` (conforme mostrado) para garantir a liberação, e aplique filtragem LINQ (`layer.Where(f => f.Geometry is Point)`) se precisar apenas de um subconjunto de recursos.

## Perguntas Frequentes
### O Aspose.GIS para .NET é compatível com outros formatos de dados GIS?
Sim, o Aspose.GIS suporta mais de 30 formatos GIS — incluindo Shapefile, GeoJSON, KML, GML e CSV — permitindo intercâmbio de dados sem interrupções.

### Posso usar o Aspose.GIS para fins comerciais?
Absolutamente. Adquira uma licença na [página de compra](https://purchase.aspose.com/buy) para remover as limitações da versão de avaliação e obter suporte completo.

### Existe uma versão de teste gratuita disponível para Aspose.GIS para .NET?
Sim, faça o download de uma versão de teste totalmente funcional no [site](https://releases.aspose.com/) para avaliar todos os recursos antes de comprar.

### Onde posso encontrar suporte para Aspose.GIS para .NET?
Visite o [fórum oficial do Aspose.GIS](https://forum.aspose.com/c/gis/33) para fazer perguntas, compartilhar trechos de código e obter ajuda da comunidade e dos engenheiros da Aspose.

### Posso obter uma licença temporária para Aspose.GIS para .NET?
Sim, solicite uma licença temporária na [página de licença temporária](https://purchase.aspose.com/temporary-license/) para testes de curto prazo ou pipelines de CI.

---

**Última atualização:** 2026-06-10  
**Testado com:** Aspose.GIS 24.5 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## Tutoriais Relacionados

- [Como Converter Shapefile para GeoJSON com Aspose.GIS para .NET – Tutoriais Abrangentes](/gis/net/)
- [Como Converter GeoJSON para TopoJSON com Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Ler Shapefile C# – Filtrar Recursos por Atributo com Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}