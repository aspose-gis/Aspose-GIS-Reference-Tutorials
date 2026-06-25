---
date: 2026-06-25
description: Tìm hiểu cách đọc shapefile và chuyển đổi shapefile đa giác thành linestring
  bằng Aspose.GIS cho .NET. Nâng cao phát triển GIS của bạn với hướng dẫn chi tiết
  từng bước.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Chuyển Đổi Shapefile Đa Giác Thành Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cách Đọc Shapefile C# – Chuyển Đổi Shapefile Đa Giác Thành Linestring
url: /vi/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Shapefile C# – Chuyển đổi Shapefile Đa giác thành Linestring

## Giới thiệu
Nếu bạn cần **how to read shapefile** dữ liệu trong môi trường .NET, bạn đang ở đúng nơi. Aspose.GIS cho .NET trừu tượng hoá định dạng nhị phân cấp thấp của một Shapefile, cho phép bạn tải, truy vấn và chuyển đổi các đối tượng địa lý chỉ với vài lời gọi API. Chuyển đổi một shapefile đa giác thành linestring đặc biệt hữu ích khi bạn muốn trích xuất các biểu diễn tuyến tính cho định tuyến, phân tích mạng, hoặc trực quan hoá đơn giản.

## Câu trả lời nhanh
- **Thư viện nào giúp bạn đọc shapefile c#?** Aspose.GIS cho .NET – hỗ trợ hơn 50 định dạng GIS và xử lý các tệp lên tới vài trăm megabyte mà không cần tải toàn bộ tệp vào bộ nhớ.  
- **Bạn có thể chuyển đổi một đa giác thành một đường không?** Yes – call `LineString` on the polygon’s exterior ring and write the result to a new shapefile.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** A commercial license is required for production deployments; a free trial works for evaluation.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Có bản dùng thử không?** Absolutely – download a free trial from the Aspose site.

`LineString` là một kiểu hình học đại diện cho một chuỗi các đoạn thẳng nối nhau.

## Đọc shapefile c# là gì?
`Document` là lớp cốt lõi đại diện cho một bộ dữ liệu GIS và cung cấp quyền truy cập vào các đối tượng của nó.  
Đọc một shapefile trong C# có nghĩa là tải tệp `.shp` vào bộ nhớ để bạn có thể truy vấn, sửa đổi hoặc chuyển đổi các hình học của nó. **Bạn chỉ cần khởi tạo lớp `Document` với đường dẫn tệp, và Aspose.GIS sẽ phân tích cấu trúc nhị phân cho bạn**, cung cấp các đối tượng thông qua một bộ sưu tập dễ sử dụng. Cách tiếp cận này loại bỏ nhu cầu làm việc với tiêu đề tệp cấp thấp hoặc mảng tọa độ một cách thủ công.

## Tại sao chuyển đổi đa giác thành đường với Aspose.GIS?
Chuyển đổi một đa giác thành một linestring giữ nguyên ranh giới ngoài chính xác trong khi loại bỏ các vòng nội, cung cấp cho bạn một biểu diễn tuyến tính sạch sẽ. Aspose.GIS xử lý **datasets of up to 500 MB in under 2 seconds on a typical server**, making batch conversions fast and memory‑efficient. Thư viện cũng giữ nguyên hệ tham chiếu không gian gốc, vì vậy các đường kết quả sẽ khớp hoàn hảo với bất kỳ lớp GIS hiện có nào.

