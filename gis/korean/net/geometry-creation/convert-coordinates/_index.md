---
date: 2026-08-18
description: Aspose.GIS for .NET를 사용하여 십진수 각도를 DMS로 변환합니다. 이 단계별 C# 가이드는 위도/경도, 십진수
  각도를 DMS로 변환하는 방법 및 기타 내용을 보여줍니다.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: 좌표 변환
og_description: Aspose.GIS for .NET를 사용한 십진수 각도에서 DMS 변환이 쉬워졌습니다. 위도‑경도 값을 분 단위의 DMS
  형식으로 변환하는 방법을 배워보세요.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Aspose.GIS for .NET를 사용하여 십진수 각도를 DMS로 변환
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
title: Aspose.GIS for .NET를 사용하여 십진수 각도를 DMS로 변환하는 방법
url: /ko/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용하여 십진수 도를 DMS로 변환하는 방법

## 소개
이 튜토리얼에서는 .NET용 강력한 Aspose.GIS 라이브러리를 사용하여 **십진수 도를 DMS로 변환하는 방법**을 배웁니다. **C#으로 위도·경도 변환**이 필요하거나, 보고서를 위한 사람이 읽을 수 있는 위치 문자열을 생성하거나, 단순히 다양한 좌표 형식을 탐색하고자 할 때, 이 가이드는 명확한 설명과 바로 실행 가능한 C# 코드 조각을 통해 모든 단계를 안내합니다.

## 빠른 답변
- **좌표를 DMS로 변환한다는 것은 무엇을 의미합니까?** 숫자 형태의 위도/경도 값을 전통적인 도-분-초 표기법으로 변환합니다.  
- **어떤 라이브러리가 변환을 처리합니까?** .NET용 Aspose.GIS는 내장된 형식 지원을 제공하는 `GeoConvert` 클래스를 제공합니다.  
- **시도하려면 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 실제 사용을 위해서는 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5 이상, .NET Core 3.1 이상, 그리고 .NET 5/6 이상을 지원합니다.  
- **다른 형식에도 동일한 코드를 사용할 수 있나요?** 예, `PointFormats` 열거형 값을 변경하면 됩니다(예: `DecimalDegrees`, `GeoRef`).  

## 좌표를 DMS로 변환한다는 것은 무엇입니까?
좌표를 DMS로 변환하면 십진수 위도와 경도 값을 `25°30'00"N 45°30'00"E`와 같은 형식으로 다시 씁니다. 이 과정은 각 십진수도를 정수 도, 분(도 1/60), 초(분 1/60)로 나눈 뒤 적절한 반구 표시(N, S, E, W)를 추가합니다. 이러한 사람이 읽을 수 있는 형태는 많은 레거시 데이터셋에 필수적이며, 십진수 표기 없이 정확한 위치를 전달하는 데 중요합니다.

