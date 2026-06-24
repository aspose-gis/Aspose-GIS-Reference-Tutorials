---
date: 2026-05-31
description: Tìm hiểu cách tạo GeoJSON, cấu hình các tùy chọn GeoJSON và thêm đối
  tượng vào lớp bằng Aspose.GIS cho .NET. Thực hiện theo hướng dẫn từng bước này.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Thiết lập dung sai tuyến tính
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
title: Cách tạo GeoJSON với dung sai Aspose.GIS cho .NET
url: /vi/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo GeoJSON với Độ Dung Sai Aspose.GIS cho .NET

## Giới thiệu
Nếu bạn muốn **học cách tạo GeoJSON** files, kiểm soát độ chính xác của đường cong, và xuất kết quả dưới dạng tài liệu sẵn sàng‑sử dụng, Aspose.GIS cho .NET làm cho việc này trở nên đơn giản. Trong hướng dẫn này, bạn sẽ khám phá cách cấu hình các tùy chọn GeoJSON, đặt độ dung sai linearization, và **add feature to layer** objects trong khi giữ mã sạch sẽ và sẵn sàng cho sản xuất.

## Câu trả lời nhanh
- **“create vector layer” có nghĩa là gì?** Nó tạo một bộ dữ liệu vector GIS mới (ví dụ, một tệp GeoJSON) có thể lưu trữ các hình học và thuộc tính.  
- **Làm thế nào để đặt linearization tolerance?** Đặt thuộc tính `LinearizationTolerance` trên một thể hiện `GeoJsonOptions` trước khi tạo layer.  
- **Tôi có thể xuất tệp GeoJSON trực tiếp không?** Có — sử dụng `VectorLayer.Create` với driver `Drivers.GeoJson` và các tùy chọn đã cấu hình.  
- **Tôi có cần giấy phép không?** Giấy phép Aspose.GIS hợp lệ sẽ mở khóa tất cả các tính năng; một khóa đánh giá tạm thời hoạt động cho việc thử nghiệm.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer” là gì?
Tạo một vector layer có nghĩa là khởi tạo một container GIS mới (chẳng hạn như một tệp GeoJSON) có thể chứa các điểm, đường, đa giác và dữ liệu thuộc tính liên quan. Layer này trở thành mục tiêu cho bất kỳ hình học nào bạn tạo và bất kỳ thuộc tính nào bạn gắn.

## Tại sao cần cấu hình các tùy chọn GeoJSON?
Cấu hình các tùy chọn GeoJSON—đặc biệt là **linearization tolerance**—đảm bảo rằng các hình học cong (ví dụ, `CircularString`) được xấp xỉ với độ chính xác đáp ứng yêu cầu độ chính xác của ứng dụng của bạn. Cấu hình đúng giảm kích thước tệp trong khi giữ nguyên độ trung thực hình ảnh, điều này rất quan trọng khi GeoJSON được sử dụng bởi các bản đồ web hoặc công cụ phân tích không gian.

## Yêu cầu trước
1. **Visual Studio** (bất kỳ phiên bản mới nào).  
2. **Giấy phép Aspose.GIS** (hoặc một khóa đánh giá tạm thời).  
3. Thư viện **Aspose.GIS for .NET** được tham chiếu trong dự án của bạn.  
4. Kiến thức cơ bản về **C#**.

## Nhập các Namespace
First, import the required namespaces so the compiler knows where to find the GIS classes:

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

## Hướng Dẫn Từng Bước

