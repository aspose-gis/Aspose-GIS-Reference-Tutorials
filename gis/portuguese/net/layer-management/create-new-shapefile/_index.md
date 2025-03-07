---
title: Criar novo shapefile
linktitle: Criar novo shapefile
second_title: API Aspose.GIS .NET
description: Aprenda como criar um novo shapefile usando Aspose.GIS for .NET. Siga nosso guia passo a passo e descubra o poder da manipulação de dados espaciais.
weight: 12
url: /pt/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar novo shapefile

## Introdução
Se você está se aprofundando no desenvolvimento de sistemas de informações geográficas (GIS) com .NET, Aspose.GIS é a solução ideal. Esta poderosa biblioteca permite que os desenvolvedores trabalhem perfeitamente com dados espaciais e, neste tutorial, orientaremos você no processo de criação de um novo shapefile usando Aspose.GIS for .NET.
## Pré-requisitos
Antes de prosseguirmos para o tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Compreensão básica da linguagem de programação C#.
- Visual Studio instalado em sua máquina.
-  Biblioteca Aspose.GIS para .NET. Você pode baixá-lo[aqui](https://releases.aspose.com/gis/net/).
## Importar namespaces
Comece importando os namespaces necessários para aproveitar a funcionalidade do Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Etapa 1: configure seu projeto
Comece criando um novo projeto C# no Visual Studio e inclua a biblioteca Aspose.GIS.
## Etapa 2: definir o diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua “Seu diretório de documentos” pelo caminho real onde você deseja salvar seu novo shapefile.
## Etapa 3: crie uma camada vetorial
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //adicione atributos antes de adicionar recursos
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Este segmento de código configura a camada vetorial e define atributos para seus recursos.
## Etapa 4: adicionar recursos
### Caso 1: Define Valores Individualmente
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Caso 2: define novos valores para todos os atributos
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Conclusão
 Parabéns! Você criou com sucesso um novo shapefile usando Aspose.GIS for .NET. Este tutorial abordou os conceitos básicos de configuração do seu projeto, definição de atributos e adição de recursos. À medida que você explora mais, consulte o[documentação](https://reference.aspose.com/gis/net/) para recursos e funcionalidades avançadas.
## perguntas frequentes
### P: Posso usar Aspose.GIS com outras linguagens de programação?
Aspose.GIS suporta principalmente .NET, mas também existem versões disponíveis para Java.
### P: Existe um teste gratuito disponível?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar suporte para Aspose.GIS?
 Visite a[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoio e discussões da comunidade.
### P: Como posso obter uma licença temporária?
 Obtenha sua licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso comprar o Aspose.GIS para .NET?
 Você pode comprar a biblioteca[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
