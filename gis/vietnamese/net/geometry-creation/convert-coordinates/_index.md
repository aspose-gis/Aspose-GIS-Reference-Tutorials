---
date: 2026-08-18
description: Chuyển đổi decimal degrees sang dms bằng Aspose.GIS for .NET. Hướng dẫn
  C# từng bước này chỉ cách chuyển đổi latitude/longitude, decimal degrees sang dms
  và nhiều hơn nữa.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Chuyển đổi tọa độ
og_description: Việc chuyển decimal degrees sang dms trở nên dễ dàng với Aspose.GIS
  for .NET. Tìm hiểu cách chuyển đổi giá trị latitude‑longitude thành định dạng DMS
  tính bằng minutes.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Chuyển decimal degrees sang dms với Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Cách chuyển đổi decimal degrees sang dms với Aspose.GIS for .NET
url: /vi/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách chuyển đổi độ thập phân sang dms với Aspose.GIS

## Giới thiệu
Trong tutorial này, bạn sẽ học **cách chuyển đổi độ thập phân sang dms** bằng cách sử dụng thư viện mạnh mẽ Aspose.GIS cho .NET. Cho dù bạn cần **c# convert lat long**, tạo các chuỗi vị trí dễ đọc cho báo cáo, hoặc chỉ đơn giản khám phá các định dạng tọa độ khác nhau, hướng dẫn này sẽ đưa bạn qua từng bước với các giải thích rõ ràng và các đoạn mã C# sẵn sàng chạy.

## Câu trả lời nhanh
- **“convert coordinates to dms” có nghĩa là gì?** Nó chuyển đổi các giá trị vĩ độ/kinh độ số sang ký hiệu độ‑phút‑giây truyền thống.  
- **Thư viện nào thực hiện việc chuyển đổi?** Aspose.GIS cho .NET cung cấp lớp `GeoConvert` với hỗ trợ định dạng tích hợp.  
- **Tôi có cần giấy phép để thử không?** Một bản dùng thử miễn phí có sẵn; giấy phép thương mại cần thiết cho việc sử dụng trong môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **Tôi có thể sử dụng cùng một đoạn mã cho các định dạng khác không?** Có — chỉ cần thay đổi giá trị enum `PointFormats` (ví dụ, `DecimalDegrees`, `GeoRef`).  

## Chuyển đổi tọa độ sang dms là gì?
Việc chuyển đổi tọa độ sang DMS ghi lại lại các giá trị vĩ độ và kinh độ thập phân dưới dạng như `25°30'00"N 45°30'00"E`. Quá trình này tách mỗi độ thập phân thành độ nguyên, phút (một phần sáu mươi của một độ), và giây (một phần sáu mươi của một phút), sau đó thêm chỉ báo bán cầu thích hợp (N, S, E, W). Dạng đọc được này rất quan trọng đối với nhiều bộ dữ liệu kế thừa và để truyền đạt vị trí chính xác mà không cần dựa vào ký hiệu thập phân.

## Tại sao nên sử dụng Aspose.GIS cho việc chuyển đổi tọa độ?
Aspose.GIS hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các tệp GIS hàng trăm trang mà không cần tải toàn bộ dữ liệu vào bộ nhớ. API cung cấp độ chính xác dưới milimet cho các trường hợp đặc biệt như giá trị âm và chỉ báo bán cầu, và hoạt động nhất quán trên các môi trường .NET của Windows, Linux và macOS.

