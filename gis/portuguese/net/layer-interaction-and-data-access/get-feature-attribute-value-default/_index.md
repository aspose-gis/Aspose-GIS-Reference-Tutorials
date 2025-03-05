---
title: Obter valor do atributo do recurso (padrão)
linktitle: Obter valor do atributo do recurso (padrão)
second_title: API Aspose.GIS .NET
description: Desbloqueie o poder do Aspose.GIS para .NET! Recupere e manipule valores de atributos de recursos sem esforço com este guia passo a passo. Baixe seu teste agora!
type: docs
weight: 14
url: /pt/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## Introdução
Bem-vindo ao mundo do Aspose.GIS para .NET! Neste guia abrangente, mergulharemos nos meandros da recuperação de valores de atributos de recursos usando os poderosos recursos do Aspose.GIS. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este tutorial fornecerá um passo a passo, garantindo que você aproveite todo o potencial desta ferramenta notável.
## Pré-requisitos
Antes de embarcarmos nesta aventura de codificação, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de C# e .NET framework.
-  Aspose.GIS para .NET instalado. Se não, baixe-o em[aqui](https://releases.aspose.com/gis/net/).
- Um editor de código, como o Visual Studio, para acompanhar perfeitamente.
## Importar namespaces
Em seu projeto C#, certifique-se de incluir os namespaces necessários:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Agora, vamos dividir cada exemplo em uma série de etapas fáceis de seguir.
## Obter valor do atributo do recurso (padrão)
### Etapa 1: configurar o ambiente
Comece definindo o caminho para o seu diretório de documentos:
```csharp
string dataDir = "Your Document Directory";
```
### Etapa 2: crie uma camada GeoJson
Crie uma camada GeoJson e defina um atributo com valores padrão:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Etapa 3: construir um recurso
Construa um recurso usando o atributo definido:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Etapa 4: recuperar valores
Recuperar valores de atributos com vários cenários:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // valor == nulo
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // valor == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // valor == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Definir valores padrão
### Etapa 1: crie outra camada GeoJson
Repita o processo com uma camada GeoJson diferente e um atributo duplo:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Etapa 2: construir um recurso (novamente)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Etapa 3: recuperar e definir valores
Recuperar e definir valores de atributos, mostrando padrões:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // valor == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // valor == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // valor == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Parabéns! Você aproveitou com sucesso o poder do Aspose.GIS para .NET na recuperação e manipulação de valores de atributos de recursos.
## Conclusão
Neste tutorial, exploramos as nuances da recuperação de valores de atributos de recursos usando Aspose.GIS for .NET. Com sua API intuitiva e recursos robustos, o Aspose.GIS abre um mundo de possibilidades para o desenvolvimento de GIS em ambientes .NET.
## perguntas frequentes
### O Aspose.GIS é compatível com .NET Core?
Sim, o Aspose.GIS é totalmente compatível com .NET Core, fornecendo suporte multiplataforma.
### Posso usar Aspose.GIS para projetos comerciais?
Absolutamente! Aspose.GIS vem com uma licença comercial que permite usá-lo em suas aplicações comerciais sem quaisquer restrições.
### Onde posso encontrar suporte e recursos adicionais?
 Visite a[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoio da comunidade e explorar o[documentação](https://reference.aspose.com/gis/net/) para obter informações detalhadas.
### Existe um teste gratuito disponível?
 Sim, você pode explorar o Aspose.GIS com uma avaliação gratuita. Baixe[aqui](https://releases.aspose.com/).
### Como obtenho uma licença temporária para fins de teste?
 Para licenças temporárias, visite[aqui](https://purchase.aspose.com/temporary-license/).