---
date: 2026-01-05
description: Узнайте, как получать значения атрибутов и задавать значения по умолчанию
  в Aspose.GIS для .NET. Это пошаговое руководство показывает создание слоёв GeoJSON
  и построение GIS‑объектов.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Как получить значение атрибута (по умолчанию) с помощью Aspose.GIS для .NET
url: /ru/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как получить значение атрибута (по умолчанию) с Aspise.GIS для .NET

## Introduction
В этом полном руководстве вы узнаете **как получить значение атрибута** из GIS‑объекта с помощью Aspose.GIS для .NET и как работать с значениями по умолчанию, когда атрибут отсутствует. Независимо от того, создаёте ли вы движок пространственной аналитики или простой просмотрщик карт, умение извлекать атрибуты и правильно обрабатывать значения по умолчанию является ключевым для надёжных GIS‑приложений.

## Quick Answers
- **Каков основной метод?** `Feature.GetValueOrDefault<T>()`  
- **Можно ли задать собственное значение по умолчанию?** Да, через перегрузку, принимающую значение по умолчанию, или задав `DefaultValue` у атрибута.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Поддерживаемые форматы геометрии?** GeoJSON, Shapefile, GML и многие другие через драйверы Aspose.GIS.  
- **Работает ли с .NET Core/.NET 6+?** Абсолютно — библиотека кросс‑платформенная.

## Prerequisites
Перед тем как приступить, убедитесь, что у вас есть:

- Базовые знания C# и экосистемы .NET.  
- Установленный Aspose.GIS для .NET. Если вы ещё этого не сделали, скачайте его [здесь](https://releases.aspose.com/gis/net/).  
- Редактор кода, например Visual Studio или Visual Studio Code.

## Import Namespaces
Добавьте необходимые `using`‑директивы в ваш C#‑файл, чтобы типы API были доступны:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Теперь пройдём каждый пример шаг за шагом.

## How to Get Attribute Value (Default)
### Step 1: Set up the Environment
Определите путь к папке, где находятся ваши тестовые документы:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create a GeoJSON Layer
Мы **создадим слой GeoJSON** — это первое место, где мы определяем атрибут, который может быть null или не задан:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Step 3: Construct a GIS Feature
Теперь мы **создаём GIS‑объект** — это даёт нам свежий экземпляр объекта, соответствующий только что определённой схеме атрибутов:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Step 4: Retrieve Values
Наконец, мы **получаем значения атрибутов объекта** с помощью нескольких сценариев, демонстрируя работу значений по умолчанию:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## How to Set Default Values
### Step 1: Create Another GeoJSON Layer
На этот раз мы **установим значение по умолчанию для атрибута** непосредственно в схеме:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Step 2: Construct a GIS Feature (Again)
```csharp
    Feature feature = layer.ConstructFeature();
```

### Step 3: Retrieve and Set Values
Мы получаем значение по умолчанию, затем меняем его, чтобы увидеть эффект **установки значения по умолчанию** во время выполнения:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Common Pitfalls & Tips
- **Никогда не забывайте закрывать блок `using`.** Слой автоматически освобождает ресурсы, закрывая файловые дескрипторы.  
- **Когда `CanBeNull` равно false, `GetValueOrDefault` всегда вернёт значение** (либо сохранённое, либо заданное по умолчанию).  
- **Используйте обобщённую перегрузку** (`GetValueOrDefault<T>`), чтобы избежать упаковки/распаковки значимых типов.  
- **Pro tip:** Если нужно проверить, установлен ли атрибут фактически, вызовите `feature.IsAttributeSet("attribute")` перед `GetValueOrDefault`.

## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
Да, Aspose.GIS полностью совместим с .NET Core, предоставляя кросс‑платформенную поддержку.

### Can I use Aspose.GIS for commercial projects?
Абсолютно! Aspose.GIS поставляется с коммерческой лицензией, позволяющей использовать её в коммерческих приложениях без ограничений.

### Where can I find additional support and resources?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения поддержки от сообщества и изучите [документацию](https://reference.aspose.com/gis/net/) для подробной информации.

### Is there a free trial available?
Да, вы можете опробовать Aspose.GIS с бесплатной пробной версией. Скачайте её [здесь](https://releases.aspose.com/).

### How do I obtain a temporary license for testing purposes?
Для получения временной лицензии перейдите [сюда](https://purchase.aspose.com/temporary-license/).

## Additional FAQ
**Q: Что происходит, если вызвать `GetValueOrDefault` для атрибута, которого не существует?**  
A: Метод бросает `ArgumentException`. Всегда проверяйте имя атрибута или сначала используйте `feature.HasAttribute("name")`.

**Q: Можно ли изменить значение по умолчанию после создания слоя?**  
A: Да, вы можете изменить `attribute.DefaultValue`, а затем вызвать `layer.UpdateAttribute(attribute)`, чтобы сохранить изменение.

**Q: Поддерживает ли Aspose.GIS массовое обновление значений атрибутов?**  
A: Вы можете перебрать коллекцию объектов и вызвать `SetValue` для каждого; для больших наборов данных рекомендуется использовать API `FeatureCursor` для повышения производительности.

## Conclusion
В этом руководстве мы рассмотрели **как получить значение атрибута**, как задавать и переопределять значения по умолчанию, а также как **создавать схемы слоёв GeoJSON**, соответствующие потребностям вашего приложения. С помощью этих приёмов вы сможете создавать надёжные GIS‑решения, которые корректно обрабатывают отсутствующие или опциональные данные.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}