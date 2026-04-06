---
date: 2026-04-06
description: Aprenda como converter curvas em linhas e linearizar a geometria com
  Aspose.GIS para .NET, permitindo processamento e análise geoespaciais rápidos em
  suas aplicações .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Linearizar uma Geometria
second_title: Aspose.GIS .NET API
title: Converter curvas em linhas usando Aspose.GIS para .NET
url: /pt/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter Curvas em Linhas usando Aspose.GIS para .NET

## Introdução
Se você precisa **converter curvas em linhas** para mapeamento, análise espacial ou tarefas de troca de dados, o Aspose.GIS para .NET oferece uma maneira limpa e programática de fazer isso. Neste tutorial, percorreremos um exemplo completo e real que mostra como pegar uma geometria complexa — contendo curvas e formas compostas — e transformá‑la em uma representação linear simples que funciona com qualquer sistema GIS.

## Respostas Rápidas
- **O que significa linearizar uma geometria?** Converter curvas e formas complexas em segmentos de linha reta.  
- **Por que usar o Aspose.GIS?** Ele suporta dezenas de formatos GIS e lida com a conversão de geometria sem ferramentas externas.  
- **Pré‑requisitos?** .NET Framework ou .NET Core, Visual Studio e a biblioteca Aspose.GIS.  
- **Quanto tempo leva o exemplo?** Menos de cinco minutos para executar após a instalação da biblioteca.  
- **Posso salvar em outros formatos?** Sim — substitua o driver KML por Shapefile, GeoJSON, etc.

## O que é Linearização de Geometria?
Linearizar geometria significa dividir qualquer forma curva ou composta em uma série de segmentos de linha reta (uma “geometria linear”). Isso simplifica a renderização, a análise e a interoperabilidade com ferramentas que entendem apenas linhas e pontos.

## Por que Converter Curvas em Linhas?
- **Desempenho:** Geometrias lineares são mais rápidas de renderizar e consultar.  
- **Compatibilidade:** Muitas plataformas GIS (por exemplo, serviços de mapa antigos) aceitam apenas recursos lineares.  
- **Simplificação:** Útil para criar miniaturas, visualizações rápidas ou alimentar dados em algoritmos que exigem entrada linear.

## Pré‑requisitos
Antes de mergulhar no código, certifique‑se de que você tem:

1. **Aspose.GIS for .NET** – faça o download a partir do [site da Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ou .NET Core) instalado na sua máquina de desenvolvimento.  
3. **Visual Studio** (ou qualquer IDE compatível com C#) para escrever e executar o exemplo.

## Importar Namespaces
Para começar a usar a funcionalidade do Aspose.GIS, importe os namespaces necessários.

### Etapa 1: Importar os Namespaces Principais do Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Etapa 2: Importar o Driver para o Formato de Destino
Neste exemplo, escreveremos o resultado em um arquivo KML:
```csharp
using Aspose.GIS.Kml;
```

## Como Converter Curvas em Linhas – Guia Passo a Passo
Abaixo está um detalhado passo a passo de cada linha de código, explicando **como converter curvas em linhas** e por que cada etapa é importante.

### Etapa 1: Definir o Caminho de Saída
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Substitua `"Your Document Directory"` pela pasta onde você deseja salvar o arquivo KML.

### Etapa 2: Criar uma Camada para o Arquivo de Saída
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Uma *camada* é um contêiner para recursos geográficos. Aqui criamos uma nova camada KML que armazenará nossa geometria linearizada.

### Etapa 3: Construir um Novo Recurso
```csharp
var feature = layer.ConstructFeature();
```
Um *recurso* representa um único objeto geográfico (ponto, linha, polígono, etc.). Anexaremos nossa geometria linear a esse recurso.

### Etapa 4: Definir a Geometria Complexa Original
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Criamos uma geometria a partir de uma string Well‑Known Text (WKT). Este exemplo inclui um `LineString`, um `CompoundCurve` e um `CircularString` — perfeito para demonstrar a conversão de curvas em linhas.

### Etapa 5: Linearizar a Geometria
```csharp
var linear = geometry.ToLinearGeometry();
```
O método `ToLinearGeometry()` converte todas as curvas em segmentos de linha reta, produzindo uma versão *linear* da geometria original.

### Etapa 6: Atribuir a Geometria Linear ao Recurso
```csharp
feature.Geometry = linear;
```
Agora o recurso contém a geometria linear simplificada.

### Etapa 7: Adicionar o Recurso à Camada
```csharp
layer.Add(feature);
```
Finalmente, adicionamos o recurso à camada KML, que grava a geometria linear no arquivo de saída quando o bloco `using` termina.

## Armadilhas Comuns & Dicas
- **Separadores de caminho:** Use `Path.Combine` para construção de caminhos multiplataforma.  
- **Geometrias grandes:** Linearizar formas muito complexas pode gerar muitos vértices; considere usar `Simplify()` após a linearização se precisar de menos pontos.  
- **Seleção de driver:** Se precisar de um formato de saída diferente, troque `Drivers.Kml` por `Drivers.Shapefile`, `Drivers.GeoJson`, etc., e ajuste a extensão do arquivo conforme necessário.

## Perguntas Frequentes (Aprimoradas)

**Q: O Aspose.GIS para .NET é compatível com .NET Core?**  
A: Sim, o Aspose.GIS para .NET funciona com .NET Core, permitindo que você crie aplicações multiplataforma.

**Q: Posso trabalhar com diferentes formatos de arquivo GIS usando Aspose.GIS para .NET?**  
A: Absolutamente! O Aspose.GIS suporta KML, Shapefile, GeoJSON e muitos outros formatos.

**Q: O Aspose.GIS oferece suporte para operações e análises espaciais?**  
A: Sim, ele fornece uma ampla gama de operações e capacidades de análise espacial para lidar com tarefas geoespaciais complexas.

**Q: Existe uma versão de avaliação gratuita disponível para Aspose.GIS para .NET?**  
A: Sim, você pode baixar uma avaliação gratuita no [site da Aspose](https://releases.aspose.com/).

**Q: Onde posso encontrar ajuda e suporte para Aspose.GIS?**  
A: Visite o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para obter assistência da comunidade e da equipe de suporte da Aspose.

**Perguntas Adicionais**

**Q: Posso linearizar geometrias que contêm coordenadas 3D (Z)?**  
A: Sim, `ToLinearGeometry()` funciona com geometrias 2D e 3D; os valores Z são preservados nos segmentos de linha resultantes.

**Q: Como a linearização afeta o tamanho do arquivo de saída?**  
A: Converter curvas em muitos segmentos de linha curtos pode aumentar o tamanho do arquivo. Use `Simplify()` após a linearização se o tamanho do arquivo for uma preocupação.

**Q: É possível controlar o comprimento do segmento ao linearizar?**  
A: O método padrão usa uma tolerância interna. Para segmentação personalizada, você pode tesselar manualmente as curvas antes de chamar `ToLinearGeometry()`.

## Conclusão
Neste tutorial, abordamos **como converter curvas em linhas** usando Aspose.GIS para .NET, desde a configuração do ambiente até a gravação do resultado linearizado em um arquivo KML. Agora você pode integrar esse fluxo de trabalho em aplicações de mapeamento, pipelines de processamento de dados ou qualquer projeto relacionado a GIS que exija geometrias simplificadas.

---

**Última atualização:** 2026-04-06  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}