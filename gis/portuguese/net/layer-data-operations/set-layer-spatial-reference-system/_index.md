---
date: 2025-12-31
description: Aprenda a criar camada vetorial e definir o sistema de referência espacial
  da camada com Aspose.GIS para .NET. Domine a definição de referência espacial, a
  adição de recurso ponto e a recuperação do código EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Criar camada vetorial e definir o sistema de referência espacial da camada
url: /pt/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial e Definir o Sistema de Referência Espacial da Camada

## Introdução
No vasto cenário dos Sistemas de Informação Geográfica (GIS), **Aspose.GIS for .NET** destaca‑se como uma ferramenta robusta e versátil para desenvolvedores. Neste tutorial você **criará camada vetorial**, definirá sua referência espacial, adicionará um recurso ponto e recuperará o código EPSG — tudo com orientações claras, passo a passo. Seja você um engenheiro GIS experiente ou esteja começando, essas técnicas ajudarão a definir corretamente o sistema de coordenadas do shapefile e melhorar a confiabilidade dos fluxos de trabalho de dados espaciais.

## Respostas Rápidas
- **O que significa “create vector layer”?** Cria uma nova camada GIS (por exemplo, um Shapefile) que pode armazenar geometrias como pontos, linhas ou polígonos.  
- **Qual código EPSG é usado no exemplo?** EPSG 26918 (NAD83 / zona UTM 18N).  
- **Posso adicionar um recurso ponto após criar a camada?** Sim — use `ConstructFeature()` e atribua uma geometria `Point`.  
- **Como recupero o CRS da camada?** Leia `layer.SpatialReferenceSystem.EpsgCode` ou `.Name`.  
- **Preciso de licença para o Aspose.GIS?** Um teste gratuito está disponível; uma licença é necessária para uso em produção.

## Pré‑requisitos
- Conhecimento prático de programação .NET.  
- Visual Studio instalado em seu sistema.  
- Biblioteca Aspose.GIS for .NET, que pode ser baixada [aqui](https://releases.aspose.com/gis/net/).  
- Compreensão básica de sistemas de referência espacial em GIS.

## Importar Namespaces
Em seu projeto .NET, comece importando os namespaces necessários para acessar as funcionalidades fornecidas pelo Aspose.GIS. Use o trecho de código a seguir:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Etapa 1: Especificar o Diretório de Documentos
Comece especificando o caminho para o seu diretório de documentos. Este será o local onde seus arquivos de dados espaciais são armazenados.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Definir Referência Espacial e Definir o Sistema de Coordenadas do Shapefile
Defina o caminho para o Shapefile e **defina a referência espacial** usando o código EPSG (26918 neste exemplo). Esta etapa **define o sistema de coordenadas do shapefile** para a camada.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Etapa 3: Criar Camada Vetorial
Agora **crie a camada vetorial** com o caminho do Shapefile especificado, tipo de driver (Shapefile) e o sistema de referência espacial que você acabou de definir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Etapa 4: Adicionar Recurso Ponto à Camada
Construa um novo recurso e **adicione o recurso ponto** definindo sua geometria (um `Point` com coordenadas 60, 24). Em seguida, adicione o recurso à camada vetorial.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Etapa 5: Recuperar Informações do Sistema de Referência Espacial (Recuperar Código EPSG)
Abra a Camada Vetorial e recupere informações sobre o sistema de referência espacial, como o código EPSG e o nome legível por humanos. Isso demonstra como **recuperar o código EPSG** e **definir o CRS da camada**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Repita estas etapas de acordo com seu caso de uso específico, e você estará bem encaminhado para dominar a arte de **criar camada vetorial** e gerenciar referências espaciais com Aspose.GIS for .NET.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **A camada falha ao abrir** | Driver errado ou caminho de arquivo corrompido | Verifique `Drivers.Shapefile` e assegure que `path` aponta para um arquivo `.shp` existente. |
| **CRS incorreto exibido** | Uso do código EPSG errado | Verifique novamente o código EPSG com uma fonte autoritária (por exemplo, EPSG.io). |
| **Recurso não salvo** | Não chamar `layer.Add(feature)` dentro do bloco `using` | Garanta que o método `Add` seja executado antes que a camada seja descartada. |

## Perguntas Frequentes
### O Aspose.GIS é compatível com outras bibliotecas GIS?
Sim, o Aspose.GIS integra‑se bem com outras bibliotecas GIS e pode ser usado em conjunto com elas.

### Posso usar o Aspose.GIS tanto para aplicativos desktop quanto web?
Absolutamente! O Aspose.GIS é versátil e pode ser utilizado tanto em aplicativos desktop quanto em aplicações baseadas na web.

### Existem opções de licenciamento disponíveis para o Aspose.GIS?
Sim, você pode explorar as opções de licenciamento e fazer uma compra [aqui](https://purchase.aspose.com/buy).

### Existe uma versão de teste gratuita disponível para o Aspose.GIS?
Certamente! Você pode baixar uma versão de teste gratuita [aqui](https://releases.aspose.com/).

### Onde posso buscar suporte para dúvidas relacionadas ao Aspose.GIS?
Para qualquer suporte ou dúvidas, visite o [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Perguntas Frequentes Adicionais
**Q: Como altero o CRS de um Shapefile existente?**  
A: Abra a camada, crie um novo `SpatialReferenceSystem` com o código EPSG desejado e atribua‑o a `layer.SpatialReferenceSystem` antes de salvar.

**Q: Posso adicionar outros tipos de geometria (por exemplo, polígonos) usando a mesma abordagem?**  
A: Sim — substitua `new Point(x, y)` por `new Polygon(...)` ou `new LineString(...)` conforme necessário.

**Q: É possível trabalhar com grandes conjuntos de dados de forma eficiente?**  
A: Use APIs de streaming (`VectorLayer.Create` com `FeatureCollection`) e descarte as camadas prontamente para liberar recursos.

**Q: O Aspose.GIS suporta transformação de coordenadas?**  
A: Sim — use `Geometry.Transform(targetSrs)` para reprojetar geometrias entre diferentes referências espaciais.

**Q: Quais versões do .NET são suportadas?**  
A: O Aspose.GIS funciona com .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Conclusão
Neste tutorial exploramos como **criar camada vetorial**, definir sua referência espacial, **adicionar recurso ponto** e **recuperar o código EPSG** usando Aspose.GIS for .NET. Ao dominar essas etapas, você poderá definir corretamente o sistema de coordenadas do shapefile, gerenciar o CRS da camada e construir aplicações GIS confiáveis.

---

**Última atualização:** 2025-12-31  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}