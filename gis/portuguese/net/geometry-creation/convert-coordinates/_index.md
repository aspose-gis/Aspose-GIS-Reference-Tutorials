---
date: 2025-12-11
description: Aprenda a converter coordenadas para DMS usando Aspose.GIS para .NET.
  Inclui exemplos em C#, conversão de latitude e longitude em C# e um guia passo a
  passo.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Converter coordenadas para DMS com Aspose.GIS para .NET
url: /pt/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter Coordenadas para DMS com Aspose.GIS

## Introduction
Nesta tutorial, você descobrirá como **converter coordenadas para DMS** (graus, minutos, segundos) usando a poderosa biblioteca Aspose.GIS para .NET. Seja para c# convert latitude longitude para aplicações de mapeamento, gerar strings de localização legíveis por humanos, ou simplesmente explorar diferentes formatos de coordenadas, este guia o conduz passo a passo com explicações claras e código C# pronto‑para‑executar.

## Quick Answers
- **O que significa “converter coordenadas para DMS”?** Ele transforma valores numéricos de latitude/longitude na notação tradicional graus‑minutos‑segundos.  
- **Qual biblioteca realiza a conversão?** Aspose.GIS para .NET fornece a classe `GeoConvert` com suporte integrado a formatos.  
- **Preciso de licença para experimentar?** Um teste gratuito está disponível; uma licença comercial é necessária para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.  
- **Posso usar o mesmo código para outros formatos?** Sim—basta alterar o valor do enum `PointFormats` (ex.: `DecimalDegrees`, `GeoRef`).  

## What is coordinate conversion to DMS?
Conversão de coordenadas para DMS reescreve valores decimais de latitude e longitude em um formato como `25°30'00"N 45°30'00"E`. Essa representação é amplamente usada em cartografia, navegação e troca de dados GIS.

## Why use Aspose.GIS for coordinate conversion?
- **API tudo‑em‑um** – Sem bibliotecas externas ou matemática complexa; Aspose.GIS lida com análise e formatação internamente.  
- **Alta precisão** – Tratamento preciso de casos extremos como valores negativos e designadores hemisféricos.  
- **Multiplataforma** – Funciona da mesma forma em runtimes .NET para Windows, Linux e macOS.  
- **Extensível** – Troque facilmente entre DMS, graus decimais, graus‑minutos‑decimais e formatos GeoRef.  

## Prerequisites
Before you start, make sure you have:

1. **Conhecimento básico de C#** – Familiaridade com variáveis, chamadas de método e saída de console.  
2. **Aspose.GIS instalado** – Baixe o pacote mais recente no [site da Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Import Namespaces
First, import the namespaces required for GIS operations:

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
We print a friendly message so you know the demo has begun.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
Even though the final goal is DMS, we start by showing the original decimal representation.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
This format (`DD°MM.m'`) is a common intermediate step when you need *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
Here’s the core of our tutorial—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing workflows.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **Letras de hemisfério incorretas** – Garanta que você passe valores positivos para norte/leste e negativos para sul/oeste; a API adiciona automaticamente o sufixo correto.  
- **Saída em branco inesperada** – Verifique se o assembly `Aspose.Gis` está referenciado corretamente e se o projeto tem como alvo uma versão .NET suportada.  
- **Licença não encontrada** – Coloque seu arquivo de licença na raiz da aplicação ou configure‑o programaticamente com `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Frequently Asked Questions

**P: O Aspose.GIS é compatível com outras linguagens de programação?**  
R: O Aspose.GIS tem como alvo principal desenvolvedores .NET, mas também há uma versão para Java disponível.

**P: Posso experimentar o Aspose.GIS antes de comprar?**  
R: Sim, você pode acessar um teste gratuito do Aspose.GIS no [site](https://releases.aspose.com/).

**P: Como posso obter suporte para o Aspose.GIS?**  
R: Você pode buscar ajuda no fórum da comunidade Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33).

**P: Licenças temporárias estão disponíveis para o Aspose.GIS?**  
R: Sim, licenças temporárias podem ser obtidas na [página de licença temporária](https://purchase.aspose.com/temporary-license/).

**P: Onde posso comprar o Aspose.GIS?**  
R: Você pode comprar o Aspose.GIS na [página de compra](https://purchase.aspose.com/buy).

## Conclusion
Seguindo estas etapas, você agora sabe como **converter coordenadas para DMS** e outros formatos GIS comuns usando Aspose.GIS para .NET. Essa capacidade permite integrar perfeitamente strings de localização legíveis por humanos em aplicações de mapeamento, relatórios ou qualquer fluxo de trabalho de dados espaciais. Sinta‑se à vontade para experimentar diferentes valores de latitude/longitude e explorar os outros formatos oferecidos pela classe `GeoConvert`.

---

**Última atualização:** 2025-12-11  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}