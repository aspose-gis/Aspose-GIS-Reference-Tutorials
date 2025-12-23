---
date: 2025-12-23
description: Aprenda a converter geometria para WKT com opções variantes, definir
  o formato numérico e ajustar a precisão decimal usando Aspose.GIS para .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Converter Geometria para Opções de Variante WKT usando Aspose.GIS
url: /pt/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter Geometria para Opções de Variante WKT usando Aspose.GIS

## Introdução
Em aplicações .NET modernas, **converter geometry to WKT** é uma etapa comum quando você precisa trocar dados espaciais com outros sistemas ou armazená‑los em um formato baseado em texto. Aspose.GIS para .NET torna essa conversão simples ao mesmo tempo que oferece controle total sobre a variante WKT, o formato numérico e a precisão decimal. Neste tutorial você aprenderá como converter geometry to WKT, escolher a variante correta e ajustar a saída para atender exatamente aos requisitos do seu projeto.

## Respostas Rápidas
- **O que significa “convert geometry to WKT”?** Ele transforma objetos geométricos (pontos, linhas, polígonos) na representação Well‑Known Text.  
- **Quais variantes de WKT são suportadas?** `Iso`, `SimpleFeatureAccessOutdated` e `ExtendedPostGis`.  
- **Como posso controlar a precisão decimal?** Use as opções `NumericFormat` como `General`, `RoundTrip` ou `Flat`.  
- **Preciso de licença para produção?** Sim, uma licença comercial é necessária para uso não‑trial.  
- **Quais versões do .NET são compatíveis?** .NET Framework 4.0+ e .NET 5/6/7.

## O que é “convert geometry to WKT”?
Converter geometry to WKT produz uma string legível por humanos que descreve objetos espaciais. Esse formato é amplamente aceito por ferramentas GIS, bancos de dados e serviços web, tornando‑o ideal para intercâmbio de dados.

## Por que usar Aspose.GIS para essa conversão?
- **Controle de precisão** – Escolha quantas casas decimais serão emitidas.  
- **Flexibilidade de variante** – Combine exatamente o dialeto WKT exigido pelo seu sistema downstream.  
- **Sem dependências externas** – Biblioteca pura .NET, sem binários nativos.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Aspose.GIS for .NET** – Baixe e instale a partir da [download page](https://releases.aspose.com/gis/net/).  
2. **Ambiente de Desenvolvimento** – Qualquer versão recente do Visual Studio ou VS Code com .NET SDK.  
3. **Conhecimento básico de C#** – Familiaridade com classes, objetos e o framework .NET.

## Importar Namespaces
Primeiro, traga os namespaces necessários para o escopo:

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

## Etapa 1: Criar um Objeto Point
Crie um `Point` que você irá posteriormente **convert geometry to WKT**. O ponto inclui latitude, longitude e um valor de medida (M) opcional:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Etapa 2: Definir Sistema de Referência Espacial (SRS)
Atribua um sistema de referência espacial para que a saída WKT saiba a qual sistema de coordenadas se refere. Aqui usamos o sistema comum WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Etapa 3: Especificar Variante WKT
Escolha a variante WKT apropriada quando você **convert geometry to WKT**. Cada variante formata a saída de forma ligeiramente diferente:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Etapa 4: Controlar o Formato Numérico (Definir Formato Numérico & Ajustar a Precisão Decimal)
Ajuste a representação numérica das coordenadas. A classe `NumericFormat` permite que você **set numeric format** e **adjust decimal precision** conforme suas necessidades:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Problemas Comuns & Dicas
- **Missing M value** – Se você não precisar de uma medida, omita a propriedade `M`; a variante ISO a removerá automaticamente.  
- **Unexpected precision** – Verifique se está usando o `NumericFormat` correto; `General` preserva a precisão total de double, enquanto `Flat` arredonda para o número especificado de casas decimais.  
- **SRID not displayed** – Apenas a variante `ExtendedPostGis` prefixa a saída com `SRID=`. Escolha essa variante quando seu sistema alvo esperar um SRID.

## Conclusão
Seguindo estas etapas, agora você sabe como **convert geometry to WKT**, selecionar a variante correta e controlar precisamente a saída numérica. Isso lhe dá a flexibilidade necessária para integrar Aspose.GIS a qualquer fluxo de trabalho GIS, banco de dados ou serviço web que consuma WKT.

## FAQ's
### O Aspose.GIS é compatível com todas as versões do .NET?
Sim, o Aspose.GIS suporta .NET Framework 4.0 e superiores.  

### Posso usar o Aspose.GIS em projetos comerciais?
Sim, o Aspose.GIS pode ser usado tanto em projetos pessoais quanto comerciais.  

### O Aspose.GIS oferece suporte a outros formatos de dados espaciais?
Sim, o Aspose.GIS suporta uma ampla variedade de formatos de dados espaciais, incluindo ESRI Shapefile, GeoJSON e KML.  

### Existe uma versão de avaliação gratuita disponível para o Aspose.GIS?
Sim, você pode baixar uma versão de avaliação gratuita do Aspose.GIS [aqui](https://releases.aspose.com/).  

### Onde posso obter ajuda ou suporte para o Aspose.GIS?
Você pode postar suas dúvidas ou buscar assistência na comunidade Aspose.GIS no [forum](https://forum.aspose.com/c/gis/33).

## Perguntas Frequentes
**Q: Como exportar uma coleção de Geometry para uma única string WKT?**  
A: Percorra cada geometria na coleção e concatene os resultados de `AsText`, opcionalmente separando‑os por vírgulas ou quebras de linha.

**Q: Posso mudar o SRID sem alterar as coordenadas?**  
A: Sim, defina a propriedade `SpatialReferenceSystem` para o SRID desejado; os valores das coordenadas permanecem inalterados.

**Q: O que acontece se eu usar uma variante WKT não suportada?**  
A: O Aspose.GIS lançará uma `ArgumentException`. Sempre valide a variante contra os valores do enum `WktVariant`.

---

**Última Atualização:** 2025-12-23  
**Testado Com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}