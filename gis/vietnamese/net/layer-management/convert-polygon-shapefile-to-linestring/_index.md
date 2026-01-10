---
date: 2026-01-10
description: Tìm hiểu cách đọc shapefile bằng C# và chuyển đổi shapefile đa giác sang
  linestring bằng Aspose.GIS cho .NET. Nâng cao phát triển GIS của bạn với hướng dẫn
  chi tiết từng bước.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Đọc Shapefile C# – Chuyển đổi Shapefile đa giác sang đường đa điểm
url: /vi/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Shapefile C# – Chuyển Shapefile Đa giác thành Linestring

## Introduction
Nếu bạn đang làm việc với hệ thống thông tin địa lý (GIS) trong .NET, **read shapefile c#** là bước đầu tiên phổ biến trước khi bạn có thể thao tác dữ liệu. Aspose.GIS làm cho quá trình này đơn giản, cho phép bạn chuyển một Shapefile Đa giác thành Linestring chỉ với vài dòng mã. Khả năng này đặc biệt hữu ích khi bạn cần trích xuất các đặc trưng tuyến tính từ các bộ dữ liệu đa giác cho các nhiệm vụ như lập kế hoạch tuyến đường, phân tích mạng, hoặc trực quan hoá dữ liệu.

## Quick Answers
- **Which library helps you read shapefile c#?** Aspose.GIS for .NET  
- **Can you convert a polygon to a line?** Yes – use `LineString` with the polygon’s exterior ring.  
- **Do I need a license for production?** A commercial license is required for production use.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is a trial available?** Absolutely – download a free trial from the Aspose site.

## What is “read shapefile c#”?
Đọc một shapefile trong C# có nghĩa là tải tệp `.shp` vào bộ nhớ để bạn có thể truy vấn, sửa đổi hoặc chuyển đổi các hình học của nó. Aspose.GIS cung cấp một API đơn giản trừu tượng hoá các chi tiết mức thấp và cho phép bạn tập trung vào logic GIS.

## Why convert polygon to line with Aspose.GIS?
- **Preserve topology** – quá trình chuyển đổi giữ nguyên ranh giới ngoài chính xác của mỗi đa giác.  
- **Performance** – thư viện được tối ưu cho các bộ dữ liệu lớn, giúp chuyển đổi hàng loạt nhanh chóng.  
- **Flexibility** – bạn có thể sau này ghi các linestring ra một shapefile khác, GeoJSON, hoặc bất kỳ định dạng nào được hỗ trợ.

## Prerequisites
Trước khi chúng ta bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yếu tố sau:

- **Aspose.GIS Library** – Download and install the Aspose.GIS library from the [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Have a Polygon Shapefile ready for conversion. If you don’t have one, you can find sample data or create your own.  
- **Development Environment** – Set up your .NET development environment with the necessary tools (Visual Studio, .NET SDK, etc.).

## Import Namespaces
Trong mã C# của bạn, cần nhập các namespace của Aspose.GIS để truy cập các lớp và phương thức cần thiết. Add the following namespaces at the beginning of your code file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to convert shapefile from polygon to line?
Dưới đây là hướng dẫn từng bước cho thấy **cách chuyển đổi shapefile** dữ liệu từ một đa giác sang một đường bằng Aspose.GIS.

### Step 1: Set the Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Thay thế `"Your Document Directory"` bằng đường dẫn thực tế nơi shapefile của bạn nằm.

### Step 2: Open the Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Dòng này **mở Shapefile Đa giác nguồn** để bạn có thể đọc các đối tượng của nó.

### Step 3: Create the Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Ở đây chúng ta **tạo một Shapefile Linestring mới** sẽ lưu trữ các hình học đã chuyển đổi.

### Step 4: Iterate Through Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Vòng lặp duyệt qua mỗi đối tượng đa giác trong tệp gốc.

### Step 5: Convert Polygon to Linestring and Write to Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Trong khối này chúng ta **chuyển đổi đa giác thành đường** (`LineString`) và thêm đối tượng mới vào shapefile đích.

## Common Issues and Tips
- **Coordinate System Mismatch** – Đảm bảo cả lớp nguồn và lớp đích đều sử dụng cùng một tham chiếu không gian; nếu không, các đường có thể bị lệch.  
- **Large Files** – Khi xử lý các shapefile rất lớn, hãy cân nhắc truyền luồng các đối tượng thay vì tải toàn bộ vào bộ nhớ cùng một lúc.  
- **Null Geometries** – Kiểm tra các đối tượng có hình học rỗng để tránh ngoại lệ thời gian chạy.

## Frequently Asked Questions

**Q: Is Aspose.GIS compatible with all versions of .NET?**  
A: Yes, Aspose.GIS supports various .NET versions, ensuring compatibility with your development environment.

**Q: Can I use Aspose.GIS for commercial projects?**  
A: Yes, you can. To use Aspose.GIS in commercial projects, consider purchasing a license [here](https://purchase.aspose.com/buy).

**Q: Are there any examples or documentation available?**  
A: Yes, you can find comprehensive documentation and examples on the [documentation page](https://reference.aspose.com/gis/net/).

**Q: Is there a trial version available?**  
A: Yes, you can explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).

**Q: Where can I seek help or support?**  
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for any assistance or support‑related queries.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}