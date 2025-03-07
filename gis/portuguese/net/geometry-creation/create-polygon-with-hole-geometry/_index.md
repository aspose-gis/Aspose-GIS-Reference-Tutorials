---
title: Crie polígono com geometria de furo usando Aspose.GIS
linktitle: Criar polígono com geometria de furo
second_title: API Aspose.GIS .NET
description: Aprenda como criar polígono com geometria de furo usando Aspose.GIS for .NET. Tutorial passo a passo com exemplos de código.
weight: 13
url: /pt/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie polígono com geometria de furo usando Aspose.GIS

## Introdução
Neste tutorial, percorreremos o processo de criação de um polígono com geometria de furo usando Aspose.GIS for .NET. Aspose.GIS é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com dados geoespaciais em seus aplicativos .NET. 
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Biblioteca Aspose.GIS for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/gis/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento configurado com o Visual Studio ou qualquer outro IDE .NET instalado.
## Importar namespaces
Primeiramente, você precisa importar os namespaces necessários para trabalhar com as funcionalidades do Aspose.GIS. Veja como fazer isso:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Agora, vamos criar um polígono com geometria de furo usando Aspose.GIS for .NET.
## Etapa 1: Criar objeto polígono
```csharp
Polygon polygon = new Polygon();
```
## Etapa 2: definir o anel externo
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Etapa 3: definir o anel interno (orifício)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Etapa 4: atribuir anel externo e adicionar anel interno ao polígono
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Conclusão
Parabéns! Você aprendeu com sucesso como criar um polígono com geometria de furo usando Aspose.GIS for .NET. Este conhecimento será benéfico para diversas aplicações geoespaciais onde tais geometrias são essenciais.
## Perguntas frequentes
### 1. O que é Aspose.GIS?
Aspose.GIS é uma biblioteca .NET que permite aos desenvolvedores trabalhar com dados geoespaciais, permitindo-lhes criar, ler e manipular vários formatos de arquivos geoespaciais.
### 2. Posso usar Aspose.GIS para projetos comerciais?
 Sim, você pode usar o Aspose.GIS para projetos pessoais e comerciais, adquirindo uma licença. Visita[aqui](https://purchase.aspose.com/buy) para mais detalhes.
### 3. Existe um teste gratuito disponível para Aspose.GIS?
 Sim, você pode aproveitar uma avaliação gratuita do Aspose.GIS em[aqui](https://releases.aspose.com/).
### 4. Onde posso encontrar suporte para Aspose.GIS?
 Você pode encontrar suporte para Aspose.GIS no site[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Como posso obter uma licença temporária do Aspose.GIS?
 Você pode obter uma licença temporária para Aspose.GIS em[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
