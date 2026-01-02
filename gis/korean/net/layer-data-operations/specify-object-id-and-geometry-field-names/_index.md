---
date: 2026-01-02
description: Aspose.GIS for .NET를 사용하여 필드 이름을 설정하고 객체 ID를 읽으면서 포인트 피처를 추가하는 방법을 배웁니다.
  개발자를 위한 단계별 가이드.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: 포인트 피처 추가 및 객체 ID와 지오메트리 필드 이름 지정
url: /ko/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 포인트 피처 추가 및 Object ID와 Geometry 필드 이름 지정

## 소개
Aspose.GIS for .NET을 사용하여 지리 정보 시스템(GIS)의 세계에 발을 들여놓으면 개발자와 애호가 모두에게 다양한 가능성이 열립니다. 이 튜토리얼에서는 **포인트 피처를 추가**하고 **필드 이름을 설정**하며 **Object ID** 값을 **읽는 방법**을 배워, 공간 데이터를 완벽히 제어할 수 있게 됩니다.

## 빠른 답변
- **이 가이드의 주요 목적은 무엇인가요?** 포인트 피처를 추가하고 Object ID와 Geometry 필드 이름을 구성하는 방법을 보여줍니다.  
- **사용된 라이브러리는?** Aspose.GIS for .NET.  
- **라이선스가 필요한가요?** 무료 체험판을 사용할 수 있으며, 프로덕션 환경에서는 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **삽입 후 Object ID를 읽을 수 있나요?** 예 – 튜토리얼에서 레이어에서 Object ID를 읽는 방법을 시연합니다.

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음 요구 사항을 준비하세요:
- Aspose.GIS for .NET: [여기](https://releases.aspose.com/gis/net/)에서 라이브러리를 다운로드하고 설치합니다.
- 문서 디렉터리: 지오데이터베이스를 저장할 디렉터리를 설정합니다.
- .NET 환경: 정상적인 .NET 환경이 구성되어 있는지 확인합니다.

## 네임스페이스 가져오기
프로젝트에 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Aspose.GIS for .NET과 상호 작용하기 위한 핵심 클래스와 메서드를 제공합니다.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## 단계 1: 포인트 피처 추가 및 Object ID와 Geometry 필드 이름 지정
이 단계에서는 GIS 데이터에 대한 Object ID와 Geometry 필드 이름을 설정하는 방법을 배웁니다. 이는 효율적인 데이터 관리와 **Object ID를 읽는** 기능을 위해 필수적입니다.

### 1.1: 문서 디렉터리 설정
문서 디렉터리 경로를 정의합니다:

```csharp
string dataDir = "Your Document Directory";
```

### 1.2: GeoDatabase 생성 및 옵션 정의
Object ID와 Geometry에 대한 **필드 이름 설정**을 포함한 GeoDatabase를 생성합니다:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### 1.3: 레이어 생성 및 추가
GeoDatabase 내에 레이어를 만들고 포인트 지오메트리를 나타내는 피처를 추가합니다:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### 1.4: 레이어 열기 및 데이터 가져오기
레이어를 열고 방금 추가한 피처를 가져옵니다. 이는 데이터셋에서 **Object ID를 읽는** 방법을 보여줍니다:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## 사용자 지정 필드 이름을 설정하는 이유
Object ID와 Geometry 필드 이름을 사용자 지정하면 기존 데이터베이스와 통합하거나 다운스트림 애플리케이션이 요구하는 명명 규칙을 따를 때 유연성을 제공합니다. 또한 데이터가 자체 설명적이 되어 유지 보수와 협업이 쉬워집니다.

## 흔히 발생하는 문제와 해결 방법
- **디렉터리 누락** – `dataDir`이 존재하는 폴더를 가리키는지 확인하세요. 그렇지 않으면 `Dataset.Create`에서 예외가 발생합니다.
- **필드 이름 충돌** – 동일한 이름의 필드가 이미 지오데이터베이스에 존재하면 생성이 실패합니다. 고유한 이름을 선택하세요.
- **공간 참조 불일치** – 저장하려는 데이터와 동일한 공간 참조 시스템(예: WGS84)을 사용해야 합니다.

## 결론
축하합니다! Aspose.GIS for .NET을 사용하여 **포인트 피처를 추가**, **필드 이름을 설정**, 그리고 **Object ID를 읽는** 방법을 성공적으로 배웠습니다. 이 기반을 바탕으로 강력한 GIS 애플리케이션을 구축하고 공간 데이터를 자신 있게 관리할 수 있습니다.

## 자주 묻는 질문
### Q: Aspose.GIS for .NET을 웹 애플리케이션에서 사용할 수 있나요?
A: 예, Aspose.GIS for .NET은 데스크톱 및 웹 애플리케이션 모두에 적합한 다목적 지리공간 기능을 제공합니다.

### Q: 구매 전에 체험판을 사용할 수 있나요?
A: 예, 무료 체험판은 [여기](https://releases.aspose.com/)에서 확인할 수 있습니다.

### Q: Aspose.GIS for .NET의 임시 라이선스를 어떻게 얻나요?
A: 평가용 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Q: Aspose.GIS for .NET이 지원하는 공간 참조 시스템은 무엇인가요?
A: Aspose.GIS for .NET은 다양한 공간 참조 시스템을 지원하여 여러 지리 데이터셋에 유연하게 대응합니다.

### Q: Aspose.GIS 관련 문의나 토론은 어디서 할 수 있나요?
A: 지원 및 토론을 위해 Aspose.GIS 포럼을 [여기](https://forum.aspose.com/c/gis/33)에서 방문하세요.

## 추가 자주 묻는 질문

**Q: 레이어를 만든 후에 Object ID 필드를 변경할 수 있나요?**  
A: 아니요. 필드 이름은 레이어 생성 시 정의되며, 새로운 `FileGdbOptions` 객체로 레이어를 다시 만들어야 변경할 수 있습니다.

**Q: Object ID 외에 다른 속성 값을 어떻게 가져오나요?**  
A: `feature.GetValue<T>("FieldName")`을 사용하면 `FieldName`에 해당하는 속성 값을 읽을 수 있습니다.

**Q: 한 번에 여러 포인트 피처를 추가할 수 있나요?**  
A: 예. 데이터를 순회하면서 각 포인트에 대한 피처를 만들고 지오메트리를 설정한 뒤, 동일한 `using` 블록 안에서 `layer.Add(feature)`를 호출하면 됩니다.

**Q: Aspose.GIS가 다른 지오메트리 타입을 지원하나요?**  
A: 물론입니다. `LineString`, `Polygon`, `MultiPoint` 등 다양한 지오메트리 객체를 생성하여 사용할 수 있습니다.

**Q: 존재하지 않는 Object ID를 읽으려고 하면 어떻게 되나요?**  
A: 존재하지 않는 인덱스(예: 피처가 하나뿐인데 `layer[10]` 호출) 접근 시 `IndexOutOfRangeException`이 발생합니다. 항상 `layer.Count`를 먼저 확인하세요.

---

**마지막 업데이트:** 2026-01-02  
**테스트 환경:** Aspose.GIS for .NET 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}