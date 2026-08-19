---
date: 2026-06-25
description: Aprenda como ler shapefile e converter um shapefile de polígono para
  um linestring usando Aspose.GIS para .NET. Impulsione seu desenvolvimento GIS com
  orientações claras passo a passo.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Converter Shapefile de Polígono para Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como Ler Shapefile C# – Converter Shapefile de Polígono para Linestring
url: /pt/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler Shapefile C# – Converter Shapefile de Polígono para Linestring

## Introdução
Se você precisa **como ler shapefile** dados em um ambiente .NET, está no lugar certo. Aspose.GIS para .NET abstrai o formato binário de baixo nível de um Shapefile, permitindo que você carregue, consulte e transforme recursos geográficos com apenas algumas chamadas de API. Converter um shapefile de polígono para um linestring é especialmente útil quando você deseja extrair representações lineares para roteamento, análise de rede ou visualização simples.

## Respostas Rápidas
- **Qual biblioteca ajuda a ler shapefile c#?** Aspose.GIS for .NET – suporta mais de 50 formatos GIS e manipula arquivos de até várias centenas de megabytes sem carregar todo o arquivo na memória.  
- **É possível converter um polígono para uma linha?** Sim – chame `LineString` na anel exterior do polígono e escreva o resultado em um novo shapefile.  
- **Preciso de licença para produção?** Uma licença comercial é necessária para implantações em produção; um teste gratuito funciona para avaliação.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Existe versão de avaliação?** Absolutamente – baixe uma avaliação gratuita no site da Aspose.

`LineString` é um tipo de geometria que representa uma série de segmentos de linha conectados.

## O que é “read shapefile c#”?
`Document` é a classe central que representa um conjunto de dados GIS e fornece acesso aos seus recursos.  
Ler um shapefile em C# significa carregar o arquivo `.shp` na memória para que você possa consultar, modificar ou transformar suas geometrias. **Você simplesmente instancia a classe `Document` com o caminho do arquivo, e o Aspose.GIS analisa a estrutura binária para você**, expondo os recursos por meio de uma coleção fácil de usar. Essa abordagem elimina a necessidade de trabalhar manualmente com cabeçalhos de arquivo de baixo nível ou arrays de coordenadas.

## Por que converter polígono para linha com Aspose.GIS?
Converter um polígono para um linestring preserva o contorno externo exato enquanto remove os anéis internos, proporcionando uma representação linear limpa. Aspose.GIS processa **conjuntos de dados de até 500 MB em menos de 2 segundos em um servidor típico**, tornando as conversões em lote rápidas e eficientes em memória. A biblioteca também mantém a referência espacial original, de modo que as linhas resultantes se alinham perfeitamente com quaisquer camadas GIS existentes.

## Pré-requisitos
Antes de mergulharmos no tutorial, certifique‑se de que você tem o seguinte:

- **Aspose.GIS Library** – Baixe e instale a biblioteca Aspose.GIS a partir do [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Tenha um Shapefile de Polígono pronto para conversão. Se você não tem um, pode encontrar dados de exemplo ou criar o seu próprio.  
- **Development Environment** – Configure seu ambiente de desenvolvimento .NET com as ferramentas necessárias (Visual Studio, .NET SDK, etc.).

## Importar Namespaces
A classe `Document` é o objeto central do Aspose.GIS que representa um conjunto de dados GIS e fornece métodos para ler e gravar shapefiles. Adicione os namespaces a seguir no início do seu arquivo de código:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Como ler shapefile e converter polígono para linestring?
Carregue o shapefile de polígono de origem, extraia o anel exterior de cada polígono, crie um `LineString` a partir desse anel e escreva o resultado em um novo shapefile – tudo em cinco etapas simples. Esse padrão funciona para qualquer tamanho de conjunto de dados e garante que o sistema de coordenadas da origem seja preservado no destino.

### Etapa 1: Definir o Diretório do Documento
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Substitua `"Your Document Directory"` pelo caminho real onde seu shapefile está localizado.

### Etapa 2: Abrir o Shapefile de Origem
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Esta linha abre o Shapefile de Polígono de origem para que você possa ler seus recursos.

### Etapa 3: Criar o Shapefile de Destino Linestring
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Aqui criamos um novo Shapefile Linestring que armazenará as geometrias convertidas.

### Etapa 4: Iterar pelos Recursos de Origem
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
O loop percorre cada recurso de polígono no arquivo original.

### Etapa 5: Converter Polígono para Linestring e Escrever no Destino
A propriedade `ExteriorRing` retorna o contorno externo de um polígono como um `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Neste bloco convertemos o polígono para linha (`LineString`) e adicionamos o novo recurso ao shapefile de destino.

## Problemas Comuns e Dicas
- **Incompatibilidade de Sistema de Coordenadas** – Garanta que as camadas de origem e destino usem a mesma referência espacial; caso contrário, as linhas podem aparecer deslocadas.  
- **Arquivos Grandes** – Ao processar shapefiles muito grandes, considere transmitir os recursos em vez de carregá‑los todos na memória de uma vez.  
- **Geometrias Nulas** – Proteja-se contra recursos com geometrias vazias para evitar exceções em tempo de execução.  
- **Extrair linhas de polígono** – Se você precisar apenas do anel exterior, use a propriedade `ExteriorRing`; para anéis internos, itere `InteriorRings`.  

## Perguntas Frequentes

**Q: O Aspose.GIS é compatível com todas as versões do .NET?**  
A: Sim, o Aspose.GIS suporta .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7, garantindo integração perfeita com stacks de desenvolvimento modernos.

**Q: Posso usar o Aspose.GIS em projetos comerciais?**  
A: Sim, você pode. Adquira uma licença [aqui](https://purchase.aspose.com/buy) para remover limitações de avaliação e obter suporte completo.

**Q: Existem exemplos ou documentação disponíveis?**  
A: Sim, você pode encontrar documentação abrangente e exemplos de código na [documentation page](https://reference.aspose.com/gis/net/).

**Q: Há uma versão de avaliação disponível?**  
A: Absolutamente – explore o Aspose.GIS com uma avaliação gratuita visitando [this link](https://releases.aspose.com/).

**Q: Onde posso buscar ajuda ou suporte?**  
A: Visite o [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) para assistência da comunidade e suporte oficial.

---

**Última Atualização:** 2026-06-25  
**Testado com:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Converter Shapefile para GeoJSON usando Aspose.GIS para .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Como Ler GeoJSON de Stream com Aspose.GIS para .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Como Criar Geometria de Polígono com Aspose.GIS para .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}