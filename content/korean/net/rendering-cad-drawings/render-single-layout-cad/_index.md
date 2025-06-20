---
"description": "GroupDocs.Viewer for .NET을 사용하여 CAD 도면에서 단일 레이아웃을 렌더링하는 방법을 알아보세요. .NET 애플리케이션에 원활하게 통합하기 위한 간단한 단계입니다."
"linktitle": "CAD 도면에서 단일 레이아웃 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD 도면에서 단일 레이아웃 렌더링"
"url": "/ko/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# CAD 도면에서 단일 레이아웃 렌더링

## 소개
.NET 개발 분야에서 CAD 도면을 처리하고 보는 것은 일반적인 요구 사항입니다. GroupDocs.Viewer for .NET은 .NET 애플리케이션 내에서 CAD 도면을 렌더링하는 포괄적인 솔루션을 제공하여 이 작업을 간소화합니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 CAD 도면에서 단일 레이아웃을 렌더링하는 방법을 자세히 살펴보겠습니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 필수 조건을 충족하는지 확인하세요.
- C# 프로그래밍 언어와 .NET 프레임워크에 대한 기본적인 이해.
- 시스템에 Visual Studio가 설치되어 있어야 합니다.
- 프로젝트에 .NET용 GroupDocs.Viewer 라이브러리와 tutorialsd가 다운로드되어 있습니다. 에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
- CAD 파일 형식과 구조에 대한 지식.

## 네임스페이스 가져오기
먼저, GroupDocs.Viewer 기능에 액세스하기 위해 필요한 네임스페이스를 C# 코드로 가져옵니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉토리 정의
렌더링된 출력을 저장할 디렉토리를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
렌더링된 각 페이지의 파일 경로에 대한 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 객체 인스턴스화
GroupDocs.Viewer에서 제공하는 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 4단계: HTML 보기 옵션 구성
내장된 리소스를 사용하여 HTML 출력을 렌더링하기 위한 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5단계: CAD 레이아웃 이름 지정
렌더링하려는 CAD 레이아웃의 이름을 지정합니다.
```csharp
options.CadOptions.LayoutName = "Model";
```
## 6단계: CAD 도면 렌더링
지정된 옵션을 사용하여 Viewer 개체의 View 메서드를 호출합니다.
```csharp
viewer.View(options);
```
## 7단계: 성공 메시지 표시
소스 문서가 성공적으로 렌더링되었음을 사용자에게 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
CAD 도면 렌더링, 특히 레이아웃을 다루는 작업은 상당히 까다로울 수 있습니다. 하지만 GroupDocs.Viewer for .NET을 사용하면 이 과정이 원활하고 효율적으로 진행됩니다. 이 튜토리얼에 설명된 단계를 따르면 .NET 애플리케이션에서 CAD 도면의 단일 레이아웃을 손쉽게 렌더링할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET을 사용하여 여러 레이아웃을 동시에 렌더링할 수 있나요?
네, GroupDocs.Viewer for .NET은 CAD 도면에서 여러 레이아웃을 렌더링하는 것을 지원합니다.
### GroupDocs.Viewer는 다양한 CAD 파일 형식과 호환됩니까?
물론입니다. GroupDocs.Viewer는 DWG, DXF, DGN 등 다양한 CAD 파일 형식을 지원합니다.
### CAD 도면의 렌더링 옵션을 사용자 정의할 수 있나요?
네, GroupDocs.Viewer는 사용자의 요구 사항에 맞게 렌더링 설정을 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### GroupDocs.Viewer for .NET에 대한 무료 평가판이 있나요?
네, 무료 평가판을 통해 GroupDocs.Viewer의 기능을 탐색할 수 있습니다. [여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 지원은 어디에서 받을 수 있나요?
질문이나 도움이 필요하면 GroupDocs.Viewer 포럼을 방문하세요. [여기](https://forum.groupdocs.com/c/viewer/9).