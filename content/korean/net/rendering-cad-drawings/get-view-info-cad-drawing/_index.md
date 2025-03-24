---
title: CAD 도면에 대한 보기 정보 얻기
linktitle: CAD 도면에 대한 보기 정보 얻기
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 CAD 도면에 대한 보기 정보를 검색하는 방법을 알아보세요. 원활한 CAD 파일 처리로 .NET 애플리케이션을 강화하세요.
weight: 10
url: /ko/net/rendering-cad-drawings/get-view-info-cad-drawing/
---
## 소개
소프트웨어 개발 세계에서는 CAD 도면을 효율적으로 처리하는 것이 중요합니다. 건축가, 엔지니어 또는 디자이너를 위한 애플리케이션을 구축하는 경우 CAD 파일에 대한 원활한 보기 환경을 제공하면 사용자 만족도를 크게 높일 수 있습니다. .NET용 GroupDocs.Viewer는 CAD 파일 보기 기능을 .NET 응용 프로그램에 쉽게 통합할 수 있는 강력한 솔루션을 제공합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 CAD 도면에 대한 보기 정보를 얻는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
 무엇보다도 개발 환경에 .NET용 GroupDocs.Viewer가 설치되어 있어야 합니다. 최신 버전은 다음 사이트에서 다운로드할 수 있습니다.[GroupDocs 웹사이트](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework의 기본 이해
이 튜토리얼을 진행하려면 .NET 프레임워크 및 C# 프로그래밍 언어에 대한 지식이 필수적입니다.
### 3. 개발 환경 설정
Visual Studio 또는 기타 .NET 호환 IDE를 사용하여 개발 환경이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기
C# 프로젝트에서 GroupDocs.Viewer 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

## 1단계: 보기 정보 옵션 정의
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
```
 이 단계에서는 인스턴스를 초기화합니다.`ViewInfoOptions` 보기 정보를 검색하기 위한 옵션을 지정합니다. 우리는 사용`ForHtmlView()` HTML 보기에 대한 정보를 검색하고 싶다는 것을 나타내는 메서드입니다.
## 2단계: CAD 렌더링 옵션 구성
```csharp
viewInfoOptions.CadOptions.RenderLayouts = true;
```
 여기서 우리는 설정했습니다.`RenderLayouts` 재산`true` 모든 레이아웃을 포함합니다. 이렇게 하면 CAD 파일 내의 모든 레이아웃이 렌더링됩니다.
## 3단계: CAD 보기 정보 검색
```csharp
CadViewInfo info = viewer.GetViewInfo(viewInfoOptions) as CadViewInfo;
```
 우리는 전화한다`GetViewInfo()` 뷰어 개체에 대한 메서드를 전달하여`viewInfoOptions` CAD 파일에 대한 뷰 정보를 검색하는 매개변수로 사용됩니다. 우리는 반환된 것을 캐스팅합니다.`ViewInfo` 반대하다`CadViewInfo` 유형.
## 4단계: 문서 유형 및 페이지 수 표시
```csharp
Console.WriteLine("Document type is: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```
이 단계에서는 문서 유형과 CAD 파일의 총 페이지 수를 콘솔에 인쇄합니다.
## 5단계: 레이아웃 및 레이어 표시
```csharp
Console.WriteLine("\nLayouts:");
foreach (Layout layout in info.Layouts)
    Console.WriteLine(layout);
Console.WriteLine("\nLayers:");
foreach (Layer layer in info.Layers)
    Console.WriteLine(layer);
```
마지막으로 CAD 파일에서 검색된 레이아웃과 레이어를 반복하여 콘솔에 인쇄합니다.

## 결론
이 자습서를 따라 .NET용 GroupDocs.Viewer를 활용하여 CAD 도면에 대한 보기 정보를 원활하게 얻는 방법을 배웠습니다. 이 기능을 .NET 애플리케이션에 통합하면 사용자 경험이 크게 향상되고 CAD 파일 처리가 간소화됩니다.
## FAQ
### 질문: .NET용 GroupDocs.Viewer는 모든 CAD 파일 형식과 호환됩니까?
.NET용 GroupDocs.Viewer는 DWG, DXF, DWF 등을 포함한 다양한 CAD 파일 형식을 지원합니다.
### Q: CAD 파일의 렌더링 옵션을 사용자 정의할 수 있습니까?
예, 요구 사항에 따라 레이아웃, 레이어, 출력 형식 등의 렌더링 옵션을 사용자 정의할 수 있습니다.
### 질문: .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
예, 웹사이트에서 .NET용 GroupDocs.Viewer의 무료 평가판에 액세스하여 구매하기 전에 기능을 살펴볼 수 있습니다.
### Q: .NET용 GroupDocs.Viewer의 업데이트는 얼마나 자주 출시됩니까?
GroupDocs는 최신 CAD 파일 형식과의 호환성을 보장하고 전반적인 성능을 향상시키기 위해 정기적으로 업데이트 및 개선 사항을 출시합니다.
### 질문: .NET용 GroupDocs.Viewer에 대한 지원은 어디에서 찾을 수 있습니까?
질문, 기술 지원 또는 문제 해결에 대해서는 GroupDocs.Viewer 포럼을 방문하거나 지원팀에 문의할 수 있습니다.