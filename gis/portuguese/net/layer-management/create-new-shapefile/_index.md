---
date: 2026-06-30
description: Aprenda como criar shapefile usando Aspose.GIS para .NET. Este guia passo
  a passo mostra como definir um vector layer, adicionar um date attribute e gerenciar
  spatial data de forma eficiente.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Criar novo Shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como criar Shapefile com Aspose.GIS para .NET
url: /pt/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Novo Shapefile

## Introdução
Se você está se aprofundando no desenvolvimento de sistemas de informação geográfica (GIS) com .NET, Aspose.GIS é a sua solução ideal para **como criar shapefile** programaticamente. Esta biblioteca oferece controle total sobre camadas vetoriais, esquemas de atributos e conformidade com o formato de arquivo, permitindo automatizar pipelines de dados ou gerar conjuntos de teste em minutos.

## Respostas Rápidas
- **O que este tutorial ensina?** Como criar um novo shapefile, definir uma camada vetorial e adicionar atributos (incluindo um campo de data).  
- **Qual biblioteca é necessária?** Aspose.GIS for .NET.  
- **Preciso de uma licença?** Um teste gratuito funciona para aprendizado; uma licença comercial é necessária para produção.  
- **Qual IDE devo usar?** Visual Studio (qualquer versão recente).  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para o exemplo básico.

## Como criar shapefile com Aspose.GIS para .NET?
Carregue a biblioteca Aspose.GIS, defina a pasta de saída, crie um `VectorLayer`, defina atributos e adicione recursos — todo esse fluxo de trabalho pode ser escrito em menos de 30 linhas de C#. A biblioteca gerencia a criação de geometria, tipagem de atributos e gravação de arquivos automaticamente, de modo que você não precise lidar com as especificações de baixo nível do Shapefile.

## Pré-requisitos
Antes de começarmos o tutorial, certifique‑se de que você tem os seguintes pré‑requisitos:
- Compreensão básica da linguagem de programação C#.  
- Visual Studio instalado na sua máquina.  
- Biblioteca Aspose.GIS for .NET. Você pode baixá‑la [aqui](https://releases.aspose.com/gis/net/).

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
Comece criando um novo projeto C# no Visual Studio e inclua a biblioteca Aspose.GIS.

## Etapa 2: Definir o Diretório de Documentos
```csharp
string dataDir = "Your Document Directory";
```
Substitua *Your Document Directory* pelo caminho real onde você deseja salvar seu novo shapefile.

## Etapa 3: Criar um VectorLayer
A classe `VectorLayer` representa uma única camada shapefile que armazena geometria e dados de atributos.  
Nesta etapa definimos uma camada vetorial e declaramos três atributos: um campo de texto (`name`), um campo inteiro (`age`) e um campo data‑hora (`dob`). Adicionar o atributo de data é crucial para análises **temporal GIS shapefile**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Etapa 4: Adicionar Recursos
### Caso 1: Define Valores Individualmente
O método `SetValues` atribui valores de atributos a um recurso na ordem em que foram definidos.  
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
Alternativamente, você pode fornecer todos os valores de atributos de uma só vez usando `SetValues` com um array de objetos.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Nessa abordagem preenchemos todos os valores de atributos em uma única chamada usando um array de objetos — útil quando você tem muitos atributos.

## Por Que Isso Importa?
Criar um shapefile programaticamente permite automatizar pipelines de dados, gerar conjuntos de teste ou incorporar a saída GIS diretamente em serviços web. Aspose.GIS suporta **30+ formatos vetoriais e raster** e pode gravar shapefiles de centenas de páginas sem carregar o arquivo inteiro na memória, oferecendo velocidade e escalabilidade.

## Armadilhas Comuns & Dicas
- **Separadores de caminho:** Use `Path.Combine` para compatibilidade multiplataforma em vez de concatenação de strings.  
- **Ordem dos atributos:** A ordem dos valores em `SetValues` deve corresponder à ordem em que você adicionou os atributos.  
- **Manipulação de datas:** Sempre use `DateTimeKind.Utc` se seus dados GIS forem compartilhados entre fusos horários.

## Conclusão
Parabéns! Você criou com sucesso um novo shapefile usando Aspose.GIS para .NET. Este tutorial abordou o básico de configurar seu projeto, definir uma camada vetorial e adicionar recursos — incluindo um atributo de data. À medida que você avança, consulte a [documentação](https://reference.aspose.com/gis/net/) para recursos avançados e funcionalidades.

## Perguntas Frequentes
**Q: Posso usar Aspose.GIS com outras linguagens de programação?**  
R: Aspose.GIS suporta principalmente .NET, mas também há versões disponíveis para Java.

**Q: Existe um teste gratuito disponível?**  
R: Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).

**Q: Onde posso encontrar suporte para Aspose.GIS?**  
R: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade e discussões.

**Q: Como posso obter uma licença temporária?**  
R: Obtenha sua licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso comprar Aspose.GIS para .NET?**  
R: Você pode comprar a biblioteca [aqui](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Tutoriais Relacionados

- [Obter Atributos da Camada – Recuperar Informações de Atributos da Camada com Aspose.GIS para .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Criar Camada Vetorial e Definir Sistema de Referência Espacial da Camada](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Criar Camada Vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}