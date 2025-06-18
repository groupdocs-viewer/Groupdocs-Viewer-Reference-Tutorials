---
"description": "GroupDocs.Viewer for .NET을 사용하여 .NET 애플리케이션에서 CAD 도면을 원활하게 렌더링하세요. 렌더링 옵션을 살펴보고, 레이어를 사용자 지정하는 등 다양한 기능을 활용할 수 있습니다."
"linktitle": "CAD 도면의 렌더 레이어"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD 도면의 렌더 레이어"
"url": "/ko/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
---

# CAD 도면의 렌더 레이어

## 소개
GroupDocs.Viewer for .NET은 개발자가 문서 렌더링 기능을 .NET 애플리케이션에 완벽하게 통합할 수 있도록 지원하는 강력한 도구입니다. CAD 도면, PDF, Microsoft Office 문서 등 어떤 형식의 문서든 GroupDocs.Viewer는 포괄적인 솔루션을 제공합니다.
## 필수 조건
.NET용 GroupDocs.Viewer를 사용하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본적인 이해.
- 컴퓨터에 .NET 개발 환경이 설정되어 있습니다.
- .NET용 GroupDocs.Viewer가 설치되어 있습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
- 튜토리얼을 위한 .NET 설명서에 대한 GroupDocs.Viewer에 대한 액세스는 다음에서 찾을 수 있습니다. [여기](https://tutorials.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
GroupDocs.Viewer for .NET을 사용하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 다음 단계를 따르세요.

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

제공된 예를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 객체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // 코드 블록은 계속됩니다...
}
```
## 4단계: HTML 보기 옵션 설정
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5단계: CAD 레이어 정의
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## 6단계: 문서 렌더링
```csharp
viewer.View(options);
```
## 7단계: 렌더링된 문서 위치 출력
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
GroupDocs.Viewer for .NET을 사용하면 .NET 애플리케이션에서 CAD 도면을 렌더링하는 과정이 더욱 간편해집니다. 이 가이드에 설명된 단계를 따르면 문서 렌더링 기능을 프로젝트에 쉽게 통합할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer는 모든 유형의 CAD 도면과 호환됩니까?
네, GroupDocs.Viewer는 DWG, DXF를 포함한 다양한 CAD 도면 형식의 렌더링을 지원합니다.
### CAD 도면의 렌더링 옵션을 사용자 정의할 수 있나요?
물론입니다. GroupDocs.Viewer는 렌더링할 레이어 지정이나 출력 형식 설정 등 다양한 사용자 정의 옵션을 제공합니다.
### GroupDocs.Viewer에서 문서를 렌더링하려면 인터넷 연결이 필요합니까?
아니요, GroupDocs.Viewer는 인터넷 연결이 필요 없이 로컬에서 렌더링을 수행합니다.
### GroupDocs.Viewer for .NET에 대한 무료 평가판이 있나요?
네, .NET용 GroupDocs.Viewer의 무료 평가판에 액세스할 수 있습니다. [여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 지원은 어디에서 받을 수 있나요?
기술 지원이나 문의 사항이 있으시면 GroupDocs.Viewer 포럼을 방문하세요. [여기](https://forum.groupdocs.com/c/viewer/9).