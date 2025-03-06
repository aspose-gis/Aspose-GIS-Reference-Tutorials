---
title: Gravar recursos no TopoJSON
linktitle: Gravar recursos no TopoJSON
second_title: API Aspose.GIS .NET
description: Domine a escrita de recursos TopoJSON com Aspose.GIS para .NET. Siga nosso tutorial passo a passo. Eleve seus aplicativos GIS.
weight: 24
url: /pt/net/layer-data-operations/write-features-to-topojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gravar recursos no TopoJSON

## Introdução
No domínio do desenvolvimento de Sistemas de Informação Geográfica (GIS), Aspose.GIS for .NET se destaca como um poderoso kit de ferramentas, oferecendo uma infinidade de funcionalidades para manipulação de dados espaciais. Entre seus muitos recursos, este tutorial se concentra em uma tarefa específica: escrever recursos no formato TopoJSON usando Aspose.GIS for .NET. Se você deseja aprimorar seus aplicativos GIS com suporte TopoJSON, siga em frente para descobrir um guia passo a passo.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Aspose.GIS for .NET: Certifique-se de ter a biblioteca Aspose.GIS instalada. Você pode encontrar a documentação e baixar a biblioteca[aqui](https://reference.aspose.com/gis/net/).
- Ambiente .NET: certifique-se de ter um ambiente de desenvolvimento .NET configurado.
-  Diretório de documentos: Escolha um diretório para seus documentos. Isto será referido como`Your Document Directory` nos exemplos de código.
## Importar namespaces
Em seu aplicativo .NET, inclua os namespaces necessários para trabalhar com Aspose.GIS e outras funcionalidades necessárias.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
Agora, vamos dividir o exemplo de código em várias etapas para uma compreensão clara.
## 1. Defina o diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```
 Substituir`"Your Document Directory"` com o caminho real para o diretório do seu documento.
## 2. Especifique o caminho de saída
```csharp
var outputPath = dataDir + "sample_out.topojson";
```
Defina o caminho para o arquivo TopoJSON de saída.
## 3. Crie um VectorLayer com driver TopoJSON
```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```
Inicialize um VectorLayer usando o driver TopoJSON.
## 4. Adicione atributos à camada
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```
Defina atributos para as feições a serem adicionadas à camada.
## 5. Adicione recursos à camada
```csharp
var feature0 = layer.ConstructFeature();
feature0.SetValue("name", "name_0");
feature0.SetValue("measurement", 1.03);
feature0.SetValue("id", 0);
feature0.Geometry = new Point(1.3, 2.3);
layer.Add(feature0);
var feature1 = layer.ConstructFeature();
feature1.SetValue("name", "name_1");
feature1.SetValue("measurement", 10.03);
feature1.SetValue("id", 1);
feature1.Geometry = new Point(241.32, 23.2);
layer.Add(feature1);
```
Construa recursos com atributos e geometrias especificados e adicione-os à camada.
## Conclusão
Parabéns! Você escreveu recursos para TopoJSON com sucesso usando Aspose.GIS for .NET. Este tutorial fornece uma compreensão básica do processo, permitindo que você integre perfeitamente essa funcionalidade em seus aplicativos GIS.
## perguntas frequentes
### P: Posso usar Aspose.GIS for .NET com outras bibliotecas GIS?
R: O Aspose.GIS for .NET foi projetado para funcionar de forma independente, mas a integração com outras bibliotecas é possível para funcionalidades aprimoradas.
### P: Existe alguma opção de licenciamento para Aspose.GIS?
 R: Sim, você pode explorar opções de licenciamento e fazer compras[aqui](https://purchase.aspose.com/buy).
### P: Existe uma avaliação gratuita disponível para Aspose.GIS for .NET?
 R: Absolutamente! Você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Onde posso buscar suporte ou me conectar com a comunidade Aspose.GIS?
 R: Vá para o[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para apoio e discussões da comunidade.
### P: Como posso obter uma licença temporária para Aspose.GIS?
 R: Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
