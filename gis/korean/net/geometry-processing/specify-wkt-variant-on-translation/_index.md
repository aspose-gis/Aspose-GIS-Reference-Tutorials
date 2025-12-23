---
date: 2025-12-23
description: Aspose.GIS for .NET를 사용하여 다양한 옵션으로 기하학을 WKT로 변환하고, 숫자 형식을 설정하며, 소수점 자릿수를
  조정하는 방법을 배워보세요.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Aspose.GIS를 사용하여 지오메트리를 WKT 변형 옵션으로 변환
url: /ko/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용한 Geometry를 WKT 변형 옵션으로 변환하기

## 소개
현대 .NET 애플리케이션에서 **converting geometry to WKT**는 다른 시스템과 공간 데이터를 교환하거나 텍스트 기반 형식으로 저장해야 할 때 흔히 수행되는 단계입니다. Aspose.GIS for .NET은 이 변환을 손쉽게 수행하도록 하면서 WKT 변형, 숫자 형식 및 소수점 정밀도에 대한 완전한 제어를 제공합니다. 이 튜토리얼에서는 geometry를 WKT로 변환하는 방법, 올바른 변형을 선택하는 방법, 그리고 프로젝트의 정확한 요구 사항에 맞게 출력을 미세 조정하는 방법을 배웁니다.

## 빠른 답변
- **“convert geometry to WKT”는 무엇을 의미합니까?** 기하학 객체(점, 선, 다각형)를 Well‑Known Text 표현으로 변환합니다.  
- **지원되는 WKT 변형은 무엇입니까?** `Iso`, `SimpleFeatureAccessOutdated`, `ExtendedPostGis`.  
- **소수점 정밀도를 어떻게 제어합니까?** `General`, `RoundTrip`, `Flat`과 같은 `NumericFormat` 옵션을 사용합니다.  
- **프로덕션에서 라이선스가 필요합니까?** 예, 비시험용으로는 상업용 라이선스가 필요합니다.  
- **호환되는 .NET 버전은 무엇입니까?** .NET Framework 4.0 이상 및 .NET 5/6/7.

## “convert geometry to WKT”란 무엇인가요?
Geometry를 WKT로 변환하면 공간 객체를 설명하는 사람이 읽을 수 있는 문자열이 생성됩니다. 이 형식은 GIS 도구, 데이터베이스 및 웹 서비스에서 널리 사용되어 데이터 교환에 이상적입니다.

## 이 변환에 Aspose.GIS를 사용하는 이유는?
- **Precision control** – 출력되는 소수점 자리수를 선택합니다.  
- **Variant flexibility** – 다운스트림 시스템에서 요구하는 정확한 WKT 방언에 맞출 수 있습니다.  
- **No external dependencies** – 순수 .NET 라이브러리이며 네이티브 바이너리가 없습니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Aspose.GIS for .NET** – [download page](https://releases.aspose.com/gis/net/)에서 다운로드하고 설치합니다.  
2. **Development Environment** – 최신 버전의 Visual Studio 또는 .NET SDK가 포함된 VS Code.  
3. **Basic C# knowledge** – 클래스, 객체 및 .NET 프레임워크에 대한 기본 이해.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 범위에 포함시킵니다:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## 단계 1: Point 객체 만들기
**convert geometry to WKT**에 사용할 `Point`를 생성합니다. 이 점은 위도, 경도 및 선택적 측정값(M)을 포함합니다:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 단계 2: 공간 참조 시스템(SRS) 설정
WKT 출력이 어떤 좌표계를 참조해야 하는지 알 수 있도록 공간 참조 시스템을 지정합니다. 여기서는 일반적인 WGS84 시스템을 사용합니다:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 단계 3: WKT 변형 지정
**convert geometry to WKT**할 때 적절한 WKT 변형을 선택합니다. 각 변형은 출력 형식을 약간씩 다르게 포맷합니다:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 단계 4: 숫자 형식 제어 (숫자 형식 설정 및 소수점 정밀도 조정)
좌표의 숫자 표현을 미세 조정합니다. `NumericFormat` 클래스를 사용하면 **set numeric format** 및 **adjust decimal precision**을 필요에 맞게 설정할 수 있습니다:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## 일반적인 문제 및 팁
- **Missing M value** – 측정값이 필요하지 않다면 `M` 속성을 생략하십시오; ISO 변형은 자동으로 이를 제거합니다.  
- **Unexpected precision** – 올바른 `NumericFormat`을 사용하고 있는지 다시 확인하십시오; `General`은 전체 double 정밀도를 유지하고, `Flat`은 지정된 소수점 자리수로 반올림합니다.  
- **SRID not displayed** – `ExtendedPostGis` 변형만 출력 앞에 `SRID=`를 붙입니다. 대상 시스템이 SRID를 기대한다면 이 변형을 선택하십시오.

## 결론
이 단계를 따르면 **convert geometry to WKT**하는 방법, 올바른 변형을 선택하는 방법, 그리고 숫자 출력을 정확히 제어하는 방법을 알게 됩니다. 이를 통해 Aspose.GIS를 어떤 GIS 워크플로, 데이터베이스 또는 WKT를 소비하는 웹 서비스와도 유연하게 통합할 수 있습니다.

## FAQ
### Aspose.GIS가 모든 .NET 버전과 호환되나요?
예, Aspose.GIS는 .NET Framework 4.0 이상을 지원합니다.  

### Aspose.GIS를 상업 프로젝트에 사용할 수 있나요?
예, Aspose.GIS는 개인 및 상업 프로젝트 모두에 사용할 수 있습니다.  

### Aspose.GIS가 다른 공간 데이터 형식을 지원하나요?
예, Aspose.GIS는 ESRI Shapefile, GeoJSON, KML 등 다양한 공간 데이터 형식을 지원합니다.  

### Aspose.GIS의 무료 체험판이 있나요?
예, [여기](https://releases.aspose.com/)에서 Aspose.GIS 무료 체험판을 다운로드할 수 있습니다.  

### Aspose.GIS에 대한 도움이나 지원을 어디서 받을 수 있나요?
[Aspose.GIS 커뮤니티 포럼](https://forum.aspose.com/c/gis/33)에서 질문을 게시하거나 지원을 받을 수 있습니다.

## 자주 묻는 질문
**Q: Geometry 컬렉션을 단일 WKT 문자열로 내보내려면 어떻게 해야 하나요?**  
A: 컬렉션의 각 geometry를 순회하면서 `AsText` 결과를 연결하고, 필요에 따라 쉼표나 새줄로 구분합니다.

**Q: 좌표값을 변경하지 않고 SRID만 바꾸려면 어떻게 하나요?**  
A: `SpatialReferenceSystem` 속성을 원하는 SRID로 설정하면 좌표값은 그대로 유지됩니다.

**Q: 지원되지 않는 WKT 변형을 사용하면 어떻게 되나요?**  
A: Aspose.GIS는 `ArgumentException`을 발생시킵니다. 항상 `WktVariant` 열거형 값으로 변형을 검증하십시오.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}