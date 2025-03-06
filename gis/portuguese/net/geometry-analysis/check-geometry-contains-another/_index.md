---
title: Verifique se a geometria contém outra
linktitle: Verifique se a geometria contém outra
second_title: API Aspose.GIS .NET
description: Explore Aspose.GIS for .NET, uma biblioteca robusta para integração perfeita de dados geoespaciais em seus aplicativos .NET.
weight: 14
url: /pt/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verifique se a geometria contém outra

## Introdução
Aspose.GIS for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com dados geoespaciais perfeitamente em seus aplicativos .NET. Esteja você construindo um aplicativo de mapeamento, realizando análises geoespaciais ou integrando recursos baseados em localização em seu software, o Aspose.GIS simplifica o processo, fornecendo APIs intuitivas e funcionalidade robusta.
## Pré-requisitos
Antes de começar a usar o Aspose.GIS for .NET, certifique-se de ter os seguintes pré-requisitos:
### 1. Configuração do ambiente de desenvolvimento .NET
Certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado em sua máquina. Isso inclui ter o SDK do .NET instalado e configurado corretamente.
### 2. Instalação do Aspose.GIS
 Instale Aspose.GIS for .NET baixando a biblioteca da página de lançamento[aqui](https://releases.aspose.com/gis/net/) . Siga as instruções de instalação fornecidas na documentação[aqui](https://reference.aspose.com/gis/net/)para integrar Aspose.GIS em seu projeto.
### 3. Compreensão básica de C#
Familiarize-se com a linguagem de programação C#, pois Aspose.GIS for .NET é usado principalmente com C#.

## Importar namespaces
Em seu projeto C#, importe os namespaces necessários para utilizar as funcionalidades do Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passo 1: Definir Objetos Geométricos
Primeiro, defina os objetos geométricos usando classes Aspose.GIS:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Passo 2: Verifique a Contenção Espacial
A seguir, verifique se uma geometria contém outra:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // Falso
```
## Passo 3: Definir Outra Geometria
Defina outro objeto de geometria:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Passo 4: Verifique novamente a contenção espacial
Verifique se a geometria recém-definida está contida na primeira geometria:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // Verdadeiro
```
## Etapa 5: Funcionalidade Equivalente
 Entenda que`a.SpatiallyContains(b)` é equivalente a`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // Verdadeiro
```

## Conclusão
Concluindo, Aspose.GIS for .NET fornece ferramentas poderosas para lidar com dados geoespaciais em aplicativos .NET. Seguindo este guia e utilizando o exemplo fornecido, você pode realizar verificações de contenção espacial com eficiência e aproveitar outras funcionalidades geoespaciais em seus projetos.
## Perguntas frequentes
### Q1: O Aspose.GIS é compatível com .NET Core?
R: Sim, o Aspose.GIS oferece suporte total ao .NET Core, permitindo desenvolver aplicativos geoespaciais em diferentes plataformas.
### Q2: Posso realizar análises geoespaciais usando Aspose.GIS?
R: Com certeza, o Aspose.GIS oferece várias funcionalidades para análise geoespacial, incluindo consultas espaciais, cálculos de distância e manipulações geométricas.
### Q3: Com que frequência as atualizações são lançadas para Aspose.GIS?
R: Aspose.GIS lança atualizações regularmente para melhorar o desempenho, adicionar novos recursos e resolver quaisquer problemas relatados. Você pode se manter atualizado visitando a página de lançamento.
### Q4: Existe um fórum comunitário para usuários do Aspose.GIS?
R: Sim, você pode participar do fórum da comunidade Aspose.GIS[aqui](https://forum.aspose.com/c/gis/33) para se conectar com outros usuários, fazer perguntas e compartilhar suas experiências.
### Q5: Posso experimentar o Aspose.GIS antes de comprar?
 R: Certamente, você pode explorar o Aspose.GIS baixando a versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
