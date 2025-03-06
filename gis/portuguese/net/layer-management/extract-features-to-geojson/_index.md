---
title: Extraia recursos para GeoJSON
linktitle: Extraia recursos para GeoJSON
second_title: API Aspose.GIS .NET
description: Explore o guia passo a passo sobre como usar Aspose.GIS for .NET para extrair recursos para GeoJSON. Aproveite o poder do GIS com facilidade! #Aspose #GIS
weight: 23
url: /pt/net/layer-management/extract-features-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraia recursos para GeoJSON

## Introdução
Bem-vindo ao nosso tutorial passo a passo sobre como extrair recursos para GeoJSON usando Aspose.GIS for .NET! Quer você seja um desenvolvedor experiente ou esteja apenas começando sua jornada na programação GIS, este guia irá orientá-lo durante o processo, garantindo que você aproveite todo o poder do Aspose.GIS for .NET.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:
-  Aspose.GIS for .NET: Certifique-se de ter a biblioteca instalada. Caso contrário, você pode baixá-lo no[Página Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
-  Dados do Shapefile: Tenha um Shapefile pronto para entrada. Se precisar de dados de amostra, você pode encontrá-los no[Documentação Aspose.GIS](https://reference.aspose.com/gis/net/).
- Ambiente .NET: configure um ambiente .NET para executar o código fornecido.
- Diretório de documentos: defina o caminho para o diretório de documentos no trecho de código.
Agora que você tem tudo pronto, vamos começar a extrair recursos para GeoJSON!
## Importar namespaces
Primeiramente, inclua os namespaces necessários em seu código:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Esses namespaces são essenciais para trabalhar com as funcionalidades do Aspose.GIS.
## Etapa 1: Abra o Shapefile de entrada
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Seu código para processar o shapefile de entrada vai aqui
}
```
 Abra o Shapefile de entrada usando o`VectorLayer.Open` método.
## Etapa 2: Criar GeoJSON de saída
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Seu código para criar a saída GeoJSON vai aqui
}
```
 Crie a saída GeoJSON usando o`VectorLayer.Create` método.
## Etapa 3: copiar atributos
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Copie atributos da camada de entrada para a camada de saída usando o`CopyAttributes` método.
## Etapa 4: Recursos do Processo
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Seu código para processar cada recurso de entrada vai aqui
}
```
Itere cada recurso na camada de entrada e processe-os individualmente.
## Etapa 5: filtrar recursos por data
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtre recursos com base em uma condição de data. Neste exemplo, ele ignora recursos com data de nascimento anterior a 1982.
## Etapa 6: construir um novo recurso
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Construa um novo recurso para a camada de saída, copiando a geometria e os valores do recurso de entrada.
Parabéns! Você extraiu com sucesso recursos para GeoJSON usando Aspose.GIS for .NET.
## Conclusão
Neste tutorial, exploramos o processo de extração de recursos para GeoJSON usando Aspose.GIS for .NET. Esta poderosa biblioteca abre um mundo de possibilidades para o desenvolvimento de GIS. Experimente diferentes conjuntos de dados e funcionalidades para desbloquear todo o potencial do Aspose.GIS.
## Perguntas frequentes
### P: Onde posso encontrar mais documentação?
 Visite a[Documentação Aspose.GIS](https://reference.aspose.com/gis/net/) para obter informações detalhadas.
### P: Como posso obter uma licença temporária?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso procurar suporte?
 Junte-se a[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoio e discussões da comunidade.
### P: Existe um teste gratuito disponível?
 Sim, você pode encontrar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Onde posso comprar o Aspose.GIS para .NET?
 Você pode comprar o produto[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
