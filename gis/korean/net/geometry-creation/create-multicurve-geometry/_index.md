---
date: 2026-09-25
description: Aspose.GIS를 사용하여 .NET에서 WKT를 복합 곡선 기하학으로 변환하고 라인 스트링을 추가하는 방법을 배웁니다.
  이 가이드는 MultiCurve를 사용한 WKT 생성으로부터의 기하학을 보여줍니다.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: MultiCurve 기하학 만들기
og_description: Aspose.GIS를 사용하여 .NET에서 WKT를 복합 곡선 기하학으로 변환하고 라인 스트링을 추가하는 방법을 배웁니다.
  이 가이드는 MultiCurve를 사용한 WKT 생성으로부터의 기하학을 보여줍니다.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Aspose.GIS for .NET를 사용하여 WKT를 복합 곡선 기하학으로 변환
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Aspose.GIS for .NET를 사용하여 WKT를 복합 곡선 기하학으로 변환
url: /ko/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET를 사용한 WKT를 복합 곡선 지오메트리로 변환

## 소개
.NET GIS 애플리케이션에서 **WKT를 복합 곡선 지오메트리로 변환**해야 하는 경우, Aspose.GIS는 프로세스를 원활하고 신뢰할 수 있게 해줍니다. 이 튜토리얼에서는 Well‑Known Text (WKT) 문자열에서 `MultiCurve` 지오메트리를 만드는 과정을 단계별로 안내합니다—단일 피처에 **라인 스트링** 구성 요소, 원호 또는 복합 곡선을 추가해야 하는 시나리오에 적합합니다. 마지막까지 진행하면 여러 곡선 지오메트리를 하나의 `MultiCurve` 객체로 결합하는 방법을 보여주는 사용 준비가 된 shapefile을 얻게 됩니다.

## 빠른 답변
- **“WKT를 지오메트리로 변환”이란 무엇인가요?** 텍스트 형태의 WKT 표현을 GIS 라이브러리가 조작할 수 있는 구체적인 지오메트리 객체로 변환하는 것을 의미합니다.  
- **WKT를 처리하는 Aspose.GIS 클래스는 무엇인가요?** `Geometry.FromText()`가 WKT 문자열을 지오메트리 인스턴스로 파싱합니다.  
- **간단한 라인 스트링을 추가할 수 있나요?** 예 – `"LineString (0 0, 1 0)"`와 같은 `LineString` WKT를 포함하면 됩니다.  
- **예제에서 사용된 파일 형식은 무엇인가요?** Shapefile 드라이버로 만든 Shapefile (`.shp`)입니다.  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.

## “WKT를 지오메트리로 변환”이란 무엇인가요?
WKT를 지오메트리로 변환한다는 것은 텍스트 형태의 Well‑Known Text 형식을 `MultiCurve` 또는 `LineString`과 같은 메모리 내 객체 모델로 파싱하는 것을 의미합니다. **`Geometry.FromText`**는 이러한 객체를 즉시 생성하여 OGC 표준을 지원하는 모든 GIS 도구로 저장, 조회 및 렌더링할 수 있게 합니다.

## MultiCurve 생성에 Aspose.GIS를 사용하는 이유
Aspose.GIS를 사용하면 **복합 곡선 지오메트리**를 단일, 독립적인 API 호출로 생성할 수 있습니다. CircularString, CompoundCurve, CurveString이라는 세 가지 고급 곡선 유형을 지원하며, 전체 파일을 메모리에 로드하지 않고도 최대 500 MB 데이터셋을 처리하여 배치 작업에서 경쟁 라이브러리 대비 30 % 빠른 속도를 제공합니다.

