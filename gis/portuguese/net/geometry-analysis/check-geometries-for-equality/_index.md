---
date: 2026-06-05
description: Aprenda como comparar geometrias no .NET usando Aspose.GIS, detectar
  geometrias duplicadas e verificar a igualdade de geometrias em suas aplicações.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Como comparar geometrias para igualdade
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como comparar geometrias para igualdade usando Aspose.GIS para .NET
url: /pt/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como comparar geometrias para igualdade usando Aspose.GIS para .NET

## Introdução
Neste tutorial, você aprenderá **como comparar geometrias** com Aspose.GIS para .NET, uma tarefa vital quando você precisa detectar geometrias duplicadas, validar dados espaciais ou impor regras topológicas. Seja construindo um serviço de mapeamento, executando análises espaciais em lote ou simplesmente verificando se duas formas ocupam o mesmo local, este guia orienta você na criação, modificação e teste de igualdade de geometria com código C# limpo e pronto para produção.

## Respostas rápidas
- **O que significa “compare geometries”?** Verifica se dois objetos geométricos ocupam o mesmo espaço, independentemente de como foram construídos.  
- **Qual método é usado?** `SpatiallyEquals` da API Aspose.GIS.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo típico de implementação?** Cerca de 5‑10 minutos para uma verificação básica de igualdade.  

## O que é igualdade de geometria?
Igualdade de geometria, também chamada de igualdade espacial, significa que duas geometrias representam exatamente o mesmo conjunto de pontos na superfície da Terra. Mesmo que uma geometria seja construída como um `MultiLineString` e a outra como um único `LineString`, elas são consideradas iguais quando cada coordenada corresponde dentro da tolerância definida. Essa definição permite que desenvolvedores detectem de forma confiável geometrias duplicadas em fontes de dados heterogêneas.

## Por que usar Aspose.GIS para comparar geometrias?
Aspose.GIS oferece um motor de geometria offline de alto desempenho que elimina a necessidade de serviços externos. Ele **suporta mais de 30 formatos vetoriais e raster** (incluindo WKT, GeoJSON, Shapefile, KML, GML) e pode processar arquivos com **centenas de milhares de vértices** mantendo o uso de memória abaixo de 50 MB. O método `SpatiallyEquals` da biblioteca é sensível à precisão, fornecendo resultados determinísticos mesmo com coordenadas de ponto flutuante.

### Por que isso importa para desenvolvedores
Quando você precisa **detectar geometrias duplicadas** em processos em lote, pipelines de validação em tempo real ou migrações de dados GIS, uma biblioteca comprovada elimina suposições e garante resultados consistentes entre diferentes provedores de dados.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

- **.NET Framework ou .NET Core instalados** – qualquer versão suportada pelo Aspose.GIS.  
- **Biblioteca Aspose.GIS para .NET** – faça o download na [Aspose.GIS download page](https://releases.aspose.com/gis/net/).  
- **Um IDE de desenvolvimento** – Visual Studio, Rider ou VS Code com extensões C#.  

## Importar namespaces
No seu projeto .NET, adicione as declarações `using` necessárias para que o compilador saiba onde encontrar as classes GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 1: Definir as geometrias
`MultiLineString` representa uma coleção de componentes de linha, enquanto `LineString` define uma única linha contínua. Ambas as classes herdam do tipo base `Geometry`.

Primeiro, criamos duas geometrias que iremos comparar. Neste exemplo, `geometry1` é um `MultiLineString` composto por dois segmentos de linha, enquanto `geometry2` é um único `LineString` que abrange os mesmos pontos de início e fim.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Etapa 2: Verificar igualdade das geometrias
`SpatiallyEquals` avalia se duas geometrias ocupam o mesmo conjunto de pontos, opcionalmente aceitando um valor de tolerância para imprecisão de ponto flutuante.

Agora usamos o método `SpatiallyEquals` para ver se as duas formas são consideradas iguais pelo motor GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

O console imprime `True` porque, apesar da construção diferente, ambas as geometrias cobrem a mesma linha de (0,0) a (2,2).

## Etapa 3: Modificar uma geometria
Para ilustrar como uma mudança afeta a igualdade, adicionamos um ponto extra ao `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Etapa 4: Verificar novamente a igualdade após modificação
Após a modificação, as geometrias não são mais iguais, portanto `SpatiallyEquals` retorna `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

A saída `False` confirma que o ponto adicional quebrou a igualdade espacial.

## Como detectar geometrias duplicadas?
Carregue cada geometria, chame `SpatiallyEquals` com uma tolerância adequada e filtre as que retornam `True`. Esse padrão escala bem com LINQ, permitindo identificar formas duplicadas em grandes coleções com apenas algumas linhas de código. Você também pode combiná‑lo com `GroupBy` para agregar geometrias idênticas e reduzir custos de armazenamento.

## Problemas comuns e dicas
- **Problemas de precisão** – Se você trabalha com coordenadas de altíssima precisão, considere arredondar ou usar a sobrecarga de tolerância de `SpatiallyEquals`.  
- **SRIDs diferentes** – Certifique‑se de que ambas as geometrias compartilham o mesmo Identificador de Sistema de Referência Espacial (SRID) antes de comparar.  
- **Desempenho** – Para grandes coleções, comparações em lote usando LINQ ou loops paralelos podem reduzir a sobrecarga drasticamente.  

## Perguntas frequentes
**Q: Posso usar Aspose.GIS para .NET com outros frameworks .NET?**  
A: Sim, Aspose.GIS funciona com projetos .NET Framework, .NET Core e .NET Standard.

**Q: Existe uma versão de avaliação gratuita?**  
A: Absolutamente. Baixe uma avaliação na [Aspose.GIS releases page](https://releases.aspose.com/).

**Q: Onde posso encontrar a documentação completa da API?**  
A: Documentação detalhada está na [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).

**Q: Como obtenho ajuda se encontrar um problema?**  
A: Publique sua pergunta no fórum da comunidade Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33).

**Q: Posso comprar uma licença temporária para avaliação?**  
A: Sim, licenças temporárias estão disponíveis na [purchase page](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você sabe **como comparar geometrias** usando Aspose.GIS para .NET, desde a criação dos objetos até a verificação da igualdade espacial e o tratamento de modificações. Essa capacidade é um bloco de construção para análises espaciais mais avançadas, como validação de topologia, detecção de duplicatas e filtragem baseada em geometria.

---

**Última atualização:** 2026-06-05  
**Testado com:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais relacionados

- [Criar geometria de polígono C# e verificar interseção com Aspose.GIS para .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Como realizar análise de sobreposição espacial de geometrias com Aspose.GIS para .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Verificação de roteamento de rede: geometrias tocando com Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}