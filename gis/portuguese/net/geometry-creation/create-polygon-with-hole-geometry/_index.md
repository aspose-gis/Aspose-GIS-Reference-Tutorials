---
date: 2026-04-03
description: Aprenda como criar polígonos com geometria de buraco usando Aspose.GIS
  para .NET. Este guia mostra como criar um buraco em um polígono e trabalhar com
  dados geoespaciais.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Criar Polígono com Geometria de Buraco
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
Neste tutorial, você **criará polígono com buraco** usando Aspose.GIS para .NET. Seja construindo um aplicativo de mapeamento, realizando análise espacial ou preparando dados para serviços GIS, saber como inserir um buraco dentro de um polígono é essencial. Percorreremos todo o processo passo a passo, desde a configuração do ambiente até a geração do objeto polígono final.

## Respostas Rápidas
- **O que significa “create polygon with hole”?** Significa construir um polígono que contém um ou mais anéis interiores (buracos) que são excluídos da área.  
- **Qual biblioteca lida com isso?** Aspose.GIS para .NET fornece suporte total para anéis externos e internos.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo leva?** Normalmente menos de 10 minutos para implementar e testar.

## Como adicionar buraco a um polígono usando Aspose.GIS
Adicionar um buraco é simplesmente uma questão de definir um **interior ring** e anexá‑lo ao polígono. A biblioteca cuida da orientação e validade, para que você possa se concentrar nas coordenadas que representam o vazio necessário.

## O que é “create polygon with hole”?
Criar um polígono com buraco envolve definir um **exterior ring** que delineia o contorno externo e um ou mais **interior rings** que criam espaços vazios. Os anéis interiores são frequentemente chamados de *buracos* porque representam áreas que não fazem parte da superfície do polígono.

## Por que criar buraco em um polígono usando Aspose.GIS?
- **Modelagem espacial precisa:** Recursos do mundo real, como lagos dentro de parcelas de terra ou pátios dentro de edifícios, requerem buracos.  
- **Interoperabilidade:** Formatos como Shapefile, GeoJSON e GML suportam nativamente anéis interiores; Aspose.GIS os preserva.  
- **Desempenho:** A biblioteca gerencia a validade da geometria, de modo que você não precise escrever código de validação personalizado.

## Cenários do Mundo Real para Polígonos com Buracos
1. **Parcela de terra com lago interno** – o lago é modelado como um buraco para que não seja contabilizado na área da parcela.  
2. **Pegadas de edifícios com pátios** – o pátio é excluído da pegada do edifício.  
3. **Zonas protegidas dentro de uma área de conservação maior** – você pode excluir seções restritas sem criar camadas separadas.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:
1. Aspose.GIS for .NET Library: Você pode baixá‑la em [here](https://releases.aspose.com/gis/net/).  
2. Ambiente de Desenvolvimento: Certifique‑se de que você tem um ambiente de desenvolvimento configurado com Visual Studio ou qualquer outra IDE .NET instalada.

## Importar Namespaces
Primeiro, você precisa importar os namespaces necessários para trabalhar com as funcionalidades do Aspose.GIS. Veja como fazer:

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
Começamos instanciando um objeto `Polygon` vazio que posteriormente conterá tanto o anel externo quanto os anéis internos.

```csharp
Polygon polygon = new Polygon();
```

## Etapa 2: Definir Anel Exterior
O anel exterior define o contorno externo do polígono. Adicione pontos em ordem horário para formar uma forma fechada.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Etapa 3: Definir Anel Interior (Buraco)
Em seguida, criamos um anel interior—este é o **buraco** que será excluído da área do polígono. Os pontos são tipicamente adicionados em ordem anti‑horária, mas o Aspose.GIS trata a orientação automaticamente.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Etapa 4: Atribuir Anel Exterior e Adicionar Anel Interior ao Polígono
Finalmente, anexe o anel exterior ao polígono e então adicione o anel interior (o buraco). O método `AddInteriorRing` pode ser chamado várias vezes se você precisar de vários buracos.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Dicas e Melhores Práticas
- **A orientação importa para a legibilidade** – embora o Aspose.GIS corrija automaticamente a orientação, manter os anéis externos no sentido horário e os anéis internos no sentido anti‑horário facilita a inspeção da geometria em visualizadores GIS.  
- **Feche cada anel** – sempre repita a primeira coordenada como o último ponto; isso garante uma forma fechada válida.  
- **Valide após a criação** – você pode chamar `polygon.IsValid` para garantir que a geometria esteja em conformidade com os padrões OGC antes de salvar.

## Problemas Comuns e Soluções
| Problema | Razão | Solução |
|----------|-------|---------|
| Buraco não aparece no visualizador GIS | Orientação do anel interno invertida | Certifique‑se de que os pontos sejam adicionados na direção oposta ao anel externo (anti‑horário). |
| Erro de polígono inválido | Anéis não fechados (primeiro ≠ último ponto) | Repita o primeiro ponto como o último ponto em cada anel (conforme mostrado acima). |
| Geometria vazia inesperada | Esqueceu de atribuir `ExteriorRing` antes de adicionar anéis internos | Defina `polygon.ExteriorRing` primeiro, então chame `AddInteriorRing`. |

## Perguntas Frequentes
### 1. O que é Aspose.GIS?
Aspose.GIS é uma biblioteca .NET que permite aos desenvolvedores trabalhar com dados geoespaciais, possibilitando criar, ler e manipular vários formatos de arquivos geoespaciais.

### 2. Posso usar Aspose.GIS para projetos comerciais?
Sim, você pode usar Aspose.GIS tanto para projetos pessoais quanto comerciais adquirindo uma licença. Visite [here](https://purchase.aspose.com/buy) para mais detalhes.

### 3. Existe uma versão de teste gratuita disponível para Aspose.GIS?
Sim, você pode obter uma versão de teste gratuita do Aspose.GIS em [here](https://releases.aspose.com/).

### 4. Onde posso encontrar suporte para Aspose.GIS?
Você pode encontrar suporte para Aspose.GIS no [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Como posso obter uma licença temporária para Aspose.GIS?
Você pode obter uma licença temporária para Aspose.GIS em [here](https://purchase.aspose.com/temporary-license/).

---

**Última Atualização:** 2026-04-03  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}