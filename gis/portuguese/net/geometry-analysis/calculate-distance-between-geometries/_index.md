---
title: Calcule a distância entre geometrias com Aspose.GIS
linktitle: Calcular distância entre geometrias
second_title: API Aspose.GIS .NET
description: Aprenda como calcular distâncias entre geometrias em .NET usando Aspose.GIS. Guia passo a passo com exemplos de código. Aprimore suas aplicações geoespaciais.
weight: 21
url: /pt/net/geometry-analysis/calculate-distance-between-geometries/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calcule a distância entre geometrias com Aspose.GIS

## Introdução
No domínio da programação geoespacial, a capacidade de calcular distâncias entre diferentes geometrias é fundamental. Quer você esteja lidando com polígonos, linhas ou pontos, saber a distância entre eles pode ser crucial para diversas aplicações, desde mapeamento até planejamento logístico. Aspose.GIS for .NET fornece ferramentas poderosas para realizar tais cálculos com facilidade e precisão.
## Pré-requisitos
Antes de se aprofundar no cálculo de distâncias entre geometrias usando Aspose.GIS for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
### Instale Aspose.GIS para .NET
 Para começar, você precisa ter o Aspose.GIS for .NET instalado em seu sistema. Você pode baixar a biblioteca do[Página de lançamentos do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/) e siga as instruções de instalação fornecidas na documentação.
### Familiaridade com desenvolvimento .NET
Uma compreensão básica do desenvolvimento .NET usando C# é necessária para acompanhar os exemplos neste tutorial. Se você é novo no desenvolvimento .NET, considere atualizar os conceitos básicos de C# antes de continuar.

## Importar namespaces
Antes de começar a usar o Aspose.GIS for .NET para calcular distâncias entre geometrias, você precisa importar os namespaces necessários para o seu projeto C#. Siga estas etapas para importar os namespaces necessários:
## Abra seu projeto C#
Navegue até seu projeto C# em seu ambiente de desenvolvimento integrado (IDE) preferido, como o Visual Studio.
## Adicionar referências de namespace
No arquivo C# onde você pretende realizar os cálculos de distância, adicione as seguintes referências de namespace no início do arquivo:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Vamos dividir o exemplo fornecido em várias etapas para entender como calcular a distância entre geometrias usando Aspose.GIS for .NET:
## Etapa 1: criar geometria poligonal
```csharp
var polygon = new Polygon();
```
Esta etapa cria uma nova instância de uma geometria poligonal.
## Etapa 2: definir o anel externo do polígono
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
Aqui, definimos o anel externo do polígono especificando uma sequência de pontos que formam o limite do polígono.
## Etapa 3: Criar geometria de string de linha
```csharp
var line = new LineString();
```
Esta etapa inicializa uma nova instância de uma geometria de sequência de linhas.
## Etapa 4: adicionar pontos à sequência de linhas
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Adicionamos dois pontos à linha, definindo sua forma e trajetória.
## Etapa 5: calcular a distância
```csharp
double distance = polygon.GetDistanceTo(line);
```
Esta etapa calcula a distância entre o polígono e a sequência de linhas.
## Etapa 6: resultado de saída
```csharp
Console.WriteLine(distance.ToString("F")); // 0,63
```
Por fim, imprimimos a distância calculada até o console, formatado para exibir duas casas decimais.

## Conclusão
Calcular distâncias entre geometrias é uma tarefa fundamental na programação geoespacial, e o Aspose.GIS for .NET simplifica esse processo com sua API intuitiva. Seguindo as etapas descritas neste tutorial, você pode calcular facilmente distâncias entre polígonos, linhas e pontos em seus aplicativos .NET.
## Perguntas frequentes
### Aspose.GIS for .NET é compatível com todos os frameworks .NET?
Sim, Aspose.GIS for .NET é compatível com .NET Framework 4.6 e superior.
### Posso usar o Aspose.GIS for .NET para realizar análises espaciais complexas?
Absolutamente! Aspose.GIS for .NET oferece uma ampla gama de funcionalidades para tarefas avançadas de análise espacial.
### O Aspose.GIS for .NET suporta geometrias 2D e 3D?
Sim, você pode trabalhar com geometrias 2D e 3D usando Aspose.GIS for .NET.
### Posso integrar o Aspose.GIS for .NET com outras bibliotecas GIS?
Aspose.GIS for .NET fornece interoperabilidade com outras bibliotecas GIS, permitindo aproveitar funcionalidades adicionais.
### O suporte técnico está disponível para usuários do Aspose.GIS para .NET?
 Sim, os usuários do Aspose.GIS for .NET podem acessar o suporte técnico através do Aspose.[fóruns](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