## 좌표 변환에 Aspose.GIS를 사용하는 이유
Aspose.GIS는 **50개 이상의 입력 및 출력 형식**을 지원하며 전체 데이터를 메모리에 로드하지 않고도 수백 페이지에 달하는 GIS 파일을 처리할 수 있습니다. 이 API는 음수 값이나 반구 표시와 같은 특수 경우에도 서브밀리미터 수준의 정확성을 제공하며, Windows, Linux, macOS .NET 런타임에서 일관되게 실행됩니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **C# 기본 지식** – 변수, 메서드 호출 및 콘솔 출력에 익숙함.  
2. **Aspose.GIS 설치** – 최신 패키지를 [Aspose.GIS 웹사이트](https://releases.aspose.com/gis/net/)에서 다운로드하십시오. 또한 주요 Aspose 릴리스 사이트를 [Aspose releases 웹사이트](https://releases.aspose.com/)에서 확인할 수 있습니다.

## 네임스페이스 가져오기
먼저 GIS 작업에 필요한 네임스페이스를 가져옵니다:

Import Namespaces placeholder는 변경되지 않습니다.

## 단계별 가이드

### GeoConvert 클래스란?
`GeoConvert` 클래스는 십진수 도, DMS, GeoRef와 같은 좌표 형식 간 변환을 위한 정적 메서드를 제공합니다. 원시 숫자 값이나 `Point` 객체를 받아 형식화된 문자열이나 새로운 `Point` 인스턴스를 반환하는 오버로드가 포함되어 있습니다. 음수 좌표 및 반올림과 같은 특수 경우를 처리함으로써 출력이 표준 GIS 사양을 준수하도록 보장하며, 이를 통해 모든 .NET 매핑 애플리케이션에 쉽게 통합할 수 있습니다.

### 단계 1: 변환 프로세스 시작
데모가 시작되었음을 알리기 위해 친절한 메시지를 출력합니다.

```csharp
using System;
using Aspose.Gis;
```

### 단계 2: 십진수 도로 변환
최종 목표가 DMS이지만, 먼저 원래의 십진수 표현을 보여줍니다. 이는 나중에 따라가게 될 **십진수 도를 DMS로 변환** 경로를 시연하는 것이기도 합니다.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 단계 3: 도-소수점 분으로 변환
이 형식(`DD°MM.m'`)은 **위도·경도 도·분을 변환**해야 할 때 흔히 사용되는 중간 단계입니다.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 단계 4: 도·분·초(DMS)로 변환
이것이 튜토리얼의 핵심인 **좌표를 DMS로 변환**입니다.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 단계 5: GeoRef로 변환
완전성을 위해 원격 감지 워크플로우에 유용한 `GeoRef` 형식도 시연합니다.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## 일반적인 문제 및 해결책
- **잘못된 반구 문자** – 북/동은 양수, 남/서를 음수로 전달했는지 확인하십시오; API가 자동으로 올바른 접미사를 추가합니다.  
- **예상치 못한 빈 출력** – `Aspose.Gis` 어셈블리가 올바르게 참조되었는지와 프로젝트가 지원되는 .NET 버전을 대상으로 하는지 확인하십시오.  
- **라이선스를 찾을 수 없음** – 라이선스 파일을 애플리케이션 루트에 두거나 `License license = new License(); license.SetLicense("Aspose.GIS.lic");`와 같이 프로그래밍 방식으로 설정하십시오.

## 자주 묻는 질문

**Q: Aspose.GIS가 다른 프로그래밍 언어와 호환됩니까?**  
A: Aspose.GIS는 주로 .NET 개발자를 대상으로 하지만, Java 버전도 제공됩니다.

**Q: 구매 전에 Aspose.GIS를 체험할 수 있나요?**  
A: 예, [웹사이트](https://releases.aspose.com/)에서 Aspose.GIS 무료 체험판을 이용할 수 있습니다.

**Q: Aspose.GIS 지원을 어떻게 받을 수 있나요?**  
A: Aspose.GIS 커뮤니티 포럼에서 도움을 받을 수 있습니다[여기](https://forum.aspose.com/c/gis/33).

**Q: Aspose.GIS에 대한 임시 라이선스가 제공되나요?**  
A: 예, [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

**Q: Aspose.GIS를 어디서 구매할 수 있나요?**  
A: [구매 페이지](https://purchase.aspose.com/buy)에서 Aspose.GIS를 구매할 수 있습니다.

## 결론
이 단계들을 따라 하면 이제 .NET용 Aspose.GIS를 사용하여 **십진수 도를 DMS로 변환**하고 다른 일반적인 GIS 형식도 변환하는 방법을 알게 됩니다. 이 기능을 통해 사람이 읽을 수 있는 위치 문자열을 매핑 애플리케이션, 보고서 또는 모든 공간 데이터 워크플로에 원활히 통합할 수 있습니다. 다양한 위도·경도 값을 실험해 보고 `GeoConvert` 클래스가 제공하는 다른 형식도 탐색해 보세요.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 관련 튜토리얼

- [Aspose.GIS for .NET을 사용하여 포인트 지오메트리 생성 및 지오메트리 유형 가져오기](/gis/net/geometry-analysis/get-geometry-type/)
- [GeoJSON 변환 방법 – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Aspose.GIS로 .NET 멀티포인트 지오메트리 생성](/gis/net/geometry-creation/create-multipoint-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}