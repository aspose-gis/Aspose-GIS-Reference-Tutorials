---
date: 2026-02-13
description: Aprenda a converter coordenadas para DMS com Aspose.GIS para .NET. Este
  guia passo a passo em C# mostra como converter latitude e longitude, graus decimais
  para DMS e muito mais.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Como Converter Coordenadas para DMS com Aspose.GIS para .NET
url: /pt/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Converter Coordenadas para DMS com Aspose.GIS

## Introdução
Neste tutorial, você aprenderá **como converter coordenadas** para DMS (graus, minutos, segundos) usando a poderosa biblioteca Aspose.GIS para .NET. Seja para **c# convert lat long**, gerar strings de localização legíveis por humanos, ou simplesmente explorar diferentes formatos de coordenadas, este guia conduz você por cada passo com explicações claras e código C# pronto‑para‑executar.

## Respostas Rápidas
- **O que significa “converter coordenadas para DMS”?** Transforma valores numéricos de latitude/longitude em notação tradicional de graus‑minutos‑segundos.  
- **Qual biblioteca realiza a conversão?** Aspose.GIS para .NET fornece a classe `GeoConvert` com suporte interno a formatos.  
- **Preciso de licença para testar?** Um teste gratuito está disponível; uma licença comercial é necessária para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+.  
- **Posso usar o mesmo código para outros formatos?** Sim—basta alterar o valor do enum `PointFormats` (por exemplo, `DecimalDegrees`, `GeoRef`).  

## Como Converter Coordenadas para DMS
Antes de mergulhar no código, vamos esclarecer por que o DMS ainda é valioso. Cartógrafos, pilotos e muitos provedores de dados GIS confiam no DMS porque é amigável ao ser humano e está alinhado com mapas tradicionais. Aspose.GIS elimina a necessidade de cálculos manuais, permitindo que você se concentre na lógica da sua aplicação.

## O que é a conversão de coordenadas para DMS?
Converter coordenadas para DMS reescreve valores decimais de latitude e longitude em um formato como `25°30'00"N 45°30'00"E`. Essa representação é amplamente usada em cartografia, navegação e intercâmbio de dados GIS.

## Por que usar Aspose.GIS para conversão de coordenadas?
- **API tudo‑em‑um** – Sem bibliotecas externas ou matemática complexa; Aspose.GIS lida com análise e formatação internamente.  
- **Alta precisão** – Tratamento preciso de casos extremos, como valores negativos e designadores hemisféricos.  
- **Multiplataforma** – Funciona da mesma forma em runtimes .NET para Windows, Linux e macOS.  
- **Extensível** – Troque facilmente entre DMS, graus decimais, graus‑minutos‑decimais e formatos GeoRef.  

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Conhecimento básico de C#** – Familiaridade com variáveis, chamadas de método e saída no console.  
2. **Aspose.GIS instalado** – Baixe o pacote mais recente no [site da Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Importar Namespaces
Primeiro, importe os namespaces necessários para operações GIS:

```csharp
using System;
using Aspose.Gis;
```

## Guia passo a passo

### Etapa 1: Iniciar o processo de conversão
Exibimos uma mensagem amigável para que você saiba que a demonstração começou.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Etapa 2: Converter para Graus Decimais  
Embora o objetivo final seja DMS, começamos mostrando a representação decimal original. Isso também demonstra o caminho **decimal degrees to dms** que você seguirá depois.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Etapa 3: Converter para Graus Minutos Decimais  
Esse formato (`DD°MM.m'`) é um passo intermediário comum quando você precisa *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Etapa 4: Converter para Graus Minutos Segundos (DMS)  
Aqui está o núcleo do nosso tutorial—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Etapa 5: Converter para GeoRef  
Para completude, também demonstramos o formato `GeoRef`, útil em fluxos de trabalho de sensoriamento remoto.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Problemas Comuns e Soluções
- **Letras de hemisfério incorretas** – Garanta que você passe valores positivos para norte/leste e negativos para sul/oeste; a API adiciona automaticamente o sufixo correto.  
- **Saída em branco inesperada** – Verifique se o assembly `Aspose.Gis` está referenciado corretamente e se o projeto tem como alvo uma versão suportada do .NET.  
- **Licença não encontrada** – Coloque seu arquivo de licença na raiz da aplicação ou configure‑a programaticamente com `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Perguntas Frequentes

**Q: O Aspose.GIS é compatível com outras linguagens de programação?**  
A: O Aspose.GIS tem foco principal em desenvolvedores .NET, mas também há uma versão Java disponível.

**Q: Posso experimentar o Aspose.GIS antes de comprar?**  
A: Sim, você pode acessar um teste gratuito do Aspose.GIS a partir do [site](https://releases.aspose.com/).

**Q: Como posso obter suporte para o Aspose.GIS?**  
A: Você pode buscar ajuda no fórum da comunidade Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33).

**Q: Licenças temporárias estão disponíveis para o Aspose.GIS?**  
A: Sim, licenças temporárias podem ser obtidas na [página de licença temporária](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso comprar o Aspose.GIS?**  
A: Você pode adquirir o Aspose.GIS na [página de compra](https://purchase.aspose.com/buy).

## Conclusão
Seguindo estas etapas, você agora sabe como **convert coordinates to DMS** e outros formatos GIS comuns usando Aspose.GIS para .NET. Essa capacidade permite integrar perfeitamente strings de localização legíveis por humanos em aplicativos de mapeamento, relatórios ou qualquer fluxo de trabalho de dados espaciais. Sinta‑se à vontade para experimentar diferentes valores de latitude/longitude e explorar os outros formatos oferecidos pela classe `GeoConvert`.

---

**Última atualização:** 2026-02-13  
**Testado com:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}