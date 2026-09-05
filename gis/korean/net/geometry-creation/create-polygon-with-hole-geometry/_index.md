---
date: 2026-09-05
description: Aspose.GIS for .NET를 사용하여 구멍이 있는 polygon interior ring을 만드는 방법을 배웁니다.
  이 가이드는 polygon에 구멍을 추가하고 데이터를 다루는 방법을 보여줍니다.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: 구멍이 있는 Polygon Geometry 만들기
og_description: Aspose.GIS for .NET를 사용하여 구멍이 있는 polygon interior ring을 만드는 방법을 배웁니다.
  이 가이드는 polygon에 구멍을 추가하고 데이터를 다루는 방법을 보여줍니다.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Aspose.GIS를 사용하여 구멍이 있는 polygon interior ring 만들기
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Aspose.GIS를 사용하여 구멍이 있는 polygon interior ring 만들기
url: /ko/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용하여 구멍이 있는 폴리곤 내부 링 만들기

## 소개
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 구멍이 포함된 **폴리곤 내부 링**을 만드는 방법을 배웁니다. 매핑 애플리케이션을 구축하든, 공간 분석을 수행하든, GIS 서비스용 데이터를 준비하든, 폴리곤 내부에 구멍을 삽입하는 것은 핵심 기술입니다. 개발 환경 설정부터 지원되는 모든 지리공간 형식으로 저장할 수 있는 유효한 폴리곤 객체를 생성하는 전체 워크플로우를 단계별로 안내합니다.

## 빠른 답변
- **“구멍이 있는 폴리곤 만들기”가 무엇을 의미하나요?** 이는 영역에서 제외되는 하나 이상의 내부 링(구멍)을 포함하는 폴리곤을 만드는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리하나요?** Aspose.GIS for .NET은 외부 및 내부 링에 대한 완전한 지원을 제공합니다.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판으로 충분하지만, 프로덕션에서는 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **소요 시간은 얼마나 되나요?** 구현 및 테스트는 일반적으로 10분 미만입니다.  

## Aspose.GIS를 사용하여 폴리곤에 구멍 추가하는 방법
GIS 환경을 로드하고 외부 링을 정의한 다음 하나 이상의 내부 링을 연결합니다. Aspose.GIS는 링의 방향을 자동으로 맞추고 기하학을 검증하므로, 필요한 빈 공간을 나타내는 좌표에 집중할 수 있습니다.

## 폴리곤 내부 링이란?
**폴리곤 내부 링**은 폴리곤 외부 형태에서 면적을 빼는 내부 경계입니다.  
Aspose.GIS가 구멍으로 인식하는 닫힌 점 시퀀스를 정의함으로써 이를 생성하며, 면적 계산이나 형태 렌더링 시 제외됩니다.

## 왜 Aspose.GIS를 사용해 폴리곤 내부 링을 만들까요?
Aspose.GIS는 일반적인 200점 폴리곤에 대해 5 ms 미만으로 링 방향을 검증하고 수정하여 사용자 정의 검증 코드를 없앨 수 있습니다. 또한 **30개 이상의 지리공간 파일 형식**(Shapefile, GeoJSON, GML, KML 등)을 지원하고 전체 파일을 메모리에 로드하지 않고도 최대 10,000점까지의 폴리곤을 처리할 수 있어 속도와 확장성을 모두 제공합니다.

## 구멍이 있는 폴리곤의 실제 시나리오
1. **내부 호수가 있는 토지 구획** – 호수를 구멍으로 모델링하여 구획 면적에 포함되지 않게 합니다.  
2. **중정이 있는 건물 외곽선** – 중정은 건물 외곽선에서 제외됩니다.  
3. **더 큰 보전 지역 내의 보호 구역** – 별도의 레이어를 만들지 않고 제한 구역을 제외할 수 있습니다.  

## 사전 요구 사항
시작하기 전에 다음 사전 요구 사항을 확인하십시오:
1. Aspose.GIS for .NET 라이브러리: **Aspose.GIS for .NET 다운로드 페이지**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/))에서 다운로드할 수 있습니다.  
2. 개발 환경: Visual Studio 또는 기타 .NET IDE가 설치된 개발 환경이 준비되어 있는지 확인하십시오.

## 네임스페이스 가져오기
`Aspose.Gis` 네임스페이스에는 `Polygon`, `LinearRing` 및 검증을 위한 도우미 메서드를 포함한 모든 기하학 유형이 포함되어 있습니다.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이제 Aspose.GIS for .NET을 사용하여 구멍이 있는 폴리곤 기하학을 생성해 보겠습니다.

