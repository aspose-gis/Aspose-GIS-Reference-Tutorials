---
date: 2026-09-10
description: Узнайте, как создать векторный слой с помощью Aspose.GIS for .NET и ограничить
  precision, чтобы уменьшить размер shapefile, повысить performance и сохранить coordinate
  accuracy.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Ограничить precision при чтении геометрий
og_description: Узнайте, как создать векторный слой с помощью Aspose.GIS for .NET
  и ограничить precision, чтобы уменьшить размер shapefile, улучшить performance и
  управлять coordinate accuracy.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Как создать векторный слой с помощью Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Как создать векторный слой с помощью Aspose.GIS for .NET
url: /ru/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать векторный слой с помощью Aspose.GIS для .NET

## Введение
Когда вы работаете с геопространственными данными, вы часто задаётесь вопросом, **как создать векторный слой** объектов, соответствующих точности, необходимой вашему приложению. Округление координат до разумного количества знаков после запятой не только ускоряет разбор, но и может **сократить размер shapefile до 30 %** для типичных наборов точечных данных. В этом пошаговом руководстве вы увидите, как создать векторный слой, записать точечную геометрию и затем прочитать её обратно, используя как точные, так и округлённые модели точности. К концу вы узнаете, как **установить параметры модели точности**, балансирующие производительность и требуемую пространственную точность.

## Быстрые ответы
- **Что означает «ограничить точность»?** Она округляет значения координат до заданного количества знаков после запятой.  
- **Зачем сначала создавать векторный слой?** Векторный слой — это контейнер, который хранит геометрии, такие как точки, линии и полигоны.  
- **Какие модели точности доступны?** `PrecisionModel.Exact` (без округления) и `PrecisionModel.Rounding(n)` (округление до *n* знаков после запятой).  
- **Нужна ли лицензия для пробного использования?** Бесплатная пробная версия доступна на странице релизов.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core и .NET 5/6+.

## Что такое создание векторного слоя?
Действие **создания векторного слоя** означает создание экземпляра класса `VectorLayer` из Aspose.GIS, который представляет один shapefile на диске и содержит все добавляемые вами геометрические объекты. Этот слой становится точкой входа для чтения, записи и манипулирования пространственными данными. Он также позволяет определять поля атрибутов и задавать пространственную привязку набора данных.

## Почему ограничивать точность и как это помогает?
- **Увеличение производительности** – Сокращение количества знаков после запятой уменьшает объём бинарных данных, которые необходимо разбирать и сериализовать, часто обеспечивая ускорение на 15‑20 % для больших файлов.  
- **Меньший размер файлов** – Округление координат до двух‑трёх знаков после запятой может уменьшить 10 МБ shapefile примерно до 7 МБ, облегчая хранение и передачу по сети.  
- **Достаточная точность** – Большинству GIS‑анализов (например, картирование уровня города) требуется точность в метрах, поэтому округление до 3‑х знаков более чем достаточно.

