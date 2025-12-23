---
date: 2025-12-23
description: Aprenda a criar linhas a partir de polígonos e converter polígonos em
  linhas usando Aspose.GIS para .NET. Domine a manipulação de dados GIS rapidamente.
linktitle: Replace Polygons with Lines
second_title: Aspose.GIS .NET API
title: Como criar linha a partir de polígono com Aspose.GIS para .NET
url: /pt/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar linha a partir de polígono com Aspose.GIS para .NET

## Introdução
Se você precisar **criar linha a partir de polígono** em uma aplicação GIS, o Aspose.GIS para .NET oferece um método simples, de uma única linha, para fazer a conversão. Converter geometrias de polígono em geometrias de linha é uma etapa comum quando se deseja visualizar limites, realizar análises lineares ou reduzir a complexidade dos dados. Neste tutorial você verá exatamente como substituir polígonos por linhas, por que isso é importante e como integrar a solução em seus projetos .NET.

## Respostas rápidas
- **O que significa “criar linha a partir de polígono”?** Transforma formas de polígono fechadas em suas linhas de contorno constituintes.  
- **Qual método realiza a conversão?** `ReplacePolygonsByLines()` da API de Geometria do Aspose.GIS.  
- **Preciso de licença para executar o código?** Um trial gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso usar isso com outros formatos GIS?** Sim – a mesma abordagem funciona com Shapefile, GeoJSON, KML, etc.

## O que é “criar linha a partir de polígono”?
Criar uma linha a partir de um polígono extrai as bordas do polígono como uma coleção de `LineString`. Essa operação costuma ser chamada de conversão *polígono para linha* e é útil para tarefas como análise de redes, renderização de mapas e simplificação de dados.

## Por que usar o Aspose.GIS para essa transformação?
- **Método embutido** – Não é necessário escrever código personalizado de análise de geometria.  
- **Alto desempenho** – Otimizado para grandes volumes de dados.  
- **Suporte a múltiplos formatos** – Funciona com diversos tipos de arquivos GIS.  
- **Documentação abrangente** – Fácil de começar.

## Pré‑requisitos
Antes de mergulhar no código, certifique‑se de que você tem o seguinte pronto:

### Instalando o Aspose.GIS para .NET
1. Baixe o Aspose.GIS para .NET: Visite [este link](https://releases.aspose.com/gis/net/) para baixar a versão mais recente.  
2. Instale o Aspose.GIS para .NET: Siga as instruções de instalação no pacote ou consulte a [documentação](https://reference.aspose.com/gis/net/) para obter detalhes.

## Importar namespaces
No seu projeto .NET, importe os namespaces necessários para trabalhar com as classes de geometria do Aspose.GIS.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Guia passo a passo para substituir polígonos por linhas

### Etapa 1: Definir a geometria de origem
Crie uma coleção de geometria que contenha os polígonos que você deseja converter.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Etapa 2: Converter polígono em linhas
Use o método `ReplacePolygonsByLines()` para **converter polígono em linhas**. Este é o núcleo da operação *criar linha a partir de polígono*.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Etapa 3: Exibir os resultados
Imprima tanto as geometrias originais quanto as transformadas para verificar a conversão.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Armadilhas comuns e solução de problemas
- **Coleção de geometria vazia** – Garanta que sua geometria de origem realmente contenha polígonos; caso contrário, `ReplacePolygonsByLines()` retornará a geometria original sem alterações.  
- **Tipos de geometria misturados** – O método afeta apenas polígonos; outros tipos de geometria (por exemplo, pontos) são passados adiante sem alterações.  
- **Compatibilidade de versão** – Use o pacote NuGet mais recente do Aspose.GIS para evitar problemas com APIs obsoletas.

## Perguntas frequentes

**Q: O Aspose.GIS para .NET funciona com vários formatos de arquivo GIS?**  
A: Sim, o Aspose.GIS para .NET oferece suporte à leitura e gravação de formatos como Shapefile, GeoJSON, KML e outros.

**Q: Existe um trial gratuito disponível para o Aspose.GIS para .NET?**  
A: Sim, você pode acessar o trial gratuito do Aspose.GIS para .NET [aqui](https://releases.aspose.com/).

**Q: O Aspose.GIS para .NET oferece suporte para desenvolvedores?**  
A: Sim, os desenvolvedores podem obter suporte e assistência no fórum da comunidade Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33).

**Q: Posso adquirir uma licença temporária para o Aspose.GIS para .NET?**  
A: Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: O Aspose.GIS para .NET é adequado tanto para iniciantes quanto para desenvolvedores experientes?**  
A: Absolutamente, o Aspose.GIS para .NET atende desenvolvedores de todos os níveis, oferecendo documentação completa e suporte.

---

**Última atualização:** 2025-12-23  
**Testado com:** Aspose.GIS para .NET 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}