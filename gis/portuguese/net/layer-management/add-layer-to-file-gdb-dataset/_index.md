---
date: 2026-01-13
description: Aprenda como adicionar uma camada a um conjunto de dados File GDB usando
  Aspose.GIS, com suporte a referência espacial WGS84. Siga este guia passo a passo
  para adicionar camada ao GDB em .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Referência espacial WGS84 – Adicionar camada ao GDB usando Aspose.GIS
url: /pt/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# referência espacial wgs84 – Adicionar Camada ao GDB usando Aspose.GIS

## Introdução
Pronto para impulsionar seu fluxo de trabalho GIS com Aspose.GIS para .NET? Neste tutorial você aprenderá **como adicionar uma camada a um conjunto de dados File GDB** enquanto trabalha com o sistema de coordenadas **referência espacial wgs84**. Vamos percorrer cada passo, desde a preparação da pasta de dados até a validação da camada recém‑criada, para que você possa começar a manipular dados geográficos com confiança.

## Respostas Rápidas
- **Qual é o sistema de coordenadas principal usado?** referência espacial wgs84 (WGS 84)  
- **Qual biblioteca fornece a API?** Aspose.GIS for .NET  
- **Preciso de uma licença para teste?** Sim – uma licença temporária da Aspose está disponível.  
- **Posso adicionar atributos à nova camada?** Absolutamente, você pode definir qualquer número de atributos de recurso.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## O que é referência espacial wgs84?
A referência espacial wgs84 (World Geodetic System 1984) é o sistema de coordenadas geográficas mais amplamente usado. Ela define latitude e longitude em graus e serve como o CRS padrão para muitos conjuntos de dados GIS, incluindo o que criaremos neste guia.

## Por que usar Aspose.GIS para adicionar uma camada?
- **Sem dependências externas:** Funciona imediatamente com código puro .NET.  
- **Controle total sobre o esquema:** Você pode definir atributos personalizados e tipos de geometria.  
- **Multiplataforma:** Compatível com runtimes Windows, Linux e macOS.  
- **Licenciamento robusto:** Licenças temporárias permitem avaliação rápida antes de comprometer.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

- Aspose.GIS for .NET Library: Baixe e instale a biblioteca a partir da [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Diretório de Documentos: Crie uma pasta dedicada em sua máquina para armazenar arquivos GIS.

## Importar Namespaces
Adicione as declarações `using` necessárias ao seu projeto C# para acessar as classes Aspose.GIS:

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

## Etapa 1: Copiar Diretório
Primeiro, duplique a pasta que contém o conjunto de dados GDB original. Manter uma cópia protege os dados fonte enquanto você experimenta.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Etapa 2: Abrir Conjunto de Dados e Verificar Capacidade de Criação
Abra o conjunto de dados recém‑copiado e confirme que ele pode criar novas camadas. A propriedade `CanCreateLayers` deve retornar **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Etapa 3: Criar e Popular uma Nova Camada com referência espacial wgs84
Agora criamos uma camada chamada **data** e definimos explicitamente sua referência espacial como **Wgs84**. Também adicionamos um atributo simples chamado **Name** e inserimos um recurso ponto.

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

## Etapa 4: Abrir e Validar a Camada Adicionada
Finalmente, abra a camada que você acabou de criar e verifique seu conteúdo. O console mostrará que a camada contém um recurso e que o atributo **Name** corresponde ao valor definido.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Problemas Comuns & Dicas
- **Caminho incorreto:** Garanta que `dataDir` termine com um separador de caminho (`/` ou `\`) para que as strings concatenadas formem caminhos de arquivo válidos.  
- **Erros de licença:** Se aparecerem avisos de licenciamento, aplique uma licença temporária do portal Aspose antes de executar o código.  
- **Incompatibilidade de CRS:** Ao abrir a camada posteriormente em outra ferramenta GIS, confirme que a ferramenta reconhece WGS 84 (EPSG:4326) como o sistema de coordenadas.

## Perguntas Frequentes
### P: Posso usar Aspose.GIS para .NET com outras bibliotecas GIS?
Aspose.GIS for .NET foi projetado para funcionar de forma independente, mas pode ser integrado a outras bibliotecas para funcionalidade aprimorada.  

### P: Existe uma licença temporária disponível para fins de teste?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para teste e avaliação.  

### P: Quais sistemas de referência espacial o Aspose.GIS para .NET suporta?
Aspose.GIS for .NET suporta uma ampla gama de sistemas de referência espacial, proporcionando flexibilidade no manuseio de dados geográficos.  

### P: Posso contribuir para a comunidade Aspose.GIS?
Absolutamente! Participe das discussões e compartilhe suas experiências no [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).  

### P: Onde posso encontrar documentação detalhada do Aspose.GIS para .NET?
Explore a documentação completa [aqui](https://reference.aspose.com/gis/net/) para informações aprofundadas sobre Aspose.GIS for .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose