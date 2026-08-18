---
date: 2026-08-18
description: Converta graus decimais em DMS usando Aspose.GIS for .NET. Este guia
  passo a passo em C# mostra como converter latitude/longitude, graus decimais em
  DMS e muito mais.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Converter Coordenadas
og_description: Conversão de graus decimais para DMS facilitada com Aspose.GIS for
  .NET. Aprenda a transformar valores de latitude‑longitude em formato DMS em minutos.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Converter graus decimais em DMS com Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Como converter graus decimais em DMS com Aspose.GIS for .NET
url: /pt/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como converter graus decimais para dms com Aspose.GIS

## Introdução
Neste tutorial você aprenderá **como converter graus decimais para dms** usando a poderosa biblioteca Aspose.GIS para .NET. Seja para **c# convert lat long**, gerar strings de localização legíveis para relatórios, ou simplesmente explorar diferentes formatos de coordenadas, este guia o conduzirá passo a passo com explicações claras e trechos de C# prontos para execução.

## Respostas rápidas
- **O que significa “convert coordinates to dms”?** Ele transforma valores numéricos de latitude/longitude na notação tradicional graus‑minutes‑seconds.  
- **Qual biblioteca realiza a conversão?** Aspose.GIS para .NET fornece a classe `GeoConvert` com suporte integrado a formatos.  
- **Preciso de licença para experimentar?** Um teste gratuito está disponível; uma licença comercial é necessária para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.  
- **Posso usar o mesmo código para outros formatos?** Sim—basta alterar o valor do enum `PointFormats` (ex.: `DecimalDegrees`, `GeoRef`).  

## O que é conversão de coordenadas para DMS?
Converter coordenadas para DMS reescreve valores decimais de latitude e longitude em um formato como `25°30'00"N 45°30'00"E`. O processo divide cada grau decimal em graus inteiros, minutos (um sextagésimo de grau) e segundos (um sextagésimo de minuto), adicionando o indicador de hemisfério apropriado (N, S, E, W). Essa forma legível é essencial para muitos conjuntos de dados legados e para comunicar localizações precisas sem depender da notação decimal.

## Por que usar Aspose.GIS para conversão de coordenadas?
Aspose.GIS suporta **mais de 50 formatos de entrada e saída** e pode processar arquivos GIS de centenas de páginas sem carregar todo o conjunto de dados na memória. A API oferece precisão sub‑milimétrica para casos extremos, como valores negativos e designadores hemisféricos, e funciona de forma consistente nos runtimes .NET para Windows, Linux e macOS.

## Pré-requisitos
Antes de começar, certifique-se de que você tem:

1. **Conhecimento básico de C#** – familiaridade com variáveis, chamadas de método e saída de console.  
2. **Aspose.GIS instalado** – faça o download do pacote mais recente no [Aspose.GIS website](https://releases.aspose.com/gis/net/). Você também pode explorar o site principal de lançamentos da Aspose em [Aspose releases website](https://releases.aspose.com/).  

## Importar namespaces
First, import the namespaces required for GIS operations:

Import Namespaces placeholder remains unchanged.

## Guia passo a passo

### O que é a classe GeoConvert?
A classe `GeoConvert` fornece métodos estáticos para converter entre formatos de coordenadas como graus decimais, DMS e GeoRef. Inclui sobrecargas que aceitam valores numéricos brutos ou objetos `Point` e retornam strings formatadas ou novas instâncias `Point`. Ao lidar com casos extremos como coordenadas negativas e arredondamento, a classe garante que a saída esteja em conformidade com as especificações GIS padrão, simplificando a integração em qualquer aplicação de mapeamento .NET.

### Etapa 1: iniciar o processo de conversão
Imprimimos uma mensagem amigável para que você saiba que a demonstração começou.

```csharp
using System;
using Aspose.Gis;
```

### Etapa 2: converter para graus decimais
Embora o objetivo final seja DMS, começamos mostrando a representação decimal original. Isso também demonstra o caminho **decimal degrees to dms** que você seguirá mais adiante.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Etapa 3: converter para minutos decimais de grau
Este formato (`DD°MM.m'`) é um passo intermediário comum quando você precisa **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Etapa 4: converter para graus minutos segundos (dms)
Aqui está o núcleo do nosso tutorial—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Etapa 5: converter para GeoRef
Para completude, também demonstramos o formato `GeoRef`, útil em fluxos de trabalho de sensoriamento remoto.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Problemas comuns e soluções
- **Letras de hemisfério incorretas** – Certifique‑se de passar valores positivos para norte/leste e negativos para sul/oeste; a API adiciona automaticamente o sufixo correto.  
- **Saída em branco inesperada** – Verifique se o assembly `Aspose.Gis` está referenciado corretamente e se o projeto tem como alvo uma versão .NET suportada.  
- **Licença não encontrada** – Coloque seu arquivo de licença na raiz da aplicação ou defina‑a programaticamente com `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Perguntas frequentes

**Q: Aspose.GIS é compatível com outras linguagens de programação?**  
A: Aspose.GIS tem como alvo principal desenvolvedores .NET, mas também há uma versão Java disponível.

**Q: Posso experimentar o Aspose.GIS antes de comprar?**  
A: Sim, você pode acessar um teste gratuito do Aspose.GIS no [website](https://releases.aspose.com/).

**Q: Como posso obter suporte para Aspose.GIS?**  
A: Você pode buscar assistência no fórum da comunidade Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33).

**Q: Licenças temporárias estão disponíveis para Aspose.GIS?**  
A: Sim, licenças temporárias podem ser obtidas na [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso comprar o Aspose.GIS?**  
A: Você pode comprar o Aspose.GIS na [purchase page](https://purchase.aspose.com/buy).

## Conclusão
Seguindo estas etapas, você agora sabe como **converter graus decimais para dms** e outros formatos GIS comuns usando Aspose.GIS para .NET. Essa capacidade permite integrar strings de localização legíveis em aplicações de mapeamento, relatórios ou qualquer fluxo de trabalho de dados espaciais. Sinta‑se à vontade para experimentar diferentes valores de latitude/longitude e explorar os outros formatos oferecidos pela classe `GeoConvert`.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Tutoriais Relacionados

- [How to Create Point Geometry and Get Geometry Type with Aspose.GIS for .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create MultiPoint Geometry .NET with Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}