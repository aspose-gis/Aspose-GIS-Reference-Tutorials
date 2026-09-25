---
date: 2026-09-25
description: Aprenda como converter WKT para geometria de curva composta e adicionar
  line string no .NET usando Aspose.GIS. Este guia mostra a criação de geometria a
  partir de WKT com MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Criar Geometria MultiCurve
og_description: Aprenda como converter WKT para geometria de curva composta e adicionar
  line string no .NET usando Aspose.GIS. Este guia mostra a criação de geometria a
  partir de WKT com MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Converter WKT para geometria de curva composta com Aspose.GIS para .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Converter WKT para geometria de curva composta com Aspose.GIS para .NET
url: /pt/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter WKT para geometria de curva composta com Aspose.GIS para .NET

## Introdução
Se você precisar **converter WKT para geometria de curva composta** em uma aplicação GIS .NET, o Aspose.GIS torna o processo suave e confiável. Neste tutorial, percorreremos a criação de uma geometria `MultiCurve` a partir de strings Well‑Known Text (WKT) — perfeito para cenários onde você precisa **adicionar componentes de linha**, arcos circulares ou curvas compostas a um único recurso. Ao final, você terá um shapefile pronto para uso que demonstra como combinar várias geometrias de curva em um único objeto `MultiCurve`.

## Respostas rápidas
- **O que significa “converter WKT para geometria”?** Significa transformar uma representação textual WKT em um objeto de geometria concreto que as bibliotecas GIS podem manipular.  
- **Qual classe do Aspose.GIS lida com WKT?** `Geometry.FromText()` analisa strings WKT em instâncias de geometria.  
- **Posso adicionar uma linha simples?** Sim – basta incluir um WKT `LineString` como `"LineString (0 0, 1 0)"`.  
- **Qual formato de arquivo é usado no exemplo?** Um Shapefile (`.shp`) criado com o driver Shapefile.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.

## O que é “converter WKT para geometria”?
Converter WKT para geometria analisa o formato textual Well‑Known Text em um modelo de objeto em memória, como `MultiCurve` ou `LineString`. **`Geometry.FromText`** cria esses objetos instantaneamente, permitindo que você os armazene, consulte e renderize com qualquer ferramenta GIS que entenda o padrão OGC.

## Por que usar Aspose.GIS para criação de MultiCurve?
O Aspose.GIS permite criar **geometria de curva composta** em uma única chamada de API autocontida. Ele suporta três tipos avançados de curva (CircularString, CompoundCurve e CurveString) e processa conjuntos de dados de até 500 MB sem carregar o arquivo inteiro na memória, proporcionando um aumento de velocidade de 30 % em relação a bibliotecas concorrentes em cenários de lote.

## Pré‑requisitos
1. Compreensão básica da linguagem de programação C#.  
2. Visual Studio instalado (ou qualquer outra IDE .NET).  
3. Biblioteca Aspose.GIS para .NET – faça o download no [site da Aspose.GIS](https://releases.aspose.com/gis/net/).  
4. Familiaridade com conceitos espaciais como pontos, linhas e curvas.

## Importar namespaces
Para começar a trabalhar com Aspose.GIS para .NET, importe os namespaces necessários para seu projeto C#.

`Geometry` fornece métodos estáticos para analisar WKT em objetos de geometria.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Esses namespaces dão acesso às classes necessárias para criar e gerenciar a geometria `MultiCurve`.

## Guia passo a passo

### Etapa 1: Definir o diretório do documento e o nome do arquivo
Defina a pasta onde o shapefile será salvo. Substitua `"Your Document Directory"` pelo caminho real em sua máquina.

### Etapa 2: Inicializar um `VectorLayer` com o driver Shapefile
VectorLayer representa um conjunto de dados vetoriais, como um shapefile, e permite a leitura e gravação de geometrias.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
O objeto `VectorLayer` representa um conjunto de dados vetoriais (neste caso, um shapefile) ao qual você pode gravar geometrias.

### Etapa 3: Construir um novo recurso
Feature é um contêiner que contém uma geometria e seus valores de atributos.  
```csharp
var feature = layer.ConstructFeature();
```
Um recurso é um contêiner para dados de geometria e atributos.

### Etapa 4: Criar uma instância de geometria `MultiCurve`
`MultiCurve` é um tipo de geometria que agrega múltiplos componentes de curva em um único objeto espacial.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` pode conter várias geometrias de curva, permitindo combiná‑las em um único objeto espacial.

### Etapa 5: Adicionar geometrias de curva ao `MultiCurve`
Aqui nós **convertimos WKT para geometria** para três tipos diferentes de curva:
* uma **linha simples**,
* um arco circular (`CircularString`),
* e uma curva composta que mistura segmentos retos com um arco circular.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Etapa 6: Atribuir o `MultiCurve` ao recurso
Agora a geometria do recurso é o `MultiCurve` composto que acabamos de criar.  
```csharp
feature.Geometry = multiCurve;
```

### Etapa 7: Adicionar o recurso ao `VectorLayer`
O recurso é persistido no shapefile quando o bloco `using` termina.  
```csharp
layer.Add(feature);
```



## Problemas comuns e soluções
| Problema | Motivo | Correção |
|----------|--------|----------|
| **`ArgumentException` em `Geometry.FromText`** | Sintaxe WKT inválida | Verifique se a string WKT segue a especificação OGC (por exemplo, vírgulas entre coordenadas, parênteses corretos). |
| **Shapefile não criado** | `path` incorreto ou permissões de gravação ausentes | Certifique-se de que o diretório existe e que a aplicação tem permissão de gravação. |
| **Curvas aparecem como linhas retas em alguns visualizadores** | O visualizador não suporta curvas circulares/compostas | Use um visualizador GIS que entenda o tipo de geometria `ARC` (por exemplo, QGIS). |

## Perguntas frequentes

**Q: O Aspose.GIS para .NET é compatível com todas as versões do .NET Framework?**  
A: Sim, ele suporta .NET Framework, .NET Core, .NET Standard e .NET 5/6+.

**Q: Posso criar formatos de dados espaciais personalizados usando Aspose.GIS para .NET?**  
A: Absolutamente. A API permite ler, gravar e transformar muitos formatos padrão, e você pode estendê‑la para formatos proprietários.

**Q: O Aspose.GIS fornece recursos de análise espacial?**  
A: Sim, inclui cálculos de distância, detecção de interseção, buffer e outras operações geométricas.

**Q: Existe uma versão de avaliação disponível para Aspose.GIS para .NET?**  
A: Sim, você pode baixar uma avaliação gratuita no [site da Aspose.GIS](https://releases.aspose.com/gis/net/) para explorar seus recursos antes de comprar.

**Q: Como posso obter ajuda se encontrar problemas?**  
A: Entre em contato pelos fóruns da comunidade Aspose.GIS ou consulte os recursos oficiais de suporte incluídos com sua licença.

---

**Última atualização:** 2026-09-25  
**Testado com:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Criar Geometria de Curva Composta](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Como contar pontos a partir de WKT com Aspose.GIS para .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Criar geometria MultiLineString usando Aspose.GIS para .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}