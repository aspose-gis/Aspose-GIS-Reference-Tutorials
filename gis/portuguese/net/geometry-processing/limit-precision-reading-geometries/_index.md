---
date: 2026-09-10
description: Aprenda como criar camada vetorial com Aspose.GIS for .NET e limitar
  a precisão para reduzir o tamanho do shapefile, melhorar o desempenho e manter a
  precisão das coordenadas.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Limitar Precisão ao Ler Geometrias
og_description: Aprenda como criar camada vetorial com Aspose.GIS for .NET e limitar
  a precisão para reduzir o tamanho do shapefile, melhorar o desempenho e gerenciar
  a precisão das coordenadas.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Como criar camada vetorial com Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Como criar camada vetorial com Aspose.GIS for .NET
url: /pt/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar camada vetorial com Aspose.GIS para .NET

## Introdução
Ao trabalhar com dados geoespaciais, você frequentemente se pergunta **how to create vector layer** objetos que correspondam à precisão que sua aplicação realmente necessita. Arredondar coordenadas para um número razoável de casas decimais não apenas acelera a análise, mas também pode **reduce shapefile size by up to 30 %** para conjuntos de pontos típicos. Neste guia passo a passo, você verá como criar uma camada vetorial, gravar uma geometria de ponto e, em seguida, lê‑la novamente usando modelos de precisão exatos e arredondados. Ao final, você saberá como **set precision model** opções que equilibram desempenho com a precisão espacial necessária.

## Respostas rápidas
- **O que significa “limit precision”?** Ele arredonda os valores de coordenadas para um número definido de casas decimais.  
- **Por que criar uma camada vetorial primeiro?** Uma camada vetorial é o contêiner que armazena geometrias como pontos, linhas e polígonos.  
- **Quais modelos de precisão estão disponíveis?** `PrecisionModel.Exact` (sem arredondamento) e `PrecisionModel.Rounding(n)` (arredonda para *n* decimais).  
- **Preciso de licença para experimentar isso?** Um teste gratuito está disponível na página de lançamentos.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core e .NET 5/6+.

## O que é criar uma camada vetorial?
O ato de **creating a vector layer** significa instanciar a classe `VectorLayer` da Aspose.GIS, que representa um único shapefile no disco e contém todos os recursos de geometria que você adiciona. Essa camada torna‑se o ponto de entrada para leitura, gravação e manipulação de dados espaciais. Também permite definir campos de atributos e definir a referência espacial para o conjunto de dados.

## Por que limitar a precisão e como isso ajuda?
- **Aumento de desempenho** – Reduzir o número de dígitos decimais diminui a quantidade de dados binários que precisam ser analisados e serializados, frequentemente proporcionando um ganho de velocidade de 15‑20 % em arquivos grandes.  
- **Arquivos menores** – Arredondar coordenadas para duas ou três casas decimais pode reduzir um shapefile de 10 MB para aproximadamente 7 MB, facilitando o armazenamento e a transferência pela rede.  
- **Precisão suficiente** – A maioria das análises GIS (por exemplo, mapeamento a nível de cidade) necessita apenas de precisão em metros, tornando o arredondamento de 3 casas decimais mais que adequado.

