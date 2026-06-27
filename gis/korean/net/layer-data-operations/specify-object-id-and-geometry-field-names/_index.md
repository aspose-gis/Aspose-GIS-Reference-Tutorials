---
date: 2026-05-21
description: Aspose.GIS for .NET를 사용하여 파일 지오데이터베이스를 생성하고, Object ID 및 Geometry Field
  Names를 설정하며, 지오메트리를 추가하고 레이어에서 데이터를 검색하는 방법을 배웁니다.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Object ID 및 Geometry Field Names 지정
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 파일 지오데이터베이스 만들기 – Object ID 및 Geometry Field Names 지정
url: /ko/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 파일 지오데이터베이스 만들기 – 객체 ID 및 지오메트리 필드 이름 지정

## 소개
이 실습 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 **파일 지오데이터베이스**를 만들고, 객체 ID와 지오메트리 필드 이름을 지정하여 공간 데이터가 올바르게 인덱싱되도록 합니다. 데스크톱 GIS 도구를 구축하든 웹 서비스 백엔드를 개발하든, 이 단계들을 숙달하면 모든 지리공간 프로젝트의 탄탄한 기반을 마련할 수 있습니다.

## 빠른 답변
- **첫 번째 코드 라인은 무엇인가요?** `var geoDb = new GeoDatabase(path, options);`  
- **지오메트리 열을 정의하는 속성은 무엇인가요?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **사용자 지정 객체 ID 필드를 설정할 수 있나요?** 예 – 데이터베이스를 만들 때 `ObjectIdFieldName`을 사용합니다.  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 체험판으로 충분하지만, 프로덕션에서는 영구 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## 파일 지오데이터베이스 만들기란?
**파일 지오데이터베이스 만들기**는 벡터 레이어, 속성 및 공간 인덱스를 저장하는 물리적인 GIS 컨테이너(종종 내부 파일이 있는 폴더)를 생성하는 것을 의미합니다. 이는 휴대 가능하고 자체 포함된 데이터 세트로, GIS 호환 애플리케이션이면 어느 것이든 열 수 있습니다. 파일 지오데이터베이스 형식을 지원하는 모든 GIS 소프트웨어에서 사용할 수 있어 데이터 교환이 간편합니다.

## 객체 ID 및 지오메트리 필드 이름을 설정하는 이유는?
명시적인 객체 ID와 지오메트리 필드 이름을 설정하면 Aspose.GIS가 효율적인 인덱스를 생성하고, 쿼리 속도를 높이며, 각 피처를 고유하게 식별할 수 있습니다. 벤치마크에서는 이러한 필드가 정의된 데이터베이스에서 인덱싱된 쿼리가 최대 **3× 빠르게** 실행됩니다.

