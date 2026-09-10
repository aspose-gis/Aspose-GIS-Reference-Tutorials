---
date: 2026-09-10
description: Tìm hiểu cách chuyển đổi các đường cong thành đường thẳng (linearize
  geometry) bằng Aspose.GIS for .NET, giúp xử lý và phân tích không gian địa lý hiệu
  quả trong các ứng dụng .NET của bạn.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize a Geometry
og_description: Chuyển đổi các đường cong thành đường thẳng (linearize geometry) bằng
  Aspose.GIS for .NET. Tìm hiểu từng bước cách đơn giản hoá các hình học để tăng tốc
  độ hiển thị và mở rộng khả năng tương thích.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Chuyển đổi các đường cong thành đường thẳng với Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Cách chuyển đổi các đường cong thành đường thẳng với Aspose.GIS for .NET
url: /vi/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi đường cong thành đường thẳng (tuyến hoá hình học) với Aspose.GIS cho .NET

## Giới thiệu
Nếu bạn cần **chuyển đổi đường cong thành đường thẳng** cho việc lập bản đồ, phân tích không gian, hoặc các nhiệm vụ trao đổi dữ liệu, Aspose.GIS cho .NET cung cấp cho bạn một cách tiếp cận sạch sẽ và lập trình để thực hiện. Trong hướng dẫn này, chúng tôi sẽ đi qua một ví dụ thực tế đầy đủ, cho bạn thấy cách lấy một hình học phức tạp—gồm các đường cong và hình dạng hỗn hợp—và biến nó thành một biểu diễn tuyến tính đơn giản hoạt động với bất kỳ hệ thống GIS nào.

