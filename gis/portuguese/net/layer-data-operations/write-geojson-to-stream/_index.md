---
date: 2026-01-02
description: Aprenda como escrever GeoJSON em um fluxo em C# usando Aspose.GIS para
  .NET. Exiba exemplos de GeoJSON em C# e impulsione seus aplicativos geoespaciais.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Como escrever GeoJSON em um stream com Aspose.GIS para .NET
url: /pt/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Escrever GeoJSON em um Stream

## Introdução
Se você precisa **how to write geojson** diretamente em um memory ou file stream em uma aplicação .NET, você está no lugar certo. Neste tutorial, vamos percorrer os passos exatos para escrever GeoJSON em um stream usando a biblioteca Aspose.GIS for .NET, e também mostraremos como **display GeoJSON C#** na saída do console. Ao final, você terá um padrão reutilizável que pode ser inserido em qualquer projeto geoespacial.

## Respostas Rápidas
- **What does “write GeoJSON to stream” mean?** Significa serializar uma camada vetorial no formato GeoJSON e enviar os bytes para um objeto `Stream` (por exemplo, `MemoryStream`).  
- **Which library handles this?** Aspose.GIS for .NET fornece um driver GeoJSON embutido.  
- **Do I need a license for development?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Can I run this on Linux?** Sim – Aspose.GIS é multiplataforma e funciona no Windows, Linux e macOS.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “how to write geojson” em .NET?
Aspose.GIS permite criar um `VectorLayer`, adicionar recursos e então serializar a camada usando o driver `Drivers.GeoJson`. O driver grava o texto GeoJSON diretamente em qualquer `Stream`, dando a você controle total sobre onde os dados vão (memória, arquivo, rede, etc.).

## Por que usar Aspose.GIS para esta tarefa?
- **Zero‑dependency serialization** – sem necessidade de bibliotecas JSON externas.  
- **Full GeoJSON spec compliance** – suporta FeatureCollections, propriedades e precisão de coordenadas.  
- **Cross‑platform** – funciona da mesma forma no Windows, Linux e macOS.  
- **Performance‑optimized** – grava diretamente no stream sem strings intermediárias.

## Pré-requisitos
1. **Aspose.GIS for .NET** – faça o download [aqui](https://releases.aspose.com/gis/net/).  
2. **Document directory** – decida onde deseja manter arquivos temporários ou streams de saída.

Agora, vamos mergulhar no código.

## Importar Namespaces
Primeiro, inclua os namespaces que dão acesso às classes Aspose.GIS e às utilidades padrão de I/O do .NET:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Etapa 1: Configurar o Diretório de Documentos
Defina a pasta que hospedará quaisquer arquivos temporários que você possa precisar.

```csharp
string dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho real na sua máquina.

## Etapa 2: Criar um Memory Stream
Um `MemoryStream` permite manter o GeoJSON na memória, o que é perfeito para APIs ou quando você deseja devolver os dados diretamente a um cliente.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Etapa 3: Criar um Vector Layer com o Driver GeoJSON
Dentro do bloco de memory‑stream, crie um `VectorLayer` que usa o driver GeoJSON. Isso indica ao Aspose.GIS para serializar a camada como GeoJSON.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Etapa 4: Definir Atributos de Feature
Adicione definições de atributos que aparecerão como propriedades na saída final do GeoJSON.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Etapa 5: Construir e Adicionar Features
Crie dois pontos de exemplo, atribua valores de atributos e adicione-os à camada.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Etapa 6: Exibir Saída GeoJSON C#
Após a camada ser preenchida, converta os bytes do stream para uma string UTF‑8 e escreva-a no console. Isso demonstra como **display GeoJSON C#** resultados.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Você deverá ver uma FeatureCollection GeoJSON válida impressa no terminal.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|--------|
| Saída vazia | A posição do stream está no final ao ler | Chame `memoryStream.Position = 0;` antes de converter para string. |
| Geometria inválida | Coordenadas fora dos intervalos válidos | Verifique se a latitude está entre -90 e 90, longitude entre -180 e 180. |
| Exceção de licença | Executando sem uma licença válida em produção | Aplique uma licença temporária ou completa usando `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Perguntas Frequentes
### Posso usar Aspose.GIS para .NET em ambientes Windows e Linux?
Sim, Aspose.GIS para .NET é compatível com sistemas Windows e Linux.  

### Existe uma avaliação gratuita disponível?
Com certeza! Você pode explorar uma avaliação gratuita [aqui](https://releases.aspose.com/).  

### Onde posso encontrar documentação detalhada?
Confira a documentação [aqui](https://reference.aspose.com/gis/net/).  

### Como posso obter licença temporária?
Licenças temporárias estão disponíveis [aqui](https://purchase.aspose.com/temporary-license/).  

### Precisa de assistência ou tem mais perguntas?
Visite nosso fórum de suporte [aqui](https://forum.aspose.com/c/gis/33).

## FAQ
**Q: Posso escrever GeoJSON diretamente em um arquivo ao invés de um memory stream?**  
A: Sim—substitua `MemoryStream` por `FileStream` e forneça um caminho de arquivo. O mesmo driver funciona.

**Q: Como controlo a indentação ou formatação do GeoJSON gerado?**  
A: Aspose.GIS grava JSON compacto por padrão. Para saída formatada, pós‑procese a string com `JsonSerializerOptions { WriteIndented = true }`.

**Q: É possível adicionar geometrias mais complexas (por exemplo, polígonos) à camada?**  
A: Absolutamente. Crie um objeto `Polygon` ou `LineString`, atribua-o a `Feature.Geometry` e adicione a feature como mostrado acima.

**Q: Conjuntos de dados grandes caberão em um `MemoryStream`?**  
A: Para coleções muito grandes, considere transmitir diretamente para um arquivo ou usar um `BufferedStream` para evitar alto consumo de memória.

**Q: O driver GeoJSON suporta definições de CRS (Sistema de Referência de Coordenadas)?**  
A: Sim—defina a propriedade `SpatialReferenceSystem` da camada antes de adicionar features se precisar de um CRS diferente de WGS84.

## Conclusão
Agora você tem um padrão completo e pronto para produção para **how to write geojson** em qualquer stream .NET usando Aspose.GIS. Seja para retornar GeoJSON de uma API web, salvá-lo em um arquivo ou simplesmente exibi-lo no console, os passos acima cobrem todo o fluxo de trabalho. Explore mais a biblioteca para trabalhar com outros formatos como Shapefile, KML ou GML, e continue construindo aplicações geoespaciais mais robustas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-02  
**Testado com:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose