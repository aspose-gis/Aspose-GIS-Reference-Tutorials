---
title: Crie arquivo GDB com camada única
linktitle: Crie arquivo GDB com camada única
second_title: API Aspose.GIS .NET
description: Desbloqueie o potencial do gerenciamento de dados geoespaciais em .NET com Aspose.GIS. Aprenda como criar bancos de dados geográficos de arquivos e camadas passo a passo. Baixe Agora!
weight: 11
url: /pt/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie arquivo GDB com camada única

## Introdução
Você está pronto para elevar seus aplicativos geoespaciais com bancos de dados e camadas de arquivos robustos? Não procure mais, Aspose.GIS para .NET. Neste tutorial, orientaremos você no processo de criação de um File Geodatabase (GDB) com uma única camada usando Aspose.GIS for .NET. Aproveite o poder do gerenciamento e visualização de dados espaciais em seus aplicativos .NET sem esforço.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Aspose.GIS for .NET: Certifique-se de ter a biblioteca Aspose.GIS instalada. Você pode baixá-lo no[Página de download do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
2. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET funcional em sua máquina.
3. Diretório de documentos: Escolha ou crie um diretório em seu sistema onde você armazenará seus arquivos de dados geoespaciais.
## Importar namespaces
Para começar, você precisa importar os namespaces necessários em seu projeto .NET. Esses namespaces fornecerão acesso às funcionalidades do Aspose.GIS. Adicione as seguintes linhas no início do seu arquivo de código:
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
## Etapa 1: configure seu diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua “Seu diretório de documentos” pelo caminho para o diretório onde você deseja armazenar seus arquivos de dados geoespaciais.
## Etapa 2: Crie um arquivo geodatabase com uma única camada
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
Este trecho de código cria um arquivo Geodatabase com uma única camada e adiciona um recurso de linha a ele.
## Etapa 3: Abra o arquivo Geodatabase e recupere as informações da camada
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Saída: Contagem de recursos: 1
}
```
Nesta etapa, abrimos o arquivo Geodatabase criado, recuperamos a camada chamada “camada” e imprimimos a contagem de feições na camada.
## Conclusão
Parabéns! Você criou com sucesso um arquivo geodatabase com uma única camada usando Aspose.GIS for .NET. Explore com facilidade os vastos recursos de gerenciamento de dados espaciais em seus aplicativos.
## perguntas frequentes
### Posso usar o Aspose.GIS for .NET em meus projetos .NET existentes?
Sim, o Aspose.GIS for .NET pode ser perfeitamente integrado aos seus projetos .NET existentes.
### Existe uma versão de teste disponível para Aspose.GIS for .NET?
 Sim, você pode explorar os recursos do Aspose.GIS for .NET baixando o[versão de teste gratuita](https://releases.aspose.com/).
### Onde posso encontrar documentação detalhada para Aspose.GIS for .NET?
 Consulte o[documentação](https://reference.aspose.com/gis/net/) para obter informações abrangentes sobre Aspose.GIS for .NET.
### Como posso obter suporte para Aspose.GIS for .NET?
 Visite a[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoio e assistência comunitária.
### As licenças temporárias estão disponíveis para Aspose.GIS for .NET?
 Sim, você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para Aspose.GIS para .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
