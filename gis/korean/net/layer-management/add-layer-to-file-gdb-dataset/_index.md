---
date: 2026-01-13
description: Aspose.GIS를 사용하여 파일 GDB 데이터셋에 레이어를 추가하는 방법을 배우세요. 공간 참조 WGS84를 지원합니다.
  .NET에서 GDB에 레이어를 추가하는 단계별 가이드를 따라보세요.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: 공간 참조 WGS84 – Aspose.GIS를 사용하여 GDB에 레이어 추가
url: /ko/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Aspose.GIS를 사용하여 GDB에 레이어 추가

## 소개
Aspose.GIS for .NET으로 GIS 워크플로를 한 단계 끌어올릴 준비가 되셨나요? 이 튜토리얼에서는 **spatial reference wgs84** 좌표계에서 **File GDB 데이터셋에 레이어를 추가하는 방법**을 배웁니다. 데이터 폴더 준비부터 새로 만든 레이어 검증까지 각 단계를 차근차근 안내하므로 지리 데이터를 자신 있게 다룰 수 있습니다.

## 빠른 답변
- **주요 좌표계는 무엇인가요?** spatial reference wgs84 (WGS 84)  
- **어떤 라이브러리가 API를 제공하나요?** Aspose.GIS for .NET  
- **테스트에 라이선스가 필요하나요?** 예 – 임시 Aspose 라이선스를 사용할 수 있습니다.  
- **새 레이어에 속성을 추가할 수 있나요?** 물론입니다. 원하는 만큼의 피처 속성을 정의할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## spatial reference wgs84란?
spatial reference wgs84 (World Geodetic System 1984)는 가장 널리 사용되는 지리 좌표계입니다. 위도와 경도를 도 단위로 정의하며, 이 가이드에서 만들 데이터셋을 포함한 많은 GIS 데이터셋의 기본 CRS 역할을 합니다.

## Aspose.GIS로 레이어를 추가하는 이유
- **외부 종속성 없음:** 순수 .NET 코드만으로 바로 사용할 수 있습니다.  
- **스키마 완전 제어:** 사용자 정의 속성과 기하 유형을 자유롭게 정의할 수 있습니다.  
- **크로스‑플랫폼:** Windows, Linux, macOS 런타임에서 모두 동작합니다.  
- **탄탄한 라이선스 정책:** 임시 라이선스로 빠르게 평가하고 정식 구매를 결정할 수 있습니다.

## 사전 준비
시작하기 전에 다음을 준비하세요:

- Aspose.GIS for .NET 라이브러리: [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/)에서 라이브러리를 다운로드하고 설치합니다.  
- 문서 디렉터리: GIS 파일을 저장할 전용 폴더를 머신에 생성합니다.

## 네임스페이스 가져오기
Aspose.GIS 클래스를 사용하려면 C# 프로젝트에 필요한 `using` 문을 추가합니다:

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

## 단계 1: 디렉터리 복사
원본 GDB 데이터셋이 들어 있는 폴더를 복제합니다. 복사본을 사용하면 실험 중에 원본 데이터를 보호할 수 있습니다.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## 단계 2: 데이터셋 열기 및 레이어 생성 가능 여부 확인
복사한 데이터셋을 열고 새 레이어를 만들 수 있는지 확인합니다. `CanCreateLayers` 속성은 **True**를 반환해야 합니다.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## 단계 3: spatial reference wgs84로 새 레이어 생성 및 채우기
이제 **data**라는 레이어를 만들고 그 spatial reference를 **Wgs84**로 명시적으로 설정합니다. 또한 **Name**이라는 간단한 속성을 추가하고 포인트 피처 하나를 삽입합니다.

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

## 단계 4: 추가된 레이어 열기 및 검증
마지막으로 방금 만든 레이어를 열어 내용을 확인합니다. 콘솔에는 레이어에 피처가 하나 포함되어 있고 **Name** 속성이 우리가 설정한 값과 일치한다는 메시지가 표시됩니다.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## 흔히 발생하는 문제 및 팁
- **경로 오류:** `dataDir`이 경로 구분자(`/` 또는 `\`)로 끝나는지 확인하여 문자열 결합이 올바른 파일 경로를 만들도록 합니다.  
- **라이선스 오류:** 라이선스 경고가 나타나면 코드 실행 전에 Aspose 포털에서 임시 라이선스를 적용하세요.  
- **CRS 불일치:** 다른 GIS 도구에서 레이어를 열 때 해당 도구가 WGS 84 (EPSG:4326)를 좌표계로 인식하는지 확인합니다.

## 자주 묻는 질문
### Q: Aspose.GIS for .NET을 다른 GIS 라이브러리와 함께 사용할 수 있나요?
Aspose.GIS for .NET은 독립적으로 동작하도록 설계되었지만, 기능을 확장하기 위해 다른 라이브러리와 통합할 수 있습니다.  

### Q: 테스트용 임시 라이선스를 받을 수 있나요?
예, [여기](https://purchase.aspose.com/temporary-license/)에서 테스트 및 평가용 임시 라이선스를 받을 수 있습니다.  

### Q: Aspose.GIS for .NET이 지원하는 spatial reference 시스템은 무엇인가요?
Aspose.GIS for .NET은 다양한 spatial reference 시스템을 폭넓게 지원하여 지리 데이터 처리에 유연성을 제공합니다.  

### Q: Aspose.GIS 커뮤니티에 기여할 수 있나요?
물론입니다! [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 토론에 참여하고 경험을 공유하세요.  

### Q: Aspose.GIS for .NET에 대한 자세한 문서는 어디서 찾을 수 있나요?
자세한 내용은 [여기](https://reference.aspose.com/gis/net/)에서 포괄적인 문서를 확인하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-13  
**테스트 환경:** Aspose.GIS for .NET (최신 안정 버전)  
**작성자:** Aspose