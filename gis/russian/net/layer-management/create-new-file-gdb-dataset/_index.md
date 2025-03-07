---
title: Создать новый набор данных файла GDB
linktitle: Создать новый набор данных файла GDB
second_title: API Aspose.GIS .NET
description: Изучите Aspose.GIS for .NET, чтобы легко создавать наборы данных ГИС и управлять ими. Загрузите сейчас и наслаждайтесь беспрепятственным геопространственным развитием. #Aspose #ГИС
weight: 10
url: /ru/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать новый набор данных файла GDB

## Введение
В сфере геопространственных разработок Aspose.GIS for .NET выделяется как мощный набор инструментов для управления и манипулирования данными Географической информационной системы (ГИС). Независимо от того, являетесь ли вы опытным разработчиком или только начинаете свой путь в ГИС, это руководство проведет вас через процесс создания нового набора данных файловой базы геоданных (GDB) с использованием Aspose.GIS для .NET.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
-  Aspose.GIS for .NET: убедитесь, что у вас установлена библиотека Aspose.GIS for .NET. Вы можете скачать его с сайта[Страница загрузки Aspose.GIS для .NET](https://releases.aspose.com/gis/net/).
- Среда разработки. Настройте среду разработки с помощью совместимой IDE, например Visual Studio, и получите базовое представление о программировании .NET.
- Каталог документов: замените «Каталог ваших документов» во фрагменте кода на соответствующий путь, по которому вы хотите хранить набор данных GDB.
- Знакомство с C#. В этом руководстве предполагается, что вы знакомы с языком программирования C#.
## Импортировать пространства имен
На первых шагах импортируйте необходимые пространства имен, чтобы использовать функциональность Aspose.GIS в вашем .NET-приложении:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Шаг 1. Создайте новый набор данных файла GDB.
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Выход: 0
    // Продолжите последующие шаги...
}
```
 Пояснение: На этом этапе мы создаем новый набор данных GDB, используя`Dataset.Create` метод. Указываем путь и драйвер (FileGdb) для создания файловой базы геоданных. Вывод консоли отображает начальное количество слоев, которое на данный момент равно нулю.
## Шаг 2. Создайте и заполните Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Пояснение: На этом этапе в наборе данных создается слой с именем «layer_1». Он определяет атрибут с именем «значение» целочисленного типа и заполняет слой десятью объектами, каждый из которых имеет точечную геометрию.
## Шаг 3. Создайте и заполните Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Пояснение: Здесь мы создаем второй слой с именем «слой_2» и добавляем один объект с геометрией линейной строки.
## Шаг 4. Проверьте количество обновленных слоев
```csharp
Console.WriteLine(dataset.LayersCount); // Выход: 2
```
Объяснение: Наконец, мы проверяем количество обновленных слоев после добавления двух слоев. В этом случае выход должен быть 2.
## Заключение
Поздравляем! Вы успешно создали новый набор данных File GDB и заполнили его слоями с помощью Aspose.GIS for .NET. Это руководство дает базовое понимание работы с геопространственными данными в среде .NET.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.GIS for .NET с другими библиотеками ГИС?
Aspose.GIS for .NET — это автономный набор инструментов; однако вы можете интегрировать его с другими библиотеками .NET для улучшения функциональности.
### Вопрос: Существует ли форум сообщества для поддержки Aspose.GIS?
 Да, вы можете найти поддержку и обсуждения на[Форум Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Вопрос: Как я могу получить временную лицензию на Aspose.GIS?
 Посетить[Временная лицензия](https://purchase.aspose.com/temporary-license/) страница с информацией о получении временной лицензии.
### Вопрос: Доступны ли дополнительные примеры и документация?
 Исследовать[Документация Aspose.GIS](https://reference.aspose.com/gis/net/) для получения дополнительных примеров и подробной информации.
### Вопрос: Где я могу приобрести Aspose.GIS для .NET?
 Вы можете приобрести Aspose.GIS для .NET на сайте[страница покупки](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
