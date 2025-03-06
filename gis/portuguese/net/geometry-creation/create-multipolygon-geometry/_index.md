---
title: Crie geometria multipolígono com Aspose.GIS
linktitle: Criar geometria multipolígono
second_title: API Aspose.GIS .NET
description: Aprenda como criar geometria MultiPolygon usando Aspose.GIS for .NET. Guia passo a passo para iniciantes. Teste gratuito disponível.
weight: 16
url: /pt/net/geometry-creation/create-multipolygon-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie geometria multipolígono com Aspose.GIS

## Introdução
No mundo do desenvolvimento de Sistemas de Informação Geográfica (GIS), Aspose.GIS for .NET se destaca como uma ferramenta poderosa para criar, editar e analisar dados geoespaciais. Quer você seja um desenvolvedor experiente ou esteja apenas começando, dominar o Aspose.GIS pode abrir um mundo de possibilidades para seus projetos.
## Pré-requisitos
Antes de começar a usar o Aspose.GIS for .NET, existem alguns pré-requisitos que você precisa ter em vigor:
### Instalando Aspose.GIS para .NET
1.  Baixe Aspose.GIS: Vá para o[página de download](https://releases.aspose.com/gis/net/) selecione a versão apropriada para seu ambiente de desenvolvimento.
2. Instale o Aspose.GIS: Siga as instruções de instalação fornecidas na documentação para instalar o Aspose.GIS for .NET em sua máquina.

## Importando Namespaces
Para começar a trabalhar com Aspose.GIS em seu projeto .NET, você precisará importar os namespaces necessários:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 1: criar anéis lineares
Primeiro, precisamos criar LinearRings para cada polígono. Cada LinearRing representa uma sequência de linhas fechadas formando o limite de um polígono.
```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```
## Etapa 2: criar polígonos
A seguir, criaremos objetos Polygon usando os LinearRings que definimos.
```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```
## Etapa 3: criar multipolígono
Agora, vamos combinar esses polígonos em uma geometria MultiPolygon.
```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```
Parabéns! Você criou com sucesso uma geometria MultiPolygon usando Aspose.GIS for .NET.

## Conclusão
Dominar o Aspose.GIS for .NET abre um mundo de possibilidades para desenvolvedores que trabalham com dados geoespaciais. Seguindo este guia passo a passo, você aprendeu como criar uma geometria MultiPolygon, estabelecendo as bases para aplicações GIS mais complexas.
## Perguntas frequentes
### O Aspose.GIS for .NET é adequado para iniciantes?
Absolutamente! Aspose.GIS oferece documentação e tutoriais abrangentes para ajudar desenvolvedores de todos os níveis de habilidade a começar.
### Posso experimentar o Aspose.GIS antes de comprar?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/) para explorar seus recursos antes de fazer uma compra.
### Onde posso encontrar suporte para Aspose.GIS?
 Você pode visitar o fórum Aspose.GIS[aqui](https://forum.aspose.com/c/gis/33) para fazer perguntas e obter assistência da comunidade.
### Existe uma licença temporária disponível para Aspose.GIS?
 Sim, você pode obter uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/) para fins de avaliação.
### Posso comprar Aspose.GIS diretamente?
 Sim, você pode comprar Aspose.GIS no site[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