### Bước 1: Cấu hình các tùy chọn GeoJSON (cách đặt tolerance)
`GeoJsonOptions` chỉ định các cài đặt tuần tự hoá được sử dụng khi ghi các tệp GeoJSON.  
`GeoJsonOptions` định nghĩa cách Aspose.GIS tuần tự hoá GeoJSON, bao gồm linearization tolerance, độ chính xác tọa độ và các cài đặt đầu ra khác.  
Chúng ta sẽ tạo một đối tượng `GeoJsonOptions` và cho Aspose.GIS biết độ gần của hình học đã linearized so với đường cong gốc.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Bước 2: Xác định Đường dẫn Đầu ra (cách xuất GeoJSON)
Xác định đường dẫn tệp đầy đủ nơi GeoJSON kết quả sẽ được lưu. Đảm bảo thư mục tồn tại và ứng dụng có quyền ghi.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Bước 3: **Create Vector Layer** với các tùy chọn đã cấu hình
Lớp `VectorLayer` đại diện cho một container GIS có thể đọc và ghi dữ liệu không gian.  
`Drivers.GeoJson` là định danh driver để ghi các tệp định dạng GeoJSON.  
Sử dụng `VectorLayer.Create` cùng với driver `Drivers.GeoJson` và `GeoJsonOptions` đã cấu hình trước đó tạo ra một tệp GeoJSON mới sẵn sàng cho việc chèn feature.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Bước 4: Xây dựng Geometry (ví dụ, một circular string)
`CircularString` là một hình học đường cong mà Aspose.GIS có thể linearize dựa trên tolerance bạn đặt. Bạn có thể thay thế nó bằng bất kỳ biểu diễn WKT hợp lệ nào như `POINT`, `LINESTRING`, hoặc `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Bước 5: **Add Feature to Layer** và lưu
`Feature` là đối tượng kết hợp một geometry với dữ liệu thuộc tính. Sau khi tạo một thể hiện `Feature`, gán geometry, tùy chọn thêm giá trị thuộc tính, và gọi `layer.Add(feature)` để lưu trữ nó. Khi khối `using` kết thúc, layer sẽ tự động được ghi vào tệp được định nghĩa trong `path`.  
Khi khối `using` kết thúc, layer sẽ tự động được ghi vào tệp được định nghĩa trong `path`, cung cấp cho bạn một tệp GeoJSON sẵn sàng sử dụng.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## Vấn đề Thường gặp & Mẹo
- **Đường dẫn không đúng** – Kiểm tra thư mục tồn tại và bạn có quyền ghi.  
- **Tolerance quá thấp** – Đặt `LinearizationTolerance` thành giá trị rất nhỏ có thể làm tăng kích thước tệp đáng kể; tolerance khoảng 0.001 thường cân bằng giữa độ chính xác và kích thước.  
- **Lỗi giấy phép** – Nếu bạn thấy cảnh báo giấy phép, hãy chắc chắn tệp giấy phép được tải trước bất kỳ lời gọi Aspose.GIS nào.  
- **Lưu ý về hiệu năng** – Aspose.GIS hỗ trợ xử lý các tệp lên tới 2 GB mà không cần tải toàn bộ tài liệu vào bộ nhớ, nhờ kiến trúc streaming của nó.

## Câu hỏi Thường gặp

**Q: Aspose.GIS cho .NET có tương thích với các framework .NET khác không?**  
A: Có, nó hoạt động với .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6/7.

**Q: Tôi có thể sử dụng Aspose.GIS trong các dự án thương mại không?**  
A: Chắc chắn. Giấy phép thương mại loại bỏ mọi hạn chế đánh giá và cung cấp hỗ trợ kỹ thuật đầy đủ.

**Q: Aspose.GIS có hỗ trợ các định dạng GIS khác ngoài GeoJSON không?**  
A: Có, nó hỗ trợ hơn 30 định dạng—bao gồm Shapefile, KML, GML và CSV—cho phép chuyển đổi liền mạch giữa chúng.

**Q: Có phiên bản dùng thử không?**  
A: Bạn có thể tải về bản dùng thử miễn phí 30 ngày từ trang web Aspose; nó bao gồm tất cả các tính năng.

**Q: Tôi có thể nhận hỗ trợ ở đâu?**  
A: Sử dụng diễn đàn Aspose, cổng hỗ trợ chuyên dụng, hoặc liên kết “Contact Support” trong bảng điều khiển sản phẩm.

## Kết luận
Bằng cách thực hiện các bước này, bạn đã biết **cách tạo GeoJSON**, cấu hình linearization tolerance, và **add feature to layer** để xuất GeoJSON một cách liền mạch. Khám phá các loại geometry bổ sung, xử lý thuộc tính và các kịch bản xử lý hàng loạt để tận dụng tối đa Aspose.GIS trong các dự án GIS .NET của bạn.

---

**Cập nhật lần cuối:** 2026-05-31  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng Dẫn Liên Quan

- [Cách Chuyển Đổi GeoJSON – Aspose.GIS cho .NET](/gis/net/geo-data-conversion/)
- [Tạo Vector Layer, Giới Hạn Độ Chính Xác với Aspose.GIS cho .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Tạo Vector Layer trong File GDB – Hướng Dẫn Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}