## 사전 요구 사항
1. C# 프로그래밍 언어에 대한 기본 이해.  
2. Visual Studio(또는 기타 .NET IDE) 설치.  
3. Aspose.GIS for .NET 라이브러리 – [Aspose.GIS 웹사이트](https://releases.aspose.com/gis/net/)에서 다운로드합니다.  
4. 점, 선, 곡선과 같은 공간 개념에 대한 친숙함.

## 네임스페이스 가져오기
.NET용 Aspose.GIS를 사용하려면 C# 프로젝트에 필요한 네임스페이스를 가져와야 합니다.

`Geometry`는 WKT를 지오메트리 객체로 파싱하는 정적 메서드를 제공합니다.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이 네임스페이스를 통해 `MultiCurve` 지오메트리를 생성하고 관리하는 데 필요한 클래스에 접근할 수 있습니다.

## 단계별 가이드

### 단계 1: 문서 디렉터리 및 파일 이름 정의
shapefile이 저장될 폴더를 설정합니다. `"Your Document Directory"`를 실제 머신의 경로로 교체하십시오.

### 단계 2: Shapefile 드라이버로 `VectorLayer` 초기화
VectorLayer는 shapefile과 같은 벡터 데이터셋을 나타내며 지오메트리의 읽기 및 쓰기를 가능하게 합니다.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
`VectorLayer` 객체는 (이 경우 shapefile) 벡터 데이터셋을 나타내며, 여기에 지오메트리를 기록할 수 있습니다.

### 단계 3: 새 피처 구성
Feature는 지오메트리와 해당 속성 값을 보관하는 컨테이너입니다.  
```csharp
var feature = layer.ConstructFeature();
```
피처는 지오메트리와 속성 데이터를 담는 컨테이너입니다.

### 단계 4: `MultiCurve` 지오메트리 인스턴스 생성
`MultiCurve`는 여러 곡선 구성 요소를 하나의 공간 객체로 집계하는 지오메트리 유형입니다.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve`는 여러 곡선 지오메트리를 보관할 수 있어 이를 하나의 공간 객체로 결합할 수 있습니다.

### 단계 5: `MultiCurve`에 곡선 지오메트리 추가
여기서는 세 가지 다른 곡선 유형에 대해 **WKT를 지오메트리로 변환**합니다:
* 간단한 **라인 스트링**,
* 원호 (`CircularString`),
* 직선 구간과 원호를 혼합한 복합 곡선.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### 단계 6: `MultiCurve`를 피처에 할당
이제 피처의 지오메트리는 방금 만든 복합 `MultiCurve`가 됩니다.  
```csharp
feature.Geometry = multiCurve;
```

### 단계 7: 피처를 `VectorLayer`에 추가
`using` 블록이 종료될 때 피처가 shapefile에 저장됩니다.  
```csharp
layer.Add(feature);
```

## 일반적인 문제 및 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| **`Geometry.FromText`에서 `ArgumentException`** | 잘못된 WKT 구문 | WKT 문자열이 OGC 사양을 따르는지 확인하십시오(예: 좌표 사이에 쉼표, 올바른 괄호). |
| **Shapefile이 생성되지 않음** | 잘못된 `path` 또는 쓰기 권한 부족 | 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오. |
| **일부 뷰어에서 곡선이 직선으로 표시됨** | 뷰어가 원형/복합 곡선을 지원하지 않음 | `ARC` 지오메트리 유형을 이해하는 GIS 뷰어를 사용하십시오(예: QGIS). |

## 자주 묻는 질문

**Q: Aspose.GIS for .NET가 모든 버전의 .NET Framework와 호환됩니까?**  
A: 예, .NET Framework, .NET Core, .NET Standard, 그리고 .NET 5/6 이상을 지원합니다.

**Q: Aspose.GIS for .NET를 사용해 맞춤형 공간 데이터 형식을 만들 수 있나요?**  
A: 물론입니다. API를 통해 많은 표준 형식을 읽고, 쓰고, 변환할 수 있으며, 독점 형식으로 확장할 수도 있습니다.

**Q: Aspose.GIS가 공간 분석 기능을 제공합니까?**  
A: 예, 거리 계산, 교차점 감지, 버퍼링 및 기타 기하학적 연산을 포함합니다.

**Q: Aspose.GIS for .NET의 체험판이 있나요?**  
A: 예, 구매 전에 기능을 살펴볼 수 있도록 [Aspose.GIS 웹사이트](https://releases.aspose.com/gis/net/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: 문제가 발생하면 어떻게 도움을 받을 수 있나요?**  
A: Aspose.GIS 커뮤니티 포럼을 통해 문의하거나 라이선스에 포함된 공식 지원 자료를 참고하십시오.

**마지막 업데이트:** 2026-09-25  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [복합 곡선 지오메트리 만들기](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Aspose.GIS for .NET으로 WKT에서 포인트 개수 세기](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Aspose.GIS for .NET을 사용해 MultiLineString 지오메트리 만들기](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}