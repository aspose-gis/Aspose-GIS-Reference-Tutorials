---
date: 2026-06-30
description: Aprenda como adicionar camada a um conjunto de dados File GDB usando
  Aspose.GIS com referência espacial WGS84. Siga este guia passo a passo para adicionar
  uma camada em .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Adicionar camada ao conjunto de dados File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como adicionar camada a um conjunto de dados File GDB com referência espacial
  WGS84 usando Aspose.GIS
url: /pt/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# como adicionar camada – referência espacial wgs84 com Aspose.GIS

## Introdução
Pronto para impulsionar seu fluxo de trabalho GIS com Aspose.GIS para .NET? Neste tutorial você aprenderá **como adicionar camada** a um conjunto de dados File GDB enquanto trabalha com o sistema de coordenadas **referência espacial WGS84**. Vamos percorrer cada passo, desde a preparação da sua pasta de dados até a validação da camada recém‑criada, para que você possa começar a manipular dados geográficos com confiança e eficiência.

## Respostas rápidas
- **Qual é o sistema de coordenadas principal usado?** spatial reference wgs84 (WGS 84)  
- **Qual biblioteca fornece a API?** Aspose.GIS for .NET  
- **Preciso de uma licença para teste?** Sim – uma licença temporária da Aspose está disponível.  
- **Posso adicionar atributos à nova camada?** Absolutamente, você pode definir qualquer número de atributos de recurso.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## O que é referência espacial wgs84?
A referência espacial wgs84 (World Geodetic System 1984) é o sistema de coordenadas geográficas mais amplamente usado. Ela define latitude e longitude em graus e serve como o CRS padrão para muitos conjuntos de dados GIS, incluindo o que criaremos neste guia.

## Por que usar Aspose.GIS para adicionar uma camada?
Carregue seus dados GIS sem binários de terceiros e mantenha controle total sobre a definição do esquema. Aspose.GIS suporta **mais de 40 sistemas de referência espacial**, pode processar arquivos maiores que **2 GB** sem carregar todo o conjunto de dados na memória, e funciona em Windows, Linux e macOS. Isso o torna uma solução confiável e multiplataforma para automação GIS de nível empresarial.

## Pré-requisitos
- Biblioteca Aspose.GIS para .NET: Baixe e instale a biblioteca a partir da [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Diretório de documentos: Crie uma pasta dedicada em sua máquina para armazenar arquivos GIS.  
- Uma licença temporária da Aspose (opcional para avaliação) – veja o FAQ abaixo para o link de download.

## Importar namespaces
Adicione as instruções `using` necessárias ao seu projeto C# para que você possa acessar as classes Aspose.GIS:

*Nenhum bloco de código é necessário aqui; basta adicionar as linhas a seguir no início do seu arquivo:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Etapa 1: Copiar diretório
**Âncora de definição:** Um conjunto de dados File GDB é um geodatabase ESRI baseado em pastas que armazena dados espaciais em um conjunto de arquivos.  
Primeiro, duplique a pasta que contém o conjunto de dados GDB original. Manter uma cópia protege os dados de origem enquanto você experimenta.

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

## Etapa 2: Abrir conjunto de dados e verificar capacidade de criação
`Dataset` representa uma coleção de camadas GIS armazenadas em um File GDB. Abra o conjunto de dados recém‑copiado e confirme que ele pode criar novas camadas. A propriedade `CanCreateLayers` deve retornar **True**. **`CanCreateLayers` é uma propriedade booleana que indica se o conjunto de dados suporta a criação de novas camadas.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Etapa 3: Criar e popular uma nova camada com referência espacial wgs84
Agora criamos uma camada chamada **data** e definimos explicitamente sua referência espacial para **Wgs84**. Também adicionamos um atributo simples chamado **Name** e inserimos um recurso ponto. **`CreateLayer` cria uma nova camada no conjunto de dados com o nome e a referência espacial especificados.** **`SpatialReference` representa o sistema de coordenadas usado por uma camada.** **`Feature` é um objeto geográfico individual (ponto, linha ou polígono) armazenado em uma camada.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Etapa 4: Abrir e validar a camada adicionada
Finalmente, abra a camada que você acabou de criar e verifique seu conteúdo. O console mostrará que a camada contém um recurso e que o atributo **Name** corresponde ao que definimos. **`Layer.Open` abre uma camada existente para leitura ou edição.** Isso confirma que a camada foi adicionada corretamente e que a referência espacial é WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Como adicionar camada a um conjunto de dados File GDB?
Carregue o conjunto de dados, chame `CreateLayer` com o nome e a referência espacial desejados, defina o esquema de atributos e então insira os recursos. Tudo isso pode ser feito com algumas chamadas de método do Aspose.GIS, e a API lida automaticamente com bloqueio de arquivos e validação de esquema. O processo garante que a nova camada esteja em conformidade com a referência espacial do conjunto de dados, que as definições de atributos sejam armazenadas no esquema da camada e que os dados possam ser acessados por qualquer software GIS que suporte File GDB.

## Problemas comuns e dicas
- **Caminho incorreto:** Certifique-se de que `dataDir` termina com um separador de caminho (`/` ou `\`) para que as strings concatenadas formem caminhos de arquivo válidos.  
- **Erros de licença:** Se você vir avisos de licença, aplique uma licença temporária do portal Aspose antes de executar o código.  
- **Incompatibilidade de CRS:** Ao abrir a camada posteriormente em outra ferramenta GIS, confirme que a ferramenta reconhece WGS 84 (EPSG:4326) como o sistema de coordenadas.  
- **Conjuntos de dados grandes:** Para conjuntos de dados que excedem 1 GB, considere usar `Dataset.OpenReadOnly` para reduzir o consumo de memória.

## Perguntas Frequentes
### P: Posso usar Aspose.GIS para .NET com outras bibliotecas GIS?
R: Sim, o Aspose.GIS funciona de forma independente, mas pode ser combinado com bibliotecas como GDAL ou NetTopologySuite para processamento avançado.

### P: Uma licença temporária está disponível para fins de teste?
R: Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para teste e avaliação.

### P: Quais sistemas de referência espacial o Aspose.GIS para .NET suporta?
R: O Aspose.GIS suporta mais de **40 códigos EPSG**, incluindo sistemas populares como WGS84 (EPSG:4326), Web Mercator (EPSG:3857) e NAD83 (EPSG:4269). Explore a documentação completa [aqui](https://reference.aspose.com/gis/net/).

### P: Posso contribuir para a comunidade Aspose.GIS?
R: Absolutamente! Participe das discussões e compartilhe suas experiências no [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### P: Onde posso encontrar documentação detalhada do Aspose.GIS para .NET?
R: Explore a documentação completa [aqui](https://reference.aspose.com/gis/net/) para informações detalhadas sobre todas as classes, métodos e boas práticas.

---

**Última atualização:** 2026-06-30  
**Testado com:** Aspose.GIS for .NET (latest stable version)  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Tutoriais relacionados

- [Criar conjunto de dados File Geodatabase .NET com Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Criar camada vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Criar conjunto de dados File GDB e definir tolerâncias para uma camada](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}