---
date: 2026-05-31
description: Aprenda a criar GeoJSON, configurar opções de GeoJSON e adicionar recursos
  à camada usando Aspose.GIS para .NET. Siga este guia passo a passo.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Definir tolerância Linearization
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Como criar GeoJSON com tolerância Aspose.GIS para .NET
url: /pt/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar GeoJSON com Tolerância Aspose.GIS para .NET

## Introdução
Se você deseja **aprender como criar GeoJSON** arquivos, controlar a precisão de curvas e exportar o resultado como um documento pronto‑para‑uso, o Aspose.GIS para .NET torna isso simples. Neste tutorial você descobrirá como configurar as opções de GeoJSON, definir a tolerância de linearização e **add feature to layer** objects mantendo o código limpo e pronto para produção.

## Respostas Rápidas
- **O que significa “create vector layer”?** Ele cria um novo conjunto de dados vetoriais GIS (por exemplo, um arquivo GeoJSON) que pode armazenar geometrias e atributos.  
- **Como definir a tolerância de linearização?** Defina a propriedade `LinearizationTolerance` em uma instância de `GeoJsonOptions` antes de criar a camada.  
- **Posso exportar um arquivo GeoJSON diretamente?** Sim—use `VectorLayer.Create` com o driver `Drivers.GeoJson` e as opções configuradas.  
- **Preciso de uma licença?** Uma licença válida do Aspose.GIS desbloqueia todos os recursos; uma chave de avaliação temporária funciona para testes.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “create vector layer”?
Criar uma camada vetorial significa inicializar um novo contêiner GIS (como um arquivo GeoJSON) que pode armazenar pontos, linhas, polígonos e dados de atributos associados. Essa camada torna‑se o alvo para qualquer geometria que você construir e quaisquer atributos que você anexar.

## Por que configurar opções de GeoJSON?
Configurar opções de GeoJSON—especialmente a **linearization tolerance**—garante que geometrias curvas (por exemplo, `CircularString`) sejam aproximadas com uma precisão que atenda aos requisitos de exatidão da sua aplicação. Uma configuração adequada reduz o tamanho do arquivo enquanto preserva a fidelidade visual, o que é crítico quando o GeoJSON é consumido por mapas web ou ferramentas de análise espacial.

## Pré‑requisitos
1. **Visual Studio** (qualquer versão recente).  
2. **Licença Aspose.GIS** (ou uma chave de avaliação temporária).  
3. Biblioteca **Aspose.GIS for .NET** referenciada no seu projeto.  
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

### Etapa 1: Configurar Opções de GeoJSON (como definir a tolerância)
`GeoJsonOptions` especifica as configurações de serialização usadas ao gravar arquivos GeoJSON.  
`GeoJsonOptions` define como o Aspose.GIS serializa GeoJSON, incluindo tolerância de linearização, precisão de coordenadas e outras configurações de saída.  
Vamos criar um objeto `GeoJsonOptions` e informar ao Aspose.GIS quão próximo a geometria linearizada deve estar da curva original.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Etapa 2: Definir o Caminho de Saída (como exportar GeoJSON)
Especifique o caminho completo do arquivo onde o GeoJSON resultante será salvo. Certifique‑se de que a pasta exista e que a aplicação tenha permissões de gravação.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Etapa 3: **Create Vector Layer** com as opções configuradas
A classe `VectorLayer` representa um contêiner GIS que pode ler e gravar dados espaciais.  
`Drivers.GeoJson` é o identificador do driver para gravação de arquivos no formato GeoJSON.  
Usar `VectorLayer.Create` juntamente com o driver `Drivers.GeoJson` e as `GeoJsonOptions` configuradas anteriormente cria um novo arquivo GeoJSON pronto para inserção de recursos.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Etapa 4: Construir uma Geometria (por exemplo, uma string circular)
`CircularString` é uma geometria de linha curva que o Aspose.GIS pode linearizar com base na tolerância que você definir. Você pode substituir isso por qualquer representação WKT válida, como `POINT`, `LINESTRING` ou `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Etapa 5: **Add Feature to Layer** e salvar
`Feature` é o objeto que associa uma geometria a dados de atributos. Após criar uma instância de `Feature`, atribua a geometria, opcionalmente adicione valores de atributos e chame `layer.Add(feature)` para persistir. Quando o bloco `using` termina, a camada é gravada automaticamente no arquivo definido em `path`.

Quando o bloco `using` termina, a camada é gravada automaticamente no arquivo definido em `path`, fornecendo um arquivo GeoJSON pronto‑para‑uso.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## Problemas Comuns & Dicas
- **Caminho incorreto** – Verifique se o diretório existe e se você tem permissões de gravação.  
- **Tolerância muito baixa** – Definir `LinearizationTolerance` para um valor muito pequeno pode aumentar o tamanho do arquivo drasticamente; uma tolerância de 0.001 geralmente equilibra precisão e tamanho.  
- **Erros de licença** – Se você vir avisos de licença, certifique‑se de que o arquivo de licença esteja carregado antes de qualquer chamada ao Aspose.GIS.  
- **Observação de desempenho** – O Aspose.GIS suporta o processamento de arquivos de até 2 GB sem carregar todo o documento na memória, graças à sua arquitetura de streaming.

## Perguntas Frequentes

**Q: O Aspose.GIS para .NET é compatível com outros frameworks .NET?**  
A: Sim, funciona com .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6/7.

**Q: Posso usar o Aspose.GIS em projetos comerciais?**  
A: Absolutamente. Uma licença comercial remove todas as restrições de avaliação e fornece suporte técnico completo.

**Q: O Aspose.GIS suporta outros formatos GIS além de GeoJSON?**  
A: Sim, ele suporta mais de 30 formatos — incluindo Shapefile, KML, GML e CSV — permitindo conversão perfeita entre eles.

**Q: Existe uma versão de avaliação disponível?**  
A: Você pode baixar uma avaliação gratuita de 30 dias no site da Aspose; ela inclui todos os recursos.

**Q: Onde posso obter suporte?**  
A: Use os fóruns da Aspose, o portal de suporte dedicado ou o link “Contact Support” no painel do produto.

## Conclusão
Seguindo estas etapas, você agora sabe **how to create GeoJSON**, configurar a tolerância de linearização e **add feature to layer** para exportação de GeoJSON sem interrupções. Explore tipos adicionais de geometria, manipulação de atributos e cenários de processamento em lote para aproveitar ao máximo o Aspose.GIS em seus projetos GIS .NET.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Converter GeoJSON – Aspose.GIS para .NET](/gis/net/geo-data-conversion/)
- [Criar Camada Vetorial, Limitar Precisão com Aspose.GIS para .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Criar Camada Vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}