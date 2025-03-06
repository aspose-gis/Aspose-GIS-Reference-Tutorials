---
title: Создать новый шейп-файл
linktitle: Создать новый шейп-файл
second_title: API Aspose.GIS .NET
description: Узнайте, как создать новый шейп-файл с помощью Aspose.GIS для .NET. Следуйте нашему пошаговому руководству и раскройте возможности манипулирования пространственными данными.
weight: 12
url: /ru/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать новый шейп-файл

## Введение
Если вы углубляетесь в разработку географических информационных систем (ГИС) с помощью .NET, Aspose.GIS — ваше идеальное решение. Эта мощная библиотека позволяет разработчикам беспрепятственно работать с пространственными данными, и в этом руководстве мы проведем вас через процесс создания нового шейп-файла с помощью Aspose.GIS для .NET.
## Предварительные условия
Прежде чем мы перейдем к руководству, убедитесь, что у вас есть следующие предварительные условия:
- Базовое понимание языка программирования C#.
- Visual Studio установлена на вашем компьютере.
-  Библиотека Aspose.GIS для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/gis/net/).
## Импортировать пространства имен
Начните с импорта необходимых пространств имен, чтобы использовать функциональность Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Шаг 1. Настройте свой проект
Начните с создания нового проекта C# в Visual Studio и включите в него библиотеку Aspose.GIS.
## Шаг 2. Определите каталог документов
```csharp
string dataDir = "Your Document Directory";
```
Замените «Каталог вашего документа» фактическим путем, по которому вы хотите сохранить новый шейп-файл.
## Шаг 3. Создайте векторный слой
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //добавляйте атрибуты перед добавлением объектов
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Этот сегмент кода настраивает векторный слой и определяет атрибуты для ваших объектов.
## Шаг 4. Добавьте функции
### Случай 1. Устанавливает значения индивидуально.
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
### Случай 2: Устанавливает новые значения для всех атрибутов
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Заключение
 Поздравляем! Вы успешно создали новый шейп-файл с помощью Aspose.GIS for .NET. В этом руководстве рассмотрены основы настройки проекта, определения атрибутов и добавления функций. По мере дальнейшего изучения см.[документация](https://reference.aspose.com/gis/net/) для расширенных функций и возможностей.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.GIS с другими языками программирования?
Aspose.GIS в основном поддерживает .NET, но существуют версии и для Java.
### Вопрос: Доступна ли бесплатная пробная версия?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу найти поддержку Aspose.GIS?
 Посетить[Форум Aspose.GIS](https://forum.aspose.com/c/gis/33) за поддержку сообщества и обсуждения.
### Вопрос: Как я могу получить временную лицензию?
 Получите временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу приобрести Aspose.GIS для .NET?
 Вы можете купить библиотеку[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