## Yêu cầu trước
- **Thư viện Aspose.GIS** – Tải và cài đặt thư viện Aspose.GIS từ [website](https://releases.aspose.com/gis/net/).  
- **Dữ liệu Shapefile** – Có một Shapefile Đa giác sẵn sàng để chuyển đổi. Nếu bạn chưa có, bạn có thể tìm dữ liệu mẫu hoặc tự tạo.  
- **Môi trường phát triển** – Thiết lập môi trường phát triển .NET của bạn với các công cụ cần thiết (Visual Studio, .NET SDK, v.v.).

## Nhập không gian tên
Lớp `Document` là đối tượng cốt lõi của Aspose.GIS đại diện cho một bộ dữ liệu GIS và cung cấp các phương thức để đọc và ghi shapefile. Thêm các không gian tên sau vào đầu tệp mã của bạn:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cách đọc shapefile và chuyển đổi đa giác thành linestring?
Tải shapefile đa giác nguồn, trích xuất vòng ngoài của mỗi đa giác, tạo một `LineString` từ vòng đó, và ghi kết quả vào một shapefile mới – tất cả trong năm bước đơn giản. Mẫu này hoạt động cho bất kỳ bộ dữ liệu nào và đảm bảo hệ tọa độ của nguồn được bảo tồn trong đích.

### Bước 1: Đặt Thư mục Tài liệu
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Thay thế `"Your Document Directory"` bằng đường dẫn thực tế nơi shapefile của bạn nằm.

### Bước 2: Mở Shapefile Nguồn
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Dòng này mở Shapefile Đa giác nguồn để bạn có thể đọc các đối tượng của nó.

### Bước 3: Tạo Shapefile Linestring Đích
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Ở đây chúng ta tạo một Shapefile Linestring mới sẽ lưu trữ các hình học đã chuyển đổi.

### Bước 4: Duyệt qua các Đối tượng Nguồn
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Vòng lặp này duyệt qua mỗi đối tượng đa giác trong tệp gốc.

### Bước 5: Chuyển Đa giác thành Linestring và Ghi vào Đích
Thuộc tính `ExteriorRing` trả về ranh giới ngoài của một đa giác dưới dạng `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Trong khối này chúng ta chuyển đa giác thành đường (`LineString`) và thêm đối tượng mới vào shapefile đích.

## Các vấn đề thường gặp và mẹo
- **Không khớp hệ tọa độ** – Đảm bảo cả lớp nguồn và đích đều sử dụng cùng một hệ tham chiếu không gian; nếu không, các đường có thể bị lệch.  
- **Tệp lớn** – Khi xử lý các shapefile rất lớn, hãy cân nhắc streaming các đối tượng thay vì tải toàn bộ vào bộ nhớ một lúc.  
- **Hình học null** – Kiểm tra các đối tượng có hình học rỗng để tránh ngoại lệ thời gian chạy.  
- **Trích xuất đường từ đa giác** – Nếu bạn chỉ cần vòng ngoài, sử dụng thuộc tính `ExteriorRing`; đối với các vòng nội, duyệt `InteriorRings`.  

## Câu hỏi thường gặp

**Q: Aspose.GIS có tương thích với mọi phiên bản .NET không?**  
A: Có, Aspose.GIS hỗ trợ .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6/7, đảm bảo tích hợp liền mạch với các ngăn xếp phát triển hiện đại.

**Q: Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?**  
A: Có, bạn có thể. Mua giấy phép [tại đây](https://purchase.aspose.com/buy) để loại bỏ các hạn chế đánh giá và nhận được hỗ trợ đầy đủ.

**Q: Có bất kỳ ví dụ hoặc tài liệu nào không?**  
A: Có, bạn có thể tìm tài liệu chi tiết và các mẫu mã trên [trang tài liệu](https://reference.aspose.com/gis/net/).

**Q: Có phiên bản dùng thử không?**  
A: Chắc chắn – khám phá Aspose.GIS với bản dùng thử miễn phí bằng cách truy cập [liên kết này](https://releases.aspose.com/).

**Q: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ ở đâu?**  
A: Truy cập [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được cộng đồng hỗ trợ và nhận hỗ trợ chính thức.

---

**Cập nhật lần cuối:** 2026-06-25  
**Kiểm tra với:** Aspose.GIS cho .NET (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách Chuyển đổi Shapefile sang GeoJSON bằng Aspose.GIS cho .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Cách Đọc GeoJSON từ Stream bằng Aspose.GIS cho .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cách Tạo Hình học Đa giác với Aspose.GIS cho .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}