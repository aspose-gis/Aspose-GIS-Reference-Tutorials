---
date: 2026-04-09
description: .NET 애플리케이션에서 Aspose.GIS for .NET을 사용하여 C#로 포인트를 생성할 때 공간 참조를 할당하고 소수점
  자릿수를 설정하는 방법을 배워보세요.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: 번역 시 WKT 변형 지정
second_title: Aspose.GIS .NET API
title: Aspose.GIS를 사용하여 공간 참조 할당 및 WKT 변형 설정
url: /ko/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용한 공간 참조 할당 및 WKT 변형 설정

## 소개
이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 기하학에 **assign spatial reference**를 적용하고 정확한 WKT 출력 형식을 제어하는 방법을 배웁니다. 매핑, 분석 또는 데이터 교환을 위해 **create point C#** 객체가 필요하든, 올바른 WKT 변형과 숫자 정밀도를 선택할 수 있으면 공간 데이터가 상호 운용 가능하고 읽기 쉬워집니다. 단계별로 과정을 살펴보겠습니다.

## 빠른 답변
- **“assign spatial reference”는 무엇을 의미합니까?** 기하학을 WGS‑84와 같은 특정 좌표계에 연결합니다.  
- **지원되는 WKT 변형은 무엇입니까?** Iso, SimpleFeatureAccessOutdated, ExtendedPostGis.  
- **소수점 정밀도를 어떻게 제어합니까?** `NumericFormat` 옵션인 `General`, `RoundTrip`, `Flat`을 사용합니다.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 상용 라이선스가 프로덕션에 필요합니다.  
- **호환되는 .NET 버전은 무엇입니까?** .NET Framework 4.0 이상 및 .NET Core/5/6+.

## “assign spatial reference”란 무엇인가요?
공간 참조(또는 공간 참조 시스템, SRS)를 할당하면 GIS 소프트웨어가 기하학의 좌표 값을 어떻게 해석해야 하는지 알려줍니다. SRS가 없으면 점의 위도‑경도 값은 실제 세계와 연결되지 않습니다.

## 왜 WKT 변형 및 숫자 형식을 제어해야 할까요?
다양한 GIS 도구는 약간씩 다른 WKT 구문을 기대합니다. 적절한 변형을 선택하면 원활한 데이터 교환이 보장되고, 소수점 정밀도를 설정하면 반올림 오류나 로그와 파일을 어지럽히는 과도하게 긴 숫자를 방지할 수 있습니다.

## 전제 조건
1. Aspose.GIS for .NET – [다운로드 페이지](https://releases.aspose.com/gis/net/)에서 다운로드합니다.  
2. .NET 개발 환경(Visual Studio, VS Code 또는 Rider).  
3. C# 및 .NET 프레임워크에 대한 기본 지식.

## 네임스페이스 가져오기
Aspose.GIS 클래스 사용 전에 필요한 네임스페이스를 가져와야 합니다:

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

## 1단계: 포인트 객체 생성 (create point C#)
위도, 경도 및 선택적 측정값(M)을 사용하여 `Point`를 생성합니다:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 2단계: 공간 참조 시스템 (SRS) 할당
이제 포인트에 **assign spatial reference**를 적용합니다. 여기서는 널리 지원되는 WGS‑84 시스템(SRID 4326)을 사용합니다:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 3단계: 원하는 WKT 변형 지정
다운스트림 애플리케이션에 맞는 WKT 변형을 선택합니다:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 4단계: WKT 출력에 대한 소수점 정밀도 설정
`NumericFormat`을 사용하여 최종 문자열에 표시되는 자릿수를 제어합니다:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### 일반적인 함정 및 팁
- **함정:** `AsText`를 호출하기 전에 SRS를 설정하지 않으면 SRID 정보가 누락될 수 있습니다.  
- **팁:** 좌표의 무손실 라운드‑트립이 필요할 때 `NumericFormat.RoundTrip`을 사용하십시오.  
- **팁:** `Iso` 변형이 가장 이식성이 높으며, SRID를 포함해야 할 경우에만 `ExtendedPostGis`를 선택하십시오.

## 결론
이제 Aspose.GIS를 사용하여 **assign spatial reference**를 수행하고, 적절한 WKT 변형을 선택하며, **create point C#** 객체를 만들 때 **set decimal precision**을 적용하는 방법을 알게 되었습니다. 이러한 제어를 통해 간단한 시각화부터 고정밀 공간 분석에 이르기까지 모든 GIS 워크플로우의 정확한 요구 사항을 충족할 수 있는 유연성을 얻을 수 있습니다.

## 자주 묻는 질문

**Q:** Aspose.GIS가 모든 .NET 버전과 호환됩니까?  
**A:** 예, Aspose.GIS는 .NET Framework 4.0 이상과 .NET Core/5/6을 지원합니다.

**Q:** 상업 프로젝트에 Aspose.GIS를 사용할 수 있나요?  
**A:** 물론입니다. 프로덕션 사용에는 상업 라이선스가 필요하지만, 평가를 위한 무료 체험판을 사용할 수 있습니다.

**Q:** Aspose.GIS가 다른 공간 데이터 형식을 지원합니까?  
**A:** 예, ESRI Shapefile, GeoJSON, KML 등 다양한 형식을 지원합니다.

**Q:** 무료 체험판은 어디서 다운로드할 수 있나요?  
**A:** [여기](https://releases.aspose.com/)에서 Aspose.GIS 무료 체험판을 다운로드할 수 있습니다.

**Q:** 문제가 발생하면 어떻게 도움을 받을 수 있나요?  
**A:** Aspose 직원과 커뮤니티 회원이 지원하는 Aspose.GIS 커뮤니티 [포럼](https://forum.aspose.com/c/gis/33)에 질문을 게시하십시오.

---

**마지막 업데이트:** 2026-04-09  
**테스트 환경:** Aspose.GIS for .NET (latest release)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}