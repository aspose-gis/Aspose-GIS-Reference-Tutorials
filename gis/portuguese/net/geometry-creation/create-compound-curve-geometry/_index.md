---
date: 2026-08-24
description: Aprenda a criar geometria de linha curva e adicionar curvas usando Aspose.GIS
  para .NET, permitindo o processamento preciso de dados geoespaciais.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Como Adicionar Curvas – Geometria de Curva Composta
og_description: Aprenda a criar geometria de linha curva usando Aspose.GIS para .NET.
  Este tutorial mostra passo a passo como adicionar curvas e construir curvas compostas
  em minutos.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Como criar geometria de linha curva com Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Como criar geometria de linha curva com Aspose.GIS
url: /pt/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar geometria de linha curva com Aspose.GIS

## Introdução
Neste guia você descobrirá **como criar geometria de linha curva** usando Aspose.GIS para .NET. Seja construindo mapas interativos, executando análises espaciais ou gerando conjuntos de dados GIS, dominar a capacidade de adicionar curvas permite modelar recursos do mundo real — como estradas sinuosas ou rios serpenteantes — com alta precisão. O tutorial orienta você em cada passo, desde a configuração do projeto até a exportação de uma geometria de curva composta reutilizável.

## Respostas rápidas
- **Qual é o objetivo principal?** Construir uma geometria de curva composta que combina linhas retas e arcos circulares.  
- **Qual biblioteca é usada?** Aspose.GIS para .NET.  
- **Pré‑requisitos?** Visual Studio, Aspose.GIS instalado e um projeto C# direcionado ao .NET 6 ou posterior.  
- **Tempo típico de implementação?** Cerca de 10‑15 minutos para um exemplo funcional.  
- **Formato de saída suportado?** Shapefile (o mesmo código também grava GeoJSON, KML e outros formatos).

## O que é uma curva composta?
Uma curva composta é uma única geometria composta por múltiplos componentes de curva conectados — `LineString`s retos e arcos circulares — unidos para formar uma forma mais complexa. É ideal quando uma única linha simples não pode representar com precisão um trajeto, como uma rodovia com curvas suaves ou um rio que segue um arco natural.

## Por que usar Aspose.GIS para adicionar curvas?
Aspose.GIS fornece uma **API de geometria rica** que suporta nativamente line strings, circular strings e curvas compostas, eliminando a necessidade de bibliotecas GIS externas. A biblioteca é **multiplataforma**, funcionando com .NET Framework 4.6+, .NET Core 2.0+, e .NET 5/6/7+. Ela **processa até 500 páginas de conjuntos de dados vetoriais sem carregar o arquivo inteiro na memória**, oferecendo operações rápidas e eficientes em memória. A exportação é simples: você pode gravar diretamente em Shapefile, GeoJSON, KML, GML e mais de 30 outros formatos.

## Por que isso importa
Adicionar curvas permite modelar recursos do mundo real com mais precisão, o que melhora a qualidade visual nas renderizações de mapas e aumenta a precisão em análises espaciais, como buscas de proximidade ou roteamento de redes. Dominar **como criar geometria de linha curva** eleva, portanto, a fidelidade de qualquer solução .NET orientada a GIS.

## Casos de uso comuns
- **Redes de transporte:** Modelar rodovias, ferrovias ou ciclovias com curvas suaves.  
- **Hidrologia:** Representar cursos de rios que seguem arcos naturais.  
- **Planejamento urbano:** Desenhar limites de propriedades que incluam trechos curvos.  
- **Símbolos personalizados:** Criar formas decorativas ou esquemáticas para legendas de mapas.

