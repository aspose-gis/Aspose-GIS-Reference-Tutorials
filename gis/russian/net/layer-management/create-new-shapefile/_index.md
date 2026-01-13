---
date: 2026-01-13
description: Узнайте, как создать новый shapefile с помощью Aspose.GIS для .NET. Это
  пошаговое руководство показывает, как определить векторный слой, добавить атрибут
  даты и управлять пространственными данными.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Создать новый shapefile
url: /ru/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание нового shapefile

## Введение
Если вы погружаетесь в разработку географических информационных систем (GIS) с .NET, Aspose.GIS — ваше решение. Эта мощная библиотека позволяет разработчикам работать с пространственными данными без проблем, и в этом руководстве мы покажем, как **создать новый shapefile** с помощью Aspose.GIS для .NET. Вы увидите, почему определение векторного слоя и добавление атрибута даты являются важными шагами для надёжных GIS‑проектов.

## Краткие ответы
- **Что обучает этот урок?** Как создать новый shapefile, определить векторный слой и добавить атрибуты (включая поле даты).  
- **Какая библиотека требуется?** Aspose.GIS для .NET.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для обучения; коммерческая лицензия требуется для продакшна.  
- **Какую IDE использовать?** Visual Studio (любая современная версия).  
- **Сколько времени займет реализация?** Около 10‑15 минут для базового примера.

## Требования
Прежде чем приступить к руководству, убедитесь, что у вас есть следующие требования:
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

## Шаг 1: Настройте ваш проект
Начните с создания нового проекта C# в Visual Studio и добавьте библиотеку Aspose.GIS.

## Шаг 2: Определите каталог документов
```csharp
string dataDir = "Your Document Directory";
```
Замените *Your Document Directory* фактическим путём, где вы хотите сохранить ваш новый shapefile.

## Шаг 3: Создайте VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Этот фрагмент кода **определяет векторный слой** и объявляет три атрибута: текстовое поле (`name`), целочисленное поле (`age`) и поле даты‑времени (`dob`). Добавление атрибута даты имеет решающее значение для временного GIS‑анализа.

## Шаг 4: Добавьте объекты
### Случай 1: Устанавливает значения по отдельности
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

### Случай 2: Устанавливает новые значения для всех атрибутов
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
В этом подходе мы заполняем все значения атрибутов одним вызовом, используя массив объектов — удобно, когда атрибутов много.

## Почему это важно
Программное создание shapefile позволяет автоматизировать конвейеры данных, генерировать тестовые наборы данных или интегрировать GIS‑вывод напрямую в веб‑службы. Овладев **созданием shapefile** с помощью Aspose.GIS, вы получаете полный контроль над геометрией объектов, схемой атрибутов и соответствием формату файла.

## Распространённые ошибки и советы
- **Разделители путей:** Используйте `Path.Combine` для кросс‑платформенной совместимости вместо конкатенации строк.  
- **Порядок атрибутов:** Порядок значений в `SetValues` должен соответствовать порядку, в котором вы добавляли атрибуты.  
- **Работа с датой:** Всегда используйте `DateTimeKind.Utc`, если ваши GIS‑данные будут использоваться в разных часовых поясах.

## Заключение
Поздравляем! Вы успешно создали новый shapefile с помощью Aspose.GIS для .NET. Это руководство охватило основы настройки проекта, определения векторного слоя и добавления объектов — включая атрибут даты. По мере дальнейшего изучения обращайтесь к [документации](https://reference.aspose.com/gis/net/) для получения информации о расширенных возможностях и функциях.

## Часто задаваемые вопросы
### Q: Могу ли я использовать Aspose.GIS с другими языками программирования?
Aspose.GIS в основном поддерживает .NET, но также доступны версии для Java.

### Q: Доступна ли бесплатная пробная версия?
Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Q: Где я могу найти поддержку Aspose.GIS?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения поддержки от сообщества и обсуждений.

### Q: Как я могу получить временную лицензию?
Получите временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

### Q: Где я могу приобрести Aspose.GIS для .NET?
Вы можете приобрести библиотеку [здесь](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}