---
date: 2026-01-02
description: Aprenda como adicionar recurso de ponto enquanto define nomes de campos
  e lê o ID do objeto usando Aspose.GIS para .NET. Guia passo a passo para desenvolvedores.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Adicionar recurso de ponto e especificar nomes dos campos de ID de objeto e
  geometria
url: /pt/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar recurso de ponto e especificar nomes de campo de ID de objeto e geometria

## Introdução
Embarcar em uma jornada pelo mundo dos Sistemas de Informação Geográfica (GIS) usando Aspose.GIS para .NET abre um leque de possibilidades para desenvolvedores e entusiastas. Neste tutorial, **você aprenderá como adicionar um recurso de ponto** enquanto também **define nomes de campo** e **lê valores de ID de objeto**, proporcionando controle total sobre seus dados espaciais.

## Respostas rápidas
- **Qual é o objetivo principal deste guia?** Mostrar como adicionar um recurso de ponto e configurar os nomes de campo de ID de objeto e geometria.  
- **Qual biblioteca é usada?** Aspose.GIS para .NET.  
- **Preciso de uma licença?** Um teste gratuito está disponível; uma licença é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Posso ler o ID do objeto após a inserção?** Sim – o tutorial demonstra como ler o ID do objeto a partir da camada.

## Pré-requisitos
Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos:
- Aspose.GIS para .NET: Baixe e instale a biblioteca a partir de [aqui](https://releases.aspose.com/gis/net/).
- Diretório de documentos: Configure um diretório para seus documentos onde armazenar os geobancos de dados.
- Ambiente .NET: Certifique‑se de que você tem um ambiente .NET funcionando.

## Importar namespaces
Para iniciar, você precisa importar os namespaces necessários ao seu projeto. Esses namespaces fornecem as classes e métodos essenciais para interagir com Aspose.GIS para .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Passo 1: Adicionar recurso de ponto e especificar nomes de campo de ID de objeto e geometria
Nesta etapa, você aprenderá a configurar os nomes de campo de ID de objeto e geometria para seus dados GIS. Isso é crucial para um gerenciamento eficiente dos dados e para poder **ler o ID do objeto** posteriormente.

### Passo 1.1: Definir diretório de documentos
Comece definindo o caminho para o seu diretório de documentos:

```csharp
string dataDir = "Your Document Directory";
```

### Passo 1.2: Criar um GeoDatabase e definir opções
Crie um GeoDatabase com os **nomes de campo desejados** para ID de objeto e geometria:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Passo 1.3: Criar e adicionar uma camada
Crie uma camada dentro do GeoDatabase e adicione um recurso que represente uma geometria de ponto:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Passo 1.4: Abrir e recuperar dados da camada
Abra a camada e recupere o recurso que você acabou de adicionar. Isso demonstra como **ler o ID do objeto** a partir do conjunto de dados:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Por que definir nomes de campo personalizados?
Personalizar os nomes de campo de ID de objeto e geometria oferece flexibilidade ao integrar-se com bancos de dados existentes ou ao aderir a convenções de nomenclatura exigidas por aplicações downstream. Também torna os dados mais auto‑descritivos, simplificando a manutenção e a colaboração.

## Problemas comuns e solução de problemas
- **Diretório ausente** – Certifique‑se de que `dataDir` aponta para uma pasta existente; caso contrário, `Dataset.Create` lançará uma exceção.
- **Conflitos de nomes de campo** – Se já existir um campo com o mesmo nome no geobanco de dados, a criação falhará. Escolha nomes únicos.
- **Incompatibilidade de referência espacial** – Sempre corresponda o sistema de referência espacial (por exemplo, WGS84) com os dados que pretende armazenar.

## Conclusão
Parabéns! Você aprendeu com sucesso como **adicionar um recurso de ponto**, **definir nomes de campo** e **ler o ID do objeto** usando Aspose.GIS para .NET. Essa base permite que você construa aplicações GIS robustas e gerencie dados espaciais com confiança.

## Perguntas Frequentes
### Q: Posso usar Aspose.GIS para .NET em minhas aplicações web?
A: Sim, Aspose.GIS para .NET é adequado tanto para aplicações desktop quanto web, oferecendo capacidades geoespaciais versáteis.

### Q: Existe uma versão de teste disponível antes da compra?
A: Sim, você pode explorar os recursos do Aspose.GIS para .NET com um teste gratuito disponível [aqui](https://releases.aspose.com/).

### Q: Como posso obter uma licença temporária para Aspose.GIS para .NET?
A: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

### Q: Quais sistemas de referência espacial o Aspose.GIS para .NET suporta?
A: Aspose.GIS para .NET suporta vários sistemas de referência espacial, proporcionando flexibilidade para diferentes conjuntos de dados geográficos.

### Q: Onde posso buscar ajuda ou discutir dúvidas relacionadas ao Aspose.GIS?
A: Visite o fórum Aspose.GIS [aqui](https://forum.aspose.com/c/gis/33) para suporte e discussões.

## Perguntas Frequentes Adicionais

**Q: Posso mudar o campo de ID de objeto após a camada ser criada?**  
A: Não. O nome do campo é definido quando a camada é criada; você deve recriar a camada com um novo objeto `FileGdbOptions` para alterá‑lo.

**Q: Como recupero outros valores de atributo além do ID de objeto?**  
A: Use `feature.GetValue<T>("FieldName")` onde `FieldName` é o nome do atributo que você deseja ler.

**Q: É possível adicionar múltiplos recursos de ponto em um único lote?**  
A: Sim. Percorra seus dados, construa um recurso para cada ponto, defina sua geometria e chame `layer.Add(feature)` dentro do mesmo bloco `using`.

**Q: O Aspose.GIS suporta outros tipos de geometria?**  
A: Absolutamente. Você pode trabalhar com `LineString`, `Polygon`, `MultiPoint` e muito mais, criando os objetos de geometria apropriados.

**Q: O que acontece se eu tentar ler um ID de objeto que não existe?**  
A: Acessar um índice fora do intervalo (por exemplo, `layer[10]` quando existe apenas um recurso) lançará uma `IndexOutOfRangeException`. Sempre verifique `layer.Count` primeiro.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}