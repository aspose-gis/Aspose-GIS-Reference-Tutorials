---
title: 단일 레이어로 파일 GDB 생성
linktitle: 단일 레이어로 파일 GDB 생성
second_title: Aspose.GIS .NET API
description: Aspose.GIS를 사용하여 .NET에서 지리공간 데이터 관리의 잠재력을 활용해 보세요. 파일 지리 데이터베이스 및 레이어를 생성하는 방법을 단계별로 알아보세요. 지금 다운로드하세요!
type: docs
weight: 11
url: /ko/net/layer-management/create-file-gdb-with-single-layer/
---
## 소개
강력한 파일 지리 데이터베이스 및 레이어로 지리 공간 애플리케이션을 향상시킬 준비가 되셨습니까? .NET용 Aspose.GIS만 있으면 됩니다. 이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 단일 레이어로 파일 지리 데이터베이스(GDB)를 생성하는 과정을 안내합니다. .NET 애플리케이션에서 공간 데이터 관리 및 시각화 기능을 손쉽게 활용하세요.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.GIS: Aspose.GIS 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET용 Aspose.GIS 다운로드 페이지](https://releases.aspose.com/gis/net/).
2. 개발 환경: 컴퓨터에 작동하는 .NET 개발 환경을 설정합니다.
3. 문서 디렉터리: 지리공간 데이터 파일을 저장할 시스템에서 디렉터리를 선택하거나 생성합니다.
## 네임스페이스 가져오기
시작하려면 .NET 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Aspose.GIS 기능에 대한 액세스를 제공합니다. 코드 파일 시작 부분에 다음 줄을 추가합니다.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## 1단계: 문서 디렉토리 설정
```csharp
string dataDir = "Your Document Directory";
```
"문서 디렉토리"를 지리공간 데이터 파일을 저장하려는 디렉토리 경로로 바꾸십시오.
## 2단계: 단일 레이어로 파일 지리 데이터베이스 생성
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
이 코드 조각은 단일 레이어로 파일 지리 데이터베이스를 생성하고 여기에 라인 기능을 추가합니다.
## 3단계: 파일 지리 데이터베이스 열기 및 레이어 정보 검색
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // 출력: 기능 개수: 1
}
```
이 단계에서는 생성된 파일 지리 데이터베이스를 열고 "layer"라는 레이어를 검색한 다음 레이어의 피처 수를 인쇄합니다.
## 결론
축하해요! .NET용 Aspose.GIS를 사용하여 단일 레이어로 파일 지리 데이터베이스를 성공적으로 생성했습니다. 애플리케이션에서 공간 데이터 관리의 방대한 기능을 쉽게 탐색해 보세요.
## 자주 묻는 질문
### 기존 .NET 프로젝트에서 .NET용 Aspose.GIS를 사용할 수 있나요?
예, .NET용 Aspose.GIS는 기존 .NET 프로젝트에 완벽하게 통합될 수 있습니다.
### .NET용 Aspose.GIS에 사용할 수 있는 평가판이 있습니까?
 예, 다음을 다운로드하여 .NET용 Aspose.GIS의 기능을 탐색할 수 있습니다.[무료 평가판](https://releases.aspose.com/).
### .NET용 Aspose.GIS에 대한 자세한 문서는 어디서 찾을 수 있나요?
 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/gis/net/) .NET용 Aspose.GIS에 대한 포괄적인 정보를 보려면
### .NET용 Aspose.GIS에 대한 지원을 받으려면 어떻게 해야 합니까?
 방문하다[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33) 지역 사회 지원 및 지원을 위해.
### .NET용 Aspose.GIS에 임시 라이센스를 사용할 수 있습니까?
 예, 다음을 얻을 수 있습니다.[임시 면허증](https://purchase.aspose.com/temporary-license/) .NET용 Aspose.GIS용.