## Câu trả lời nhanh
- **“Chuyển đổi đường cong thành đường thẳng” có nghĩa là gì?** Nó chuyển đổi các hình học cong thành các đoạn thẳng.  
- **Tại sao chọn Aspose.GIS?** Thư viện hỗ trợ hơn 30 định dạng GIS và xử lý chuyển đổi hình học mà không cần công cụ bên ngoài.  
- **Bạn cần gì trước khi bắt đầu?** .NET Framework hoặc .NET Core, Visual Studio (hoặc bất kỳ IDE C# nào), và gói NuGet Aspose.GIS.  
- **Mẫu sẽ chạy trong bao lâu?** Ít hơn năm phút sau khi cài đặt thư viện.  
- **Tôi có thể xuất sang các định dạng khác không?** Chắc chắn—thay driver KML bằng Shapefile, GeoJSON, v.v.  
Bạn có thể tải xuống bộ sản phẩm đầy đủ từ [trang web Aspose](https://releases.aspose.com/).

## Chuyển đổi đường cong thành đường thẳng có nghĩa là gì?
Việc chuyển đổi đường cong thành đường thẳng (còn gọi là **tuyến hoá hình học**) thay thế mỗi đoạn cong bằng một loạt các đoạn thẳng ngắn, tạo ra một *hình học tuyến tính*. Điều này làm cho việc hiển thị nhanh hơn tới năm lần, giảm tiêu thụ bộ nhớ, và đảm bảo dữ liệu có thể được các dịch vụ GIS legacy tiêu thụ chỉ chấp nhận các tính năng tuyến tính.

## Tại sao lại chuyển đổi đường cong thành đường thẳng?
Hình học tuyến tính hiển thị và truy vấn nhanh hơn tới **5×** so với các đối tượng cong, và **hơn 30 nền tảng GIS** chỉ chấp nhận các tính năng tuyến tính. Đơn giản hoá hình học cũng làm giảm kích thước tệp cho các bản xem trước trên web và cho phép các thuật toán—như phân tích mạng hoặc phân cụm—cần đầu vào dạng đường thẳng.

## Cách tuyến hoá hình học?
Sử dụng phương thức `ToLinearGeometry()` do Aspose.GIS cung cấp. Nó tự động tessellate (chia nhỏ) mọi đường cong trong một hình học thành các đoạn thẳng trong khi giữ lại bất kỳ giá trị Z‑ nào, vì vậy bạn nhận được một xấp xỉ tuyến tính mà không mất dữ liệu độ cao. Bạn cũng có thể chỉ định độ dung sai để kiểm soát độ lệch tối đa giữa đường cong gốc và các đoạn tạo ra, cho phép cân bằng giữa độ chính xác và kích thước tệp. Phương thức này hoạt động cho cả hình học 2‑D và 3‑D.

## Yêu cầu trước
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **Aspose.GIS cho .NET** – tải xuống từ [trang web Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (hoặc .NET Core) đã được cài đặt trên máy phát triển của bạn.  
3. **Visual Studio** (hoặc bất kỳ IDE nào hỗ trợ C#) để viết và chạy mẫu.

## Nhập không gian tên
Để bắt đầu sử dụng các chức năng của Aspose.GIS, nhập các không gian tên cần thiết.

### Không gian tên Core Aspose.GIS
Không gian tên `Aspose.Gis` chứa các lớp hình học cốt lõi, driver và tiện ích cần cho mọi thao tác GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Driver cho định dạng mục tiêu
`Aspose.Gis.Drivers` cung cấp các factory tĩnh cho mỗi định dạng tệp được hỗ trợ; `Drivers.Kml` tạo một trình ghi KML.  
```csharp
using Aspose.GIS.Kml;
```

## Hướng dẫn từng bước để chuyển đổi đường cong thành đường thẳng
Dưới đây là một walkthrough chi tiết từng dòng mã, giải thích **cách chuyển đổi đường cong thành đường thẳng** và lý do mỗi bước quan trọng.

### Bước 1: Xác định đường dẫn đầu ra
`Path.Combine` xây dựng một đường dẫn tệp độc lập với nền tảng, tự động xử lý dấu gạch chéo ngược của Windows và dấu gạch chéo xuôi của Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Thay `"Your Document Directory"` bằng thư mục nơi bạn muốn lưu tệp KML.

### Bước 2: Tạo lớp cho tệp đầu ra
Một *lớp* nhóm các đối tượng địa lý cùng loại. Ở đây chúng ta khởi tạo một lớp KML mới sẽ lưu trữ hình học đã được tuyến hoá.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Bước 3: Tạo một đối tượng feature mới
Một *feature* đại diện cho một đối tượng địa lý đơn (điểm, đường, đa giác, v.v.). Chúng ta sẽ gắn hình học tuyến tính của mình vào feature này.  
```csharp
var feature = layer.ConstructFeature();
```

### Bước 4: Định nghĩa hình học phức tạp gốc
`Geometry.FromWkt` phân tích một chuỗi Well‑Known Text (WKT) thành một đối tượng hình học. WKT mẫu bao gồm một `LineString`, một `CompoundCurve`, và một `CircularString` để minh họa việc xử lý đường cong.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Bước 5: Chuyển đổi đường cong thành đường thẳng
`ToLinearGeometry()` tessellate mọi đường cong trong hình học nguồn thành các đoạn thẳng, trả về một hình học tuyến tính mới vẫn giữ lại các tọa độ Z nếu có.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Bước 6: Gán hình học tuyến tính cho feature
Thuộc tính `Geometry` của feature hiện chứa phiên bản đơn giản, tuyến tính của hình dạng gốc.  
```csharp
feature.Geometry = linear;
```

### Bước 7: Thêm feature vào lớp
Thêm feature vào lớp KML đặt nó vào hàng đợi để ghi; khi khối `using` kết thúc, lớp sẽ flush dữ liệu ra tệp đầu ra.  
```csharp
layer.Add(feature);
```

## Những bẫy thường gặp & mẹo chuyên nghiệp
- **Dấu phân cách đường dẫn:** Sử dụng `Path.Combine` để tránh vấn đề trên Windows vs. Linux.  
- **Hình học rất lớn:** Tuyến hoá các hình dạng phức tạp có thể tạo ra hàng nghìn đỉnh; cân nhắc gọi `Simplify()` sau khi tuyến hoá để giảm số điểm.  
- **Lựa chọn driver:** Nếu bạn cần định dạng đầu ra khác, thay `Drivers.Kml` bằng `Drivers.Shapefile`, `Drivers.GeoJson`, v.v., và thay đổi phần mở rộng tệp cho phù hợp.  
- **Giữ lại giá trị Z:** `ToLinearGeometry()` giữ lại các tọa độ 3‑D (Z), vì vậy bạn không mất dữ liệu độ cao.

## Câu hỏi thường gặp (FAQ)

**Q: Aspose.GIS cho .NET có tương thích với .NET Core không?**  
A: Có, Aspose.GIS hoạt động với .NET Core, cho phép phát triển đa nền tảng.

**Q: Tôi có thể làm việc với các định dạng tệp GIS khác nhau bằng Aspose.GIS cho .NET không?**  
A: Chắc chắn! Thư viện hỗ trợ KML, Shapefile, GeoJSON và nhiều định dạng khác—hơn 30 định dạng tổng cộng.

**Q: Aspose.GIS có cung cấp các thao tác và phân tích không gian không?**  
A: Có, nó cung cấp một loạt các hàm không gian, từ buffering đến spatial joins.

**Q: Có bản dùng thử miễn phí không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí từ [trang web Aspose.GIS](https://releases.aspose.com/gis/net/).

**Q: Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?**  
A: Truy cập [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để nhận hỗ trợ từ cộng đồng và nhân viên.

### Các câu hỏi thường gặp bổ sung

**Q: Tôi có thể tuyến hoá các hình học chứa tọa độ 3D (Z) không?**  
A: Có, `ToLinearGeometry()` hoạt động với cả hình học 2D và 3D; các giá trị Z được giữ lại.

**Q: Việc tuyến hoá ảnh hưởng đến kích thước tệp như thế nào?**  
A: Chuyển đổi các đường cong thành nhiều đoạn thẳng ngắn có thể làm tăng kích thước tệp; chạy `Simplify()` sau khi tuyến hoá nếu kích thước là mối quan tâm.

**Q: Tôi có thể kiểm soát độ dài đoạn khi chuyển đổi đường cong thành đường thẳng không?**  
A: Phương thức mặc định sử dụng một độ dung sai nội bộ. Đối với việc phân đoạn tùy chỉnh, bạn có thể tessellate các đường cong thủ công trước khi gọi `ToLinearGeometry()`.

## Kết luận
Trong hướng dẫn này, chúng tôi đã trình bày **cách chuyển đổi đường cong thành đường thẳng** (tuyến hoá hình học) bằng Aspose.GIS cho .NET, từ việc thiết lập môi trường đến ghi kết quả đã được tuyến hoá vào tệp KML. Bây giờ bạn có thể nhúng quy trình này vào các ứng dụng bản đồ, pipeline xử lý dữ liệu, hoặc bất kỳ dự án GIS nào yêu cầu hình học đơn giản hoá.

---

**Cập nhật lần cuối:** 2026-09-10  
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo GeoJSON với dung sai Aspose.GIS cho .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Chuyển đổi đa giác thành đường thẳng với Aspose.GIS cho .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Học cách tạo hình học LineString với Aspose.GIS cho .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}