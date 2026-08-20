---
date: 2026-06-30
description: Tìm hiểu cách thêm lớp vào bộ dữ liệu File GDB bằng Aspose.GIS với hệ
  tham chiếu không gian WGS84. Thực hiện theo hướng dẫn chi tiết từng bước để thêm
  lớp trong .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Thêm Lớp vào Bộ Dữ Liệu File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cách Thêm Lớp vào Bộ Dữ Liệu File GDB với hệ tham chiếu không gian WGS84 bằng
  Aspose.GIS
url: /vi/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# cách thêm lớp – tham chiếu không gian wgs84 với Aspose.GIS

## Giới thiệu
Sẵn sàng nâng cao quy trình GIS của bạn với Aspose.GIS cho .NET? Trong hướng dẫn này, bạn sẽ học **cách thêm lớp** vào một dataset File GDB trong khi làm việc với hệ tọa độ **spatial reference WGS84**. Chúng tôi sẽ hướng dẫn từng bước, từ việc chuẩn bị thư mục dữ liệu đến việc xác thực lớp mới tạo, để bạn có thể bắt đầu thao tác dữ liệu địa lý một cách tự tin và hiệu quả.

## Câu trả lời nhanh
- **Hệ tọa độ chính được sử dụng là gì?** spatial reference wgs84 (WGS 84)  
- **Thư viện nào cung cấp API?** Aspose.GIS cho .NET  
- **Tôi có cần giấy phép để thử nghiệm không?** Có – một giấy phép tạm thời của Aspose có sẵn.  
- **Tôi có thể thêm thuộc tính vào lớp mới không?** Chắc chắn, bạn có thể định nghĩa bất kỳ số lượng thuộc tính nào cho đối tượng.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Tham chiếu không gian wgs84 là gì?
Tham chiếu không gian wgs84 (World Geodetic System 1984) là hệ tọa độ địa lý được sử dụng rộng rãi nhất. Nó định nghĩa vĩ độ và kinh độ bằng độ và là CRS mặc định cho nhiều dataset GIS, bao gồm cả dataset mà chúng ta sẽ tạo trong hướng dẫn này.

## Tại sao nên sử dụng Aspose.GIS để thêm lớp?
Tải dữ liệu GIS của bạn mà không cần các binary của bên thứ ba và giữ toàn quyền kiểm soát việc định nghĩa schema. Aspose.GIS hỗ trợ **hơn 40 hệ tham chiếu không gian**, có thể xử lý các tệp lớn hơn **2 GB** mà không cần tải toàn bộ dataset vào bộ nhớ, và chạy trên Windows, Linux và macOS. Điều này biến nó thành một giải pháp đáng tin cậy, đa nền tảng cho tự động hoá GIS cấp doanh nghiệp.

