---
date: 2025-12-20
description: Aprenda como limitar a precisão ao gravar geometrias usando Aspose.GIS
  para .NET. Este guia passo a passo ajuda você a gerenciar dados espaciais com controle
  exato de coordenadas.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Como Limitar a Precisão ao Gravar Geometrias com Aspose.GIS
url: /pt/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Limitar a Precisão ao Gravar Geometrias com Aspose.GIS

Se você está se perguntando **como limitar a precisão** ao gravar geometrias em uma aplicação GIS .NET, o Aspose.GIS para .NET oferece uma maneira simples e de alto desempenho para controlar o arredondamento de coordenadas. Neste tutorial, percorreremos todo o processo — desde a configuração do ambiente até a verificação de que a saída respeita as regras de precisão que você definir.

## Respostas Rápidas
- **O que significa “limitar a precisão”?** Ele arredonda os valores das coordenadas para um número definido de dígitos fracionários ao gravar um arquivo espacial.  
- **Qual formato é usado no exemplo?** GeoJSON, mas as mesmas opções se aplicam a outros formatos suportados.  
- **Preciso de uma licença para experimentar isso?** Um teste gratuito funciona para desenvolvimento e teste; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso controlar a precisão da coordenada Z separadamente?** Sim — use `ZPrecisionModel` para definir valores exatos ou arredondados.

## Como Limitar a Precisão ao Gravar Geometrias
Limitar a precisão é essencial quando você precisa de uma representação consistente de coordenadas entre diferentes ferramentas GIS, reduzir o tamanho do arquivo ou cumprir padrões de intercâmbio de dados. A seguir, definiremos opções de precisão, gravaremos uma geometria e, em seguida, leremos de volta para confirmar o arredondamento.

## Pré-requisitos

### 1. Download e Instalação
Obtenha o pacote mais recente do Aspose.GIS para .NET no site oficial: [download link](https://releases.aspose.com/gis/net/). Siga o guia de instalação para adicionar o pacote NuGet ao seu projeto.

### 2. Importação de Namespace
Adicione os namespaces necessários para que você possa acessar as classes GIS e utilitários auxiliares.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guia Passo a Passo

### Etapa 1: Definir Opções de Precisão
Crie uma instância de `GeoJsonOptions` e informe ao Aspose.GIS quantos dígitos fracionários você deseja para as coordenadas X/Y e Z.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Etapa 2: Definir o Caminho de Saída
Especifique onde o arquivo GeoJSON resultante será salvo.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Etapa 3: Criar e Popular a Geometria
Abra um novo `VectorLayer` com as opções definidas acima, construa uma geometria `Point` e adicione-a à camada.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

### Etapa 4: Ler e Verificar a Precisão
Abra o arquivo que você acabou de criar e imprima as coordenadas. Você deve ver os valores X/Y arredondados para três casas decimais, enquanto o valor Z permanece exato.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Problemas Comuns & Dicas
- **Erros de Caminho:** Certifique-se de que o diretório em `path` exista ou use `Path.Combine` com `Environment.CurrentDirectory` para construir um caminho de arquivo seguro.  
- **Precisão Não Aplicada:** Verifique se você passa o objeto `GeoJsonOptions` ao criar a camada; caso contrário, a precisão padrão (double completo) é usada.  
- **Conjuntos de Dados Grandes:** Para operações em lote, considere reutilizar uma única instância de `VectorLayer` e adicionar recursos em lote para melhorar o desempenho.

## Perguntas Frequentes

**Q: O Aspose.GIS para .NET é compatível com outros formatos GIS?**  
A: Sim, ele suporta Shapefile, GeoJSON, KML, GML e muitos outros, permitindo conversão perfeita entre formatos.

**Q: Posso experimentar o Aspose.GIS para .NET antes de comprar?**  
A: Absolutamente. Um teste gratuito está disponível na página de download, oferecendo acesso total a todos os recursos para avaliação.

**Q: Como obtenho uma licença temporária para teste?**  
A: Licenças de avaliação temporárias podem ser geradas através do portal de licenças da Aspose; são válidas por 30 dias.

**Q: Onde posso obter ajuda se encontrar problemas?**  
A: O fórum Aspose.GIS e a tag do Stack Overflow `aspose-gis` são ótimos lugares para fazer perguntas e encontrar soluções da comunidade.

**Q: A biblioteca funciona tanto para scripts pequenos quanto para aplicações em escala empresarial?**  
A: Sim, o Aspose.GIS foi projetado para lidar com tudo, desde protótipos rápidos até aplicações de servidor de alta taxa de transferência.

## Conclusão
Seguindo os passos acima, você agora sabe **como limitar a precisão** ao gravar geometrias com Aspose.GIS para .NET. Controlar o arredondamento de coordenadas ajuda a manter seus dados espaciais limpos, interoperáveis e eficientes em armazenamento — benefícios essenciais para qualquer projeto centrado em GIS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última Atualização:** 2025-12-20  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose