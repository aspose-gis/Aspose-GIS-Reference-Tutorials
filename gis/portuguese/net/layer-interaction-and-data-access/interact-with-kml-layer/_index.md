---
date: 2026-01-07
description: Aprenda a escrever arquivos KML usando o Aspose.GIS para .NET, como criar
  KML, adicionar um atributo booleano e criar uma linha (line string) em seus aplicativos.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Como escrever um arquivo KML com Aspose.GIS para .NET
url: /pt/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar um Arquivo KML com Aspose.GIS para .NET

## Introdução
No mundo orientado a dados de hoje, a capacidade de **escrever arquivos KML** programaticamente lhe dá o poder de compartilhar informações geográficas entre plataformas, visualizar rotas em mapas e integrar dados de localização em aplicativos web ou móveis. Aspose.GIS para .NET torna esse processo simples, permitindo que você se concentre na lógica em vez das complexidades do formato de arquivo. Neste tutorial, percorreremos a criação de uma camada KML, a adição de atributos (incluindo um atributo booleano) e a construção de uma geometria de linha – tudo com código claro, passo a passo.

## Respostas Rápidas
- **O que significa “escrever arquivo KML”?** Gerar um documento KML (Keyhole Markup Language) que descreve recursos geográficos como pontos, linhas e polígonos.  
- **Qual biblioteca é a melhor para .NET?** Aspose.GIS para .NET oferece uma API fluente para criar e editar arquivos KML.  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença é necessária para uso em produção.  
- **Posso adicionar atributos personalizados?** Sim – você pode adicionar atributos string, integer, boolean e double a cada recurso.  
- **A criação de geometria é suportada?** Absolutamente – você pode criar pontos, linhas, polígonos e muito mais.

## Pré‑requisitos
Antes de iniciar esta jornada, certifique‑se de que você tem os seguintes pré‑requisitos:
- Aspose.GIS para .NET: Baixe e instale a biblioteca a partir da [página de download do Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Ambiente de Desenvolvimento: Configure um ambiente adequado, como o Visual Studio, para integrar o Aspose.GIS perfeitamente em seus projetos .NET.

## Importar Namespaces
Antes de começarmos a interagir com camadas KML, inclua os namespaces necessários em seu projeto. Esta etapa garante que você tenha acesso às classes e métodos requeridos para a manipulação de dados geoespaciais.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Etapa 1: Definir o Diretório do Documento
Defina o caminho para o diretório onde os arquivos KML serão armazenados.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar uma Camada KML
Inicialize uma camada KML usando Aspose.GIS, especificando o caminho para o arquivo KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Etapa 3: Definir Atributos (adicionar atributo booleano)
Adicione atributos à camada KML para representar diferentes tipos de dados, como string, integer, **boolean**, e double. É aqui que você “adiciona atributo booleano” a cada recurso.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Etapa 4: Construir e Popular Recursos (criar linha)
Construa recursos que representam entidades geoespaciais e defina valores para os atributos definidos. Aqui nós **criamos uma linha** (line string) para ilustrar um caminho simples.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Etapa 5: Adicionar Outro Recurso
Repita o processo para adicionar um segundo recurso com valores de atributos diferentes e uma geometria nula.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Como Escrever um Arquivo KML – Juntando Tudo
Seguindo as etapas acima, você agora tem um arquivo KML totalmente funcional que contém atributos personalizados (incluindo uma bandeira boolean) e uma geometria de linha. Você pode abrir o `Kml_File_out.kml` resultante no Google Earth, ArcGIS ou qualquer visualizador GIS que suporte KML.

## Problemas Comuns & Solução de Problemas
- **Erros de caminho de arquivo** – Certifique‑se de que `dataDir` termina com um separador de caminho (`\` ou `/`) adequado ao seu SO.  
- **Licença ausente** – A avaliação funciona para testes, mas uma versão licenciada é necessária para escrita ilimitada de arquivos KML.  
- **Geometria nula** – Definir `Geometry.Null` é intencional para recursos sem dados espaciais; omita se você sempre precisar de geometria.

## Perguntas Frequentes
### O Aspose.GIS é compatível com outros formatos GIS?
Sim, o Aspose.GIS suporta vários formatos GIS, incluindo shapefile, GeoJSON e KML.

### Posso visualizar os dados geoespaciais criados com Aspose.GIS?
Absolutamente! O Aspose.GIS integra‑se perfeitamente com bibliotecas de mapeamento, permitindo a visualização dos seus dados geoespaciais.

### Existe uma versão de avaliação disponível para o Aspose.GIS?
Sim, você pode explorar os recursos do Aspose.GIS baixando a [versão de avaliação gratuita](https://releases.aspose.com/).

### Como posso obter suporte para o Aspose.GIS?
Visite o [fórum do Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade ou explore opções de suporte premium [aqui](https://purchase.aspose.com/buy).

### Licenças temporárias estão disponíveis para o Aspose.GIS?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

## Perguntas Frequentes Adicionais

**Q: Como eu **crio arquivos KML** com estilo personalizado?**  
A: Use o namespace `Aspose.Gis.Formats.Kml.Styles` para definir ícones, cores de linhas e estilos de rótulo antes de adicionar recursos.

**Q: Posso escrever arquivos KML grandes de forma eficiente?**  
A: Escreva recursos em lotes e faça flush da camada periodicamente para manter o uso de memória baixo.

**Q: O Aspose.GIS suporta .NET Core e .NET 6+?**  
A: Sim, a biblioteca é totalmente compatível com .NET Core, .NET 5 e .NET 6.

---

**Última atualização:** 2026-01-07  
**Testado com:** Aspose.GIS 24.10 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}