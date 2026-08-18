---
date: 2026-06-05
description: Узнайте, как создать line string в ASP.NET и выполнить проверку сетевого
  маршрутизации, обнаруживая соприкасающиеся геометрии с помощью Aspose.GIS для .NET,
  мощной библиотеки для работы с пространственными данными и их анализа.
keywords:
- create line string asp.net
- touching geometries
- Aspose.GIS spatial analysis
linktitle: Как проверить соприкасающиеся геометрии
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  headline: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  type: TechArticle
- description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  name: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  steps:
  - name: '**Visual Studio** (any recent version).'
    text: '**Visual Studio** (any recent version).'
  - name: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
  - name: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
    text: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
  - name: Install Visual Studio if you haven’t already.
    text: Install Visual Studio if you haven’t already.
  - name: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
    text: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
  - name: Apply your license file in code (or use a temporary license for testing).
    text: Apply your license file in code (or use a temporary license for testing).
  type: HowTo
- questions:
  - answer: Yes. It supports .NET Framework, .NET Core, .NET 5+, and .NET 6+, giving
      you flexibility across desktop, web, and cloud projects.
    question: Is Aspose.GIS compatible with all .NET frameworks?
  - answer: Absolutely. You can obtain a free trial from the Aspose website [here](https://purchase.aspose.com/temporary-license/)
      to explore all features, including the `Touches` operation.
    question: Can I try Aspose.GIS before purchasing a license?
  - answer: Visit the official [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to ask questions, share examples, and get help from both the community and Aspose
      engineers.
    question: Where can I find support for Aspose.GIS‑related queries?
  - answer: Aspose releases regular updates that add new format support, performance
      improvements, and bug fixes, ensuring compatibility with the latest .NET releases.
    question: How often are updates released for Aspose.GIS?
  - answer: By confirming that road segments only meet at shared endpoints (touch),
      you can validate that a routing network is correctly connected without unintended
      overlaps.
    question: How does the `Touches` method help with a network routing check?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Создание line string в ASP.NET – Проверка соприкасающихся геометрий с Aspose.GIS
url: /ru/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание линейного объекта ASP.NET – проверка соприкасающихся геометрий с Aspose.GIS

## Введение
When you need to **perform a network routing check** between two spatial objects, the first step is to **create line string ASP.NET** objects that model your road segments. Aspose.GIS for .NET provides a clean, type‑safe API that makes this operation trivial, letting you focus on business logic rather than low‑level geometry math. In this tutorial we’ll walk through creating line strings, adding a point, and using the `Touches` method to verify that geometries only meet at their boundaries – a key requirement for route validation, map overlay verification, and proximity queries.

## Быстрые ответы
- **Что означает «touching»?** Two geometries share at least one boundary point but their interiors do not intersect.  
- **Какой метод проверяет это?** `Geometry.Touches(otherGeometry)`.  
- **Нужна ли лицензия для этой функции?** A trial works for development; a permanent license is required for production.  
- **Поддерживаемые версии .NET?** .NET Framework, .NET Core, .NET 5/6/7 – all covered by Aspose.GIS.  
- **Сколько времени занимает реализация?** About 5‑10 minutes for a basic example.  

## Что такое «Touching» в пространственном анализе?
**Touching** describes a spatial relationship where two geometries meet at their edges without overlapping interiors. This is different from *intersects*, which also includes interior overlap, and is essential when you need to confirm that road segments connect only at junctions.

The `Touches` method returns **true** when the geometries share a boundary point but no interior points, making it ideal for validating network connectivity without unintended crossings.

## Почему стоит использовать Aspose.GIS для пространственного анализа в .NET?
Aspose.GIS supports **30+ input and output formats** (including Shapefile, GeoJSON, KML, and GML) and can process files up to **2 GB** without loading the entire document into memory, thanks to its streaming architecture. The library offers high‑performance geometry operations—`Touches`, `Intersects`, `Contains`, `Distance`—all fully managed in .NET, so you can embed spatial analysis directly into web services, desktop apps, or Azure Functions without external GIS installations.

## Предварительные требования
Before you start, ensure you have:

1. **Visual Studio** (any recent version).  
2. **Aspose.GIS for .NET** – download the latest package from the [official download page](https://releases.aspose.com/gis/net/).  
3. **A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/) or view all releases at [here](https://releases.aspose.com/).  

### Настройка окружения
1. Install Visual Studio if you haven’t already.  
2. Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package Aspose.GIS`).  
3. Apply your license file in code (or use a temporary license for testing).

## Импорт пространств имён
To start using the API, import the required namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Как проверить соприкасающиеся геометрии в Aspose.GIS?
`Touches` is a method that returns true when two geometries share only a boundary point and no interior points.  
Load or create the geometries, then call `Touches` to evaluate the relationship. The method returns a Boolean indicating whether the two shapes only share a boundary point. This single‑line check is sufficient for most routing‑validation scenarios and can be executed in a tight loop for large networks.

## Шаг 1: Создание линейных строк (и точки)
`LineString` is a geometry type representing a series of connected line segments defined by ordered points.  

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*Объяснение*:  
- `geometry1` и `geometry2` share the endpoint `(2, 2)`.  
- `geometry3` is a point located exactly at that shared endpoint.  
- `geometry4` crosses the same area but does **not** share a boundary with `geometry1`.

## Шаг 2: Проверка соприкасающихся отношений
Now we call the `Touches` method to see which pairs are considered touching.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Результат*:  
- The first three checks return **True** because the geometries meet at a single point without interior overlap.  
- The last check returns **False** because the two line strings intersect over a line segment, not just at a boundary point.

## Распространённые проблемы и советы
- **Проблемы точности** – GIS calculations are floating‑point based. If you encounter unexpected `False` results, consider normalizing coordinates or using a tolerance with `Geometry.EqualsExact(other, tolerance)`.  
- **Смешанные типы геометрий** – `Touches` works across points, lines, and polygons, but the semantics differ; always verify the expected relationship for your data model.  
- **Производительность** – For large datasets, batch the checks or use spatial indexes (e.g., R‑tree) provided by Aspose.GIS to avoid O(N²) comparisons.

## Часто задаваемые вопросы

**Q: Is Aspose.GIS compatible with all .NET frameworks?**  
A: Yes. It supports .NET Framework, .NET Core, .NET 5+, and .NET 6+, giving you flexibility across desktop, web, and cloud projects.

**Q: Can I try Aspose.GIS before purchasing a license?**  
A: Absolutely. You can obtain a free trial from the Aspose website [here](https://purchase.aspose.com/temporary-license/) to explore all features, including the `Touches` operation.

**Q: Where can I find support for Aspose.GIS‑related queries?**  
A: Visit the official [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask questions, share examples, and get help from both the community and Aspose engineers.

**Q: How often are updates released for Aspose.GIS?**  
A: Aspose releases regular updates that add new format support, performance improvements, and bug fixes, ensuring compatibility with the latest .NET releases.

**Q: How does the `Touches` method help with a network routing check?**  
A: By confirming that road segments only meet at shared endpoints (touch), you can validate that a routing network is correctly connected without unintended overlaps.

---

**Последнее обновление:** 2026-06-05  
**Тестировано с:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Работа с геопространственными данными с Aspose.GIS для .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Создание полигональной геометрии C# и проверка пересечения с Aspose.GIS для .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Как вычислить длину геометрии в .NET с Aspose.GIS](/gis/net/geometry-analysis/get-geometry-length/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}