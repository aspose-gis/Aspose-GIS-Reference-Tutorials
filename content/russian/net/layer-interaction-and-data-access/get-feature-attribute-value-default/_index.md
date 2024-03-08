---
title: Получить значение атрибута объекта (по умолчанию)
linktitle: Получить значение атрибута объекта (по умолчанию)
second_title: API Aspose.GIS .NET
description: Раскройте возможности Aspose.GIS для .NET! С помощью этого пошагового руководства можно легко получать значения атрибутов объектов и манипулировать ими. Загрузите пробную версию прямо сейчас!
type: docs
weight: 14
url: /ru/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## Введение
Добро пожаловать в мир Aspose.GIS для .NET! В этом подробном руководстве мы углубимся в тонкости получения значений атрибутов объектов с использованием мощных возможностей Aspose.GIS. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, это руководство предоставит вам пошаговое руководство, позволяющее использовать весь потенциал этого замечательного инструмента.
## Предварительные условия
Прежде чем мы приступим к этому приключению по программированию, убедитесь, что у вас есть следующие предварительные условия:
- Знание C# и .NET framework.
-  Установлен Aspose.GIS для .NET. Если нет, загрузите его с[здесь](https://releases.aspose.com/gis/net/).
- Редактор кода, например Visual Studio, для удобной работы.
## Импортировать пространства имен
Обязательно включите в свой проект C# необходимые пространства имен:
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
Теперь давайте разобьем каждый пример на ряд простых для выполнения шагов.
## Получить значение атрибута объекта (по умолчанию)
### Шаг 1: Настройте среду
Начните с определения пути к каталогу ваших документов:
```csharp
string dataDir = "Your Document Directory";
```
### Шаг 2. Создайте слой GeoJson
Создайте слой GeoJson и определите атрибут со значениями по умолчанию:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Шаг 3: Создайте объект
Создайте объект, используя определенный атрибут:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Шаг 4: Получить значения
Получение значений атрибутов с помощью различных сценариев:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // значение == ноль
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // значение == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // значение == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Установка значений по умолчанию
### Шаг 1. Создайте еще один слой GeoJson
Повторите процесс с другим слоем GeoJson и двойным атрибутом:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Шаг 2. Создайте объект (снова)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Шаг 3: Получение и установка значений
Получите и установите значения атрибутов, демонстрируя значения по умолчанию:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // значение == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // значение == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // значение == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Поздравляем! Вы успешно использовали возможности Aspose.GIS for .NET для получения значений атрибутов объектов и управления ими.
## Заключение
В этом уроке мы изучили нюансы получения значений атрибутов объектов с помощью Aspose.GIS для .NET. Благодаря интуитивно понятному API и надежным возможностям Aspose.GIS открывает мир возможностей для разработки ГИС в средах .NET.
## Часто задаваемые вопросы
### Совместим ли Aspose.GIS с .NET Core?
Да, Aspose.GIS полностью совместим с .NET Core, обеспечивая кроссплатформенную поддержку.
### Могу ли я использовать Aspose.GIS для коммерческих проектов?
Абсолютно! Aspose.GIS поставляется с коммерческой лицензией, которая позволяет использовать его в коммерческих приложениях без каких-либо ограничений.
### Где я могу найти дополнительную поддержку и ресурсы?
 Посетить[Форум Aspose.GIS](https://forum.aspose.com/c/gis/33) за поддержку сообщества и изучить[документация](https://reference.aspose.com/gis/net/) для более подробной информации.
### Доступна ли бесплатная пробная версия?
 Да, вы можете изучить Aspose.GIS, воспользовавшись бесплатной пробной версией. Загрузить[здесь](https://releases.aspose.com/).
### Как получить временную лицензию для целей тестирования?
 Для получения временных лицензий посетите[здесь](https://purchase.aspose.com/temporary-license/).