---
date: 2026-05-31
description: Узнайте, как создать GeoJSON, настроить параметры GeoJSON и добавить
  объект в слой с помощью Aspose.GIS для .NET. Следуйте этому пошаговому руководству.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Установить допуск линейризации
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как создать GeoJSON с допуском в Aspose.GIS для .NET
url: /ru/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать GeoJSON с допуском в Aspose.GIS для .NET

## Введение
Если вы хотите **узнать, как создавать GeoJSON** файлы, контролировать точность кривых и экспортировать результат как готовый к использованию документ, Aspose.GIS для .NET делает это простым. В этом руководстве вы узнаете, как настроить параметры GeoJSON, установить допуск линейризации и **add feature to layer** objects, сохраняя код чистым и готовым к продакшену.

## Быстрые ответы
- **Что означает “create vector layer”?** Он создает новый векторный набор данных GIS (например, файл GeoJSON), который может хранить геометрии и атрибуты.  
- **Как установить допуск линейризации?** Установите свойство `LinearizationTolerance` у экземпляра `GeoJsonOptions` перед созданием слоя.  
- **Можно ли экспортировать файл GeoJSON напрямую?** Да — используйте `VectorLayer.Create` с драйвером `Drivers.GeoJson` и настроенными параметрами.  
- **Нужна ли лицензия?** Действительная лицензия Aspose.GIS открывает все функции; временный ключ оценки работает для тестирования.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое “create vector layer”?
Создание векторного слоя означает инициализацию нового GIS‑контейнера (например, файла GeoJSON), который может хранить точки, линии, полигоны и связанные атрибутные данные. Этот слой становится целью для любой создаваемой вами геометрии и прикрепляемых атрибутов.

## Почему необходимо настраивать параметры GeoJSON?
Настройка параметров GeoJSON — особенно **linearization tolerance** — гарантирует, что изогнутые геометрии (например, `CircularString`) будут аппроксимированы с точностью, соответствующей требованиям вашего приложения. Правильная настройка уменьшает размер файла, сохраняя визуальное качество, что критично, когда GeoJSON используется в веб‑картах или инструментах пространственного анализа.

## Предварительные требования
1. **Visual Studio** (любая современная версия).  
2. **Лицензия Aspose.GIS** (или временный ключ оценки).  
3. **Библиотека Aspose.GIS for .NET**, подключенная к вашему проекту.  
4. Базовое знакомство с **C#**.

## Импорт пространств имён
Сначала импортируйте необходимые пространства имён, чтобы компилятор знал, где находятся классы GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Пошаговое руководство

### Шаг 1: Настройка параметров GeoJSON (как установить допуск)
`GeoJsonOptions` определяет параметры сериализации, используемые при записи файлов GeoJSON.  
`GeoJsonOptions` описывает, как Aspose.GIS сериализует GeoJSON, включая допуск линейризации, точность координат и другие параметры вывода.  
Мы создадим объект `GeoJsonOptions` и укажем Aspose.GIS, насколько близкой должна быть линейризованная геометрия к исходной кривой.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Шаг 2: Определение пути вывода (как экспортировать GeoJSON)
Укажите полный путь к файлу, где будет сохранён полученный GeoJSON. Убедитесь, что папка существует и приложение имеет права записи.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Шаг 3: **Create Vector Layer** с настроенными параметрами
`VectorLayer` представляет GIS‑контейнер, способный читать и записывать пространственные данные.  
`Drivers.GeoJson` — идентификатор драйвера для записи файлов в формате GeoJSON.  
Использование `VectorLayer.Create` совместно с драйвером `Drivers.GeoJson` и ранее настроенными `GeoJsonOptions` создаёт новый файл GeoJSON, готовый к вставке объектов.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Шаг 4: Создание геометрии (например, circular string)
`CircularString` — это изогнутая линейная геометрия, которую Aspose.GIS может линейризовать в соответствии с установленным допуском. Вы можете заменить её любой допустимой WKT‑репрезентацией, такой как `POINT`, `LINESTRING` или `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Шаг 5: **Add Feature to Layer** и сохранить
`Feature` — объект, связывающий геометрию с атрибутными данными. После создания экземпляра `Feature` назначьте геометрию, при необходимости добавьте значения атрибутов и вызовите `layer.Add(feature)`, чтобы сохранить её. Когда блок `using` завершается, слой автоматически записывается в файл, указанный в `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Когда блок `using` завершается, слой автоматически записывается в файл, указанный в `path`, предоставляя вам готовый к использованию файл GeoJSON.

## Распространённые проблемы и советы
- **Неправильный путь** — проверьте, что каталог существует и у вас есть права записи.  
- **Слишком низкий допуск** — установка `LinearizationTolerance` в очень маленькое значение может резко увеличить размер файла; обычно допуск 0.001 обеспечивает баланс между точностью и размером.  
- **Ошибки лицензии** — если появляются предупреждения о лицензировании, убедитесь, что файл лицензии загружен до любых вызовов Aspose.GIS.  
- **Примечание о производительности** — Aspose.GIS поддерживает обработку файлов до 2 ГБ без загрузки всего документа в память благодаря потоковой архитектуре.

## Часто задаваемые вопросы

**В: Совместим ли Aspose.GIS для .NET с другими .NET‑фреймворками?**  
О: Да, работает с .NET Framework 4.5+, .NET Core 3.1+ и .NET 5/6/7.

**В: Можно ли использовать Aspose.GIS в коммерческих проектах?**  
О: Абсолютно. Коммерческая лицензия снимает все ограничения оценки и предоставляет полную техническую поддержку.

**В: Поддерживает ли Aspose.GIS другие GIS‑форматы, кроме GeoJSON?**  
О: Да, поддерживает более 30 форматов — включая Shapefile, KML, GML и CSV — позволяя бесшовно конвертировать их между собой.

**В: Доступна ли пробная версия?**  
О: Вы можете скачать бесплатную 30‑дневную пробную версию с сайта Aspose; она включает все функции.

**В: Где можно получить поддержку?**  
О: Используйте форумы Aspose, специальный портал поддержки или ссылку «Contact Support» в панели управления продуктом.

## Заключение
Следуя этим шагам, вы теперь знаете **как создавать GeoJSON**, настраивать допуск линейризации и **add feature to layer** для бесшовного экспорта GeoJSON. Исследуйте дополнительные типы геометрий, работу с атрибутами и сценарии пакетной обработки, чтобы полностью использовать возможности Aspose.GIS в ваших .NET GIS‑проектах.

---

**Последнее обновление:** 2026-05-31  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как конвертировать GeoJSON – Aspose.GIS для .NET](/gis/net/geo-data-conversion/)
- [Создать Vector Layer, ограничить точность с Aspose.GIS для .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Создать Vector Layer в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}