## Pré‑requisitos
- Visual Studio (qualquer edição recente).  
- Aspose.GIS para .NET baixado da [página de download](https://releases.aspose.com/gis/net/).  
- Um projeto C# direcionado ao .NET 6 (ou qualquer versão suportada).

## Importar namespaces
As diretivas `using` trazem os tipos necessários do Aspose.GIS para o escopo.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guia passo a passo para criar geometria de curva composta

### Etapa 1: definir o caminho de saída
Primeiro, especifique onde o Shapefile resultante será salvo. Substitua o placeholder por uma pasta válida em sua máquina.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Etapa 2: criar uma camada vetorial
`VectorLayer` representa uma camada espacial que contém recursos e suas geometrias dentro de um conjunto de dados GIS. O bloco `using` garante que o arquivo seja fechado corretamente após a gravação.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Etapa 3: construir o recurso de curva composta
A classe `CompoundCurve` é o objeto de nível superior do Aspose.GIS para uma geometria que consiste em múltiplas partes de curva conectadas. Aqui instanciamos uma curva composta vazia que receberá posteriormente componentes individuais.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Etapa 4: definir curvas componentes
Preparamos cinco partes — duas `LineString`s retas, duas arcos `CircularString` e uma `LineString` final. `LineString` representa uma linha reta simples definida por uma lista ordenada de pontos. `CircularString` é a representação do Aspose.GIS de um arco circular definido por três pontos (início, meio, fim) que estão na mesma circunferência.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Etapa 5: adicionar curvas componentes à curva composta
Cada componente é anexado em ordem, preservando a continuidade e a orientação. O método `Add` valida automaticamente que o ponto final de um segmento corresponde ao ponto inicial do próximo.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Etapa 6: atribuir geometria ao recurso
Agora o `CompoundCurve` montado torna‑se a geometria do recurso que armazenaremos na camada.

```csharp
feature.Geometry = compoundCurve;
```

### Etapa 7: adicionar o recurso à camada
Finalmente, gravamos o recurso no Shapefile. Quando o bloco `using` termina, o arquivo é fechado e fica pronto para uso em qualquer aplicação GIS.

```csharp
layer.Add(feature);
```

## Problemas comuns e dicas
- **Ordem das coordenadas:** Aspose.GIS espera coordenadas na ordem `X Y` (longitude, latitude). Trocar a ordem inverte a geometria.  
- **Sintaxe do CircularString:** O ponto do meio deve estar no arco desejado; caso contrário a curva colapsa em uma linha reta.  
- **Sobrescrita de arquivo:** `VectorLayer.Create` sobrescreve um Shapefile existente sem aviso — use um nome de arquivo exclusivo durante o desenvolvimento.  
- **Desempenho:** Para grandes conjuntos de dados, adicione recursos em lote em vez de inseri‑los um a um dentro do bloco `using`.  
- **Dica profissional:** Reutilize a mesma instância de `CompoundCurve` ao criar muitos recursos semelhantes; chame `compoundCurve.Clear()` antes de repovoar para reduzir alocações.

## Perguntas frequentes

**Q: Posso usar Aspose.GIS para .NET com outros frameworks .NET?**  
A: Sim, Aspose.GIS funciona com .NET Framework, .NET Core e .NET Standard, cobrindo versões de 4.6 até .NET 7.

**Q: O Aspose.GIS suporta leitura e gravação de diferentes formatos de arquivos geoespaciais?**  
A: Absolutamente. Ele lê e grava Shapefile, GeoJSON, KML, GML e mais de 30 formatos adicionais.

**Q: O Aspose.GIS é adequado tanto para aplicações desktop quanto web?**  
A: Sim, a biblioteca pode ser usada em desktop, web e serviços de nuvem sem dependências específicas de plataforma.

**Q: Posso realizar análises espaciais com Aspose.GIS para .NET?**  
A: Sim, você pode calcular distâncias, executar operações geométricas e executar consultas espaciais diretamente nas geometrias.

**Q: Onde posso obter ajuda da comunidade para Aspose.GIS?**  
A: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para fazer perguntas e compartilhar ideias com outros desenvolvedores.

---

**Última atualização:** 2026-08-24  
**Testado com:** Aspose.GIS para .NET (última versão estável)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar camada vetorial e Circular String no Aspose.GIS para .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Criar camada vetorial e polígono curvo com Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Converter WKT para Geometria: MultiCurve com Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}