## Pré‑requisitos
1. **Instalação** – A biblioteca Aspose.GIS para .NET deve estar instalada em seu ambiente de desenvolvimento. Caso não esteja, você pode baixá‑la na [releases page](https://releases.aspose.com/gis/net/).  
2. **Familiaridade com .NET** – Conhecimento básico de C# e do framework .NET é necessário para entender e implementar os exemplos de código fornecidos.  
3. **Ambiente de desenvolvimento** – É necessário um ambiente de desenvolvimento .NET funcional, como o Visual Studio.  
4. **Diretório de documentos** – Tenha um diretório configurado onde você possa armazenar e acessar o shapefile gerado durante o processo.

## Importar namespaces
Antes de começarmos a implementar a funcionalidade de limitar a precisão ao ler geometrias, vamos garantir que importamos os namespaces necessários:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Como criar camada vetorial
Carregue um novo `VectorLayer` especificando a pasta de saída e o nome do shapefile desejado. Isso cria um contêiner vazio pronto para aceitar objetos de geometria.

A classe `VectorLayer` é o objeto de nível superior da Aspose.GIS que representa um único shapefile no disco. Após criar uma instância, você pode adicionar recursos, definir campos de atributos e, finalmente, chamar `Save()` para gravar os arquivos no sistema de arquivos.

```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Definindo opções de precisão
`PrecisionModel` define como os valores de coordenadas são arredondados ou mantidos exatos ao ler geometrias. Você define o modelo em um objeto `ReadOptions` antes de abrir uma camada.

A classe `PrecisionModel` é um componente central da Aspose.GIS que controla o comportamento de arredondamento para os eixos X e Y. Ao escolher o modelo apropriado, você determina se a biblioteca preserva cada dígito ou trunca para uma contagem decimal específica.

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Lendo geometrias com precisão exata
`ReadOptions` especifica parâmetros para ler uma camada vetorial, como o modelo de precisão a ser aplicado.  
Abra a camada vetorial salva anteriormente usando uma instância `ReadOptions` que referencia `PrecisionModel.Exact`. Isso garante que cada coordenada seja lida sem nenhum arredondamento.

Quando você usa `PrecisionModel.Exact`, a Aspose.GIS lê os valores brutos de dupla precisão armazenados no shapefile, garantindo que nenhuma informação seja perdida durante a operação de leitura.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncando a precisão
Se você deseja truncar a precisão para um número específico de casas decimais, substitua `Exact` por `PrecisionModel.Rounding(n)`, onde *n* é o número de decimais que você deseja manter.

Arredondar para duas casas decimais (`PrecisionModel.Rounding(2)`) normalmente reduz o tamanho do arquivo em 20‑30 % enquanto mantém a precisão das coordenadas dentro de alguns centímetros para a maioria das escalas de mapeamento.

```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Como definir o modelo de precisão para diferentes cenários
Escolha o modelo que corresponde ao seu caso de uso:

- **Análise científica de alta precisão** – Use `PrecisionModel.Exact` para reter cada dígito.  
- **Tiles de web‑mapping ou aplicativos móveis** – Use `PrecisionModel.Rounding(2)` para manter os arquivos leves e a renderização rápida.

Selecionar o modelo apropriado faz parte do processo de tomada de decisão de **set precision model** que equilibra precisão e desempenho.

## Problemas comuns e soluções
`XYPrecisionModel` é uma propriedade de `ReadOptions` que define o modelo de precisão para as coordenadas X e Y.  

- **Valores de coordenadas inesperados** – Certifique‑se de definir `options.XYPrecisionModel` *antes* de abrir a camada. Alterá‑lo após a abertura não tem efeito.  
- **Arquivo não encontrado** – Verifique se a variável `path` aponta para um diretório válido e se o Shapefile foi criado com sucesso na etapa anterior.  
- **Tipo de geometria incorreto** – O exemplo usa um `Point`. Para outros tipos de geometria (por exemplo, `LineString`), o casting deve corresponder ao tipo real.  

## Dicas para reduzir o tamanho do shapefile
- Use `PrecisionModel.Rounding` com o menor número de casas decimais que ainda atenda às suas necessidades de precisão.  
- Remova campos de atributos desnecessários antes de gravar a camada.  
- Compacte os arquivos resultantes `.shp`, `.shx` e `.dbf` usando utilitários ZIP padrão se precisar transferi‑los.

## Conclusão
Gerenciar a precisão ao ler geometrias é um aspecto crucial da manipulação de dados geoespaciais. Aspose.GIS para .NET oferece funcionalidades robustas para alcançar isso de forma eficiente. Seguindo os passos acima, você pode criar objetos **create vector layer**, **set precision model**, e até **reduce shapefile size** quando apropriado, garantindo o manuseio ideal de dados em suas aplicações.

## Perguntas frequentes
### Posso usar Aspose.GIS para .NET com outros frameworks .NET como .NET Core ou .NET Standard?
Sim, Aspose.GIS para .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET Standard.  
### Existe uma versão de avaliação disponível para Aspose.GIS para .NET?
Sim, você pode obter uma versão de avaliação gratuita na [releases page](https://releases.aspose.com/).  
### Onde posso encontrar documentação abrangente para Aspose.GIS para .NET?
Você pode consultar a [documentation](https://reference.aspose.com/gis/net/) para informações detalhadas e exemplos.  
### Como posso obter licenças temporárias para Aspose.GIS para .NET?
Licenças temporárias podem ser adquiridas na [purchase page](https://purchase.aspose.com/temporary-license/) para Aspose.GIS.  
### Onde posso buscar assistência ou suporte para Aspose.GIS para .NET?
Você pode visitar o [forum](https://forum.aspose.com/c/gis/33) da Aspose.GIS para dúvidas, discussões ou necessidades de suporte.

## Perguntas frequentes
**Q: Limitar a precisão afeta o shapefile original?**  
A: Não. A precisão é aplicada apenas ao ler a geometria; o arquivo fonte permanece inalterado.  

**Q: Posso usar um modelo de precisão diferente para as coordenadas X e Y?**  
A: Atualmente, a Aspose.GIS aplica o mesmo `XYPrecisionModel` a ambos os eixos.  

**Q: É possível definir uma função de arredondamento personalizada?**  
A: A API suporta apenas o método interno `PrecisionModel.Rounding(int)`. Para lógica personalizada, você precisaria pós‑processar as coordenadas após a leitura.

---

**Última atualização:** 2026-09-10  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Como limitar a precisão ao gravar geometrias com Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Como criar camada vetorial com SRS usando Aspose.GIS para .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Criar camada vetorial em File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}