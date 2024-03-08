---
title: Domínio de GIS - Adicione camadas ao GDB com Aspose.GIS para .NET
linktitle: Adicionar camada ao conjunto de dados GDB do arquivo
second_title: API Aspose.GIS .NET
description: Desbloqueie o poder do GIS com Aspose.GIS for .NET! Aprenda como adicionar camadas aos conjuntos de dados do File GDB neste tutorial passo a passo. #dados geográficos #Aspose #GIS
type: docs
weight: 16
url: /pt/net/layer-management/add-layer-to-file-gdb-dataset/
---
## Introdução
Você está pronto para aprimorar seus recursos GIS usando Aspose.GIS for .NET? Neste guia passo a passo, orientaremos você no processo de adição de uma camada a um conjunto de dados File Geodatabase (GDB). Aspose.GIS for .NET fornece recursos poderosos para manipular informações geográficas e, com este tutorial, você poderá integrar perfeitamente camadas adicionais em seus conjuntos de dados.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Biblioteca Aspose.GIS for .NET: Baixe e instale a biblioteca do[Documentação Aspose.GIS para .NET](https://reference.aspose.com/gis/net/).
- Diretório de documentos: Crie um diretório de documentos dedicado em sua máquina para armazenar e gerenciar arquivos relacionados ao GIS.
## Importar namespaces
Em seu projeto .NET, certifique-se de importar os namespaces necessários para acessar as funcionalidades do Aspose.GIS. Use o seguinte trecho de código:
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
## Etapa 1: copiar diretório
Antes de continuar, duplique o diretório que contém seu conjunto de dados GDB. Esta etapa garante que o conjunto de dados original permaneça intacto. Use o trecho de código fornecido:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Etapa 2: abrir o conjunto de dados e verificar a capacidade de criação
 Abra o conjunto de dados duplicado e verifique se ele pode criar camadas. Isto é confirmado pela presença de`True` na saída do console.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // Verdadeiro
```
## Etapa 3: criar e preencher uma nova camada
Crie uma nova camada dentro do conjunto de dados, definindo seu sistema de referência espacial, atributos e um recurso de amostra. Este trecho de código demonstra o processo:
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
## Etapa 4: abra e valide a camada adicionada
Abra a camada que acabou de criar e valide seu conteúdo. Verifique a contagem e recupere os valores dos atributos usando o seguinte código:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Nome_1"
}
```
## Conclusão
Parabéns! Você aprendeu com sucesso como adicionar uma camada a um conjunto de dados File GDB usando Aspose.GIS for .NET. Com essas novas habilidades, você pode manipular dados geográficos com eficiência em seus projetos GIS.
## perguntas frequentes
### P: Posso usar Aspose.GIS for .NET com outras bibliotecas GIS?
Aspose.GIS for .NET foi projetado para funcionar de forma independente, mas pode ser integrado com outras bibliotecas para funcionalidade aprimorada.
### P: Existe uma licença temporária disponível para fins de teste?
 Sim, você pode obter uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/) para teste e avaliação.
### P: Quais sistemas de referência espacial o Aspose.GIS for .NET suporta?
Aspose.GIS for .NET suporta uma ampla gama de sistemas de referência espacial, proporcionando flexibilidade no tratamento de dados geográficos.
### P: Posso contribuir com a comunidade Aspose.GIS?
 Absolutamente! Participe das discussões e compartilhe suas experiências no[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### P: Onde posso encontrar documentação detalhada do Aspose.GIS for .NET?
 Explore a documentação abrangente[aqui](https://reference.aspose.com/gis/net/) para obter informações detalhadas sobre Aspose.GIS for .NET.