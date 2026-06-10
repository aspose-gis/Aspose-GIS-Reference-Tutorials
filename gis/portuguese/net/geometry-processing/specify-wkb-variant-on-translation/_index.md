---
date: 2026-06-10
description: Aprenda como criar geometria linestring no .NET e converter geometria
  para WKB usando o Aspose.GIS para .NET com a variante ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Especificar Variante WKB na Tradução
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Criar Geometria Linestring e Variante WKB no Aspose.GIS para .NET
url: /pt/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Geometria Linestring e Variante WKB no Aspose.GIS para .NET

## Introdução
If you need to **create linestring geometry .NET** and then translate that geometry into a binary form, Aspose.GIS for .NET gives you a clean, high‑performance API that works across .NET Framework, .NET Core, and .NET 5/6+. In this tutorial we’ll walk through every step—from importing namespaces to writing an EWKB file—so you can preserve SRID information and integrate GIS data into PostgreSQL/PostGIS or any binary‑based workflow without hassle.

## Respostas Rápidas
- **O que significa WKB?** Well‑Known Binary, uma representação binária compacta de objetos geométricos.  
- **Qual variante WKB armazena SRID?** A variante `ExtendedPostGis` (EWKB) incorpora o SRID diretamente no binário.  
- **Preciso de uma licença?** Uma licença temporária ou completa do Aspose.GIS é necessária para implantações em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos para um exemplo básico.

## O que é uma Geometria Linestring?
A linestring geometry is a simple shape made of an ordered list of points connected by straight line segments. It’s the go‑to representation for linear features such as roads, pipelines, or river paths in spatial databases.

## Por que especificar uma variante WKB?
Using the correct WKB variant guarantees that critical metadata—especially the Spatial Reference System Identifier (SRID)—travels with your geometry. The `ExtendedPostGis` (EWKB) variant stores the SRID inside the binary payload, enabling seamless round‑tripping with PostGIS, Oracle Spatial, or any system that expects SRID‑aware binaries.

## Pré-requisitos
Before you start, make sure you have the following:

### Instalando Aspose.GIS para .NET
1. Baixe o Aspose.GIS: Visite o [download link](https://releases.aspose.com/gis/net/) para obter o pacote mais recente.  
2. Adicione o pacote NuGet ao seu projeto (por exemplo, `Install-Package Aspose.GIS`).  

### Familiaridade com Programação C#
- Compreensão básica da sintaxe C# e da estrutura do projeto.  
- Capacidade de executar um projeto console ou de biblioteca de classes .NET.

## Importar Namespaces
The `Aspose.GIS` namespace gives you access to all geometry‑related classes.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

These namespaces provide the core GIS functionality, including geometry creation, transformation, and binary serialization.

## Como criar geometria linestring?
To create a linestring, instantiate a `Linestring` object with an ordered list of coordinate pairs, set its SRID if needed, and then serialize it to the desired WKB variant. The process involves three steps: building the geometry, choosing the `ExtendedPostGis` variant to retain SRID, and writing the resulting byte array to a file.

### Etapa 1: Criando um Objeto de Geometria
The `Geometry` class is Aspose.GIS's base type that represents any spatial object in memory.  
Linestring represents a series of connected points forming a linear geometry.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In this step we instantiate a `Linestring` with a collection of coordinate pairs that model a simple road segment.

### Etapa 2: Gerando Representação WKB
`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to include SRID in the output binary.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Here we call the `AsBinary` method, passing the EWKB variant, which returns a `byte[]` containing the full binary representation.

### Etapa 3: Gravando no Arquivo
`File.WriteAllBytes` writes the binary array to disk.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
The resulting file (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB` function.

## Problemas Comuns e Soluções
| Problema | Razão | Solução |
|----------|-------|----------|
| **Arquivo vazio** | `Path.Combine` aponta para um diretório inexistente. | Certifique-se de que o diretório de destino exista ou crie-o com `Directory.CreateDirectory`. |
| **SRID incorreto** | Usar o padrão `WkbVariant.Standard` remove o SRID. | Sempre use `WkbVariant.ExtendedPostGis` quando a preservação do SRID for necessária. |
| **Exceção de licença** | Executar sem uma licença válida em produção. | Aplique uma licença temporária ou completa antes de executar o código em um ambiente de produção. |

## Perguntas Frequentes
**P: Posso usar o arquivo EWKB com PostGIS?**  
R: Sim, a variante `ExtendedPostGis` produz EWKB que inclui SRID, que o PostGIS lê diretamente via `ST_GeomFromEWKB`.  

**P: É possível ler um arquivo WKB de volta para um objeto de geometria?**  
R: Absolutamente. Use `Geometry.FromBinary(byteArray)` para reconstruir a geometria a partir de sua forma binária.  

**P: A biblioteca suporta outros tipos de geometria, como polígonos?**  
R: Sim, o Aspose.GIS lida com pontos, linestrings, polígonos, multipolígonos e muitos outros tipos espaciais.  

**P: Como especificar um SRID diferente ao criar a geometria?**  
R: Defina a propriedade `SRID` no objeto de geometria antes de chamar `AsBinary`, por exemplo, `linestring.SRID = 4326;`.  

**P: Este código funciona no .NET Core?**  
R: Sim, a mesma API funciona em .NET Framework, .NET Core e .NET 5/6 sem modificações.

---

**Última atualização:** 2026-06-10  
**Testado com:** Aspose.GIS for .NET 23.9 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Traduzindo Geometria para Formato WKB com Aspose.GIS para .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Especificar Variante WKT na Tradução usando Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Criar Geometria MultiLineString usando Aspose.GIS para .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}