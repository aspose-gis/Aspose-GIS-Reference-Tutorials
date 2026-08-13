---
date: 2026-08-13
description: Aprenda a calcular o comprimento de geometria .NET usando Aspose.GIS
  para um manuseio eficiente de dados espaciais. Inclui exemplos de obter comprimento
  de linha C# e calcular comprimento de linha C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Obter Comprimento de Geometria
og_description: Calcule o comprimento de geometria .NET usando Aspose.GIS. Obtenha
  exemplos de comprimento de linha C# e perímetro de polígono em um guia conciso e
  de alto desempenho para desenvolvedores .NET.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Calcule o comprimento de geometria .NET com Aspose.GIS – Medições espaciais
  rápidas
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Como Calcular o Comprimento de Geometria .NET com Aspose.GIS
url: /pt/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como calcular o comprimento da geometria .NET com Aspose.GIS

## Introdução
Se você está procurando uma maneira clara e prática de **calcular o comprimento da geometria .NET**, você está no lugar certo. Aspose.GIS para .NET oferece um conjunto rico de APIs focadas em GIS que tornam os cálculos espaciais — como medir o comprimento de linhas ou o perímetro de polígonos — simples e de alto desempenho. Neste tutorial, percorreremos todo o processo, desde a configuração do ambiente até a escrita do código C# que retorna valores de comprimento precisos.

## Respostas Rápidas
- **O que “GetLength()” retorna?** Para linhas, retorna o comprimento da linha; para polígonos, retorna o perímetro.  
- **Qual namespace é necessário?** `Aspose.Gis.Geometries`.  
- **Posso usar isso com .NET 6?** Sim, Aspose.GIS suporta .NET 5, .NET 6 e versões posteriores.  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para avaliação; uma licença é necessária para produção.  
- **O cálculo considera unidades?** O comprimento é retornado nas unidades do sistema de coordenadas (por exemplo, metros para CRS projetado).

## O que é comprimento de geometria?
Geometry.GetLength() calcula a distância linear total de um objeto de geometria com base em seus valores de coordenadas. Para um LineString, soma as distâncias entre vértices consecutivos, retornando o comprimento da linha. Quando aplicado a um Polygon, soma os comprimentos de todas as arestas, fornecendo efetivamente o perímetro da forma.

## Por que usar Aspose.GIS para cálculos de comprimento?
Aspose.GIS oferece uma biblioteca .NET totalmente gerenciada que realiza cálculos espaciais sem exigir binários nativos, tornando a implantação simples em Windows, Linux e macOS. Suporta mais de cinquenta sistemas de referência de coordenadas, fornecendo resultados de alta precisão em double‑precision mesmo para linhas de centenas de quilômetros, e integra‑se perfeitamente com projetos .NET 5/6/7, garantindo desempenho e precisão consistentes.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem o seguinte:

