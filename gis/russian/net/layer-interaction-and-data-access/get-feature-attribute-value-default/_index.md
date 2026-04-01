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

## Введение
В этом руководстве вы узнаете **как получить значение атрибута** из ГИС-объекта с помощью Aspose.GIS для .NET и как получить значения по умолчанию, когда атрибут отсутствует. Независимо от того, создаёте ли вы движение пространственной аналитики или простой просмотрщик карт, умение учитывать атрибуты и правильно обрабатывать значения по умолчанию является ключевым для надёжных ГИС-приложений.

## Быстрые ответы
- **Каков основной метод?** `Feature.GetValueOrDefault<T>()`
- **Можно ли задать собственное значение по умолчанию?** Да, через перегрузку, добавив значение по умолчанию, или задав `DefaultValue` в атрибуте.
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.
- **Поддерживаемые формы геометрии?** GeoJSON, Shapefile, GML и многие другие через драйверы Aspose.GIS.
- **Работает ли с .NET Core/.NET 6+?** Абсолютно — библиотека кросс‑платформенная.

## Предварительные условия
Перед тем как приступить, убедитесь, что у вас есть:

- Базовые знания C# и экосистемы .NET.
- Установленный Aspose.GIS для .NET. Если вы ещё этого не сделали, скачайте его [здесь](https://releases.aspose.com/gis/net/).
- Редактор кода, например Visual Studio или VisualStudioCode.

## Импортировать пространства имен
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

## Как получить значение атрибута (по умолчанию)
### Шаг 1: Настройка среды
Определите путь к папке, где находятся ваши тестовые документы:

```csharp
string dataDir = "Your Document Directory";
```

### Шаг 2: Создание слоя GeoJSON
Мы **создадим слой GeoJSON** — это первое место, где мы определяем атрибут, который может быть null или не задан:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Шаг 3: Создание объекта ГИС
Теперь мы **создаём GIS‑объект** — это даёт нам свежий экземпляр объекта, соответствующий только что определённой схеме атрибутов:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Шаг 4: Получение значений
Наконец, мы **получаем значения атрибутов объекта** с помощью нескольких сценариев, демонстрируя работу значений по умолчанию:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Как установить значения по умолчанию
### Шаг 1: Создание еще одного слоя GeoJSON
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

### Шаг 2: Создание объекта ГИС (снова)
```csharp
    Feature feature = layer.ConstructFeature();
```

### Шаг 3: Получение и установка значений
Мы получаем значение по умолчанию, затем меняем его, чтобы увидеть эффект **установки значения по умолчанию** во время выполнения:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Распространенные ошибки и советы
- **Никогда не забывайте закрывать блок «использование».** Слой автоматически освобождает ресурсы, закрывая файловые дескрипторы.
- **Когда `CanBeNull` равно false, `GetValueOrDefault` всегда вернёт значение** (либо сохранённое, либо заданное по умолчанию).
- **Используйте общедоступную перегрузку** (`GetValueOrDefault<T>`), чтобы избежать упаковки/распаковки значимых типов.
- **Совет для профессионалов:** если необходимо проверить, установлен ли атрибут фактически, вызовите `feature.IsAttributeSet("attribute")` перед `GetValueOrDefault`.

## Часто задаваемые вопросы
### Совместим ли Aspose.GIS с .NET Core?
Да, Aspose.GIS полностью совместим с .NET Core, обеспечивая кросс‑платформенную поддержку.

### Могу ли я использовать Aspose.GIS для коммерческих проектов?
Абсолютно! Aspose.GIS работает с коммерческой лицензией и может использовать ее в коммерческих приложениях без ограничений.

### Где я могу найти дополнительную поддержку и ресурсы?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения поддержки со стороны сообщества и изучите [документацию](https://reference.aspose.com/gis/net/) для получения подробной информации.

### Доступна ли бесплатная пробная версия?
Да, вы можете выбрать Aspose.GIS с хорошей пробной маркой. скачайте ее [здесь](https://releases.aspose.com/).

### Как получить временную лицензию для тестирования?
Для получения временной лицензии [сюда](https://purchase.aspose.com/temporary-license/).

## Дополнительные часто задаваемые вопросы
**Вопрос: Что происходит, если вызвать `GetValueOrDefault` для атрибута, которого не существует?**
A: Метод бросает `ArgumentException`. Всегда проверяйте имя атрибута или сначала используйте `feature.HasAttribute("name")`.

**Вопрос: Можно ли изменить значение по умолчанию после создания слоя?**
О: Да, вы можете изменить `attribute.DefaultValue`, а затем вызвать `layer.UpdateAttribute(attribute)`, чтобы сохранить изменение.

**Вопрос: Поддерживает ли Aspose.GIS массовое обновление меток атрибутов?**
О: Вы можете перебрать объекты коллекции и вызвать SetValue для каждого; для больших наборов данных рекомендуется использовать API FeatureCursor для повышения производительности.

## Заключение
В этом руководстве мы далее **как получить значение атрибута**, как задавать и переопределять значения по умолчанию, а также как **создавать схемы слоев GeoJSON**, соответствующие потребностям вашего приложения. С помощью этих приемов вы сможете создавать надёжные ГИС‑решения, которые правильно обрабатывают отсутствующие или опциональные данные.

---

**Последнее обновление:** 5 января 2026 г.
**Протестировано с:** Aspose.GIS 24.11 для .NET.
**Автор:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}