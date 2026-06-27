---
date: 2026-04-24
description: Aprenda a ler dados de geodatabase usando o Aspose.GIS para .NET, uma
  biblioteca abrangente para dados geoespaciais em aplicações .NET.
keywords:
- how to read geodatabase
- Aspose.GIS .NET
- read File Geodatabase
- GIS data extraction
linktitle: Ler feições de geodatabase de arquivo
second_title: Aspose.GIS .NET API
title: Como ler recursos de geodatabase a partir de um File Geodatabase no Aspose.GIS
url: /pt/net/layer-data-operations/read-features-from-file-geodatabase/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler Recursos de um File Geodatabase no Aspose.GIS

## Introdução
Se você está procurando uma maneira confiável **de ler dados de geodatabase** em um ambiente .NET, o Aspose.GIS para .NET oferece uma API limpa e de alto desempenho que permite extrair informações de recursos de um File Geodatabase com apenas algumas linhas de código C#. Neste tutorial percorreremos todo o processo — desde a configuração do projeto até a iteração sobre camadas e extração de geometria — para que você possa começar a criar aplicações habilitadas para GIS imediatamente.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.GIS para .NET (versão de avaliação gratuita disponível).  
- **Qual formato de arquivo é suportado?** File Geodatabase (.gdb) via o driver `FileGdb`.  
- **Preciso de licença para desenvolvimento?** Não, a avaliação funciona para desenvolvimento e testes.  
- **Posso executar isso em .NET 6+?** Sim, o Aspose.GIS suporta .NET 5, .NET 6 e posteriores.  
- **Quantas linhas de código?** Aproximadamente 30 linhas para ler e exibir todas as geometrias dos recursos.

## O que é um File Geodatabase?
Um File Geodatabase (frequentemente abreviado como **GDB**) é o repositório de dados baseado em pastas da Esri que armazena dados vetoriais e raster em um conjunto de arquivos. É amplamente usado em GIS de desktop, e o Aspose.GIS abstrai o manuseio de arquivos de baixo nível para que você possa focar nos próprios dados.

## Por que usar o Aspose.GIS para ler um geodatabase?
- **Sem dependências externas** – puro .NET, sem DLLs nativas.  
- **Multiplataforma** – funciona no Windows, Linux e macOS.  
- **Conjunto completo de recursos** – ler, gravar, editar e analisar dados sem ferramentas adicionais.  
- **Desempenho otimizado** – iteração rápida em grandes conjuntos de dados.

## Pré‑requisitos
Antes de mergulhar no código, certifique‑se de que você tem o seguinte:

1. **Ambiente de Desenvolvimento .NET** – Visual Studio 2022 (ou qualquer IDE que suporte .NET 6+).  
2. **Aspose.GIS para .NET** – baixe o pacote mais recente na [página de download](https://releases.aspose.com/gis/net/).  
3. **Conhecimento básico de C#** – você deve estar confortável com instruções `using` e loops.

## Importar Namespaces
Primeiro, importe os namespaces que expõem as classes GIS necessárias.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
```

## Guia Passo a Passo

### Passo 1: Abrir o File Geodatabase
Especifique o caminho para a pasta `.gdb` e abra‑a com o driver `FileGdb`.

```csharp
using (var dataset = Dataset.Open(dataDir + "ThreeLayers.gdb", Drivers.FileGdb))
```

### Passo 2: Iterar Sobre as Camadas
Um File Geodatabase pode conter várias camadas (classes de recursos). Percorra‑as para processar cada uma.

```csharp
for (int i = 0; i < dataset.LayersCount; ++i)
{
    // Access layer information
}
```

### Passo 3: Acessar Informações da Camada
Dentro do loop, recupere o nome da camada e a contagem de recursos. Isso ajuda a entender a estrutura do conjunto de dados antes de aprofundar.

```csharp
Console.WriteLine("Layer {0} name: {1}", i, dataset.GetLayerName(i));
```

### Passo 4: Abrir uma Camada e Enumerar Seus Recursos
Abra a camada atual e percorra cada recurso que ela contém.

```csharp
using (var layer = dataset.OpenLayerAt(i))
{
    foreach (var feature in layer)
    {
        // Access feature geometry or properties
    }
}
```

### Passo 5: Trabalhar com a Geometria do Recurso
Para cada recurso, você pode ler sua geometria, atributos ou até modificá‑los. Aqui simplesmente imprimimos a geometria como WKT (Well‑Known Text).

```csharp
Console.WriteLine(feature.Geometry.AsText());
```

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Exceção `File not found`** | O caminho para a pasta `.gdb` está incorreto ou a pasta está ausente. | Verifique se `dataDir` aponta para a pasta que contém `ThreeLayers.gdb`. Use caminhos absolutos para depuração. |
| **Nenhuma camada retornada** | O conjunto de dados foi aberto com o driver errado. | Certifique‑se de que `Drivers.FileGdb` está sendo usado; outros drivers (ex.: `Drivers.Shapefile`) não leem um GDB. |
| **Geometria é nula** | O recurso não possui geometria (ex.: camada de anotação). | Adicione uma verificação de nulidade antes de chamar `AsText()`. |
| **Desaceleração de desempenho em GDBs grandes** | Iterar sem paginação carrega tudo na memória. | Processar recursos em lotes ou usar `layer.Select` com filtro para limitar linhas. |

## Perguntas Frequentes

**P: O Aspose.GIS para .NET é compatível com todas as versões do .NET Framework?**  
R: Sim, funciona com .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 e posteriores.

**P: Posso integrar o Aspose.GIS com outras plataformas GIS?**  
R: Absolutamente. Você pode ler de um File Geodatabase e depois exportar para Shapefile, GeoJSON ou qualquer outro formato suportado para ferramentas downstream.

**P: O Aspose.GIS oferece suporte a diferentes formatos de dados geoespaciais?**  
R: Sim, suporta mais de 60 formatos, incluindo Shapefile, GeoJSON, KML, GML e formatos raster como GeoTIFF.

**P: Existe um fórum da comunidade onde eu possa buscar ajuda sobre questões relacionadas ao Aspose.GIS?**  
R: Sim, você pode visitar o [fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) para interagir com a comunidade e obter suporte de especialistas.

**P: Posso experimentar o Aspose.GIS para .NET antes de comprar?**  
R: Claro, você pode aproveitar a avaliação gratuita do Aspose.GIS para .NET na [página de releases](https://releases.aspose.com/), permitindo explorar seus recursos antes de decidir pela compra.

## Conclusão
Seguindo os passos acima, você agora sabe **como ler dados de geodatabase** usando o Aspose.GIS para .NET. Essa abordagem lhe dá controle programático total sobre camadas e recursos, abrindo caminho para análises GIS personalizadas, migração de dados ou visualizações de mapas em qualquer aplicação .NET.

---

**Última atualização:** 2026-04-24  
**Testado com:** Aspose.GIS para .NET 24.11 (mais recente)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}