### 1. Biblioteca Aspose.GIS para .NET
Primeiramente, você precisa ter a biblioteca Aspose.GIS para .NET instalada em seu ambiente de desenvolvimento. Se ainda não o fez, pode baixá‑la na página da [Documentação do Aspose.GIS para .NET](https://reference.aspose.com/gis/net/).

### 2. Ambiente de desenvolvimento .NET
Certifique‑se de que você tem um ambiente de desenvolvimento .NET configurado em sua máquina. Isso inclui ter o Visual Studio ou qualquer outra IDE compatível instalada.

### 3. Compreensão básica de C#
Uma compreensão básica da linguagem de programação C# é essencial para acompanhar este tutorial.

## Importar namespaces
Para utilizar as funcionalidades fornecidas pelo Aspose.GIS para .NET, você precisa importar os namespaces necessários ao seu projeto C#.

### Importar namespace Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Como obter o comprimento da linha C#
Um `LineString` no Aspose.GIS representa uma série de dois ou mais pontos conectados por segmentos de linha reta, modelando recursos lineares como estradas, rios ou linhas de utilidade dentro de um determinado sistema de referência de coordenadas.  
Após construir o `LineString` com os vértices desejados, invocar o método `GetLength()` retorna a distância total medida nas unidades do CRS da geometria, permitindo obter rapidamente medições precisas de linhas para roteamento, análises baseadas em distância ou fins de relatório, podendo ser processado ou armazenado conforme necessário.

### Etapa 1: Criar objetos de geometria
Para começar, crie os objetos de geometria que representam as formas para as quais você deseja calcular o comprimento. Isso pode incluir linhas, polígonos ou quaisquer outras formas geométricas.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Etapa 2: Calcular o comprimento da linha em C#
Depois de criar a geometria da linha, você pode calcular seu comprimento usando o método `GetLength()`. Isso demonstra **calcular o comprimento da linha c#** em uma única linha de código.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Como calcular o comprimento da linha C# para polígonos
Um `Polygon` no Aspose.GIS consiste em um `LinearRing` externo que define seu contorno e anéis internos opcionais para furos, representando recursos de área como lotes, lagos ou zonas administrativas dentro de uma referência espacial específica.  
Crie o `LinearRing` externo fornecendo os pontos de canto do polígono, depois instancie um `Polygon` com esse anel; chamar `GetLength()` no polígono calcula o perímetro total, o que é útil para tarefas como estimativa de comprimento de cercas, relatórios de limites ou conversão de valores de perímetro para outras unidades.

### Etapa 3: Criar geometria de polígono
Da mesma forma, você pode criar objetos de geometria de polígono usando as classes `Polygon` e `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Etapa 4: Obter o comprimento de um polígono
Para polígonos, o método `GetLength()` retorna o perímetro, que é efetivamente o **como obter o comprimento** da forma.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Problemas comuns e soluções
| Problema | Solução |
|----------|---------|
| **Comprimento zero inesperado** | Verifique se o sistema de coordenadas da geometria corresponde aos dados fornecidos; pontos duplicados podem causar segmentos de comprimento zero. |
| **Unidades incorretas** | Lembre‑se de que `GetLength()` retorna valores nas unidades do CRS. Converta para metros/pés se necessário. |
| **Desempenho com grandes conjuntos de dados** | Reutilize objetos de geometria quando possível e evite criar milhares de pontos temporários dentro de loops apertados. |

## Perguntas frequentes

**Q: O Aspose.GIS para .NET é compatível com todos os frameworks .NET?**  
A: Aspose.GIS para .NET é compatível com .NET Framework 4.6.1 ou versões posteriores, bem como .NET 5/6/7.

**Q: Posso experimentar o Aspose.GIS para .NET antes de comprar?**  
A: Sim, você pode obter uma avaliação gratuita do Aspose.GIS para .NET [aqui](https://releases.aspose.com/).

**Q: Onde posso encontrar suporte para Aspose.GIS para .NET?**  
A: Você pode encontrar suporte e assistência no fórum da comunidade Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33).

**Q: Como posso obter uma licença temporária para Aspose.GIS para .NET?**  
A: Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Posso personalizar o formato de saída para cálculos de comprimento de geometria?**  
A: Sim, Aspose.GIS para .NET oferece várias opções de formatação para personalizar o formato de saída conforme suas necessidades.

## Conclusão
Neste tutorial, abordamos **como calcular o comprimento da geometria .NET** para geometria de linhas e polígonos usando Aspose.GIS para .NET. Seguindo os exemplos passo a passo, você agora pode integrar medições espaciais precisas em qualquer aplicação .NET, seja uma ferramenta GIS de desktop, um serviço web ou um pipeline de processamento de dados backend.

---

**Última atualização:** 2026-08-13  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Aprenda a criar geometria LineString com Aspose.GIS para .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Como calcular área com Aspose.GIS para .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [Como criar geometria Point e obter o tipo de geometria com Aspose.GIS para .NET](/gis/net/geometry-analysis/get-geometry-type/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}