---
date: 2026-05-21
description: Aprenda como criar file geodatabase, definir Object ID e nomes dos campos
  de geometria, adicionar geometria e recuperar dados da camada usando Aspose.GIS
  for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Especificar Object ID e Nomes dos Campos de Geometria
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Criar file geodatabase – Especificar Object ID e Nomes dos Campos de Geometria
url: /pt/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Geodatabase de Arquivo – Especificar Nomes dos Campos Object ID e Geometry

## Introdução
Neste tutorial prático, você **criará um file geodatabase** com Aspose.GIS para .NET, e então especificará os nomes dos campos Object ID e Geometry para que seus dados espaciais sejam indexados corretamente. Seja construindo uma ferramenta GIS de desktop ou um backend de serviço web, dominar estas etapas fornece uma base sólida para qualquer projeto geoespacial.

## Respostas Rápidas
- **Qual é a primeira linha de código?** `var geoDb = new GeoDatabase(path, options);`  
- **Qual propriedade define a coluna de geometria?** `GeometryFieldName` em `GeoDatabaseCreateOptions`.  
- **Posso definir um campo Object ID personalizado?** Sim – use `ObjectIdFieldName` ao criar o banco de dados.  
- **Preciso de uma licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença permanente é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## O que é criar file geodatabase?
**Create file geodatabase** significa gerar um contêiner GIS físico (geralmente uma pasta com arquivos internos) que armazena camadas vetoriais, atributos e índices espaciais. Ele fornece um conjunto de dados portátil e autocontido que pode ser aberto por qualquer aplicação compatível com GIS. Pode ser usado por qualquer software GIS que suporte o formato File Geodatabase, facilitando a troca de dados.

## Por que definir nomes dos campos Object ID e Geometry?
Definir explicitamente os nomes dos campos Object ID e Geometry permite que o Aspose.GIS crie índices eficientes, acelere as consultas e garanta que cada feição possa ser identificada de forma única. Em benchmarks, consultas indexadas são até **3× mais rápidas** em bancos de dados onde esses campos são definidos.

## Pré-requisitos
- Aspose.GIS para .NET instalado – faça o download a partir de [here](https://releases.aspose.com/gis/net/).  
- Uma pasta gravável na sua máquina para atuar como diretório de documentos.  
- Um ambiente de desenvolvimento .NET (Visual Studio, VS Code ou a .NET CLI).  

## Como criar file geodatabase?
`GeoDatabase` é uma classe que representa um geodatabase baseado em arquivo no disco. Carregue o namespace Aspose.GIS, defina um caminho de pasta e instancie um `GeoDatabase` com opções personalizadas. Esta única etapa cria o geodatabase baseado em arquivo no disco. O objeto `GeoDatabaseCreateOptions` permite especificar tanto a coluna Object ID (`ObjectIdFieldName`) quanto a coluna de geometria (`GeometryFieldName`). Aspose.GIS suporta **mais de 30 formatos espaciais** e pode lidar com arquivos de até **2 GB** sem carregar todo o conjunto de dados na memória.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Como definir objectid?
`ObjectIdFieldName` é uma propriedade de `GeoDatabaseCreateOptions` que especifica o nome da coluna usada como identificador único para cada feição. `ObjectIdFieldName` informa ao mecanismo qual atributo identifica exclusivamente cada feição. Escolha um nome curto e alfanumérico (por exemplo, `"FeatureId"`). Quando você posteriormente adicionar ou consultar feições, essa coluna será usada automaticamente para buscas rápidas.

```csharp
string dataDir = "Your Document Directory";
```

## Como adicionar geometria?
`GeometryFieldName` é uma propriedade de `GeoDatabaseCreateOptions` que determina qual coluna de atributo armazena os objetos de geometria para cada feição. `GeometryFieldName` define a coluna que armazena os dados de forma (pontos, linhas, polígonos). Ao nomeá‑la explicitamente, você evita o nome padrão `"Shape"` e mantém seu esquema consistente em várias camadas.

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Como criar uma camada e adicionar camada de feição ponto?
`CreateLayer` é um método de `GeoDatabase` que cria uma nova camada vetorial com um nome especificado, opções e sistema de referência espacial. `Feature` é um objeto que representa um único registro espacial, contendo geometria e valores de atributos. `Point` é uma classe de geometria que representa uma única localização definida pelas coordenadas X (longitude) e Y (latitude). Após o banco de dados estar pronto, crie uma nova camada com `CreateLayer`. Em seguida, construa um objeto `Feature`, atribua uma geometria `Point` e adicione‑a à camada. Isso demonstra **como adicionar geometria** e **como criar camada** em um fluxo único.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Como recuperar dados da camada?
`OpenLayer` é um método de `GeoDatabase` que abre uma camada existente para leitura ou edição, retornando um objeto `Layer`. Abra a camada com `OpenLayer`, então itere sobre sua coleção `Features` ou consulte pelo campo Object ID personalizado. Isso demonstra **recuperar dados da camada** usando o identificador que você definiu anteriormente.

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Problemas Comuns e Soluções
- **Erro de coluna Object ID ausente** – Certifique-se de que `ObjectIdFieldName` esteja definido *antes* de chamar `CreateLayer`.  
- **Geometria não exibida** – Verifique se o tipo de geometria (por exemplo, `Point`) corresponde ao sistema de referência espacial da camada.  
- **Bloqueio de arquivo no Windows** – Feche todos os objetos `GeoDatabase` ou envolva‑os em declarações `using` para liberar os manipuladores de arquivo.

## Perguntas Frequentes

**Q: Posso usar Aspose.GIS para .NET em minhas aplicações web?**  
A: Sim, a biblioteca funciona em projetos ASP.NET Core, MVC e Web API, fornecendo funcionalidade GIS completa no lado do servidor.

**Q: Existe uma versão de avaliação disponível antes da compra?**  
A: Sim, você pode explorar os recursos do Aspose.GIS para .NET com uma avaliação gratuita disponível [here](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.GIS para .NET?**  
A: Você pode obter uma licença temporária [here](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

**Q: Quais sistemas de referência espacial o Aspose.GIS para .NET suporta?**  
A: O produto suporta códigos EPSG de 1‑9999, incluindo WGS 84, Web Mercator e muitos sistemas de coordenadas nacionais.

**Q: Onde posso buscar ajuda ou discutir questões relacionadas ao Aspose.GIS?**  
A: Visite o fórum Aspose.GIS [here](https://forum.aspose.com/c/gis/33) para suporte e discussões da comunidade.

---

**Última Atualização:** 2026-05-21  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Camada Vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Como Definir Grade para Camada File GDB no Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Ler Object ID da Camada File GDB no Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}