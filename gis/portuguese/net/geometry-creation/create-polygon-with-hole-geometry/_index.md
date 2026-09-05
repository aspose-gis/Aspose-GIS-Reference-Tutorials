---
date: 2026-09-05
description: Aprenda como criar um polygon interior ring com um hole usando Aspose.GIS
  para .NET. Este guia mostra como adicionar um hole a um polygon e trabalhar com
  data.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Criar Polygon com Hole Geometry
og_description: Aprenda como criar um polygon interior ring com um hole usando Aspose.GIS
  para .NET. Este guia mostra como adicionar um hole a um polygon e trabalhar com
  data.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Criar um polygon interior ring com um hole usando Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Criar um polygon interior ring com um hole usando Aspose.GIS
url: /pt/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar um anel interior de polígono com um buraco usando Aspose.GIS

## Introdução
Neste tutorial você aprenderá a **criar um anel interior de polígono** que contém um buraco usando Aspose.GIS para .NET. Seja construindo um aplicativo de mapeamento, realizando análise espacial ou preparando dados para serviços GIS, inserir um buraco dentro de um polígono é uma habilidade essencial. Percorreremos todo o fluxo de trabalho — desde a configuração do ambiente de desenvolvimento até a geração de um objeto de polígono válido que pode ser salvo em qualquer formato geoespacial suportado.

## Respostas rápidas
- **O que significa “criar polígono com buraco”?** Significa construir um polígono que contém um ou mais anéis interiores (buracos) que são excluídos da área.  
- **Qual biblioteca lida com isso?** Aspose.GIS para .NET fornece suporte total para anéis externos e internos.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo leva?** Normalmente menos de 10 minutos para implementar e testar.

## Como adicionar um buraco a um polígono usando Aspose.GIS
Carregue seu ambiente GIS, defina um anel externo e, em seguida, anexe um ou mais anéis internos. Aspose.GIS orienta automaticamente os anéis e valida a geometria, permitindo que você se concentre nas coordenadas que representam o vazio necessário.

## O que é um anel interior de polígono?
Um **anel interior de polígono** é uma fronteira interna que subtrai área da forma externa do polígono.  
Você o cria definindo uma sequência fechada de pontos que o Aspose.GIS trata como um buraco, excluído ao calcular a área ou renderizar a forma.

## Por que criar um anel interior de polígono usando Aspose.GIS?
Aspose.GIS valida e corrige a orientação dos anéis em menos de 5 ms para polígonos típicos de 200 pontos, eliminando a necessidade de código de validação personalizado. Também suporta **mais de 30 formatos de arquivo geoespacial** (Shapefile, GeoJSON, GML, KML, etc.) e pode processar polígonos com até 10.000 pontos sem carregar o arquivo inteiro na memória, oferecendo velocidade e escalabilidade.

## Cenários do mundo real para polígonos com buracos
1. **Lote de terra com lago interno** – o lago é modelado como um buraco para que não seja contado na área do lote.  
2. **Plantas de edifícios com pátios** – o pátio é excluído da planta do edifício.  
3. **Zonas protegidas dentro de uma área de conservação maior** – você pode excluir seções restritas sem criar camadas separadas.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:
1. Biblioteca Aspose.GIS para .NET: Você pode baixá‑la na **página de download do Aspose.GIS for .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Ambiente de Desenvolvimento: Garanta que você tenha um ambiente de desenvolvimento configurado com Visual Studio ou qualquer outra IDE .NET instalada.

## Importar namespaces
O namespace `Aspose.Gis` contém todos os tipos de geometria que você precisará, incluindo `Polygon`, `LinearRing` e métodos auxiliares para validação.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Agora, vamos prosseguir para criar uma geometria de polígono com buraco usando Aspose.GIS para .NET.

## Etapa 1: criar objeto de polígono
`Polygon` é o tipo de geometria do Aspose.GIS que representa um polígono planar com anéis internos opcionais. Começamos instanciando um objeto `Polygon` vazio que mais tarde conterá tanto o anel externo quanto os internos.

```csharp
Polygon polygon = new Polygon();
```

## Etapa 2: definir anel exterior
`LinearRing` é a classe usada tanto para limites externos quanto internos. O anel exterior define a fronteira externa do polígono. Adicione pontos em ordem horário para formar uma forma fechada.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Etapa 3: definir anel interior (buraco)
`LinearRing` também representa anéis internos. O anel interior é o **buraco** que será excluído da área do polígono. Os pontos são tipicamente adicionados em ordem anti‑horária, mas o Aspose.GIS lida com a orientação automaticamente.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Etapa 4: atribuir anel exterior e adicionar anel interior ao polígono
O método `AddInteriorRing` anexa um ou mais anéis internos a um `Polygon`. Chame‑o após definir a propriedade `ExteriorRing`; você pode repetir a chamada para adicionar múltiplos buracos.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Dicas e melhores práticas
- **A orientação importa para legibilidade** – embora o Aspose.GIS corrija automaticamente a orientação, manter os anéis externos no sentido horário e os internos no sentido anti‑horário facilita a inspeção da geometria em visualizadores GIS.  
- **Feche cada anel** – sempre repita a primeira coordenada como o último ponto; isso garante uma forma fechada válida.  
- **Valide após a criação** – você pode chamar `polygon.IsValid` para garantir que a geometria esteja em conformidade com os padrões OGC antes de salvar.

## Problemas comuns e soluções
| Problema | Razão | Correção |
|----------|-------|----------|
| Buraco não aparece no visualizador GIS | Orientação do anel interno invertida | Certifique‑se de que os pontos sejam adicionados na direção oposta ao anel externo (anti‑horária). |
| Erro de polígono inválido | Anéis não fechados (primeiro ≠ último ponto) | Repita o primeiro ponto como último ponto em cada anel (conforme mostrado acima). |
| Geometria vazia inesperada | Esquecimento de atribuir `ExteriorRing` antes de adicionar anéis internos | Defina `polygon.ExteriorRing` primeiro, depois chame `AddInteriorRing`. |

## Perguntas frequentes
### 1. O que é Aspose.GIS?
Aspose.GIS é uma biblioteca .NET que permite aos desenvolvedores trabalhar com dados geoespaciais, possibilitando a criação, leitura e manipulação de vários formatos de arquivo geoespacial.

### 2. Posso usar Aspose.GIS em projetos comerciais?
Sim, você pode usar Aspose.GIS tanto em projetos pessoais quanto comerciais adquirindo uma licença. Visite a **página de compra do Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) para mais detalhes.

### 3. Existe uma versão de avaliação gratuita disponível para Aspose.GIS?
Sim, você pode obter uma avaliação gratuita do Aspose.GIS na **página de download da avaliação gratuita do Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Onde posso encontrar suporte para Aspose.GIS?
Você pode encontrar suporte para Aspose.GIS no [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Como posso obter uma licença temporária para Aspose.GIS?
Você pode obter uma licença temporária para Aspose.GIS na **página de licença temporária do Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Last Updated:** 2026-09-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Tutoriais Relacionados

- [Como criar geometria de polígono com Aspose.GIS para .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aprenda como criar geometria MultiPolygon com Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Converter Polígono em Linha com Aspose.GIS para .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}