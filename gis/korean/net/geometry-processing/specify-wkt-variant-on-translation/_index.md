---
date: 2026-09-15
description: Aspose.GIS for .NET를 사용한 C#에서 point geometry를 생성할 때 coordinate system을
  할당하고, WKT variant를 설정하며, decimal precision을 제어하는 방법을 배웁니다.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: 번역 시 WKT Variant 지정
og_description: Aspose.GIS for .NET를 사용한 C#에서 point geometry를 생성할 때 coordinate system을
  할당하고, WKT variant를 설정하며, decimal precision을 제어하는 방법을 배웁니다.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Aspose.GIS를 사용하여 coordinate system 할당 및 WKT variant 설정
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Aspose.GIS를 사용하여 coordinate system 할당 및 WKT variant 설정
url: /ko/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 좌표계 할당 및 Aspose.GIS를 사용한 WKT 변형 설정

## 소개
이 튜토리얼에서는 **좌표계 할당**, 올바른 WKT 변형 선택, 그리고 C#에서 Aspose.GIS for .NET을 사용하여 **점 지오메트리 생성** 시 소수점 정밀도 제어 방법을 배웁니다. 매핑 서비스를 구축하거나, 공간 분석을 수행하거나, GIS 플랫폼 간에 데이터를 교환할 때, 이러한 설정은 출력이 상호 운용 가능하고 읽기 쉬운 것을 보장합니다. 단계별로 과정을 살펴보겠습니다.

## 빠른 답변
- **‘좌표계 할당’은 무엇을 의미하나요?** 기하학을 WGS‑84와 같은 특정 좌표 기준 시스템에 연결합니다.  
- **지원되는 WKT 변형은 무엇인가요?** Iso, SimpleFeatureAccessOutdated, ExtendedPostGis.  
- **소수점 정밀도를 어떻게 제어할 수 있나요?** `NumericFormat` 열거형(`General`, `RoundTrip`, `Flat`)을 사용합니다.  
- **Aspose.GIS에 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 상용 사용을 위해서는 상업용 라이선스가 필요합니다.  
- **호환되는 .NET 버전은 무엇인가요?** .NET Framework 4.0 이상 및 .NET Core/5/6 이상.

## ‘좌표계 할당’이란 무엇인가요?
공간 참조(또는 공간 참조 시스템, SRS)를 할당하면 GIS 소프트웨어에 기하학의 좌표 값을 어떻게 해석할지 알려주며, 숫자를 WGS‑84와 같은 실제 세계 좌표계에 연결합니다. SRS가 없으면 점의 위도‑경도 값은 실제 세계 의미를 갖지 못합니다.

## 왜 WKT 변형 및 숫자 형식을 제어해야 할까요?
30개 이상의 GIS 도구가 특정 WKT 구문을 기대하므로 적절한 변형을 선택하면 가져오기 오류를 방지할 수 있습니다. 숫자 형식을 설정하면 반올림 노이즈를 줄이고 출력이 간결해져, 로그나 파일을 프로그래밍 방식으로 파싱할 때 특히 중요합니다.

## 전제 조건
1. Aspose.GIS for .NET – [다운로드 페이지](https://releases.aspose.com/gis/net/)에서 다운로드합니다.  
2. .NET 개발 환경(Visual Studio, VS Code 또는 Rider).  
3. C# 및 .NET 프레임워크에 대한 기본 지식.

## 네임스페이스 가져오기
Aspose.GIS 클래스를 사용하기 전에 필요한 네임스페이스를 가져옵니다:

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

## 점에 좌표계를 할당하는 방법은?
`Point` 인스턴스를 로드한 다음 `SpatialReference` 클래스를 사용하여 공간 참조 시스템(SRS)을 연결합니다. 이 두 단계 패턴은 기하학이 내보낼 때 좌표계 메타데이터를 포함하도록 보장하여, 하위 도구가 좌표를 올바르게 해석할 수 있게 합니다. `Point` 클래스는 X(경도)와 Y(위도) 좌표로 정의된 단일 위치를 나타냅니다.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 단계 2: 공간 참조 시스템(SRS) 할당
이제 점에 **공간 참조**를 할당합니다. `SpatialReference`는 SRID로 식별되는 좌표 기준 시스템을 나타냅니다. 여기서는 널리 지원되는 WGS‑84 시스템(SRID 4326)을 사용합니다:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 단계 3: 원하는 WKT 변형 지정
하위 애플리케이션에 맞는 WKT 변형을 선택합니다:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## WKT 출력에 대한 소수점 정밀도 설정 방법
`NumericFormat` 열거형을 사용하여 최종 문자열에 표시되는 자릿수를 제어합니다. 이 열거형은 `General`, `RoundTrip`, `Flat`과 같은 형식 규칙을 정의합니다. `RoundTrip`을 선택하면 라운드‑트립 시나리오에서 전체 좌표 정밀도가 유지되고, `General`은 대부분의 시각화 작업에 적합한 간결한 표현을 제공합니다. `NumericFormat` 열거형은 WKT 출력에서 좌표 숫자가 어떻게 형식화되는지를 제어합니다.

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
이제 Aspose.GIS를 사용하여 **좌표계 할당**, 적절한 WKT 변형 선택, 그리고 **점 지오메트리 생성** 시 **소수점 정밀도 설정** 방법을 알게 되었습니다. 이러한 제어를 통해 간단한 시각화부터 고정밀 공간 분석까지 모든 GIS 워크플로우의 정확한 요구 사항을 충족할 수 있는 유연성을 얻을 수 있습니다.

## 자주 묻는 질문

**Q:** Aspose.GIS가 모든 .NET 버전과 호환되나요?  
**A:** 예, Aspose.GIS는 .NET Framework 4.0 이상 및 .NET Core/5/6을 지원합니다.

**Q:** 상업 프로젝트에 Aspose.GIS를 사용할 수 있나요?  
**A:** 물론입니다. 상용 사용을 위해서는 상업용 라이선스가 필요하지만, 평가를 위한 무료 체험판을 사용할 수 있습니다.

**Q:** Aspose.GIS가 다른 공간 데이터 형식을 지원하나요?  
**A:** 예, ESRI Shapefile, GeoJSON, KML, CSV 등을 포함한 30개 이상의 형식을 지원합니다.

**Q:** 무료 체험판은 어디서 다운로드할 수 있나요?  
**A:** [Aspose.GIS 무료 체험판 다운로드 페이지](https://releases.aspose.com/)에서 Aspose.GIS 무료 체험판을 다운로드할 수 있습니다.

**Q:** 문제가 발생하면 어떻게 도움을 받을 수 있나요?  
**A:** Aspose 직원과 커뮤니티 회원이 지원하는 Aspose.GIS 커뮤니티 [포럼](https://forum.aspose.com/c/gis/33)에 질문을 게시하십시오.

---

**마지막 업데이트:** 2026-09-15  
**테스트 환경:** Aspose.GIS for .NET (latest release)  
**작성자:** Aspose

## 관련 튜토리얼

- [벡터 레이어 생성 및 공간 참조 시스템 설정](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Aspose.GIS for .NET을 사용하여 지오메트리를 WKT로 변환하는 방법](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Aspose.GIS를 사용하여 지오메트리 작성 시 정밀도 제한하는 방법](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}