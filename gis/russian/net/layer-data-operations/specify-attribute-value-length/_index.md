---
date: 2026-05-16
description: Пример векторного слоя, показывающий, как установить ширину поля, задать
  ширину атрибута и добавить длину атрибута в Aspose.GIS для .NET – полное пошаговое
  руководство.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Как установить ширину поля
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Пример векторного слоя – Как установить ширину поля в Aspose.GIS для .NET
url: /ru/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример векторного слоя – Как задать ширину поля в Aspose.GIS для .NET

В этом **примерe векторного слоя** вы узнаете, как задать ширину поля для атрибута при создании Shapefile с помощью Aspose.GIS для .NET. Мы пройдем каждый шаг, от импорта пространств имён до добавления объекта, и объясним, почему контроль длины атрибутов важен для целостности данных и совместимости с другими GIS‑инструментами.

## Быстрые ответы
- **Какова основная цель данного руководства?** Показать, как задать ширину поля для атрибута в shapefile с использованием Aspose.GIS для .NET.  
- **Какой класс определяет ширину поля?** `FeatureAttribute.Width`.  
- **Нужна ли лицензия для выполнения кода?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Какой формат файла используется в примере?** ESRI Shapefile (`.shp`).  
- **Можно ли изменить ширину после создания слоя?** Нет — ширина должна быть определена до добавления объектов.

## Что такое ширина поля и почему это важно?
Ширина поля (также называемая длиной атрибута) — это максимальное количество символов, которое строковое поле может хранить в компоненте DBF Shapefile. Установка правильной ширины предотвращает бесшумное усечение, гарантирует, что другие GIS‑приложения читают данные точно так, как вы их ввели, и делает размер файла предсказуемым — каждый дополнительный символ добавляет один байт на запись.

