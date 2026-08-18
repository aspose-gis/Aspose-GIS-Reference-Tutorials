---
date: 2026-06-10
description: Aspose.GIS for .NET와 ExtendedPostGis Variant를 사용하여 .NET에서 linestring
  geometry를 생성하고 geometry를 WKB로 변환하는 방법을 배웁니다.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: 번역 시 WKB Variant 지정
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET에서 Linestring Geometry 및 WKB Variant 생성
url: /ko/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET에서 라인스트링 지오메트리 및 WKB 변형 만들기

## 소개
**create linestring geometry .NET**을(를) 생성하고 해당 지오메트리를 바이너리 형태로 변환해야 한다면, Aspose.GIS for .NET은 .NET Framework, .NET Core, 그리고 .NET 5/6+에서 작동하는 깔끔하고 고성능 API를 제공합니다. 이 튜토리얼에서는 네임스페이스 가져오기부터 EWKB 파일 쓰기까지 모든 단계를 단계별로 안내하므로 SRID 정보를 보존하고 GIS 데이터를 PostgreSQL/PostGIS 또는 바이너리 기반 워크플로에 손쉽게 통합할 수 있습니다.

## 빠른 답변
- **WKB는 무엇을 의미합니까?** Well‑Known Binary, 기하 객체의 압축 바이너리 표현입니다.  
- **어떤 WKB 변형이 SRID를 저장합니까?** `ExtendedPostGis` (EWKB) 변형은 SRID를 바이너리 내부에 직접 포함합니다.  
- **라이선스가 필요합니까?** 프로덕션 배포에는 임시 또는 정식 Aspose.GIS 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, 그리고 .NET 5/6+.  
- **구현에 얼마나 걸립니까?** 기본 예제의 경우 일반적으로 10분 미만이 소요됩니다.

## 라인스트링 지오메트리란?
라인스트링 지오메트리는 순서가 지정된 점들의 리스트를 직선 구간으로 연결하여 만든 단순한 형태입니다. 도로, 파이프라인, 강 경로와 같은 선형 피처를 공간 데이터베이스에 표현할 때 주로 사용됩니다.

## 왜 WKB 변형을 지정해야 할까요?
올바른 WKB 변형을 사용하면 중요한 메타데이터, 특히 공간 참조 시스템 식별자(SRID)가 지오메트리와 함께 전달됩니다. `ExtendedPostGis` (EWKB) 변형은 SRID를 바이너리 페이로드에 저장하므로 PostGIS, Oracle Spatial, 또는 SRID‑인식 바이너리를 기대하는 모든 시스템과 원활하게 라운드‑트립할 수 있습니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하십시오:

### Aspose.GIS for .NET 설치
1. Aspose.GIS 다운로드: 최신 패키지를 받으려면 [download link](https://releases.aspose.com/gis/net/)를 방문하십시오.  
2. 프로젝트에 NuGet 패키지를 추가합니다(예: `Install-Package Aspose.GIS`).  

### C# 프로그래밍에 대한 친숙도
- C# 구문 및 프로젝트 구조에 대한 기본 이해.  
- .NET 콘솔 또는 클래스‑라이브러리 프로젝트를 실행할 수 있는 능력.

## 네임스페이스 가져오기
`Aspose.GIS` 네임스페이스는 모든 지오메트리 관련 클래스를 사용할 수 있게 해줍니다.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이 네임스페이스들은 지오메트리 생성, 변환 및 바이너리 직렬화를 포함한 핵심 GIS 기능을 제공합니다.

## 라인스트링 지오메트리를 만드는 방법은?
라인스트링을 만들려면 순서가 지정된 좌표 쌍 리스트로 `Linestring` 객체를 인스턴스화하고, 필요하면 SRID를 설정한 뒤 원하는 WKB 변형으로 직렬화합니다. 이 과정은 세 단계로 이루어집니다: 지오메트리 구축, SRID 보존을 위한 `ExtendedPostGis` 변형 선택, 그리고 결과 바이트 배열을 파일에 쓰기.

### 단계 1: 지오메트리 객체 생성
`Geometry` 클래스는 메모리 내의 모든 공간 객체를 나타내는 Aspose.GIS의 기본 타입입니다.  
라인스트링은 연결된 점들의 연속으로 선형 지오메트리를 형성합니다.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
이 단계에서는 간단한 도로 구간을 모델링하는 좌표 쌍 컬렉션으로 `Linestring`을 인스턴스화합니다.

### 단계 2: WKB 표현 생성
`WkbVariant.ExtendedPostGis`는 Aspose.GIS에 SRID를 포함한 바이너리를 출력하도록 지시하는 열거형 값입니다.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
여기서는 `AsBinary` 메서드를 호출하면서 EWKB 변형을 전달하고, 전체 바이너리 표현을 담은 `byte[]`를 반환받습니다.

### 단계 3: 파일에 쓰기
`File.WriteAllBytes`는 바이너리 배열을 디스크에 씁니다.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
생성된 파일(`EWkbFile.ewkb`)은 `ST_GeomFromEWKB` 함수를 사용해 PostGIS 테이블에 직접 가져올 수 있습니다.

## 일반적인 문제와 해결책
| 문제 | 이유 | 해결책 |
|-------|--------|----------|
| **빈 파일** | `Path.Combine`가 존재하지 않는 디렉터리를 가리킵니다. | 대상 디렉터리가 존재하는지 확인하거나 `Directory.CreateDirectory`로 생성하십시오. |
| **잘못된 SRID** | 기본 `WkbVariant.Standard`를 사용하면 SRID가 누락됩니다. | SRID 보존이 필요할 때는 항상 `WkbVariant.ExtendedPostGis`를 사용하십시오. |
| **라이선스 예외** | 프로덕션 환경에서 유효한 라이선스 없이 실행합니다. | 프로덕션 환경에서 코드를 실행하기 전에 임시 또는 정식 라이선스를 적용하십시오. |

## 자주 묻는 질문
**Q: EWKB 파일을 PostGIS와 함께 사용할 수 있나요?**  
A: 네, `ExtendedPostGis` 변형은 SRID를 포함한 EWKB를 생성하며, PostGIS는 `ST_GeomFromEWKB`를 통해 이를 직접 읽을 수 있습니다.  

**Q: WKB 파일을 다시 지오메트리 객체로 읽을 수 있나요?**  
A: 물론입니다. `Geometry.FromBinary(byteArray)`를 사용하면 바이너리 형태에서 지오메트리를 재구성할 수 있습니다.  

**Q: 라이브러리가 폴리곤과 같은 다른 지오메트리 타입을 지원하나요?**  
A: 예, Aspose.GIS는 포인트, 라인스트링, 폴리곤, 멀티폴리곤 등 다양한 공간 타입을 처리합니다.  

**Q: 지오메트리를 만들 때 다른 SRID를 지정하려면 어떻게 해야 하나요?**  
A: `AsBinary`를 호출하기 전에 지오메트리 객체의 `SRID` 속성을 설정하면 됩니다. 예: `linestring.SRID = 4326;`.  

**Q: 이 코드는 .NET Core에서도 작동하나요?**  
A: 네, 동일한 API가 .NET Framework, .NET Core, 그리고 .NET 5/6 전반에 걸쳐 수정 없이 작동합니다.

---

**마지막 업데이트:** 2026-06-10  
**테스트 환경:** Aspose.GIS for .NET 23.9 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.GIS for .NET을 사용한 지오메트리 WKB 형식 변환](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Aspose.GIS를 사용한 변환 시 WKT 변형 지정](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Aspose.GIS for .NET을 사용한 MultiLineString 지오메트리 만들기](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}