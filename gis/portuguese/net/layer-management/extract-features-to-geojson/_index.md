---
date: 2026-01-13
description: Aprenda como converter shapefile para geojson usando Aspose.GIS para
  .NET. O guia também aborda a cópia de atributos entre camadas e a geração de arquivo
  geojson em C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Como converter Shapefile para GeoJSON usando Aspose.GIS para .NET
url: /pt/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter Shapefile para GeoJSON com Aspose.GIS para .NET

## Introdução
Neste tutorial abrangente, passo a passo, você aprenderá **como converter shapefile para geojson** usando a poderosa biblioteca Aspose.GIS para .NET. Seja você quem está construindo um serviço de mapeamento web, preparando dados para um aplicativo GIS móvel ou simplesmente precisa trocar dados entre formatos, este guia mostra exatamente o que fazer, por que cada etapa importa e como evitar armadilhas comuns.

## Respostas Rápidas
- **O que este tutorial cobre?** Conversão de um Shapefile para um arquivo GeoJSON, cópia de atributos entre camadas e geração da saída com C#.
- **Qual biblioteca é necessária?** Aspose.GIS para .NET.
- **Preciso de licença?** Uma licença temporária ou completa é necessária para produção; uma avaliação gratuita funciona para testes.
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para uma conversão básica.
- **Posso executar isso no .NET Core/.NET 6?** Sim – o código funciona em todas as versões suportadas do .NET.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem o seguinte:

- Aspose.GIS para .NET: Garanta que a biblioteca esteja instalada. Caso contrário, você pode baixá‑la na página [Aspose.GIS para .NET](https://releases.aspose.com/gis/net/).
- Dados Shapefile: Tenha um Shapefile pronto para entrada. Se precisar de dados de exemplo, você pode encontrá‑los na [documentação do Aspose.GIS](https://reference.aspose.com/gis/net/).
- Ambiente .NET: Configure um ambiente .NET para executar o código fornecido.
- Diretório de Documentos: Defina o caminho para o seu diretório de documentos no trecho de código.

Agora que tudo está pronto, vamos começar a converter shapefile para geojson!

## O que significa “converter shapefile para geojson”?
Converter um Shapefile para GeoJSON significa ler recursos vetoriais do formato clássico ESRI Shapefile e gravá‑los como um documento GeoJSON moderno e amigável para a web. GeoJSON é amplamente usado em bibliotecas de mapeamento JavaScript (Leaflet, Mapbox GL) e APIs, tornando a conversão uma tarefa frequente no desenvolvimento GIS.

## Por que usar Aspose.GIS para essa conversão?
Aspose.GIS abstrai os detalhes de baixo nível dos formatos de arquivo, permite copiar tabelas de atributos sem esforço e fornece uma API limpa e orientada a objetos que funciona em .NET Framework, .NET Core e .NET 5/6. Isso significa que você pode focar na lógica de negócio em vez de analisar arquivos binários.

## Importar Namespaces
Primeiro, inclua os namespaces necessários no seu código:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Esses namespaces são essenciais para trabalhar com as funcionalidades do Aspose.GIS.

## Como Converter Shapefile para GeoJSON
A seguir está o fluxo completo dividido em etapas claras. Cada etapa inclui uma breve explicação seguida pelo bloco de código exato que você precisa copiar para o seu projeto.

### Etapa 1: Abrir o Shapefile de Entrada
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Abra o Shapefile de entrada usando o método `VectorLayer.Open`. Isso fornece uma coleção enumerável de objetos `Feature`.

### Etapa 2: Criar o GeoJSON de Saída
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Crie o arquivo de saída com o método `VectorLayer.Create`, especificando o driver `Drivers.GeoJson`.

### Etapa 3: Copiar Atributos Entre Camadas
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Esta única linha copia o esquema de atributos (nomes de campos, tipos) do Shapefile de origem para a nova camada GeoJSON – exatamente o que a palavra‑chave secundária *copy attributes between layers* descreve.

### Etapa 4: Processar Recursos
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Itere por cada recurso no Shapefile para que você possa aplicar qualquer lógica personalizada antes de gravá‑lo.

### Etapa 5: Filtrar Recursos por Data
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Neste exemplo, ignoramos registros cujo campo `dob` (date of birth) está ausente ou anterior a 1 Jan 1982. Sinta‑se à vontade para ajustar o filtro conforme os requisitos dos seus dados.

### Etapa 6: Construir um Novo Recurso (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Aqui criamos um novo `Feature` para a camada GeoJSON, copiamos a geometria e os valores de atributos e o adicionamos à saída. Este é o núcleo de *c# generate geojson file*.

Parabéns! Você converteu com sucesso **shapefile para geojson** e aprendeu como copiar atributos entre camadas ao longo do caminho.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| Arquivo de saída vazio | `CopyAttributes` chamado após o fechamento da camada de saída | Garanta que o bloco `using` para `outputLayer` permaneça aberto até depois que todos os recursos sejam adicionados. |
| Filtro de data remove todos os registros | Nome de campo errado ou formato de data inesperado | Verifique o nome do atributo (`dob`) e use `GetValue<string>` se as datas estiverem armazenadas como strings. |
| Exceção de licença | Execução sem licença válida do Aspose.GIS em produção | Aplique uma licença temporária ou completa conforme descrito na documentação da Aspose. |

## Perguntas Frequentes
**P: Onde posso encontrar mais documentação?**  
R: Visite a [documentação do Aspose.GIS](https://reference.aspose.com/gis/net/) para informações detalhadas.

**P: Como obter uma licença temporária?**  
R: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**P: Onde posso buscar suporte?**  
R: Participe do [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para suporte da comunidade e discussões.

**P: Existe uma avaliação gratuita disponível?**  
R: Sim, você pode encontrar a avaliação gratuita [aqui](https://releases.aspose.com/).

**P: Onde posso comprar Aspose.GIS para .NET?**  
R: Você pode adquirir o produto [aqui](https://purchase.aspose.com/buy).

## Conclusão
Neste tutorial exploramos o processo completo de **converter shapefile para geojson** usando Aspose.GIS para .NET, demonstramos como copiar atributos entre camadas e mostramos uma forma limpa de *c# generate geojson file*. Experimente diferentes filtros, conjuntos de dados maiores ou transformações geométricas adicionais para aproveitar ao máximo as capacidades da biblioteca.

---

**Última atualização:** 2026-01-13  
**Testado com:** Aspose.GIS para .NET (última versão estável)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}