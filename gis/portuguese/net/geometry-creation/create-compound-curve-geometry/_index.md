---
date: 2026-08-24
description: Aprenda a escrever linhas curvas e criar geometrias de curva composta
  em .NET com Aspose.GIS, permitindo o processamento preciso de dados geoespaciais.
keywords:
- write curved lines
- how to add curves
- create compound curve
- curve geometry .net
lastmod: 2026-08-24
linktitle: Como adicionar curvas – Geometria de curva composta
og_description: Escreva linhas curvas com Aspose.GIS em .NET para criar geometrias
  de curva composta precisas. Este guia mostra código passo a passo, armadilhas comuns
  e dicas de boas práticas para desenvolvedores GIS.
og_image_alt: Developer guide showing how to write curved lines using Aspose.GIS in
  a .NET project
og_title: Escreva linhas curvas com Aspose.GIS em .NET para dados GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to write curved lines and create compound curve geometries
    in .NET with Aspose.GIS, enabling precise geospatial data processing.
  headline: How to write curved lines using Aspose.GIS in .NET
  type: TechArticle
- description: Learn how to write curved lines and create compound curve geometries
    in .NET with Aspose.GIS, enabling precise geospatial data processing.
  name: How to write curved lines using Aspose.GIS in .NET
  steps:
  - name: define the output path
    text: Replace the placeholder path with a folder that exists on your machine.
  - name: create a vector layer
    text: A **vector layer** stores spatial features. **Definition anchor:** `VectorLayer`
      represents a container for features of a single geometry type and manages reading/writing
      of GIS files.
  - name: construct the compound curve feature
    text: Here we create a new `Feature` and an empty `CompoundCurve` that will hold
      the individual curve parts.
  - name: define component curves
    text: 'A `LineString` is a sequence of points connected by straight line segments.
      A `CircularString` defines a circular arc using three points: start, intermediate,
      and end. We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. **Definition anchor:** `Line'
  - name: add component curves to the compound curve
    text: Append each component in order so the geometry stays continuous and correctly
      oriented.
  - name: assign geometry to the feature
    text: The assembled `CompoundCurve` becomes the geometry of the feature we will
      store.
  - name: add the feature to the layer
    text: Write the feature into the Shapefile. When the `using` block ends, the file
      is closed and ready for any GIS application.
  type: HowTo
- questions:
  - answer: Yes, the library runs on .NET Framework, .NET Core, .NET Standard, and
      .NET 5/6+ without modification.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It handles Shapefile, GeoJSON, KML, GML, and more than 30
      additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the same API works in console apps, Windows services, ASP.NET Core
      web apps, and cloud‑based functions.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, perform geometric unions/intersections,
      and execute spatial queries directly on the geometry objects.
    question: Can I perform spatial analysis with Aspose.GIS?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions, share snippets, and learn from other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- write curved lines
- Aspose.GIS
- compound curve
- .NET GIS
- geospatial programming
title: Como escrever linhas curvas usando Aspose.GIS em .NET
url: /pt/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como escrever linhas curvas usando Aspose.GIS em .NET

## Introdução
Se você precisa **escrever linhas curvas** para mapas, roteamento ou qualquer análise espacial, o Aspose.GIS oferece uma API .NET limpa e totalmente gerenciada para criar essas geometrias. Neste tutorial você aprenderá como adicionar curvas, montá‑las em uma curva composta e exportar o resultado como Shapefile (ou qualquer outro formato suportado). As etapas são rápidas, o código é direto, e o resultado está pronto para uso em qualquer aplicação GIS.

## Respostas rápidas
- **Qual é o objetivo principal?** Escrever linhas curvas e agrupá‑las em uma única geometria de curva composta.  
- **Qual biblioteca realiza a tarefa?** Aspose.GIS para .NET, um toolkit GIS puro‑gerenciado.  
- **O que é necessário antes?** Visual Studio, o pacote NuGet Aspose.GIS e um projeto .NET 6 (ou superior).  
- **Quanto tempo leva um exemplo básico?** Aproximadamente 10‑15 minutos para executar de ponta a ponta.  
- **Quais formatos de saída são suportados?** Shapefile nativamente; o mesmo código funciona para GeoJSON, KML, GML e mais.

## O que é uma curva composta?
Uma **curva composta** é uma única geometria que une vários componentes curvos — linhas retas e arcos circulares — em um caminho contínuo. Ela permite modelar recursos como estradas sinuosas, curvas de rios ou qualquer elemento que não possa ser representado com precisão por uma linha reta simples.

## Por que usar Aspose.GIS para escrever linhas curvas?
Um `VectorLayer` representa um contêiner para recursos espaciais de um único tipo de geometria e lida com I/O de arquivos para formatos GIS.  
Um `CompoundCurve` é uma geometria que combina múltiplos componentes de linha e arco em uma forma contínua.  
Um `Feature` contém geometria e dados de atributos que podem ser armazenados em uma camada GIS.  

Aspose.GIS fornece uma API de geometria abrangente e totalmente gerenciada que permite aos desenvolvedores criar e manipular `LineString`, `CircularString` e `CompoundCurve` sem dependências externas. Ela abstrai o manuseio de formatos de arquivo, suporta runtimes .NET multiplataforma e garante operações de leitura/escrita de alto desempenho para dados GIS.

## Por que isso importa
Quando geometrias curvas são armazenadas com precisão, os renderizadores de mapas podem exibir transições suaves, e cálculos espaciais como comprimento, buffer ou análise de rede produzem resultados confiáveis. Isso melhora tanto a fidelidade visual quanto a precisão analítica para aplicações que vão de sistemas de navegação a modelagem ambiental. Representações corretas de linhas curvas aprimoram a qualidade visual do mapa e permitem cálculos espaciais precisos, como medição de distância, roteamento de rede e análise de proximidade. Dominar a escrita de linhas curvas eleva a fidelidade de qualquer solução .NET orientada a GIS.

## Casos de uso comuns
- **Redes de transporte:** Modelar rodovias, ferrovias ou ciclovias que contêm curvas suaves.  
- **Hidrologia:** Capturar meandros de rios que seguem arcos naturais.  
- **Planejamento urbano:** Definir limites de propriedade com trechos curvos.  
- **Símbolos personalizados:** Criar formas decorativas para legendas de mapa ou sobreposições de UI.

## Pré‑requisitos
- **Visual Studio** (qualquer edição recente).  
- **Aspose.GIS para .NET** – baixe na [página de download](https://releases.aspose.com/gis/net/).  
- Um projeto C# direcionado ao **.NET 6** (ou qualquer versão suportada).

## Importar namespaces
Os namespaces a seguir dão acesso às classes de geometria e I/O necessárias.

**Âncora de definição:** `Aspose.Gis` fornece os tipos GIS centrais; `Aspose.Gis.Geometries` contém classes de geometria como `LineString` e `CompoundCurve`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Como escrever linhas curvas usando Aspose.GIS?
O processo envolve definir um diretório de saída, criar um `VectorLayer`, montar um `CompoundCurve` adicionando partes `LineString` e `CircularString`, atribuir a geometria a um `Feature` e, finalmente, adicionar o recurso à camada. O bloco `using` garante que os recursos sejam liberados e o Shapefile seja gravado corretamente.

### Etapa 1: definir o caminho de saída
Substitua o caminho placeholder por uma pasta que exista na sua máquina.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Etapa 2: criar uma camada vetorial
Uma **camada vetorial** armazena recursos espaciais.  

**Âncora de definição:** `VectorLayer` representa um contêiner para recursos de um único tipo de geometria e gerencia a leitura/escrita de arquivos GIS.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Etapa 3: construir o recurso de curva composta
Aqui criamos um novo `Feature` e um `CompoundCurve` vazio que armazenará as partes individuais da curva.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Etapa 4: definir as curvas componentes
Um `LineString` é uma sequência de pontos conectados por segmentos de linha reta.  
Um `CircularString` define um arco circular usando três pontos: início, intermediário e fim.  

Preparamos cinco peças — dois `LineString` retos, dois arcos `CircularString` e um `LineString` final.  

**Âncora de definição:** `LineString` é uma sequência de pontos formando uma polilinha de linha reta, enquanto `CircularString` define um arco circular usando três pontos (início, intermediário, fim).  

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Etapa 5: adicionar as curvas componentes ao curve composto
Anexe cada componente na ordem para que a geometria permaneça contínua e corretamente orientada.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Etapa 6: atribuir a geometria ao recurso
O `CompoundCurve` montado torna‑se a geometria do recurso que será armazenado.

```csharp
feature.Geometry = compoundCurve;
```

### Etapa 7: adicionar o recurso à camada
Grave o recurso no Shapefile. Quando o bloco `using` termina, o arquivo é fechado e fica pronto para qualquer aplicação GIS.

```csharp
layer.Add(feature);
```

## Problemas comuns & dicas
- **Ordem das coordenadas:** Aspose.GIS espera `X Y` (longitude, latitude). Trocar a ordem inverte a geometria.  
- **Sintaxe do CircularString:** O ponto do meio deve estar no arco desejado; caso contrário a curva colapsa para uma linha reta.  
- **Sobrescrita de arquivo:** `VectorLayer.Create` sobrescreve um Shapefile existente sem aviso — use um nome de arquivo único durante o desenvolvimento.  
- **Dica de desempenho:** Para grandes volumes de dados, adicione recursos em lote ao invés de inseri‑los um a um dentro do bloco `using`.  
- **Dica profissional:** Reutilize a mesma instância de `CompoundCurve` para múltiplos recursos semelhantes; limpe seu conteúdo com `compoundCurve.Clear()` antes de repopular.

## Perguntas frequentes

**Q: Posso usar Aspose.GIS para .NET com outros frameworks .NET?**  
A: Sim, a biblioteca funciona em .NET Framework, .NET Core, .NET Standard e .NET 5/6+ sem modificações.

**Q: O Aspose.GIS suporta leitura e escrita de diferentes formatos de arquivos geoespaciais?**  
A: Absolutamente. Ele lida com Shapefile, GeoJSON, KML, GML e mais de 30 formatos adicionais.

**Q: O Aspose.GIS é adequado tanto para aplicações desktop quanto web?**  
A: Sim, a mesma API funciona em aplicativos de console, serviços Windows, apps web ASP.NET Core e funções em nuvem.

**Q: Posso realizar análises espaciais com Aspose.GIS?**  
A: Sim, você pode calcular distâncias, executar uniões/interseções geométricas e realizar consultas espaciais diretamente nos objetos de geometria.

**Q: Onde posso obter ajuda da comunidade para Aspose.GIS?**  
A: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para fazer perguntas, compartilhar trechos de código e aprender com outros desenvolvedores.

---

**Última atualização:** 2026-08-24  
**Testado com:** Aspose.GIS para .NET (última versão estável)  
**Autor:** Aspose

## Tutoriais relacionados

- [Como converter curvas em linhas com Aspose.GIS para .NET](/gis/net/geometry-processing/linearize-geometry/)
- [Aprenda a criar geometria LineString com Aspose.GIS para .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Criar geometria MultiLineString usando Aspose.GIS para .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}