---
title: Criar novo conjunto de dados GDB de arquivo
linktitle: Criar novo conjunto de dados GDB de arquivo
second_title: API Aspose.GIS .NET
description: Explore o Aspose.GIS for .NET para criar e gerenciar conjuntos de dados GIS sem esforço. Baixe agora para um desenvolvimento geoespacial perfeito. #Aspose #GIS
weight: 10
url: /pt/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar novo conjunto de dados GDB de arquivo

## Introdução
No domínio do desenvolvimento geoespacial, Aspose.GIS for .NET se destaca como um poderoso kit de ferramentas para gerenciar e manipular dados de Sistemas de Informação Geográfica (GIS). Quer você seja um desenvolvedor experiente ou esteja apenas começando sua jornada no GIS, este tutorial irá orientá-lo no processo de criação de um novo conjunto de dados File Geodatabase (GDB) usando Aspose.GIS for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Aspose.GIS for .NET: Certifique-se de ter a biblioteca Aspose.GIS for .NET instalada. Você pode baixá-lo no[Página de download do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento com um IDE compatível, como o Visual Studio, e tenha um conhecimento básico de programação .NET.
- Diretório de documentos: substitua "Seu diretório de documentos" no trecho de código pelo caminho apropriado onde você deseja armazenar seu conjunto de dados GDB.
- Familiaridade com C#: Este tutorial pressupõe que você esteja familiarizado com a linguagem de programação C#.
## Importar namespaces
Nas etapas iniciais, importe os namespaces necessários para aproveitar a funcionalidade Aspose.GIS em seu aplicativo .NET:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Etapa 1: criar um novo conjunto de dados GDB de arquivo
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Saída: 0
    // Continue com as etapas subsequentes...
}
```
 Explicação: Nesta etapa, criamos um novo conjunto de dados GDB usando o`Dataset.Create` método. Especificamos o caminho e o driver (FileGdb) para criar um arquivo Geodatabase. A saída do console exibe a contagem inicial de camadas, que é zero neste ponto.
## Etapa 2: criar e preencher a camada_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Explicação: Esta etapa envolve a criação de uma camada chamada "camada_1" no conjunto de dados. Ele define um atributo denominado "valor" do tipo inteiro e preenche a camada com dez feições, cada uma possuindo uma geometria de ponto.
## Etapa 3: criar e preencher a camada_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Explicação: Aqui, criamos uma segunda camada chamada "camada_2" e adicionamos um único recurso com uma geometria de sequência de linhas.
## Etapa 4: verifique a contagem de camadas atualizadas
```csharp
Console.WriteLine(dataset.LayersCount); // Saída: 2
```
Explicação: Finalmente, verificamos a contagem de camadas atualizadas após adicionar as duas camadas. Neste caso, a saída deve ser 2.
## Conclusão
Parabéns! Você criou com sucesso um novo conjunto de dados File GDB e o preencheu com camadas usando Aspose.GIS for .NET. Este tutorial fornece uma compreensão básica do trabalho com dados geoespaciais em um ambiente .NET.
## perguntas frequentes
### P: Posso usar Aspose.GIS for .NET com outras bibliotecas GIS?
Aspose.GIS for .NET é um kit de ferramentas independente; no entanto, você pode integrá-lo a outras bibliotecas .NET para aprimorar a funcionalidade.
### P: Existe um fórum da comunidade para suporte do Aspose.GIS?
 Sim, você pode encontrar suporte e discussões no[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### P: Como posso obter uma licença temporária para Aspose.GIS?
 Visite a[Licença Temporária](https://purchase.aspose.com/temporary-license/) página para obter informações sobre como obter uma licença temporária.
### P: Existem exemplos e documentação adicionais disponíveis?
 Explore o[Documentação Aspose.GIS](https://reference.aspose.com/gis/net/) para mais exemplos e informações detalhadas.
### P: Onde posso comprar o Aspose.GIS para .NET?
 Você pode adquirir o Aspose.GIS for .NET no site[página de compra](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
