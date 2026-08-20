---
date: 2026-06-30
description: Aspose.GIS를 사용하여 WGS84 공간 참조가 있는 File GDB 데이터셋에 레이어를 추가하는 방법을 배웁니다. .NET에서
  레이어를 추가하는 단계별 가이드를 따라 보세요.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: File GDB 데이터셋에 레이어 추가
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS를 사용하여 WGS84 공간 참조가 있는 File GDB 데이터셋에 레이어 추가하는 방법
url: /ko/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 레이어 추가 방법 – 공간 기준 wgs84와 Aspose.GIS

## 소개
Aspose.GIS for .NET와 함께 GIS 워크플로를 향상시킬 준비가 되셨나요? 이 튜토리얼에서는 **레이어 추가 방법**을 배우게 되며, **spatial reference WGS84** 좌표계와 함께 File GDB 데이터셋에 레이어를 추가하는 방법을 다룹니다. 데이터 폴더 준비부터 새로 만든 레이어 검증까지 각 단계를 차근차근 안내하므로, 지리 데이터를 자신 있게 효율적으로 다룰 수 있습니다.

## 빠른 답변
- **주요 좌표계는 무엇입니까?** spatial reference wgs84 (WGS 84)  
- **어떤 라이브러리가 API를 제공합니까?** Aspose.GIS for .NET  
- **테스트에 라이선스가 필요합니까?** 예 – 임시 Aspose 라이선스를 사용할 수 있습니다.  
- **새 레이어에 속성을 추가할 수 있나요?** 물론이며, 원하는 만큼의 피처 속성을 정의할 수 있습니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## spatial reference wgs84란?
spatial reference wgs84 (World Geodetic System 1984)는 가장 널리 사용되는 지리 좌표계입니다. 위도와 경도를 도 단위로 정의하며, 많은 GIS 데이터셋의 기본 CRS로 사용됩니다. 이 가이드에서 생성할 데이터셋도 기본적으로 이 좌표계를 사용합니다.

## 레이어 추가에 Aspose.GIS를 사용하는 이유
타사 바이너리 없이 GIS 데이터를 로드하고 스키마 정의를 완전하게 제어할 수 있습니다. Aspose.GIS는 **40개 이상의 spatial reference 시스템**을 지원하고, **2 GB** 이상의 파일도 전체 데이터를 메모리에 로드하지 않고 처리할 수 있으며, Windows, Linux, macOS에서 실행됩니다. 따라서 엔터프라이즈 수준 GIS 자동화에 신뢰할 수 있는 크로스‑플랫폼 솔루션입니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하십시오:

- Aspose.GIS for .NET Library: [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/)에서 라이브러리를 다운로드하고 설치합니다.  
- Document Directory: GIS 파일을 저장할 전용 폴더를 머신에 생성합니다.  
- 임시 Aspose 라이선스(평가용 선택 사항) – 다운로드 링크는 아래 FAQ를 참고하십시오.

## 네임스페이스 가져오기
C# 프로젝트에서 Aspose.GIS 클래스를 사용하려면 필요한 `using` 문을 추가하십시오:

*코드 블록이 필요하지 않으며, 파일 상단에 다음 줄을 추가하면 됩니다:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## 단계 1: 디렉터리 복사
**Definition anchor:** File GDB 데이터셋은 파일 기반 ESRI 지오데이터베이스로, 공간 데이터를 여러 파일에 저장합니다.  
먼저 원본 GDB 데이터셋이 들어 있는 폴더를 복제합니다. 복사본을 유지하면 실험 중에 원본 데이터를 보호할 수 있습니다.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 단계 2: 데이터셋 열기 및 생성 가능성 확인
`Dataset`은 File GDB에 저장된 GIS 레이어 컬렉션을 나타냅니다. 복제한 데이터셋을 열고 새 레이어를 생성할 수 있는지 확인하십시오. `CanCreateLayers` 속성은 **True**를 반환해야 합니다. **`CanCreateLayers`는 데이터셋이 새 레이어 생성을 지원하는지 여부를 나타내는 부울 속성입니다.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## 단계 3: spatial reference wgs84와 함께 새 레이어 생성 및 채우기
이제 **data**라는 이름의 레이어를 만들고, 공간 기준을 **Wgs84**로 명시적으로 설정합니다. 또한 **Name**이라는 간단한 속성을 추가하고 포인트 피처 하나를 삽입합니다. **`CreateLayer`는 지정된 이름과 spatial reference를 사용해 데이터셋에 새 레이어를 생성합니다.** **`SpatialReference`는 레이어가 사용하는 좌표계를 나타냅니다.** **`Feature`는 레이어에 저장되는 개별 지리 객체(점, 선, 폴리곤)입니다.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## 단계 4: 추가된 레이어 열기 및 검증
마지막으로 방금 만든 레이어를 열어 내용물을 확인합니다. 콘솔에 레이어에 피처가 하나 포함되어 있고 **Name** 속성이 우리가 설정한 값과 일치한다는 메시지가 표시됩니다. **`Layer.Open`은 기존 레이어를 읽기 또는 편집용으로 엽니다.** 이를 통해 레이어가 올바르게 추가되었으며 spatial reference가 WGS84임을 확인할 수 있습니다.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## File GDB 데이터셋에 레이어를 추가하는 방법
데이터셋을 로드하고, 원하는 이름과 spatial reference를 지정해 `CreateLayer`를 호출한 뒤, 속성 스키마를 정의하고 피처를 삽입합니다. 이 모든 작업은 몇 번의 Aspose.GIS 메서드 호출만으로 수행되며, API가 파일 잠금 및 스키마 검증을 자동으로 처리합니다. 이 과정은 새 레이어가 데이터셋의 spatial reference에 맞게 생성되고, 속성 정의가 레이어 스키마에 저장되며, File GDB를 지원하는 모든 GIS 소프트웨어에서 데이터를 사용할 수 있도록 보장합니다.

## 일반적인 문제 및 팁
- **잘못된 경로:** `dataDir`이 경로 구분자(`/` 또는 `\`)로 끝나는지 확인하여 문자열 결합이 유효한 파일 경로를 형성하도록 합니다.  
- **라이선스 오류:** 라이선스 경고가 표시되면 코드를 실행하기 전에 Aspose 포털에서 임시 라이선스를 적용하십시오.  
- **CRS 불일치:** 다른 GIS 도구에서 레이어를 열 때 해당 도구가 WGS 84 (EPSG:4326)를 좌표계로 인식하는지 확인하십시오.  
- **대용량 데이터셋:** 데이터셋 크기가 1 GB를 초과하는 경우 `Dataset.OpenReadOnly`를 사용해 메모리 사용량을 줄이는 것을 고려하십시오.

## 자주 묻는 질문

### Q: Aspose.GIS for .NET를 다른 GIS 라이브러리와 함께 사용할 수 있나요?
A: 예, Aspose.GIS는 독립적으로 동작하지만 GDAL이나 NetTopologySuite와 같은 라이브러리와 결합해 고급 처리를 수행할 수 있습니다.

### Q: 테스트용 임시 라이선스를 제공하나요?
A: 예, 테스트 및 평가를 위해 [여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 얻을 수 있습니다.

### Q: Aspose.GIS for .NET가 지원하는 spatial reference 시스템은 무엇인가요?
A: Aspose.GIS는 **40개 이상의 EPSG 코드**를 지원하며, WGS84 (EPSG:4326), Web Mercator (EPSG:3857), NAD83 (EPSG:4269) 등 인기 있는 시스템을 포함합니다. 자세한 내용은 [여기](https://reference.aspose.com/gis/net/)에서 확인하십시오.

### Q: Aspose.GIS 커뮤니티에 기여할 수 있나요?
A: 물론입니다! [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 토론에 참여하고 경험을 공유하십시오.

### Q: Aspose.GIS for .NET에 대한 자세한 문서는 어디서 찾을 수 있나요?
A: 모든 클래스, 메서드 및 모범 사례에 대한 심층 정보를 제공하는 포괄적인 문서는 [여기](https://reference.aspose.com/gis/net/)에서 확인하십시오.

---

**마지막 업데이트:** 2026-06-30  
**테스트 환경:** Aspose.GIS for .NET (최신 안정 버전)  
**작성자:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## 관련 튜토리얼

- [Aspose.GIS로 파일 지오데이터베이스 .NET 데이터셋 만들기](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [File GDB에서 벡터 레이어 만들기 – Aspose.GIS .NET 튜토리얼](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [File GDB 데이터셋 만들고 레이어에 대한 공차 설정](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}