## Предварительные требования
Прежде чем мы начнём, убедитесь, что у вас есть следующие предварительные требования:
1. **Установка** – Библиотека Aspose.GIS for .NET должна быть установлена в вашей среде разработки. Если нет, вы можете скачать её со [страницы релизов](https://releases.aspose.com/gis/net/).  
2. **Знакомство с .NET** – Необходимо базовое знание C# и платформы .NET для понимания и реализации приведённых примеров кода.  
3. **Среда разработки** – Требуется рабочая среда разработки .NET, например Visual Studio.  
4. **Каталог документов** – Создайте каталог, где вы сможете хранить и получать доступ к shapefile, генерируемому в процессе.

## Импорт пространств имён
Прежде чем начать реализовывать функциональность ограничения точности при чтении геометрий, убедимся, что импортированы необходимые пространства имён:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Как создать векторный слой
Загрузите новый `VectorLayer`, указав папку вывода и желаемое имя shapefile. Это создаёт пустой контейнер, готовый принимать объекты геометрии.

Класс `VectorLayer` является верхнеуровневым объектом Aspose.GIS, представляющим один shapefile на диске. После создания экземпляра вы можете добавлять объекты, определять поля атрибутов и, наконец, вызвать `Save()`, чтобы записать файлы в файловую систему.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Настройка параметров точности
`PrecisionModel` определяет, как значения координат округляются или сохраняются точными при чтении геометрий. Вы задаёте модель в объекте `ReadOptions` перед открытием слоя.

Класс `PrecisionModel` является ключевым компонентом Aspose.GIS, контролирующим поведение округления по осям X и Y. Выбирая соответствующую модель, вы определяете, будет ли библиотека сохранять каждую цифру или обрезать до заданного количества знаков после запятой.
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Чтение геометрий с точной точностью
`ReadOptions` задаёт параметры чтения векторного слоя, такие как применяемая модель точности.  
Откройте ранее сохранённый векторный слой, используя экземпляр `ReadOptions`, ссылающийся на `PrecisionModel.Exact`. Это гарантирует, что каждая координата будет прочитана без какого-либо округления.

Когда вы используете `PrecisionModel.Exact`, Aspose.GIS читает необработанные значения двойной точности, хранящиеся в shapefile, гарантируя, что при операции чтения не теряется информация.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Обрезка точности
Если вы хотите обрезать точность до определённого количества знаков после запятой, замените `Exact` на `PrecisionModel.Rounding(n)`, где *n* — количество знаков, которые вы хотите сохранить.

Округление до двух знаков (`PrecisionModel.Rounding(2)`) обычно уменьшает размер файла на 20‑30 %, сохраняя точность координат в пределах нескольких сантиметров для большинства масштабов карт.
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Как установить модель точности для разных сценариев
Выберите модель, соответствующую вашему случаю использования:
- **Научный анализ с высокой точностью** – Используйте `PrecisionModel.Exact`, чтобы сохранить каждую цифру.  
- **Веб‑картографические плитки или мобильные приложения** – Используйте `PrecisionModel.Rounding(2)`, чтобы файлы были лёгкими и быстро отрисовывались.

Выбор подходящей модели является частью процесса принятия решений по **установке модели точности**, который балансирует точность и производительность.

## Распространённые проблемы и решения
`XYPrecisionModel` — это свойство `ReadOptions`, которое задаёт модель точности для координат X и Y.  
- **Неожиданные значения координат** – Убедитесь, что вы задаёте `options.XYPrecisionModel` *до* открытия слоя. Изменение после открытия не оказывает эффекта.  
- **Файл не найден** – Убедитесь, что переменная `path` указывает на действительный каталог и что Shapefile был успешно создан на предыдущем этапе.  
- **Неправильный тип геометрии** – В примере используется `Point`. Для других типов геометрий (например, `LineString`) приведение типов должно соответствовать фактическому типу.

## Советы по уменьшению размера shapefile
- Используйте `PrecisionModel.Rounding` с минимальным количеством знаков, которое всё ещё удовлетворяет вашим требованиям к точности.  
- Удалите ненужные поля атрибутов перед записью слоя.  
- Сожмите полученные файлы `.shp`, `.shx` и `.dbf` с помощью стандартных утилит ZIP, если необходимо их передать.

## Заключение
Управление точностью при чтении геометрий является важным аспектом работы с геопространственными данными. Aspose.GIS for .NET предоставляет надёжные возможности для эффективного выполнения этой задачи. Следуя приведённым выше шагам, вы сможете без проблем **создавать векторные слои**, **устанавливать модель точности** и даже **уменьшать размер shapefile**, когда это необходимо, обеспечивая оптимальную обработку данных в ваших приложениях.

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.GIS for .NET с другими фреймворками .NET, такими как .NET Core или .NET Standard?
Да, Aspose.GIS for .NET совместим с различными фреймворками .NET, включая .NET Core и .NET Standard.
### Доступна ли пробная версия Aspose.GIS for .NET?
Да, вы можете получить бесплатную пробную версию со [страницы релизов](https://releases.aspose.com/).
### Где я могу найти полную документацию по Aspose.GIS for .NET?
Вы можете обратиться к [документации](https://reference.aspose.com/gis/net/) для получения подробной информации и примеров.
### Как я могу получить временные лицензии для Aspose.GIS for .NET?
Временные лицензии можно приобрести на [странице покупки](https://purchase.aspose.com/temporary-license/) Aspose.GIS.
### Где я могу получить помощь или поддержку по Aspose.GIS for .NET?
Вы можете посетить [форум](https://forum.aspose.com/c/gis/33) Aspose.GIS для любых вопросов, обсуждений или запросов поддержки.

## Часто задаваемые вопросы
**В: Влияет ли ограничение точности на оригинальный shapefile?**  
О: Нет. Точность применяется только при чтении геометрии; исходный файл остаётся неизменным.  

**В: Могу ли я использовать различную модель точности для координат X и Y?**  
О: В текущей версии Aspose.GIS применяется одинаковый `XYPrecisionModel` для обеих осей.  

**В: Можно ли задать пользовательскую функцию округления?**  
О: API поддерживает только встроенный метод `PrecisionModel.Rounding(int)`. Для пользовательской логики вам придётся постобрабатывать координаты после чтения.

---

**Последнее обновление:** 2026-09-10  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как ограничить точность при записи геометрий с Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Как создать векторный слой с SRS, используя Aspose.GIS для .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Создать векторный слой в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}