---
date: 2025-12-20
description: Aprenda a criar polígonos com geometria de furo usando Aspose.GIS para
  .NET. Este guia mostra como criar um furo em um polígono e trabalhar com dados geoespaciais.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Criar Polígono com Geometria de Buraco usando Aspose.GIS
url: /pt/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Geometria de Polígono com Buraco usando Aspose.GIS

## Introdução
Neste tutorial, você **criará um polígono com buraco** usando Aspose.GIS para .NET. Seja construindo uma aplicação de mapeamento, realizando análise espacial ou preparando dados para serviços GIS, saber como inserir um buraco dentro de um polígono é essencial. Vamos percorrer todo o processo passo a passo, desde a configuração do ambiente até a geração do objeto polígono final.

## Respostas Rápidas
- **O que significa “criar polígono com buraco”?** Significa construir um polígono que contém um ou mais anéis internos (buracos) que são excluídos da área.  
- **Qual biblioteca lida com isso?** Aspose.GIS for .NET fornece suporte total para anéis externos e internos.  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo leva?** Normalmente menos de 10 minutos para implementar e testar.

## O que é “criar polígono com buraco”?
Criar um polígono com buraco envolve definir um **anel externo** que delimita a fronteira externa e um ou mais **anéis internos** que removem áreas vazias. Os anéis internos são frequentemente chamados de *buracos* porque representam áreas que não fazem parte da superfície do polígono.

## Por que criar buraco em polígono usando Aspose.GIS?
- **Modelagem espacial precisa:** Recursos do mundo real, como lagos dentro de parcelas de terra ou pátios dentro de edifícios, requerem buracos.  
- **Interoperabilidade:** Formatos como Shapefile, GeoJSON e GML suportam nativamente anéis internos; Aspose.GIS os preserva.  
- **Desempenho:** A biblioteca gerencia a validade da geometria, então você não precisa escrever código de validação personalizado.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:
1. Biblioteca Aspose.GIS for .NET: Você pode baixá‑la [aqui](https://releases.aspose.com/gis/net/).  
2. Ambiente de Desenvolvimento: Certifique‑se de que você tem um ambiente de desenvolvimento configurado com Visual Studio ou qualquer outra IDE .NET instalada.

## Importar Namespaces
Primeiro, você precisa importar os namespaces necessários para trabalhar com as funcionalidades do Aspose.GIS. Veja como fazer isso:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Agora, vamos prosseguir para criar uma geometria de polígono com buraco usando Aspose.GIS para .NET.

## Etapa 1: Criar Objeto Polygon
Começamos instanciando um objeto `Polygon` vazio que, mais tarde, conterá tanto o anel externo quanto os anéis internos.

```csharp
Polygon polygon = new Polygon();
```

## Etapa 2: Definir Anel Externo
O anel externo define a fronteira externa do polígono. Adicione pontos em ordem horário para formar uma forma fechada.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Etapa 3: Definir Anel Interno (Buraco)
Em seguida, criamos um anel interno—este é o **buraco** que será excluído da área do polígono. Os pontos são tipicamente adicionados em ordem anti‑horária, mas o Aspose.GIS lida com a orientação automaticamente.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Etapa 4: Atribuir Anel Externo e Adicionar Anel Interno ao Polígono
Por fim, anexe o anel externo ao polígono e então adicione o anel interno (o buraco). O método `AddInteriorRing` pode ser chamado várias vezes se você precisar de vários buracos.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Problemas Comuns e Soluções
| Problema | Razão | Solução |
|----------|-------|---------|
| Buraco não aparece no visualizador GIS | Orientação do anel interno invertida | Certifique‑se de que os pontos são adicionados na direção oposta ao anel externo (sentido anti‑horário). |
| Erro de polígono inválido | Anéis não fechados (primeiro ≠ último ponto) | Repita o primeiro ponto como o último ponto em cada anel (conforme mostrado acima). |
| Geometria vazia inesperada | Esquecer de atribuir `ExteriorRing` antes de adicionar anéis internos | Defina `polygon.ExteriorRing` primeiro, depois chame `AddInteriorRing`. |

## Conclusão
Parabéns! Você aprendeu com sucesso como **criar um polígono com buraco** usando Aspose.GIS para .NET. Esta técnica é fundamental para muitos cenários geoespaciais onde você precisa representar formas complexas com vazios internos.

## Perguntas Frequentes
### 1. O que é Aspose.GIS?
Aspose.GIS é uma biblioteca .NET que permite aos desenvolvedores trabalhar com dados geoespaciais, possibilitando criar, ler e manipular diversos formatos de arquivos geoespaciais.

### 2. Posso usar Aspose.GIS em projetos comerciais?
Sim, você pode usar Aspose.GIS tanto em projetos pessoais quanto comerciais adquirindo uma licença. Visite [aqui](https://purchase.aspose.com/buy) para mais detalhes.

### 3. Existe um teste gratuito disponível para Aspose.GIS?
Sim, você pode obter um teste gratuito do Aspose.GIS [aqui](https://releases.aspose.com/).

### 4. Onde posso encontrar suporte para Aspose.GIS?
Você pode encontrar suporte para Aspose.GIS no [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Como posso obter uma licença temporária para Aspose.GIS?
Você pode obter uma licença temporária para Aspose.GIS [aqui](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}