---
date: 2026-06-30
description: Узнайте, как создать shapefile с использованием Aspose.GIS for .NET.
  Это пошаговое руководство покажет, как определить векторный слой, добавить атрибут
  даты и эффективно управлять пространственными данными.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Создать новый Shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как создать Shapefile с помощью Aspose.GIS for .NET
url: /ru/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание нового Shapefile

## Введение
Если вы погружаетесь в разработку геоинформационных систем (GIS) с .NET, Aspose.GIS — ваше решение для **создания shapefile** программно. Эта библиотека предоставляет полный контроль над векторными слоями, схемами атрибутов и соответствием формату файлов, позволяя автоматизировать конвейеры данных или генерировать тестовые наборы данных за считанные минуты.

## Быстрые ответы
- **Что рассматривается в этом учебнике?** Как создать новый shapefile, определить векторный слой и добавить атрибуты (включая поле даты).  
- **Какая библиотека требуется?** Aspose.GIS for .NET.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для обучения; для продакшн‑использования требуется коммерческая лицензия.  
- **Какую IDE следует использовать?** Visual Studio (любая современная версия).  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера.

## Как создать shapefile с помощью Aspose.GIS для .NET?
Загрузите библиотеку Aspose.GIS, укажите папку вывода, создайте `VectorLayer`, определите атрибуты и добавьте объекты — весь этот процесс можно реализовать менее чем в 30 строках C#. Библиотека автоматически обрабатывает создание геометрии, типизацию атрибутов и запись файлов, поэтому вам не нужно вручную управлять низкоуровневыми спецификациями Shapefile.

## Предварительные требования
Прежде чем приступить к учебнику, убедитесь, что у вас есть следующие предварительные требования:
- Базовое понимание языка программирования C#.
- Установленная Visual Studio на вашем компьютере.
- Библиотека Aspose.GIS для .NET. Вы можете скачать её [здесь](https://releases.aspose.com/gis/net/).

## Импорт пространств имён
Начните с импорта необходимых пространств имён, чтобы использовать функциональность Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Настройте ваш проект
Начните с создания нового проекта C# в Visual Studio и добавьте библиотеку Aspose.GIS.

## Шаг 2: Определите каталог документов
```csharp
string dataDir = "Your Document Directory";
```
Замените *Your Document Directory* реальным путём, где вы хотите сохранить новый shapefile.

## Шаг 3: Создайте VectorLayer
`VectorLayer` класс представляет отдельный слой shapefile, который хранит геометрию и данные атрибутов.  
На этом шаге мы определяем векторный слой и объявляем три атрибута: текстовое поле (`name`), целочисленное поле (`age`) и поле даты‑времени (`dob`). Добавление атрибута даты имеет решающее значение для **временных GIS shapefile** анализов.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Шаг 4: Добавьте объекты
### Случай 1: Установка значений по отдельности
Метод `SetValues` присваивает значения атрибутов объекту в порядке их определения.  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Здесь мы создаём две точки, задаём каждый атрибут отдельно и добавляем объекты в слой.

### Случай 2: Установка новых значений для всех атрибутов
В качестве альтернативы можно передать все значения атрибутов сразу, используя `SetValues` с массивом объектов.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
В этом подходе мы заполняем все значения атрибутов одним вызовом, используя массив объектов — удобно, когда атрибутов много.

## Почему это важно?
Программное создание shapefile позволяет автоматизировать конвейеры данных, генерировать тестовые наборы данных или встраивать GIS‑вывод непосредственно в веб‑сервисы. Aspose.GIS поддерживает **более 30 векторных и растровых форматов** и может записывать shapefile на сотни страниц без загрузки всего файла в память, обеспечивая как скорость, так и масштабируемость.

## Распространённые ошибки и советы
- **Разделители путей:** Используйте `Path.Combine` для кросс‑платформенной совместимости вместо конкатенации строк.  
- **Порядок атрибутов:** Порядок значений в `SetValues` должен соответствовать порядку, в котором вы добавляли атрибуты.  
- **Работа с датой:** Всегда используйте `DateTimeKind.Utc`, если ваши GIS‑данные будут передаваться между часовыми поясами.

## Заключение
Поздравляем! Вы успешно создали новый shapefile с помощью Aspose.GIS для .NET. Этот учебник охватил основы настройки проекта, определения векторного слоя и добавления объектов — включая атрибут даты. По мере дальнейшего изучения обращайтесь к [документации](https://reference.aspose.com/gis/net/) для получения информации о расширенных возможностях и функциях.

## Часто задаваемые вопросы
**Q: Можно ли использовать Aspose.GIS с другими языками программирования?**  
A: Aspose.GIS в основном поддерживает .NET, но также доступны версии для Java.  

**Q: Есть ли бесплатная пробная версия?**  
A: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).  

**Q: Где можно найти поддержку Aspose.GIS?**  
A: Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения поддержки от сообщества и обсуждений.  

**Q: Как получить временную лицензию?**  
A: Получите временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).  

**Q: Где можно приобрести Aspose.GIS для .NET?**  
A: Вы можете купить библиотеку [здесь](https://purchase.aspose.com/buy).  

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные учебники

- [Получить атрибуты слоя – Получить информацию об атрибутах слоя с помощью Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Создать векторный слой и задать систему пространственной привязки слоя](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Создать векторный слой в File GDB – учебник Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}