## Предварительные требования
- **Библиотека Aspose.GIS для .NET** — загрузить по [ссылке для скачивания](https://releases.aspose.com/gis/net/).  
- **Среда разработки** — Visual Studio 2022, Visual Studio Code или любой IDE, поддерживающий .NET 6+.  
- **Права записи** — папка на диске, куда будет сохранён сгенерированный shapefile.

## Почему использовать пример векторного слоя с заданной шириной?
Aspose.GIS поддерживает **более 30 форматов GIS‑файлов**, включая Shapefile, GeoJSON, KML и GML. Когда вы явно задаёте ширину поля, вы избегаете ограничения по умолчанию в 255 символов, которое может ненужно раздувать файл `.dbf` до 255 × количествоЗаписей байт. В больших наборах данных это приводит к заметной экономии места.

## Как задать ширину поля для атрибута?
В этом разделе мы загружаем или создаём `VectorLayer`, указывающий на целевой файл `.shp`, определяем строковый атрибут с точной шириной, а затем добавляем объекты — всё в нескольких лаконичных инструкциях. `VectorLayer` представляет векторный набор данных, такой как Shapefile, и предоставляет доступ к его геометрии и таблице атрибутов. Ниже приведён прямой, практический рецепт, которому можно следовать шаг за шагом:

Загрузите или создайте `VectorLayer`, указывающий на целевой файл `.shp`, объявите строковый атрибут с именем **wide** и `Width = 120`, затем добавьте объект, значение которого укладывается в ограничение в 120 символов. Aspose.GIS автоматически усечёт любую более длинную строку до заданной ширины, сохраняя согласованность данных без выброса исключений.

### Импорт пространств имён
`FeatureAttribute`, `VectorLayer` и связанные типы находятся в пространстве имён `Aspose.Gis`. Импортируйте их в начале вашего файла:

Пространство имён `Aspose.Gis` предоставляет основные GIS‑объекты, с которыми вы будете работать, такие как `VectorLayer`, `Feature` и `FeatureAttribute`. Импортируя его, вы делаете классы доступными без необходимости указывать полные имена.

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Создание VectorLayer
Класс `VectorLayer` представляет векторный источник данных (например, Shapefile). Это контейнер, который хранит объекты и их атрибуты.

Класс `VectorLayer` — это представление Aspose.GIS векторного набора данных, управляющего геометрией и таблицами атрибутов в памяти. Создайте экземпляр, указывающий на новый или существующий файл `.shp`.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Добавление атрибута с конкретной длиной
Определите строковый атрибут с именем **wide** и задайте его свойство `Width` равным 120 символам. Это основной шаг **примера векторного слоя**.

Объект `FeatureAttribute` описывает колонку в таблице атрибутов; установка `Width = 120` указывает записывающему Shapefile выделить ровно 120 байт для каждой записи этого поля.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Совет:** Свойство `Width` применяется только к строковым атрибутам. Для числовых, датовых или логических полей `Width` игнорируется, так как их размер фиксирован типом данных.

### Создание и добавление объекта
Создайте `Feature`, присвойте значение, которое укладывается в ограничение в 120 символов, и добавьте его в слой. Если строка превышает лимит, Aspose.GIS бесшумно усечёт её до заданной ширины, сохраняя целостность данных.

Класс `Feature` инкапсулирует геометрию и значения атрибутов; после установки атрибута вызов `layer.Add(feature)` записывает запись в Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Если попытаться присвоить более длинную строку, Aspose.GIS усечёт её до заданной ширины, сохраняя целостность данных.

## Распространённые ошибки и устранение неполадок
- **Забыли установить `Width` перед добавлением атрибута?** Ширина по умолчанию — 255 символов; изменение позже не влияет на уже созданные поля. Всегда задавайте ширину сначала.  
- **Используете тип данных, отличный от строки?** `Width` игнорируется для числовых или датовых полей; убедитесь, что `AttributeDataType` атрибута установлен в `String`.  
- **Ошибка «Поле не найдено»?** Имена атрибутов чувствительны к регистру. Убедитесь, что имя, используемое в `SetValue`, точно соответствует имени, определённому в схеме.  
- **Неожиданное увеличение размера файла?** Большие ширины линейно увеличивают размер `.dbf`. Для 10 000 записей увеличение ширины с 50 до 120 добавит примерно 700 KB.

## Часто задаваемые вопросы
**В: Как получить временную лицензию для Aspose.GIS для .NET?**  
О: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где можно найти поддержку сообщества для Aspose.GIS для .NET?**  
О: Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для помощи от коллег и официальных ответов.

**В: Доступна ли бесплатная пробная версия Aspose.GIS для .NET?**  
О: Да, ознакомьтесь с [бесплатной пробной версией](https://releases.aspose.com/), чтобы испытать полный набор функций без оплаты.

**В: Как приобрести лицензию для Aspose.GIS для .NET?**  
О: Приобретите лицензию [здесь](https://purchase.aspose.com/buy).

**В: Где можно найти документацию по Aspose.GIS для .NET?**  
О: Обратитесь к [документации](https://reference.aspose.com/gis/net/) для подробных сведений об API.

**В: Можно ли изменить ширину поля после создания слоя?**  
О: Нет. Ширина поля должна быть определена до добавления атрибута; чтобы изменить её, необходимо пересоздать слой с новой схемой.

**В: Влияет ли установка большей ширины на размер файла?**  
О: Shapefile хранит строковые поля фиксированной длины, поэтому увеличение ширины напрямую увеличивает размер файла `.dbf` пропорционально количеству записей.

## Заключение
Этот **пример векторного слоя** продемонстрировал, как задать ширину поля для атрибута в Shapefile с помощью Aspose.GIS для .NET, и показал, как эффективно добавить атрибут с конкретной длиной. Контролируя ширину атрибутов, вы избегаете усечения данных, поддерживаете оптимальный размер файлов и обеспечиваете беспрепятственную совместимость с другими GIS‑платформами. Экспериментируйте с разными ширинами, изучайте [документацию](https://reference.aspose.com/gis/net/), и раскрывайте весь потенциал геопространственной разработки с Aspose.GIS.

---

**Последнее обновление:** 2026-05-16  
**Проверено с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Получить атрибуты слоя – Получить информацию об атрибутах слоя с Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Как получить значение атрибута (по умолчанию) с Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Создание векторного слоя в File GDB – Руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}