---
"description": "GroupDocs.Viewer for .NET을 사용하여 PDF 문서에서 계층적 렌더링을 활성화하는 방법을 알아보세요. 손쉽게 문서 보기 환경을 개선해 보세요."
"linktitle": "PDF에서 계층형 렌더링 활성화"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF에서 계층형 렌더링 활성화"
"url": "/ko/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# PDF에서 계층형 렌더링 활성화

## 소개
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 PDF 문서에서 계층적 렌더링을 활성화하는 방법을 자세히 살펴보겠습니다. 계층적 렌더링을 통해 향상된 문서 표시 및 조작이 가능해져 사용자에게 더욱 인터랙티브한 보기 환경을 제공합니다.

![GroupDocs.Viewer .NET을 사용하여 PDF에서 계층형 렌더링 활성화](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## 필수 조건
시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.
1. .NET용 GroupDocs.Viewer: 프로젝트에서 .NET용 GroupDocs.Viewer를 사용하는 데 필요한 패키지나 라이브러리를 설치했는지 확인하세요.
2. Visual Studio: 제공된 예제를 코딩하고 실행하려면 시스템에 Visual Studio가 설치되어 있어야 합니다.
3. C#에 대한 기본적인 이해: 이 튜토리얼은 C# 프로그래밍 언어 구문과 개념에 익숙하다고 가정합니다.

## 네임스페이스 가져오기
프로젝트에 필요한 네임스페이스를 가져와서 시작하세요.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 출력을 저장할 디렉토리 경로를 지정해야 합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
이 단계에서는 렌더링된 출력에서 개별 페이지의 파일 경로에 대한 형식을 설정합니다. `{0}` 는 페이지 번호의 자리 표시자입니다.
## 3단계: 레이어드 렌더링 활성화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
여기서 우리는 다음을 생성합니다. `Viewer` 객체를 생성하고 처리할 PDF 문서를 지정합니다. 그런 다음 구성합니다. `HtmlViewOptions` 정의된 페이지 파일 경로 형식을 사용합니다. 설정하여 `EnableLayeredRendering` 재산에 `true` ~에 `PdfOptions`PDF 문서에 대해 계층형 렌더링을 활성화합니다.
## 4단계: 출력 디렉토리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로, 소스 문서가 성공적으로 렌더링되었다는 메시지를 출력하고 사용자에게 지정된 디렉토리에서 출력을 확인하라는 메시지를 표시합니다.

## 결론
GroupDocs.Viewer for .NET을 사용하여 PDF 문서에서 계층형 렌더링을 활성화하면 문서 보기 기능이 향상되어 사용자에게 더욱 풍부하고 인터랙티브한 경험을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### PDF 문서의 계층 렌더링이란 무엇입니까?
계층화된 렌더링을 사용하면 PDF 문서 내의 다양한 구성 요소를 분리하고 조작할 수 있어 대화형 보기와 향상된 사용자 경험이 가능합니다.
### 렌더링된 문서의 출력 디렉토리를 사용자 정의할 수 있나요?
네, 요구 사항에 맞게 출력에 대한 디렉토리 경로를 지정할 수 있습니다.
### GroupDocs.Viewer는 PDF 외에 다른 파일 형식을 지원합니까?
네, GroupDocs.Viewer는 Word, Excel, PowerPoint 등 다양한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환됩니까?
네, GroupDocs.Viewer는 .NET Framework와 .NET Core 환경 모두와 호환됩니다.
### 추가 지원이나 도움은 어디에서 받을 수 있나요?
뷰어 라이브러리에 관한 질문이나 지원이 있으면 GroupDocs.Viewer 포럼을 방문하세요.