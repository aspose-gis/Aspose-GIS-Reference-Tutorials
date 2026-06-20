---
date: 2026-06-20
description: Aprenda como converter geojson para gdb com Aspose.GIS para .NET. Este
  guia passo a passo cobre a leitura de GeoJSON em C#, a criação de um File Geodatabase
  e o tratamento de problemas comuns.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Converter Camada GeoJSON para GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como Converter GeoJSON para GDB Usando Aspose.GIS para .NET
url: /pt/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Converter GeoJSON para GDB Usando Aspose.GIS para .NET

## Introdução
Se você está procurando **convert geojson to gdb** rapidamente e de forma confiável, está no lugar certo. Este tutorial orienta você em cada passo — começando pela leitura de um arquivo GeoJSON em C# até a criação de um File Geodatabase (GDB) com Aspose.GIS. Você verá por que o Aspose.GIS é uma biblioteca preferida para conversão de dados geoespaciais, como configurar o ambiente e como executar a conversão em apenas alguns minutos.

## Respostas Rápidas
- **O que este guia ensina?** Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.  
- **Qual palavra‑chave principal é alvo?** *convert geojson to gdb*.  
- **Preciso de uma licença?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo de implementação?** Aproximadamente 10‑15 minutes for a basic conversion.

## O que é GeoJSON e File GDB?
GeoJSON é um formato leve, baseado em texto, para recursos geográficos, enquanto File GDB é um geodatabase ESRI de alto desempenho baseado em pastas.  
GeoJSON armazena pontos, linhas e polígonos como texto simples, facilitando o compartilhamento e a edição, enquanto File GDB mantém os dados em arquivos binários que proporcionam consultas espaciais rápidas e manipulação robusta de atributos. Juntos, eles cobrem tanto a troca amigável para a web quanto o processamento GIS de desktop de alta velocidade.

## Por que usar Aspose.GIS para conversão de dados geoespaciais?
Aspose.GIS fornece uma API única e consistente que oculta peculiaridades específicas de formatos. Ele suporta **30+ formatos geoespaciais**, pode processar arquivos de até **2 GB** sem carregar todo o conjunto de dados na memória e preserva automaticamente os sistemas de referência de coordenadas. Isso significa que você gasta menos tempo escrevendo analisadores e mais tempo construindo a lógica da sua aplicação.

## Pré‑requisitos
- Familiaridade com C# e a estrutura de projetos .NET.  
- Aspose.GIS para .NET instalado. Se ainda não o instalou, faça o download [aqui](https://releases.aspose.com/gis/net/) e siga o guia de instalação. Você também pode explorar outros produtos Aspose [aqui](https://releases.aspose.com/).

## Importar Namespaces
O primeiro passo é trazer os namespaces necessários para o escopo.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Como ler GeoJSON em C#?
Carregue o arquivo GeoJSON com a classe `GeoJsonReader`, que analisa o JSON e cria uma `FeatureCollection` na memória. O leitor detecta automaticamente o sistema de referência de coordenadas, portanto você não precisa tratar a análise de CRS manualmente. Ele também suporta streaming de arquivos grandes, preservando tipos de atributos, e pode ser combinado com transformações de geometria personalizadas, se necessário.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Etapa 1: Configurar a Camada GeoJSON
Crie um arquivo GeoJSON temporário que contenha os atributos e recursos que você deseja converter. Este exemplo adiciona dois recursos de ponto simples.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Etapa 2: Copiar Conjunto de Dados de Teste
Para manter os dados de teste originais intactos, duplique o conjunto de dados File GDB existente. Isso garante um ambiente limpo para a conversão.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Etapa 3: Converter GeoJSON para GDB
`FileGdb` representa um contêiner File Geodatabase e fornece métodos para gerenciar camadas. Abra a camada GeoJSON, crie uma nova camada dentro do File GDB copiado, copie os atributos e transfira cada recurso. Este é o núcleo do processo de **conversão Aspose.GIS**.

CODE_BLOCK_PLACEHOLDER_4_END

## Como converter GeoJSON para GDB?
Carregue o GeoJSON com `GeoJsonReader`, instancie um objeto `FileGdb` apontando para a sua pasta de destino, crie uma nova camada de recursos e, em seguida, itere sobre cada recurso para inseri‑lo. Na prática, é um fluxo de três etapas — ler, criar, copiar — que termina em menos de um minuto para conjuntos de dados típicos.

## Problemas Comuns e Soluções
- **Referência espacial ausente:** Certifique‑se de que o GeoJSON de origem inclua uma definição de CRS ou defina explicitamente `SpatialReferenceSystem.Wgs84` ao criar a camada GDB.  
- **Incompatibilidade de tipo de atributo:** Os tipos de dados de atributo no GeoJSON devem corresponder ao esquema de destino; caso contrário, o Aspose.GIS lançará uma exceção.  
- **Erros de acesso a arquivos:** Verifique se a pasta de destino tem permissões de gravação e se nenhum outro processo está bloqueando os arquivos GDB.

## Perguntas Frequentes
### O Aspose.GIS é compatível com o framework .NET mais recente?
Sim, o Aspose.GIS funciona com .NET Framework 4.5+, .NET Core 3.1+, .NET 5 e .NET 6+.

### Posso converter outros formatos geoespaciais usando Aspose.GIS?
Absolutamente! O Aspose.GIS suporta mais de 30 formatos de entrada e saída, incluindo Shapefile, KML, GML e SQLite.

### Existe uma versão de avaliação disponível para Aspose.GIS?
Sim, você pode explorar as funcionalidades do Aspose.GIS baixando a versão de avaliação [aqui](https://releases.aspose.com/).

### Como posso obter suporte para consultas relacionadas ao Aspose.GIS?
Visite o [fórum](https://forum.aspose.com/c/gis/33) do Aspose.GIS para obter assistência dedicada da comunidade e da equipe do produto.

### Posso obter uma licença temporária para Aspose.GIS?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Última atualização:** 2026-06-20  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Conjunto de Dados File Geodatabase .NET com Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Ler Recursos de File Geodatabase no Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Criar Camada Vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}