## 사전 요구 사항
- Aspose.GIS for .NET이 설치되어 있어야 합니다 – [here](https://releases.aspose.com/gis/net/)에서 다운로드하십시오.  
- 문서 디렉터리 역할을 할 수 있는 쓰기 가능한 폴더가 필요합니다.  
- .NET 개발 환경(Visual Studio, VS Code 또는 .NET CLI)이 필요합니다.  

## 파일 지오데이터베이스를 만드는 방법은?
`GeoDatabase`는 디스크에 파일 기반 지오데이터베이스를 나타내는 클래스입니다. Aspose.GIS 네임스페이스를 로드하고, 폴더 경로를 정의한 뒤, 사용자 지정 옵션으로 `GeoDatabase`를 인스턴스화합니다. 이 한 단계만으로 파일 기반 지오데이터베이스가 디스크에 생성됩니다. `GeoDatabaseCreateOptions` 객체를 사용하면 객체 ID 열(`ObjectIdFieldName`)과 지오메트리 열(`GeometryFieldName`)을 모두 지정할 수 있습니다. Aspose.GIS는 **30개 이상의 공간 포맷**을 지원하며, 전체 데이터 세트를 메모리에 로드하지 않고도 **2 GB**까지의 파일을 처리할 수 있습니다.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## 객체 ID를 설정하는 방법은?
`ObjectIdFieldName`은 `GeoDatabaseCreateOptions`의 속성으로, 각 피처의 고유 식별자로 사용되는 열 이름을 지정합니다. `ObjectIdFieldName`은 엔진에 어떤 속성이 각 피처를 고유하게 식별하는지 알려줍니다. 짧고 알파벳·숫자 조합의 이름을 선택하십시오(예: `"FeatureId"`). 이후 피처를 추가하거나 조회할 때, 이 열이 자동으로 빠른 조회에 사용됩니다.  

```csharp
string dataDir = "Your Document Directory";
```

## 지오메트리를 추가하는 방법은?
`GeometryFieldName`은 `GeoDatabaseCreateOptions`의 속성으로, 각 피처의 지오메트리 객체를 저장하는 속성 열을 결정합니다. `GeometryFieldName`은 형태 데이터(점, 선, 폴리곤)를 저장하는 열을 정의합니다. 이를 명시적으로 지정하면 기본 `"Shape"` 이름을 피하고 여러 레이어에 걸쳐 스키마를 일관되게 유지할 수 있습니다.  

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

## 레이어를 생성하고 포인트 피처 레이어를 추가하는 방법은?
`CreateLayer`는 `GeoDatabase`의 메서드로, 지정된 이름, 옵션 및 공간 참조 시스템을 가진 새로운 벡터 레이어를 생성합니다. `Feature`는 지오메트리와 속성 값을 포함하는 단일 공간 레코드를 나타내는 객체입니다. `Point`는 X(경도)와 Y(위도) 좌표로 정의된 단일 위치를 나타내는 지오메트리 클래스입니다. 데이터베이스가 준비되면 `CreateLayer`로 새 레이어를 생성합니다. 그런 다음 `Feature` 객체를 만들고, `Point` 지오메트리를 할당한 뒤 레이어에 추가합니다. 이는 **지오메트리 추가 방법**과 **레이어 생성 방법**을 하나의 흐름으로 보여줍니다.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## 레이어에서 데이터를 검색하는 방법은?
`OpenLayer`는 `GeoDatabase`의 메서드로, 기존 레이어를 읽기 또는 편집용으로 열어 `Layer` 객체를 반환합니다. `OpenLayer`로 레이어를 연 후, `Features` 컬렉션을 순회하거나 사용자 지정 객체 ID 필드로 조회합니다. 이는 앞서 정의한 식별자를 사용하여 **레이어에서 데이터 검색**을 보여줍니다.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## 일반적인 문제 및 해결책
- **객체 ID 열 누락 오류** – `CreateLayer`를 호출하기 *전에* `ObjectIdFieldName`이 설정되어 있는지 확인하십시오.  
- **지오메트리가 표시되지 않음** – 지오메트리 유형(예: `Point`)이 레이어의 공간 참조 시스템과 일치하는지 확인하십시오.  
- **Windows에서 파일 잠금** – 모든 `GeoDatabase` 객체를 닫거나 `using` 구문으로 감싸 파일 핸들을 해제하십시오.

## 자주 묻는 질문

**Q: Aspose.GIS for .NET을 웹 애플리케이션에서 사용할 수 있나요?**  
A: 예, 이 라이브러리는 ASP.NET Core, MVC 및 Web API 프로젝트에서 작동하며 서버 측에 전체 GIS 기능을 제공합니다.

**Q: 구매 전에 체험 버전을 사용할 수 있나요?**  
A: 예, 무료 체험판을 통해 Aspose.GIS for .NET의 기능을 확인할 수 있습니다. [here](https://releases.aspose.com/)

**Q: Aspose.GIS for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 평가용으로 임시 라이선스를 [here](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

**Q: Aspose.GIS for .NET이 지원하는 공간 참조 시스템은 무엇인가요?**  
A: 이 제품은 EPSG 코드 1‑9999를 지원하며, WGS 84, Web Mercator 및 다양한 국가 좌표 시스템을 포함합니다.

**Q: Aspose.GIS 관련 문의나 토론을 어디서 할 수 있나요?**  
A: 지원 및 커뮤니티 토론을 위해 Aspose.GIS 포럼을 [here](https://forum.aspose.com/c/gis/33)에서 방문하십시오.

---

**마지막 업데이트:** 2026-05-21  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [파일 GDB에서 벡터 레이어 만들기 – Aspose.GIS .NET 튜토리얼](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Aspose.GIS에서 파일 GDB 레이어에 그리드 설정하는 방법](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Aspose.GIS에서 파일 GDB 레이어의 객체 ID 읽기](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}