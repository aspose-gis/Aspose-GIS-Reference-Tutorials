---
title: .NET용 Aspose.GIS를 사용하여 스트림에서 GeoJSON 읽기
linktitle: 스트림에서 GeoJSON 읽기
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 사용하여 스트림에서 GeoJSON을 읽는 방법을 알아보세요. 지리공간을 귀하의 애플리케이션에 원활하게 통합하려면 당사의 단계별 가이드를 따르십시오.
type: docs
weight: 14
url: /ko/net/layer-data-operations/read-geojson-from-stream/
---
## 소개
.NET용 Aspose.GIS를 사용하여 스트림에서 GeoJSON을 읽는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.GIS는 .NET 애플리케이션에 지리공간 기능을 제공하는 강력한 API로, 다양한 GIS 형식을 원활하게 사용할 수 있습니다. 이 튜토리얼에서는 Aspose.GIS를 사용하여 스트림에서 GeoJSON 데이터를 읽는 과정을 안내하고 명확성과 이해 용이성을 위해 각 단계를 세분화합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. C# 기본 지식: C# 프로그래밍 언어와 해당 구문에 익숙해야 합니다.
2.  Aspose.GIS 설치: .NET용 Aspose.GIS를 설치했는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/gis/net/).
3. 개발 환경: Visual Studio 또는 JetBrains Rider 등 원하는 개발 환경을 설정합니다.

## 네임스페이스 가져오기
시작하려면 C# 코드에 필요한 네임스페이스를 가져오세요.
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## 1단계: GeoJSON 데이터 정의
먼저 C# 코드에서 GeoJSON 데이터를 문자열로 정의해야 합니다. 예를 들어:
```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```
## 2단계: 스트림에서 GeoJSON 읽기
다음으로 Aspose.GIS를 사용하여 스트림에서 GeoJSON 데이터를 읽습니다.
```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // 출력: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // 출력: 메리
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 스트림에서 GeoJSON 데이터를 읽는 방법을 배웠습니다. 위에서 설명한 단계를 따르면 지리공간 기능을 .NET 애플리케이션에 쉽게 통합할 수 있습니다.
## FAQ
### Aspose.GIS는 다른 GIS 형식과 호환됩니까?
예, Aspose.GIS는 GeoJSON, Shapefile, KML 등과 같은 다양한 GIS 형식을 지원합니다.
### 구매하기 전에 Aspose.GIS를 사용해 볼 수 있나요?
 예, 다음에서 Aspose.GIS 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.GIS에 대한 문서는 어디서 찾을 수 있나요?
 Aspose.GIS에 대한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/gis/net/).
### Aspose.GIS에 대한 지원은 어떻게 받을 수 있나요?
 Aspose 포럼에서 Aspose.GIS에 대한 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/gis/33).
### Aspose.GIS를 사용하려면 임시 라이선스가 필요합니까?
 Aspose.GIS에 대한 임시 라이선스는 다음에서 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).