## Yêu cầu trước
1. **Kiến thức cơ bản về C#** – quen thuộc với các biến, lời gọi phương thức và đầu ra console.  
2. **Aspose.GIS đã được cài đặt** – tải gói mới nhất từ [trang web Aspose.GIS](https://releases.aspose.com/gis/net/). Bạn cũng có thể khám phá trang phát hành chính của Aspose tại [trang web phát hành Aspose](https://releases.aspose.com/).  

## Nhập không gian tên
First, import the namespaces required for GIS operations:

Import Namespaces placeholder remains unchanged.

## Hướng dẫn từng bước

### Lớp GeoConvert là gì?
Lớp `GeoConvert` cung cấp các phương thức tĩnh để chuyển đổi giữa các định dạng tọa độ như độ thập phân, DMS và GeoRef. Nó bao gồm các overload chấp nhận giá trị số thô hoặc đối tượng `Point` và trả về chuỗi định dạng hoặc các thể hiện `Point` mới. Bằng cách xử lý các trường hợp đặc biệt như tọa độ âm và làm tròn, lớp này đảm bảo đầu ra tuân thủ các tiêu chuẩn GIS, giúp tích hợp dễ dàng vào bất kỳ ứng dụng .NET mapping nào.

### Bước 1: bắt đầu quá trình chuyển đổi
Chúng tôi in một thông báo thân thiện để bạn biết bản demo đã bắt đầu.

```csharp
using System;
using Aspose.Gis;
```

### Bước 2: chuyển sang độ thập phân
Mặc dù mục tiêu cuối cùng là DMS, chúng tôi bắt đầu bằng cách hiển thị biểu diễn thập phân gốc. Điều này cũng minh họa đường dẫn **decimal degrees to dms** mà bạn sẽ theo sau.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Bước 3: chuyển sang độ phút thập phân
Định dạng này (`DD°MM.m'`) là một bước trung gian phổ biến khi bạn cần **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Bước 4: chuyển sang độ phút giây (dms)
Đây là phần cốt lõi của tutorial—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Bước 5: chuyển sang GeoRef
Để đầy đủ, chúng tôi cũng trình diễn định dạng `GeoRef` , hữu ích trong quy trình xử lý ảnh viễn thám.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Các vấn đề thường gặp và giải pháp
- **Chữ cái bán cầu không đúng** – Đảm bảo bạn truyền giá trị dương cho bắc/đông và âm cho nam/tây; API tự động thêm hậu tố đúng.  
- **Kết quả trống không mong đợi** – Kiểm tra rằng assembly `Aspose.Gis` được tham chiếu đúng và dự án nhắm tới phiên bản .NET được hỗ trợ.  
- **Không tìm thấy giấy phép** – Đặt file giấy phép của bạn ở thư mục gốc của ứng dụng hoặc thiết lập nó bằng mã: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Câu hỏi thường gặp

**Q: Aspose.GIS có tương thích với các ngôn ngữ lập trình khác không?**  
A: Aspose.GIS chủ yếu hướng tới các nhà phát triển .NET, nhưng cũng có phiên bản Java.

**Q: Tôi có thể thử Aspose.GIS trước khi mua không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.GIS từ [trang web](https://releases.aspose.com/).

**Q: Làm sao tôi có thể nhận hỗ trợ cho Aspose.GIS?**  
A: Bạn có thể tìm trợ giúp tại diễn đàn cộng đồng Aspose.GIS [tại đây](https://forum.aspose.com/c/gis/33).

**Q: Có giấy phép tạm thời cho Aspose.GIS không?**  
A: Có, giấy phép tạm thời có thể được lấy từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể mua Aspose.GIS ở đâu?**  
A: Bạn có thể mua Aspose.GIS từ [trang mua hàng](https://purchase.aspose.com/buy).

## Kết luận
Bằng cách thực hiện các bước này, bạn đã biết **cách chuyển đổi độ thập phân sang dms** và các định dạng GIS phổ biến khác bằng Aspose.GIS cho .NET. Khả năng này cho phép bạn tích hợp các chuỗi vị trí dễ đọc vào các ứng dụng bản đồ, báo cáo, hoặc bất kỳ quy trình dữ liệu không gian nào. Hãy thử nghiệm với các giá trị vĩ độ/kinh độ khác nhau và khám phá các định dạng khác mà lớp `GeoConvert` cung cấp.

---

**Cập nhật lần cuối:** 2026-08-18  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Hướng dẫn liên quan

- [Cách tạo hình học điểm và lấy loại hình học với Aspose.GIS cho .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Cách chuyển đổi GeoJSON – Aspose.GIS cho .NET](/gis/net/geo-data-conversion/)
- [Tạo hình học MultiPoint .NET với Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}