---
date: 2026-06-15
description: Aspose.GIS for .NET를 사용하여 벡터 레이어를 생성하고 레이어 공간 참조 시스템을 설정하는 방법을 배웁니다.
  공간 참조 정의, 포인트 피처 추가 및 EPSG 코드를 검색하는 방법을 마스터하세요.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: 레이어 공간 참조 시스템 설정
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 벡터 레이어 생성 및 레이어 공간 참조 시스템 설정
url: /ko/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 벡터 레이어 생성 및 레이어 공간 기준 시스템 설정

## 소개
광범위한 지리 정보 시스템(GIS) 분야에서 **Aspose.GIS for .NET**은 견고하고 고성능의 라이브러리로, **70개 이상의** 벡터 및 래스터 형식을 지원하며 전체 데이터를 메모리에 로드하지 않고도 **10 GB** 이상의 파일을 처리할 수 있습니다. 이 튜토리얼에서는 **벡터 레이어를 생성하고**, 공간 기준을 정의하며, **포인트 피처를 추가하고**, EPSG 코드를 가져오는 방법을 단계별로 명확히 안내합니다. 매핑 서비스, 데이터 변환 파이프라인, 혹은 공간 분석 엔진을 구축하든, 이러한 기본을 숙달하면 shapefile 좌표 시스템을 정확하게 유지하고 GIS 워크플로우를 신뢰할 수 있게 됩니다.

## 빠른 답변
- **“벡터 레이어 생성”이 의미하는 것은?** 새로운 GIS 레이어(예: Shapefile)를 생성하여 포인트, 라인, 폴리곤과 같은 기하학을 저장할 수 있게 합니다.  
- **예제에서 사용된 EPSG 코드는?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **레이어를 만든 후 포인트 피처를 추가할 수 있나요?** 예—`ConstructFeature()`를 사용하고 `Point` 기하학을 할당합니다.  
- **레이어의 CRS를 어떻게 가져오나요?** `layer.SpatialReferenceSystem.EpsgCode` 또는 `.Name`을 읽습니다.  
- **Aspose.GIS에 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 실제 사용에는 라이선스가 필요합니다.

## 벡터 레이어 생성이란?
**벡터 레이어 생성** 작업은 기하학 피처와 속성 데이터를 저장할 수 있는 새로운 벡터 데이터셋(예: Shapefile)을 만듭니다. Aspose.GIS에서는 드라이버와 공간 기준 시스템을 지정하여 `VectorLayer` 객체를 인스턴스화함으로써 수행합니다.

## 레이어 좌표 시스템(CRS)을 올바르게 설정해야 하는 이유
올바른 좌표 기준 시스템(CRS)을 설정하면 저장하는 모든 기하학이 다른 공간 데이터셋과 정렬됩니다. Aspose.GIS를 사용하면 표준 EPSG 코드를 통해 CRS를 정의할 수 있어 전 세계 GIS 소프트웨어와의 상호 운용성을 보장합니다. 예를 들어, EPSG 26918은 미국 동부 지역 데이터에 흔히 사용되는 NAD83 / UTM zone 18N을 정의합니다.

