---
date: 2026-01-13
description: Aprenda como criar um novo shapefile com Aspose.GIS para .NET. Este guia
  passo a passo mostra como definir uma camada vetorial, adicionar um atributo de
  data e gerenciar dados espaciais.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Criar Novo Shapefile
url: /pt/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Novo Shapefile

## Introdução
Se você está se aprofundando no desenvolvimento de sistemas de informação geográfica (GIS) com .NET, Aspose.GIS é a sua solução ideal. Esta poderosa biblioteca permite que os desenvolvedores trabalhem de forma fluida com dados espaciais e, neste tutorial, vamos guiá‑lo sobre como **criar um novo shapefile** usando Aspose.GIS para .NET. Você verá por que definir uma camada vetorial e adicionar um atributo de data são etapas essenciais para projetos GIS robustos.

## Respostas Rápidas
- **O que este tutorial ensina?** Como criar um novo shapefile, definir uma camada vetorial e adicionar atributos (incluindo um campo de data).  
- **Qual biblioteca é necessária?** Aspose.GIS para .NET.  
- **Preciso de licença?** Uma avaliação gratuita serve para aprendizado; uma licença comercial é necessária para produção.  
- **Qual IDE devo usar?** Visual Studio (qualquer versão recente).  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para o exemplo básico.

## Pré‑requisitos
Antes de começarmos o tutorial, certifique‑se de que você tem os seguintes pré‑requisitos:
- Compreensão básica da linguagem de programação C#.
- Visual Studio instalado na sua máquina.
- Biblioteca Aspose.GIS para .NET. Você pode baixá‑la [aqui](https://releases.aspose.com/gis/net/).

## Importar Namespaces
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

## Etapa 1: Configurar Seu Projeto
Inicie criando um novo projeto C# no Visual Studio e inclua a biblioteca Aspose.GIS.

## Etapa 2: Definir o Diretório de Documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua *Your Document Directory* pelo caminho real onde você deseja salvar seu novo shapefile.

## Etapa 3: Criar um VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Este segmento de código **define uma camada vetorial** e declara três atributos: um campo de texto (`name`), um campo inteiro (`age`) e um campo data‑hora (`dob`). Adicionar o atributo de data é crucial para análises GIS temporais.

## Etapa 4: Adicionar Recursos
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
Aqui criamos dois pontos, definimos cada atributo separadamente e adicionamos os recursos à camada.

### Caso 2: Define Novos Valores para Todos os Atributos
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Nesta abordagem preenchemos todos os valores de atributos em uma única chamada usando um array de objetos — útil quando há muitos atributos.

## Por Que Isso É Importante
Criar um shapefile programaticamente permite automatizar pipelines de dados, gerar conjuntos de teste ou integrar a saída GIS diretamente em serviços web. Ao dominar **como criar shapefile** com Aspose.GIS, você obtém controle total sobre a geometria dos recursos, o esquema de atributos e a conformidade com o formato de arquivo.

## Erros Comuns & Dicas
- **Separadores de caminho:** Use `Path.Combine` para compatibilidade entre plataformas em vez de concatenação de strings.  
- **Ordem dos atributos:** A ordem dos valores em `SetValues` deve corresponder à ordem em que você adicionou os atributos.  
- **Manipulação de datas:** Sempre use `DateTimeKind.Utc` se seus dados GIS forem compartilhados entre fusos horários.

## Conclusão
Parabéns! Você criou com sucesso um novo shapefile usando Aspose.GIS para .NET. Este tutorial abordou o básico de configurar seu projeto, definir uma camada vetorial e adicionar recursos — incluindo um atributo de data. À medida que você avança, consulte a [documentação](https://reference.aspose.com/gis/net/) para recursos e funcionalidades avançadas.

## Perguntas Frequentes
### Q: Posso usar Aspose.GIS com outras linguagens de programação?
Aspose.GIS suporta principalmente .NET, mas também há versões disponíveis para Java.

### Q: Existe uma avaliação gratuita disponível?
Sim, você pode acessar a avaliação gratuita [aqui](https://releases.aspose.com/).

### Q: Onde posso encontrar suporte para Aspose.GIS?
Visite o [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade e discussões.

### Q: Como posso obter uma licença temporária?
Obtenha sua licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q: Onde posso comprar Aspose.GIS para .NET?
Você pode adquirir a biblioteca [aqui](https://purchase.aspose.com/buy).

---

**Última atualização:** 2026-01-13  
**Testado com:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}