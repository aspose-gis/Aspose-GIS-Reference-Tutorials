---
title: GIS 숙달 - .NET용 Aspose.GIS를 사용하여 GDB에 레이어 추가
linktitle: 파일 GDB 데이터세트에 레이어 추가
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 사용하여 GIS의 강력한 기능을 활용해 보세요! 이 단계별 튜토리얼에서 File GDB 데이터세트에 레이어를 추가하는 방법을 알아보세요. #지리적 데이터 #Aspose #GIS
weight: 16
url: /ko/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GIS 숙달 - .NET용 Aspose.GIS를 사용하여 GDB에 레이어 추가

## 소개
.NET용 Aspose.GIS를 사용하여 GIS 기능을 향상시킬 준비가 되셨습니까? 이 단계별 가이드에서는 파일 지리 데이터베이스(GDB) 데이터세트에 레이어를 추가하는 과정을 안내합니다. .NET용 Aspose.GIS는 지리 정보를 조작하는 강력한 기능을 제공하며, 이 튜토리얼을 사용하면 추가 레이어를 데이터 세트에 원활하게 통합할 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET 라이브러리용 Aspose.GIS: 다음에서 라이브러리를 다운로드하고 설치하세요.[.NET 문서용 Aspose.GIS](https://reference.aspose.com/gis/net/).
- 문서 디렉터리: GIS 관련 파일을 저장하고 관리하기 위해 컴퓨터에 전용 문서 디렉터리를 만듭니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.GIS 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 다음 코드 조각을 사용하세요.
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
## 1단계: 디렉터리 복사
계속하기 전에 GDB 데이터 세트가 포함된 디렉터리를 복제하세요. 이 단계를 수행하면 원본 데이터세트가 그대로 유지됩니다. 제공된 코드 조각을 사용하세요.
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## 2단계: 데이터세트 열기 및 생성 기능 확인
 복제된 데이터셋을 열어 레이어 생성이 가능한지 확인합니다. 이는 의 존재로 확인됩니다.`True` 콘솔 출력에서.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // 진실
```
## 3단계: 새 레이어 생성 및 채우기
공간 참조 시스템, 속성 및 샘플 기능을 정의하여 데이터세트 내에 새 레이어를 만듭니다. 이 코드 조각은 프로세스를 보여줍니다.
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
## 4단계: 추가된 레이어 열기 및 유효성 검사
방금 생성한 레이어를 열고 해당 콘텐츠를 확인하세요. 다음 코드를 사용하여 개수를 확인하고 속성 값을 검색합니다.
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "이름_1"
}
```
## 결론
축하해요! .NET용 Aspose.GIS를 사용하여 파일 GDB 데이터세트에 레이어를 추가하는 방법을 성공적으로 배웠습니다. 이러한 새로 발견된 기술을 사용하면 GIS 프로젝트에서 지리 데이터를 효율적으로 조작할 수 있습니다.
## 자주 묻는 질문
### Q: Aspose.GIS for .NET을 다른 GIS 라이브러리와 함께 사용할 수 있습니까?
.NET용 Aspose.GIS는 독립적으로 작동하도록 설계되었지만 향상된 기능을 위해 다른 라이브러리와 통합될 수 있습니다.
### Q: 테스트 목적으로 임시 라이센스를 사용할 수 있습니까?
 예, 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 테스트 및 평가를 위해.
### Q: Aspose.GIS for .NET은 어떤 공간 참조 시스템을 지원합니까?
.NET용 Aspose.GIS는 광범위한 공간 참조 시스템을 지원하여 지리 데이터 처리에 유연성을 제공합니다.
### Q: Aspose.GIS 커뮤니티에 기여할 수 있나요?
 전적으로! 토론에 참여하고 경험을 공유하세요.[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33).
### Q: .NET용 Aspose.GIS에 대한 자세한 문서는 어디서 찾을 수 있나요?
 포괄적인 문서 살펴보기[여기](https://reference.aspose.com/gis/net/) .NET용 Aspose.GIS에 대한 자세한 정보를 확인하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
