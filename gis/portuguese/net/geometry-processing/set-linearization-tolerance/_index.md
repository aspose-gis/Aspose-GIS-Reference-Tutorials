---
date: 2025-12-21
description: Aprenda como criar camada vetorial, definir a tolerância de linearização
  e adicionar recurso à camada usando Aspose.GIS para .NET. Siga este guia passo a
  passo para exportar arquivos GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Criar camada vetorial e definir tolerância de linearização usando Aspose.GIS
  para .NET
url: /pt/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Camada Vetorial e Definir Tolerância de Linearização usando Aspose.GIS para .NET

## Introdução
Se você precisa **criar camada vetorial**, controlar a precisão de curvas e exportar o resultado como um documento GeoJSON, o Aspose.GIS para .NET torna tudo simples. Neste tutorial você aprenderá como configurar as opções do GeoJSON, definir a tolerância de linearização e **adicionar recurso à camada** — tudo mantendo o código limpo e pronto para produção.

## Respostas Rápidas
- **O que significa “criar camada vetorial”?** Cria um novo conjunto de dados GIS vetorial (por exemplo, um arquivo GeoJSON) que pode armazenar geometrias e atributos.  
- **Como definir a tolerância?** Use a propriedade `LinearizationTolerance` de `GeoJsonOptions`.  
- **Posso exportar um arquivo GeoJSON?** Sim — basta criar um `VectorLayer` com o driver `Drivers.GeoJson`.  
- **Preciso de licença?** Uma licença válida do Aspose.GIS desbloqueia todos os recursos; uma licença temporária funciona para avaliação.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “criar camada vetorial”?
Criar uma camada vetorial significa inicializar um novo contêiner GIS (como um arquivo GeoJSON) que pode conter recursos geométricos como pontos, linhas e polígonos. Essa camada se torna o destino para qualquer geometria que você construir e quaisquer atributos que você anexar.

## Por que configurar as opções do GeoJSON?
Configurar as opções do GeoJSON — especialmente a **tolerância de linearização** — garante que geometrias curvas (por exemplo, `CircularString`) sejam aproximadas com a precisão que atende aos requisitos de acurácia da sua aplicação. Essa etapa é crucial quando você posteriormente **exporta o arquivo GeoJSON** para uso em mapas web ou análises espaciais.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Visual Studio** instalado (qualquer versão recente).  
2. **Licença Aspose.GIS** (ou uma chave de avaliação temporária).  
3. Biblioteca **Aspose.GIS para .NET** baixada e referenciada no seu projeto.  
4. Familiaridade básica com **C#**.

## Importar Namespaces
Primeiro, importe os namespaces necessários para que o compilador saiba onde encontrar as classes GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guia Passo a Passo

### Passo 1: Configurar Opções do GeoJSON (como definir a tolerância)
Vamos criar um objeto `GeoJsonOptions` e informar ao Aspose.GIS quão próximo a geometria linearizada deve estar da curva original.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Passo 2: Definir o Caminho de Saída (como exportar GeoJSON)
Especifique onde o arquivo resultante será salvo. Substitua o placeholder pelo seu diretório real.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Passo 3: **Criar Camada Vetorial** com as opções configuradas
Agora realmente **criamos camada vetorial** usando o método `VectorLayer.Create`. O bloco `using` garante a liberação adequada dos recursos.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Passo 4: Construir uma Geometria (por exemplo, uma string circular)
Aqui construímos uma geometria de exemplo — um `CircularString`. Você pode substituir isso por qualquer WKT válido.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Passo 5: **Adicionar Recurso à Camada** e salvar
Por fim, criamos um recurso, atribuímos a geometria e o adicionamos à camada. Este é o núcleo da operação **adicionar recurso à camada**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Quando o bloco `using` termina, a camada é gravada automaticamente no arquivo definido em `path`, fornecendo um arquivo GeoJSON pronto para uso.

## Problemas Comuns & Dicas
- **Caminho incorreto** – Verifique se o diretório existe e se você tem permissão de gravação.  
- **Tolerância muito baixa** – Definir `LinearizationTolerance` com um valor muito pequeno pode aumentar drasticamente o tamanho do arquivo. Ajuste conforme suas necessidades de precisão.  
- **Erros de licença** – Se aparecerem avisos de licenciamento, confirme que o arquivo de licença foi carregado corretamente antes de qualquer chamada ao Aspose.GIS.

## Perguntas Frequentes

**P: O Aspose.GIS para .NET é compatível com outras plataformas .NET?**  
R: Sim, funciona com .NET Framework, .NET Core e .NET 5/6/7.

**P: Posso usar o Aspose.GIS em projetos comerciais?**  
R: Absolutamente. Uma licença comercial remove todas as restrições de avaliação.

**P: O Aspose.GIS suporta outros formatos GIS além do GeoJSON?**  
R: Sim, suporta Shapefile, KML, GML e muitos outros.

**P: Existe uma versão de avaliação disponível?**  
R: Você pode baixar uma avaliação gratuita no site da Aspose.

**P: Onde posso obter suporte?**  
R: Use os fóruns da Aspose ou o link de suporte na seção de recursos.

## Conclusão
Seguindo estes passos, você agora sabe como **criar camada vetorial**, configurar a tolerância de linearização e **adicionar recurso à camada** para criar **exportar arquivo GeoJSON** de forma fluida. Explore tipos de geometria adicionais e o tratamento de atributos para aproveitar ao máximo o Aspose.GIS em seus projetos GIS .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-21  
**Testado com:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

---