---
date: 2026-01-10
description: Aprenda a criar camada vetorial em um File Geodatabase usando Aspose.GIS
  para .NET. Gerencie dados geoespaciais com referência espacial WGS84 e opções de
  arquivo gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Criar camada vetorial no File GDB – Tutorial Aspose.GIS .NET
url: /pt/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial em File GDB

## Introdução
Se você precisa **create vector layer** dentro de um File Geodatabase (GDB) e gerenciar dados geoespaciais de forma eficiente, o Aspose.GIS for .NET oferece uma abordagem limpa, code‑first. Neste guia passo a passo, mostraremos como escrever um recurso de linha, configurar as opções de file gdb e trabalhar com a **spatial reference WGS84** — tudo em algumas linhas de C#. Ao final, você poderá contar os recursos em uma camada e integrar o GDB resultante em qualquer fluxo de trabalho de mapeamento ou análise .NET.

## Respostas Rápidas
- **O que significa “create vector layer”?** Significa adicionar um novo conjunto de dados vetoriais (pontos, linhas ou polígonos) a um arquivo de geodatabase.  
- **Qual biblioteca devo usar?** O Aspose.GIS for .NET fornece suporte total para criação e edição de File GDB.  
- **Preciso de licença para desenvolvimento?** Uma versão de avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso definir a referência espacial?** Sim – use `SpatialReferenceSystem.Wgs84` para o datum WGS84 comum.  
- **Quantas linhas de código?** Menos de 30 linhas para criar o GDB, adicionar um recurso de linha e ler novamente a contagem de recursos.

## O que é uma operação “create vector layer”?
Criar uma camada vetorial significa definir uma nova tabela dentro de um geodatabase que armazena objetos geométricos (pontos, linhas, polígonos) junto com seus atributos. Esta operação é a base para qualquer aplicação baseada em GIS que precise **manage geospatial data**.

## Por que usar Aspose.GIS para criar uma camada vetorial?
- **Zero dependências externas** – a API funciona pronta para uso em .NET Framework, .NET Core e .NET 5/6.  
- **Suporte total para File GDB** – você pode configurar `FileGdbOptions` para controlar compressão, indexação espacial e mais.  
- **Manipulação integrada de referência espacial** – basta passar `SpatialReferenceSystem.Wgs84` para trabalhar no sistema de coordenadas global.  
- **API simples** – escreva um recurso de linha, adicione‑o a uma camada e recupere a contagem de recursos com apenas algumas chamadas de método.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Aspose.GIS for .NET** – faça o download na [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Um ambiente de desenvolvimento .NET** – Visual Studio, Rider ou a CLI `dotnet`.  
3. **Uma pasta** onde o File GDB será criado (chamaremos de *Your Document Directory*).

## Importar Namespaces
Adicione as declarações `using` necessárias no início do seu arquivo C#:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Etapa 1: Configurar Seu Diretório de Documentos
Substitua `"Your Document Directory"` pelo caminho absoluto onde você deseja que o File GDB seja criado.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar um File Geodatabase com uma Única Camada
Este trecho **creates a vector layer** usando `FileGdbOptions`, grava um recurso de linha simples e o armazena em um File GDB que usa a **spatial reference WGS84**.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## Etapa 3: Abrir o File Geodatabase e Recuperar Informações da Camada
Aqui nós **count features layer** ao abrir o conjunto de dados e imprimir o número de recursos – neste caso, `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Problemas Comuns e Soluções
| Problema | Motivo | Correção |
|----------|--------|----------|
| **`File not found`** | Variável `path` incorreta | Verifique se `dataDir` aponta para uma pasta existente e se `path` a combina com um nome de arquivo, por exemplo, `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Usando um tipo de geometria não permitido no File GDB | Use apenas `Point`, `LineString` ou `Polygon` para camadas básicas. |
| **`License not set`** | Executando sem uma licença válida em produção | Registre sua licença com `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Perguntas Frequentes
### Posso usar Aspose.GIS for .NET em meus projetos .NET existentes?
Sim, Aspose.GIS for .NET pode ser integrado perfeitamente em seus projetos .NET existentes.

### Existe uma versão de avaliação disponível para Aspose.GIS for .NET?
Sim, você pode explorar os recursos do Aspose.GIS for .NET baixando a [free trial version](https://releases.aspose.com/).

### Onde posso encontrar documentação detalhada para Aspose.GIS for .NET?
Consulte a [documentation](https://reference.aspose.com/gis/net/) para informações abrangentes sobre Aspose.GIS for .NET.

### Como posso obter suporte para Aspose.GIS for .NET?
Visite o [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) para suporte da comunidade e assistência.

### Licenças temporárias estão disponíveis para Aspose.GIS for .NET?
Sim, você pode obter uma [temporary license](https://purchase.aspose.com/temporary-license/) para Aspose.GIS for .NET.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}