---
date: 2025-12-12
description: Aprenda a criar camada vetorial e adicionar geometria de string circular
  usando Aspose.GIS para .NET – uma forma rápida de desenvolver aplicações GIS.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Criar Camada Vetorial e String Circular no Aspose.GIS para .NET
url: /pt/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial e Geometria de String Circular com Aspose.GIS para .NET

## Introdução
Se você está desenvolvendo uma aplicação GIS na plataforma .NET, o primeiro passo costuma ser **criar objetos de camada vetorial** que armazenam seus recursos espaciais. Aspose.GIS para .NET torna esse processo simples e permite enriquecer essas camadas com geometrias avançadas, como strings circulares. Neste tutorial você aprenderá exatamente como criar uma camada vetorial, adicionar uma geometria de string circular e salvar o resultado como um Shapefile — tudo com código C# limpo e pronto para produção.

## Respostas Rápidas
- **O que significa “criar camada vetorial”?** Cria um novo contêiner (camada) que pode armazenar recursos espaciais como pontos, linhas ou polígonos.  
- **Qual classe representa uma string circular?** `CircularString` de `Aspose.Gis.Geometries`.  
- **Posso salvar a camada como Shapefile?** Sim – use `Drivers.Shapefile` ao criar a camada.  
- **Preciso de licença para desenvolvimento?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “criar camada vetorial”?
Uma camada vetorial é um agrupamento lógico de recursos vetoriais (pontos, linhas, polígonos) armazenados em uma única fonte de dados. No Aspose.GIS você instancia uma camada chamando `VectorLayer.Create`, passando o caminho do arquivo de destino e o driver desejado (por exemplo, Shapefile). Uma vez que a camada exista, você pode adicionar recursos, atribuir geometrias e executar operações espaciais.

## Por que adicionar uma string circular?
Strings circulares são um tipo de **geometria linear** que aproxima arcos usando uma sequência de pontos. Elas são úteis para representar estradas curvas, curvas de rios ou qualquer recurso onde seja necessário um traço suave sem recorrer a muitos pequenos segmentos de linha.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- **.NET Framework ou .NET Core** instalados na sua máquina.  
- Biblioteca **Aspose.GIS para .NET** – faça o download no site oficial **[aqui](https://releases.aspose.com/gis/net/)**.  
- Uma IDE como **Visual Studio** ou **JetBrains Rider**.  
- Familiaridade básica com programação em **C#**.

## Importar Namespaces
Adicione os namespaces necessários ao seu arquivo C#:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guia Passo a Passo

### Etapa 1: Definir o caminho do arquivo de saída
Defina a localização onde o Shapefile será gravado.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Substitua `"Your Document Directory"` pelo caminho real da pasta no seu sistema.

### Etapa 2: **Criar camada vetorial**
Abra um `VectorLayer` usando o método `Create`. Esta é a essência da operação **criar camada vetorial**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Etapa 3: Construir um novo recurso
Um recurso representa um único registro espacial dentro da camada.

```csharp
    var feature = layer.ConstructFeature();
```

### Etapa 4: Construir a geometria de string circular
Adicione os pontos que definem a forma curva. A sequência de pontos cria um arco que começa e termina no mesmo local, formando uma string circular fechada.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Etapa 5: Atribuir a geometria e adicionar o recurso à camada
Vincule a geometria ao recurso e armazene‑o na camada.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Quando o bloco `using` termina, a camada é automaticamente gravada no Shapefile em disco.

## Problemas Comuns & Soluções
| Problema | Solução |
|----------|----------|
| **Caminho do arquivo inválido** | Verifique se o diretório existe e se você tem permissão de escrita. |
| **CircularString aparece como linha reta** | Certifique‑se de que os pontos foram adicionados na ordem correta; o primeiro e o último ponto devem ser idênticos para uma forma fechada. |
| **Exceção de licença** | Aplique uma licença temporária durante o desenvolvimento ou adquira uma licença completa para uso em produção. |

## Perguntas Frequentes

### O Aspose.GIS para .NET é compatível com todas as versões do .NET Framework?
Sim, o Aspose.GIS para .NET foi projetado para funcionar com uma ampla gama de versões do .NET, desde o Framework 4.5 até as versões mais recentes do .NET 8.

### Posso integrar o Aspose.GIS para .NET com outras bibliotecas GIS?
Com certeza! Você pode ler dados com outras bibliotecas, manipulá‑los com Aspose.GIS e depois gravá‑los novamente, graças à sua API flexível.

### O Aspose.GIS para .NET oferece visualização de dados espaciais?
Sim, a biblioteca inclui utilitários de renderização que permitem gerar mapas e representações visuais das suas geometrias.

### Existe um fórum da comunidade onde eu possa buscar ajuda sobre Aspose.GIS para .NET?
Sim, você pode visitar o fórum Aspose.GIS **[aqui](https://forum.aspose.com/c/gis/33)** para fazer perguntas e compartilhar experiências.

### Posso obter uma licença temporária para avaliar o Aspose.GIS para .NET?
Certamente! Uma licença de avaliação temporária está disponível **[aqui](https://purchase.aspose.com/temporary-license/)**.

### Como adiciono geometrias mais complexas (por exemplo, MultiLineString) à mesma camada?
Crie o objeto de geometria apropriado (por exemplo, `MultiLineString`), preencha‑o com objetos `LineString` individuais, atribua‑o a `feature.Geometry` e adicione o recurso da mesma forma que fizemos com a string circular.

## Conclusão
Seguindo estas etapas, você agora sabe como **criar objetos de camada vetorial** e enriquecê‑los com uma geometria de string circular usando Aspose.GIS para .NET. Essa base permite que você construa soluções GIS mais robustas — seja mapeando redes de transporte, visualizando dados ambientais ou desenvolvendo ferramentas personalizadas de análise espacial.

---

**Última atualização:** 2025-12-12  
**Testado com:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}