## 단계 1: 폴리곤 객체 생성
`Polygon`은 선택적 내부 링을 포함할 수 있는 평면 폴리곤을 나타내는 Aspose.GIS의 기하학 유형입니다. 외부와 내부 링을 모두 보유할 빈 `Polygon` 객체를 인스턴스화하는 것으로 시작합니다.

```csharp
Polygon polygon = new Polygon();
```

## 단계 2: 외부 링 정의
`LinearRing`은 외부 및 내부 경계 모두에 사용되는 클래스입니다. 외부 링은 폴리곤의 외곽 경계를 정의합니다. 시계 방향으로 점을 추가하여 닫힌 형태를 만듭니다.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 단계 3: 내부 링 정의 (구멍)
`LinearRing`은 내부 링도 나타냅니다. 내부 링은 폴리곤 면적에서 제외되는 **구멍**입니다. 점은 일반적으로 반시계 방향으로 추가되지만, Aspose.GIS가 자동으로 방향을 처리합니다.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 단계 4: 외부 링 할당 및 폴리곤에 내부 링 추가
`AddInteriorRing` 메서드는 하나 이상의 내부 링을 `Polygon`에 연결합니다. `ExteriorRing` 속성을 설정한 후 호출하십시오; 여러 구멍을 추가하려면 메서드를 반복 호출할 수 있습니다.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 팁 및 모범 사례
- **방향은 가독성에 중요합니다** – Aspose.GIS가 자동으로 방향을 교정하지만, 외부 링을 시계 방향, 내부 링을 반시계 방향으로 유지하면 GIS 뷰어에서 기하학을 더 쉽게 확인할 수 있습니다.  
- **각 링을 닫으세요** – 첫 번째 좌표를 마지막 점으로 항상 반복하십시오; 이렇게 하면 유효한 닫힌 형태가 보장됩니다.  
- **생성 후 검증** – 저장하기 전에 `polygon.IsValid`를 호출하여 기하학이 OGC 표준을 준수하는지 확인할 수 있습니다.  

## 일반적인 문제와 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| GIS 뷰어에 구멍이 표시되지 않음 | 내부 링 방향이 반대로 설정됨 | 외부 링과 반대 방향(반시계)으로 점을 추가하십시오. |
| 폴리곤 무효 오류 | 링이 닫히지 않음(첫 번째 ≠ 마지막 점) | 각 링에서 첫 번째 점을 마지막 점으로 반복하십시오(위와 같이). |
| 예상치 못한 빈 기하학 | 내부 링을 추가하기 전에 `ExteriorRing`을 할당하지 않음 | `polygon.ExteriorRing`을 먼저 설정한 다음 `AddInteriorRing`을 호출하십시오. |

## 자주 묻는 질문
### 1. Aspose.GIS란?
Aspose.GIS는 개발자가 지리공간 데이터를 다룰 수 있도록 하는 .NET 라이브러리로, 다양한 지리공간 파일 형식을 생성, 읽기 및 조작할 수 있게 해줍니다.

### 2. Aspose.GIS를 상업 프로젝트에 사용할 수 있나요?
예, 라이선스를 구매하면 개인 및 상업 프로젝트 모두에 Aspose.GIS를 사용할 수 있습니다. 자세한 내용은 **Aspose.GIS 구매 페이지**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy))를 방문하십시오.

### 3. Aspose.GIS 무료 체험판이 있나요?
예, **Aspose.GIS 무료 체험판 다운로드 페이지**([https://releases.aspose.com/](https://releases.aspose.com/))에서 무료 체험판을 이용할 수 있습니다.

### 4. Aspose.GIS 지원을 어디서 찾을 수 있나요?
Aspose.GIS에 대한 지원은 [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 찾을 수 있습니다.

### 5. Aspose.GIS 임시 라이선스를 어떻게 얻을 수 있나요?
Aspose.GIS 임시 라이선스는 **Aspose.GIS 임시 라이선스 페이지**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/))에서 얻을 수 있습니다.

---

**마지막 업데이트:** 2026-09-05  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.GIS for .NET을 사용하여 폴리곤 기하학 만들기](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aspose.GIS를 사용하여 MultiPolygon 기하학 만드는 방법 배우기](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Aspose.GIS for .NET을 사용하여 폴리곤을 라인으로 변환하기](/gis/net/geometry-processing/replace-polygons-with-lines/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}