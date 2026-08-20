---
date: 2026-06-30
description: Aprenda como criar camada vetorial em um File Geodatabase usando Aspose.GIS
  para .NET. Gerencie dados geoespaciais com referência espacial WGS84 e opções de
  file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Criar File GDB com Camada Única
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Criar Camada Vetorial em File GDB – Tutorial Aspose.GIS .NET
url: /pt/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial em File GDB

## Introdução
Se você precisa **criar camada vetorial** dentro de um File Geodatabase (GDB) e gerenciar dados geoespaciais de forma eficiente, o Aspose.GIS para .NET oferece uma abordagem limpa, code‑first. Neste guia passo a passo, mostraremos como escrever um recurso de linha, configurar as opções do file GDB e trabalhar com a referência espacial WGS84 — tudo em algumas linhas de C#. Ao final, você será capaz de contar os recursos em uma camada e integrar o GDB resultante em qualquer fluxo de trabalho de mapeamento ou análise .NET.

## Respostas Rápidas
- **O que significa “criar camada vetorial”?** Significa adicionar um novo conjunto de dados vetoriais (pontos, linhas ou polígonos) a um arquivo de geodatabase.  
- **Qual biblioteca devo usar?** Aspose.GIS para .NET fornece suporte completo para criação e edição de File GDB.  
- **Preciso de uma licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso definir a referência espacial?** Sim – use `SpatialReferenceSystem.Wgs84` para o datum WGS84 comum.  
- **Quantas linhas de código?** Menos de 30 linhas para criar o GDB, adicionar um recurso de linha e ler novamente a contagem de recursos.

## O que é uma operação “criar camada vetorial”?
Criar uma camada vetorial define uma nova tabela em um geodatabase que armazena objetos geométricos (pontos, linhas, polígonos) e seus atributos. Cada linha representa um recurso, e a coluna de geometria contém sua forma. No Aspose.GIS você a cria instanciando um `FeatureClass` dentro de um `FileGdbDataSource` e especificando o tipo de geometria.

## Por que usar Aspose.GIS para criar uma camada vetorial?
Aspose.GIS elimina dependências externas e suporta **50+** formatos GIS, tornando‑se uma solução única para desenvolvedores .NET.  
Ele fornece compressão integrada de file GDB (até 70 % de redução para dados vetoriais típicos), indexação espacial e suporte completo ao WGS84 pronto para uso. A biblioteca funciona em .NET Framework 4.6+, .NET Core 2.0+ e .NET 5/6, permitindo direcionar qualquer ambiente Windows moderno ou multiplataforma sem bibliotecas nativas adicionais.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Aspose.GIS para .NET** – faça o download na [página de download do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).  
2. **Um ambiente de desenvolvimento .NET** – Visual Studio, Rider ou a CLI `dotnet`.  
3. **Uma pasta** onde o File GDB será criado (chamaremos de *Your Document Directory*).

## Importar Namespaces
As instruções `using` trazem os tipos necessários para o escopo.  

O namespace `Document` fornece os objetos GIS principais, enquanto `System.IO` lida com caminhos de arquivos.

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

## Etapa 1: Configurar seu Diretório de Documentos
Substitua `"Your Document Directory"` pelo caminho absoluto onde você deseja que o File GDB seja criado.  
Criar o diretório antecipadamente evita o erro “File not found” que frequentemente atrapalha novos usuários.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar um File Geodatabase com uma Única Camada
FileGdbOptions é uma classe que permite configurar compressão, indexação espacial e outras opções para um File Geodatabase.  
Este trecho **cria uma camada vetorial** usando `FileGdbOptions`, grava um recurso de linha simples e o armazena em um File GDB que utiliza a **referência espacial WGS84**.

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
`FileGdbDataSource` é o ponto de entrada para criar e abrir File Geodatabases.  
`FeatureClass` representa uma camada vetorial dentro de um geodatabase e fornece acesso aos seus recursos.  
Aqui nós **contamos os recursos na camada** abrindo o conjunto de dados e imprimindo o número de recursos – neste caso, `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Como verificar se a camada foi criada corretamente?
Abra o geodatabase com `FileGdbDataSource.Open` e consulte o `FeatureClass`. A propriedade `Count` retorna o número total de recursos, confirmando que a linha foi persistida. Esta etapa de verificação rápida ajuda a detectar problemas cedo, especialmente ao automatizar importações em massa.

## Problemas Comuns e Soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **`File not found`** | Variável `path` incorreta | Verifique se `dataDir` aponta para uma pasta existente e se `path` a combina com um nome de arquivo, por exemplo, `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Usando um tipo de geometria não permitido no File GDB | Use `Point`, `LineString` ou `Polygon` para camadas básicas. |
| **`License not set`** | Executando sem uma licença válida em produção | Registre sua licença com `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Perguntas Frequentes
### Posso usar Aspose.GIS para .NET em meus projetos .NET existentes?
Sim, o Aspose.GIS para .NET pode ser integrado perfeitamente aos seus projetos .NET existentes.

### Existe uma versão de avaliação disponível para Aspose.GIS para .NET?
Sim, você pode explorar os recursos do Aspose.GIS para .NET baixando a [versão de avaliação gratuita](https://releases.aspose.com/).

### Onde posso encontrar documentação detalhada do Aspose.GIS para .NET?
Consulte a [documentação](https://reference.aspose.com/gis/net/) para informações abrangentes sobre o Aspose.GIS para .NET.

### Como posso obter suporte para Aspose.GIS para .NET?
Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade e assistência.

### Licenças temporárias estão disponíveis para Aspose.GIS para .NET?
Sim, você pode obter uma [licença temporária](https://purchase.aspose.com/temporary-license/) para o Aspose.GIS para .NET.

---

**Última atualização:** 2026-06-30  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Conjunto de Dados File Geodatabase .NET com Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Criar Camada Vetorial e Definir Sistema de Referência Espacial da Camada](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Como Excluir Camada de Conjunto de Dados File GDB com Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}