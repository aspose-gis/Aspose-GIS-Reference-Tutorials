---
date: 2026-07-05
description: Aprenda como converter shapefile para geojson usando Aspose.GIS para
  .NET. O guia também aborda copiar atributos entre camadas e gerar arquivo geojson
  em C#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Extrair recursos para GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Converter Shapefile para GeoJSON com Aspose.GIS para .NET
url: /pt/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter Shapefile para GeoJSON com Aspose.GIS para .NET

## Introdução
Neste tutorial abrangente, passo a passo, você aprenderá **como converter shapefile para geojson** usando a poderosa biblioteca Aspose.GIS para .NET. Seja construindo um serviço web de mapeamento, preparando dados para um aplicativo GIS móvel ou simplesmente precisando trocar dados entre formatos, este guia mostra exatamente o que fazer, por que cada passo é importante e como evitar armadilhas comuns.

## Respostas Rápidas
- **O que este tutorial cobre?** Conversão de um Shapefile para um arquivo GeoJSON, cópia de atributos entre camadas e geração da saída com C#.
- **Qual biblioteca é necessária?** Aspose.GIS para .NET.
- **Preciso de uma licença?** Uma licença temporária ou completa é necessária para produção; um teste gratuito funciona para avaliação.
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para uma conversão básica.
- **Posso executar isso no .NET Core/.NET 6?** Sim – o código funciona em todas as versões suportadas do .NET.

## O que é converter shapefile para geojson?
Converter um Shapefile para GeoJSON significa ler recursos vetoriais do clássico formato ESRI Shapefile e gravá‑los como um documento GeoJSON moderno e amigável para a web. Essa transformação permite alimentar dados GIS diretamente em bibliotecas de mapeamento JavaScript como Leaflet ou Mapbox GL, e simplifica a troca de dados entre ferramentas GIS de desktop e APIs web.

## Por que usar Aspose.GIS para esta conversão?
Aspose.GIS abstrai a análise binária de baixo nível, suporta mais de 50 formatos de entrada e saída, e pode processar conjuntos de dados com centenas de páginas sem carregar o arquivo inteiro na memória. A biblioteca também fornece uma API limpa e orientada a objetos que funciona em .NET Framework, .NET Core e .NET 5/6, permitindo que você dedique tempo à lógica de negócios em vez de às peculiaridades de formatos.

## Pré-requisitos
- Aspose.GIS para .NET: Certifique‑se de que a biblioteca está instalada. Caso não esteja, você pode baixá‑la na [página Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Dados Shapefile: Tenha um Shapefile pronto para entrada. Se precisar de dados de exemplo, pode encontrá‑los na [documentação Aspose.GIS](https://reference.aspose.com/gis/net/).
- Ambiente .NET: Configure um ambiente .NET para executar o código fornecido.
- Diretório de Documentos: Defina o caminho para o seu diretório de documentos no trecho de código.

Agora que tudo está pronto, vamos começar a converter shapefile para geojson!

## Como Converter Shapefile para GeoJSON
Carregue o Shapefile de origem, crie uma camada GeoJSON de destino, copie o esquema de atributos, filtre os registros e grave os resultados — tudo em alguns passos concisos. O fluxo de trabalho completo cabe confortavelmente em um único bloco `using`, garantindo que os recursos sejam liberados automaticamente.

### Etapa 1: Abrir Shapefile de Entrada
O método `VectorLayer.Open` lê um Shapefile e retorna uma coleção enumerável de objetos `Feature` que podem ser iterados.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Etapa 2: Criar GeoJSON de Saída
`VectorLayer.Create` com o driver `Drivers.GeoJson` cria um arquivo GeoJSON vazio pronto para receber recursos.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Etapa 3: Copiar Atributos Entre Camadas
`CopyAttributes` copia o esquema de atributos (nomes de campos e tipos de dados) do Shapefile de origem para a nova camada GeoJSON em uma única chamada.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Etapa 4: Processar Recursos
Itere por cada recurso no Shapefile para que você possa aplicar qualquer lógica personalizada antes de gravá‑lo.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Etapa 5: Filtrar Recursos por Data
Neste exemplo, ignoramos registros cujo campo `dob` (data de nascimento) está ausente ou é anterior a 1 Jan 1982. Ajuste o filtro para atender aos requisitos dos seus próprios dados.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Etapa 6: Construir um Novo Recurso (C# Gerar Arquivo GeoJSON)
Um `Feature` representa um único elemento espacial contendo geometria e dados de atributos.  
Aqui construímos um novo `Feature` para a camada GeoJSON, copiamos a geometria e os valores de atributos e o adicionamos à saída. Este é o núcleo de *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Parabéns! Você converteu **shapefile para geojson** com sucesso e aprendeu como **copiar atributos entre camadas** ao longo do caminho.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|--------|
| O arquivo de saída está vazio | `CopyAttributes` chamado após a camada de saída ser fechada | Certifique‑se de que o bloco `using` para `outputLayer` permaneça aberto até depois que todos os recursos sejam adicionados. |
| O filtro de data remove todos os registros | Nome de campo errado ou formato de data inesperado | Verifique o nome do atributo (`dob`) e use `GetValue<string>` se as datas estiverem armazenadas como strings. |
| Exceção de licença | Executando sem uma licença válida do Aspose.GIS em produção | Aplique uma licença temporária ou completa conforme descrito na documentação da Aspose. |

## Perguntas Frequentes
**Q: Onde posso encontrar mais documentação?**  
A: Visite a [documentação Aspose.GIS](https://reference.aspose.com/gis/net/) para informações detalhadas.

**Q: Como posso obter uma licença temporária?**  
A: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso buscar suporte?**  
A: Participe do [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade e discussões.

**Q: Existe uma avaliação gratuita disponível?**  
A: Sim, você pode encontrar a avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso comprar Aspose.GIS para .NET?**  
A: Você pode adquirir o produto [aqui](https://purchase.aspose.com/buy).

## Conclusão
Neste tutorial exploramos o processo completo de **converter shapefile para geojson** usando Aspose.GIS para .NET, demonstramos como **copiar atributos entre camadas** e mostramos uma maneira limpa de *c# generate geojson file*. Experimente diferentes filtros, conjuntos de dados maiores ou transformações geométricas adicionais para aproveitar ao máximo as capacidades da biblioteca.

---

**Last Updated:** 2026-07-05  
**Testado com:** Aspose.GIS for .NET (latest stable release)  
**Autor:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Tutoriais Relacionados

- [Como Converter GeoJSON para File GDB Usando Aspose.GIS para .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Como Ler GeoJSON de Stream com Aspose.GIS para .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Como Converter GeoJSON para TopoJSON com Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}