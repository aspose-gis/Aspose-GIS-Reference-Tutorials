---
date: 2026-04-09
description: Aprenda como atribuir referência espacial e definir a precisão decimal
  ao criar pontos em C# com Aspose.GIS para .NET em suas aplicações .NET.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Especificar variante WKT na tradução
second_title: Aspose.GIS .NET API
title: Atribuir Referência Espacial e Definir Variante WKT usando Aspose.GIS
url: /pt/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atribuir Referência Espacial e Definir Variante WKT usando Aspose.GIS

## Introdução
Neste tutorial você aprenderá como **atribuir referência espacial** a uma geometria e controlar o formato exato da saída WKT com Aspose.GIS para .NET. Seja para **criar ponto C#** objetos para mapeamento, análise ou troca de dados, poder escolher a variante WKT correta e a precisão numérica torna seus dados espaciais interoperáveis e fáceis de ler. Vamos percorrer o processo passo a passo.

## Respostas Rápidas
- **O que significa “atribuir referência espacial”?** Ela vincula uma geometria a um sistema de coordenadas específico, como WGS‑84.  
- **Quais variantes WKT são suportadas?** Iso, SimpleFeatureAccessOutdated e ExtendedPostGis.  
- **Como posso controlar a precisão decimal?** Use as opções `NumericFormat` como `General`, `RoundTrip` ou `Flat`.  
- **Preciso de uma licença?** Um teste gratuito está disponível; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são compatíveis?** .NET Framework 4.0+ e .NET Core/5/6+.

## O que significa “atribuir referência espacial”?
Atribuir uma referência espacial (ou sistema de referência espacial, SRS) informa ao software GIS como interpretar os valores de coordenadas de uma geometria. Sem um SRS, os números de latitude‑longitude de um ponto não têm significado no mundo real.

## Por que controlar a variante WKT e o formato numérico?
Diferentes ferramentas GIS esperam sintaxes WKT ligeiramente diferentes. Selecionar a variante correta garante troca de dados sem problemas, enquanto definir a precisão decimal evita erros de arredondamento ou números excessivamente longos que poluem logs e arquivos.

## Pré-requisitos
1. Aspose.GIS para .NET – download da [página de download](https://releases.aspose.com/gis/net/).  
2. Um ambiente de desenvolvimento .NET (Visual Studio, VS Code ou Rider).  
3. Familiaridade básica com C# e o framework .NET.

## Importar Namespaces
Antes de usar quaisquer classes Aspose.GIS, importe os namespaces necessários:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Etapa 1: Criar um Objeto Point (criar ponto C#)
Começamos construindo um `Point` com latitude, longitude e um valor de medida (M) opcional:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Etapa 2: Atribuir Sistema de Referência Espacial (SRS)
Agora **atribuímos referência espacial** ao ponto. Aqui usamos o sistema amplamente suportado WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Etapa 3: Especificar a Variante WKT Desejada
Escolha a variante WKT que corresponde à sua aplicação downstream:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Etapa 4: Definir Precisão Decimal para a Saída WKT
Controle quantos dígitos aparecem na string final usando `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Armadilhas Comuns e Dicas
- **Armadilha:** Esquecer de definir o SRS antes de chamar `AsText` pode resultar na falta de informação SRID.  
- **Dica:** Use `NumericFormat.RoundTrip` quando precisar de ida‑e‑volta sem perdas das coordenadas.  
- **Dica:** A variante `Iso` é a mais portátil; escolha `ExtendedPostGis` somente quando precisar do SRID incorporado.

## Conclusão
Agora você sabe como **atribuir referência espacial**, escolher a variante WKT apropriada e **definir a precisão decimal** ao **criar ponto C#** objetos com Aspose.GIS. Esses controles lhe dão a flexibilidade para atender aos requisitos exatos de qualquer fluxo de trabalho GIS, desde visualização simples até análise espacial de alta precisão.

## Perguntas Frequentes

**Q:** O Aspose.GIS é compatível com todas as versões do .NET?  
**A:** Sim, o Aspose.GIS suporta .NET Framework 4.0 e superiores, bem como .NET Core/5/6.

**Q:** Posso usar o Aspose.GIS em projetos comerciais?  
**A:** Absolutamente. Uma licença comercial é necessária para uso em produção, mas um teste gratuito está disponível para avaliação.

**Q:** O Aspose.GIS suporta outros formatos de dados espaciais?  
**A:** Sim, ele funciona com ESRI Shapefile, GeoJSON, KML e muitos outros formatos.

**Q:** Onde posso baixar um teste gratuito?  
**A:** Você pode baixar uma versão de teste gratuita do Aspose.GIS [aqui](https://releases.aspose.com/).

**Q:** Como obtenho ajuda se encontrar problemas?  
**A:** Publique suas perguntas no [fórum](https://forum.aspose.com/c/gis/33) da comunidade Aspose.GIS, onde tanto a equipe da Aspose quanto membros da comunidade podem ajudar.

---

**Última atualização:** 2026-04-09  
**Testado com:** Aspose.GIS para .NET (última versão)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}