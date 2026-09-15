---
date: 2026-09-15
description: Aprenda como atribuir o sistema de coordenadas, definir a variante WKT
  e controlar a precisão decimal ao criar geometria de ponto em C# com Aspose.GIS
  para .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Especificar variante WKT na tradução
og_description: Aprenda como atribuir o sistema de coordenadas, definir a variante
  WKT e controlar a precisão decimal ao criar geometria de ponto em C# com Aspose.GIS
  para .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Atribuir sistema de coordenadas, definir variante WKT usando Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Atribuir sistema de coordenadas, definir variante WKT usando Aspose.GIS
url: /pt/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atribuir sistema de coordenadas, definir variante WKT usando Aspose.GIS

## Introdução
Neste tutorial, você aprenderá como **atribuir sistema de coordenadas**, escolher a variante WKT correta e controlar a precisão decimal ao **criar geometria de ponto** em C# com Aspose.GIS para .NET. Seja construindo um serviço de mapeamento, realizando análises espaciais ou trocando dados entre plataformas GIS, essas configurações garantem que sua saída seja interoperável e fácil de ler. Vamos percorrer o processo passo a passo.

## Respostas rápidas
- **O que significa “assign coordinate system”?** Ele vincula uma geometria a um sistema de referência de coordenadas específico, como WGS‑84.  
- **Quais variantes WKT são suportadas?** Iso, SimpleFeatureAccessOutdated e ExtendedPostGis.  
- **Como posso controlar a precisão decimal?** Use o enum `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Preciso de uma licença para Aspose.GIS?** Uma versão de avaliação gratuita está disponível; uma licença comercial é necessária para uso em produção.  
- **Quais versões do .NET são compatíveis?** .NET Framework 4.0+ e .NET Core/5/6+.

## O que é “assign coordinate system”?
Atribuir uma referência espacial (ou sistema de referência espacial, SRS) informa ao software GIS como interpretar os valores de coordenadas de uma geometria, vinculando os números a um sistema de coordenadas do mundo real, como WGS‑84. Sem um SRS, os números de latitude‑longitude de um ponto não têm significado no mundo real.

## Por que controlar a variante WKT e o formato numérico?
Mais de 30 ferramentas GIS esperam sintaxes WKT específicas, portanto selecionar a variante correta evita erros de importação. Definir o formato numérico reduz ruído de arredondamento e mantém a saída concisa, o que é especialmente importante quando logs ou arquivos são analisados programaticamente.

## Pré-requisitos
1. Aspose.GIS for .NET – faça o download na [página de download](https://releases.aspose.com/gis/net/).  
2. Um ambiente de desenvolvimento .NET (Visual Studio, VS Code ou Rider).  
3. Familiaridade básica com C# e o framework .NET.

## Importar namespaces
Antes de usar qualquer classe Aspose.GIS, importe os namespaces necessários:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Como atribuir sistema de coordenadas a um ponto?
Carregue uma instância `Point`, então anexe um sistema de referência espacial (SRS) usando a classe `SpatialReference`. Esse padrão de duas etapas garante que a geometria carregue seus metadados de sistema de coordenadas ao ser exportada, permitindo que ferramentas subsequentes interpretem corretamente as coordenadas. A classe `Point` representa uma única localização definida pelas coordenadas X (longitude) e Y (latitude).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Etapa 2: atribuir sistema de referência espacial (SRS)
Agora nós **atribuímos referência espacial** ao ponto. `SpatialReference` representa um sistema de referência de coordenadas identificado por um SRID. Aqui usamos o amplamente suportado sistema WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Etapa 3: especificar a variante WKT desejada
Escolha a variante WKT que corresponde à sua aplicação subsequente:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Como definir a precisão decimal para a saída WKT?
Controle quantos dígitos aparecem na string final usando o enum `NumericFormat`, que define regras de formatação como `General`, `RoundTrip` ou `Flat`. Selecionar `RoundTrip` preserva a fidelidade total das coordenadas para cenários de ida‑e‑volta, enquanto `General` fornece uma representação concisa adequada para a maioria das tarefas de visualização. O enum `NumericFormat` controla como os números de coordenadas são formatados na saída WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Armadilhas comuns e dicas
- **Armadilha:** Esquecer de definir o SRS antes de chamar `AsText` pode resultar em ausência de informação SRID.  
- **Dica:** Use `NumericFormat.RoundTrip` quando precisar de ida‑e‑volta sem perdas das coordenadas.  
- **Dica:** A variante `Iso` é a mais portátil; escolha `ExtendedPostGis` apenas quando precisar que o SRID esteja embutido.

## Conclusão
Agora você sabe como **atribuir sistema de coordenadas**, escolher a variante WKT apropriada e **definir a precisão decimal** ao **criar geometria de ponto** com Aspose.GIS. Esses controles lhe dão a flexibilidade para atender aos requisitos exatos de qualquer fluxo de trabalho GIS, desde visualização simples até análise espacial de alta precisão.

## Perguntas frequentes

**Q:** O Aspose.GIS é compatível com todas as versões do .NET?  
**A:** Sim, o Aspose.GIS suporta .NET Framework 4.0 e superior, bem como .NET Core/5/6.

**Q:** Posso usar o Aspose.GIS em projetos comerciais?  
**A:** Absolutamente. Uma licença comercial é necessária para uso em produção, mas uma versão de avaliação gratuita está disponível para avaliação.

**Q:** O Aspose.GIS suporta outros formatos de dados espaciais?  
**A:** Sim, ele funciona com mais de 30 formatos, incluindo ESRI Shapefile, GeoJSON, KML, CSV e muitos outros.

**Q:** Onde posso baixar uma versão de avaliação gratuita?  
**A:** Você pode baixar uma versão de avaliação gratuita do Aspose.GIS na [página de download de avaliação gratuita do Aspose.GIS](https://releases.aspose.com/).

**Q:** Como obtenho ajuda se encontrar problemas?  
**A:** Publique suas perguntas no [fórum](https://forum.aspose.com/c/gis/33) da comunidade Aspose.GIS, onde tanto a equipe da Aspose quanto os membros da comunidade podem ajudar.

---

**Última atualização:** 2026-09-15  
**Testado com:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose

## Tutoriais relacionados

- [Criar uma camada vetorial e definir seu sistema de referência espacial](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Como traduzir geometria para WKT com Aspose.GIS para .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Como limitar a precisão ao escrever geometrias com Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}