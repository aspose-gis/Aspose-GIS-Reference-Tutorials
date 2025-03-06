---
title: 새 파일 GDB 데이터 세트 생성
linktitle: 새 파일 GDB 데이터 세트 생성
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 탐색하여 GIS 데이터세트를 손쉽게 생성하고 관리하세요. 원활한 지리공간 개발을 위해 지금 다운로드하세요. #Aspose #GIS
weight: 10
url: /ko/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 새 파일 GDB 데이터 세트 생성

## 소개
지리공간 개발 영역에서 .NET용 Aspose.GIS는 지리 정보 시스템(GIS) 데이터를 관리하고 조작하기 위한 강력한 도구 키트로 돋보입니다. 숙련된 개발자이든 이제 막 GIS를 시작하는 개발자이든 이 튜토리얼은 .NET용 Aspose.GIS를 사용하여 새로운 파일 지리 데이터베이스(GDB) 데이터 세트를 생성하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET용 Aspose.GIS: .NET용 Aspose.GIS 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET용 Aspose.GIS 다운로드 페이지](https://releases.aspose.com/gis/net/).
- 개발 환경: Visual Studio와 같은 호환 IDE를 사용하여 개발 환경을 설정하고 .NET 프로그래밍에 대한 기본적인 이해를 갖추고 있습니다.
- 문서 디렉터리: 코드 조각의 "문서 디렉터리"를 GDB 데이터세트를 저장하려는 적절한 경로로 바꿉니다.
- C#에 익숙함: 이 자습서에서는 사용자가 C# 프로그래밍 언어에 익숙하다고 가정합니다.
## 네임스페이스 가져오기
초기 단계에서는 .NET 애플리케이션에서 Aspose.GIS 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1단계: 새 파일 GDB 데이터세트 생성
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // 출력: 0
    // 다음 단계를 계속 진행하세요...
}
```
 설명: 이 단계에서는 다음을 사용하여 새 GDB 데이터 세트를 생성합니다.`Dataset.Create` 방법. 파일 지리 데이터베이스를 생성하기 위해 경로와 드라이버(FileGdb)를 지정합니다. 콘솔 출력에는 현재 0인 초기 레이어 수가 표시됩니다.
## 2단계: Layer_1 생성 및 채우기
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
설명: 이 단계에는 데이터세트 내에 "layer_1"이라는 레이어를 생성하는 작업이 포함됩니다. 정수 유형의 "값"이라는 속성을 정의하고 각각 포인트 도형을 갖는 10개의 피처로 레이어를 채웁니다.
## 3단계: Layer_2 생성 및 채우기
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
설명: 여기서는 "layer_2"라는 두 번째 레이어를 생성하고 라인 스트링 기하학이 있는 단일 기능을 추가합니다.
## 4단계: 업데이트된 레이어 수 확인
```csharp
Console.WriteLine(dataset.LayersCount); // 출력: 2
```
설명: 마지막으로 두 레이어를 추가한 후 업데이트된 레이어 수를 확인합니다. 이 경우 출력은 2가 되어야 합니다.
## 결론
축하해요! 새로운 File GDB 데이터 세트를 성공적으로 생성하고 .NET용 Aspose.GIS를 사용하여 레이어로 채웠습니다. 이 자습서에서는 .NET 환경에서 지리공간 데이터 작업에 대한 기본적인 이해를 제공합니다.
## 자주 묻는 질문
### Q: Aspose.GIS for .NET을 다른 GIS 라이브러리와 함께 사용할 수 있습니까?
.NET용 Aspose.GIS는 독립형 툴킷입니다. 그러나 이를 다른 .NET 라이브러리와 통합하여 기능을 향상시킬 수 있습니다.
### Q: Aspose.GIS 지원을 위한 커뮤니티 포럼이 있습니까?
 예, 다음에서 지원과 토론을 찾을 수 있습니다.[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33).
### Q: Aspose.GIS에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 방문하다[임시면허](https://purchase.aspose.com/temporary-license/) 임시 면허 취득에 대한 정보 페이지입니다.
### Q: 추가 예제와 문서가 제공됩니까?
 탐색[Aspose.GIS 문서](https://reference.aspose.com/gis/net/) 더 많은 예시와 자세한 정보를 확인하세요.
### Q: .NET용 Aspose.GIS를 어디서 구입할 수 있나요?
 .NET용 Aspose.GIS를 다음에서 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