## Yêu cầu trước
- Aspose.GIS cho .NET Library: Tải và cài đặt thư viện từ [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Thư mục tài liệu: Tạo một thư mục riêng trên máy của bạn để lưu các tệp GIS.  
- Một giấy phép tạm thời của Aspose (tùy chọn để đánh giá) – xem phần FAQ bên dưới để lấy liên kết tải về.

## Nhập không gian tên
Thêm các câu lệnh `using` cần thiết vào dự án C# của bạn để có thể truy cập các lớp Aspose.GIS:

*Không cần khối mã ở đây; chỉ cần thêm các dòng sau vào đầu tệp của bạn:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Bước 1: Sao chép thư mục
**Definition anchor:** Một dataset File GDB là một geodatabase của ESRI dựa trên thư mục, lưu trữ dữ liệu không gian trong một tập hợp các tệp.  
Đầu tiên, sao chép thư mục chứa dataset GDB gốc. Việc giữ một bản sao bảo vệ dữ liệu nguồn khi bạn thử nghiệm.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Bước 2: Mở Dataset và Xác minh Khả năng Tạo
`Dataset` đại diện cho một tập hợp các lớp GIS được lưu trong một File GDB. Mở dataset vừa sao chép và xác nhận rằng nó có thể tạo lớp mới. Thuộc tính `CanCreateLayers` phải trả về **True**. **`CanCreateLayers` là một thuộc tính boolean cho biết dataset có hỗ trợ tạo lớp mới hay không.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Bước 3: Tạo và Điền Dữ liệu cho Lớp Mới với tham chiếu không gian wgs84
Bây giờ chúng ta tạo một lớp có tên **data** và đặt rõ ràng tham chiếu không gian thành **Wgs84**. Chúng ta cũng thêm một thuộc tính đơn giản có tên **Name** và chèn một đối tượng điểm. **`CreateLayer` tạo một lớp mới trong dataset với tên và tham chiếu không gian được chỉ định.** **`SpatialReference` đại diện cho hệ tọa độ được lớp sử dụng.** **`Feature` là một đối tượng địa lý riêng lẻ (điểm, đường hoặc đa giác) được lưu trong lớp.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Bước 4: Mở và Xác thực Lớp Đã Thêm
Cuối cùng, mở lớp vừa tạo và xác thực nội dung của nó. Console sẽ hiển thị lớp chứa một đối tượng và thuộc tính **Name** khớp với giá trị chúng ta đã đặt. **`Layer.Open` mở một lớp hiện có để đọc hoặc chỉnh sửa.** Điều này xác nhận lớp đã được thêm đúng cách và tham chiếu không gian là WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Cách thêm lớp vào dataset File GDB?
Tải dataset, gọi `CreateLayer` với tên và tham chiếu không gian mong muốn, định nghĩa schema thuộc tính, sau đó chèn các đối tượng. Tất cả các bước này có thể thực hiện bằng một vài lời gọi phương thức của Aspose.GIS, và API sẽ tự động xử lý khóa tệp và xác thực schema. Quá trình này đảm bảo lớp mới tuân theo tham chiếu không gian của dataset, các định nghĩa thuộc tính được lưu trong schema của lớp, và dữ liệu có thể được truy cập bởi bất kỳ phần mềm GIS nào hỗ trợ File GDB.

## Các vấn đề thường gặp & Mẹo
- **Đường dẫn không đúng:** Đảm bảo `dataDir` kết thúc bằng dấu phân cách đường dẫn (`/` hoặc `\`) để các chuỗi nối tạo thành các đường dẫn tệp hợp lệ.  
- **Lỗi giấy phép:** Nếu bạn thấy cảnh báo giấy phép, áp dụng giấy phép tạm thời từ cổng thông tin Aspose trước khi chạy mã.  
- **Không khớp CRS:** Khi mở lớp sau này trong công cụ GIS khác, xác nhận công cụ nhận diện WGS 84 (EPSG:4326) là hệ tọa độ.  
- **Dataset lớn:** Đối với các dataset vượt quá 1 GB, cân nhắc sử dụng `Dataset.OpenReadOnly` để giảm tiêu thụ bộ nhớ.

## Câu hỏi thường gặp
### Q: Tôi có thể sử dụng Aspose.GIS cho .NET với các thư viện GIS khác không?
A: Có, Aspose.GIS hoạt động độc lập nhưng có thể kết hợp với các thư viện như GDAL hoặc NetTopologySuite để xử lý nâng cao.

### Q: Có giấy phép tạm thời để thử nghiệm không?
A: Có, bạn có thể lấy giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/) để thử nghiệm và đánh giá.

### Q: Aspose.GIS cho .NET hỗ trợ những hệ tham chiếu không gian nào?
A: Aspose.GIS hỗ trợ hơn **40 mã EPSG**, bao gồm các hệ phổ biến như WGS84 (EPSG:4326), Web Mercator (EPSG:3857), và NAD83 (EPSG:4269). Khám phá tài liệu chi tiết [tại đây](https://reference.aspose.com/gis/net/).

### Q: Tôi có thể đóng góp cho cộng đồng Aspose.GIS không?
A: Chắc chắn! Tham gia thảo luận và chia sẻ kinh nghiệm của bạn trên [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.GIS cho .NET ở đâu?
A: Khám phá tài liệu toàn diện [tại đây](https://reference.aspose.com/gis/net/) để biết thông tin sâu về tất cả các lớp, phương thức và thực hành tốt nhất.

---

**Cập nhật lần cuối:** 2026-06-30  
**Kiểm tra với:** Aspose.GIS cho .NET (phiên bản ổn định mới nhất)  
**Tác giả:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Hướng dẫn liên quan

- [Tạo Dataset File Geodatabase .NET với Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Tạo Lớp Vector trong File GDB – Hướng dẫn Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Tạo Dataset File GDB và Đặt Khoảng dung sai cho Lớp](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}