## 전제 조건
- .NET 개발 경험(C# 또는 VB.NET).  
- Visual Studio 2022 이상.  
- Aspose.GIS for .NET 라이브러리 – **[here](https://releases.aspose.com/gis/net/)**에서 다운로드하십시오.  
- 공간 기준 시스템(CRS/EPSG)에 대한 기본 지식.

## 네임스페이스 가져오기
`Aspose.Gis` 네임스페이스는 핵심 GIS 클래스를 제공하고, `Aspose.Gis.Geometries`는 `Point`와 같은 기하학 유형을 제공합니다.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Aspose.GIS for .NET에서 벡터 레이어를 어떻게 생성합니까?
VectorLayer는 Shapefile과 같은 벡터 데이터셋을 나타내며 피처를 생성, 읽기 및 편집하는 메서드를 제공합니다.  
SpatialReferenceSystem은 EPSG 코드를 사용하여 좌표 기준 시스템을 정의합니다.

대상 폴더를 로드하고 EPSG 코드가 지정된 `SpatialReferenceSystem`을 정의한 뒤 Shapefile 드라이버와 함께 `VectorLayer.Create`를 호출합니다. 이 한 번의 호출로 새로운 `.shp` 파일이 생성되고, 관련 `.shx` 및 `.dbf` 파일이 작성되며, CRS 메타데이터가 삽입되어 피처 삽입을 효율적으로 준비합니다.

### 단계 1: 문서 디렉터리 지정
먼저 문서 디렉터리 경로를 지정합니다. 이 위치에 공간 데이터 파일이 저장됩니다.

```csharp
string dataDir = "Your Document Directory";
```

### 단계 2: 공간 기준 정의 및 Shapefile 좌표 시스템 설정
SpatialReferenceSystem은 EPSG 코드로 식별되는 레이어의 CRS를 나타냅니다.  

Shapefile 경로를 정의하고, EPSG 코드(이 예에서는 26918)를 사용하여 **공간 기준을 정의**합니다. 이 단계는 레이어의 **Shapefile 좌표 시스템을 설정**합니다.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## 벡터 레이어에 포인트 피처를 어떻게 추가합니까?
`Point`는 단일 X/Y 좌표 쌍을 나타내는 기하학 유형입니다.  

새 피처를 구성하고 원하는 X/Y 좌표를 가진 `Point` 기하학을 할당한 뒤, 열려 있는 `VectorLayer`에 피처를 추가합니다. 이 작업은 기하학을 `.shp` 파일에, 속성 레코드를 `.dbf` 파일에 한 번의 트랜잭션으로 기록합니다.

### 단계 3: 벡터 레이어 생성
`ConstructFeature`는 기하학 및 속성 데이터를 보유할 수 있는 새로운 피처 객체를 생성합니다.  

이제 지정한 Shapefile 경로, 드라이버 유형(Shapefile) 및 방금 정의한 공간 기준 시스템으로 **벡터 레이어를 생성**합니다.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### 단계 4: 레이어에 포인트 피처 추가
새 피처를 구성하고 기하학을 설정하여 **포인트 피처를 추가**합니다(`Point` 좌표 60, 24). 그런 다음 피처를 벡터 레이어에 추가합니다.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### 단계 5: 공간 기준 시스템 정보 가져오기 (EPSG 코드 조회)
Vector Layer를 열고 EPSG 코드 및 사람이 읽을 수 있는 이름과 같은 공간 기준 시스템 정보를 가져옵니다. 이는 **EPSG 코드를 조회**하고 **레이어 CRS를 설정**하는 방법을 보여줍니다.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|----------|----------|
| **레이어를 열 수 없음** | 잘못된 드라이버 또는 손상된 파일 경로 | `Drivers.Shapefile`을 확인하고 `path`가 존재하는 `.shp` 파일을 가리키는지 확인하십시오. |
| **잘못된 CRS 표시** | 잘못된 EPSG 코드를 사용 | 권위 있는 소스(e.g., EPSG.io)에서 EPSG 코드를 다시 확인하십시오. |
| **피처가 저장되지 않음** | `using` 블록 내부에서 `layer.Add(feature)`를 호출하지 않음 | 레이어가 폐기되기 전에 `Add` 메서드가 실행되었는지 확인하십시오. |

## 자주 묻는 질문
**Q: 기존 Shapefile의 CRS를 어떻게 변경합니까?**  
A: 레이어를 열고 원하는 EPSG 코드를 사용해 새로운 `SpatialReferenceSystem`을 생성한 뒤 `layer.SpatialReferenceSystem`에 할당하고 레이어를 저장합니다.

**Q: 동일한 방법으로 다른 기하학 유형(예: 폴리곤)을 추가할 수 있나요?**  
A: 예—필요에 따라 `new Point(x, y)`를 `new Polygon(...)` 또는 `new LineString(...)`로 교체하면 됩니다.

**Q: 대용량 데이터셋을 효율적으로 작업할 수 있나요?**  
A: 스트리밍 API(`VectorLayer.Create`와 `FeatureCollection` 사용)를 활용하고 레이어를 즉시 폐기하여 리소스를 해제하십시오.

**Q: Aspose.GIS가 좌표 변환을 지원합니까?**  
A: 예—`Geometry.Transform(targetSrs)`를 사용하여 서로 다른 공간 기준 간에 기하학을 재투영할 수 있습니다.

**Q: 지원되는 .NET 버전은 무엇입니까?**  
A: Aspose.GIS는 .NET Framework 4.6 이상, .NET Core 3.1 이상, .NET 5/6/7과 호환됩니다.

---

**마지막 업데이트:** 2026-06-15  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.GIS for .NET을 사용하여 벡터 레이어 생성 및 선형화 허용오차 설정](/gis/net/geometry-processing/set-linearization-tolerance/)
- [File GDB에서 벡터 레이어 생성 – Aspose.GIS .NET 튜토리얼](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Aspose.GIS를 사용하여 GDB에 레이어 추가](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}