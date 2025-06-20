---
"description": "GroupDocs.Viewer for .NET을 사용하여 PDF에서 텍스트 선택을 비활성화하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요."
"linktitle": "PDF에서 텍스트 선택 비활성화"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF에서 텍스트 선택 비활성화"
"url": "/ko/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
---

# PDF에서 텍스트 선택 비활성화

## 소개
GroupDocs.Viewer for .NET은 개발자가 문서 보기 기능을 .NET 애플리케이션에 손쉽게 통합할 수 있도록 지원하는 강력한 문서 렌더링 API입니다. GroupDocs.Viewer의 주요 기능 중 하나는 PDF 문서의 텍스트 선택을 비활성화하는 기능입니다. 이 기능은 사용자가 민감한 문서의 텍스트를 복사하는 것을 방지하여 문서 보안과 무결성을 보장해야 하는 상황에서 특히 유용합니다.

![GroupDocs.Viewer .NET을 사용하여 PDF에서 텍스트 선택 비활성화](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## 필수 조건
GroupDocs.Viewer for .NET을 사용하여 PDF에서 텍스트 선택을 비활성화하는 방법에 대한 단계별 가이드를 살펴보기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. .NET용 GroupDocs.Viewer 설치: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치했는지 확인하십시오. [다운로드 링크](https://releases.groupdocs.com/viewer/net/).
2. 문서 디렉터리: 문서를 저장할 디렉터리를 준비하세요. PDF 문서를 렌더링하려면 코드 조각에서 이 디렉터리를 지정해야 합니다.

## 네임스페이스 가져오기
먼저, GroupDocs.Viewer for .NET에서 제공하는 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 GroupDocs.Viewer for .NET을 사용하여 PDF 문서에서 텍스트 선택을 비활성화하는 프로세스를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 지정
```csharp
string outputDirectory = "Your Document Directory";
```
이 단계에서는 다음을 교체합니다. `"Your Document Directory"` PDF 문서가 있는 디렉토리 경로를 사용합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
이 단계에서는 렌더링된 HTML 페이지의 파일 경로 형식을 정의합니다. PDF 문서의 각 페이지는 순차적인 페이지 번호가 있는 HTML 파일로 변환됩니다.
## 3단계: 텍스트 선택이 비활성화된 PDF 문서 렌더링
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
바꾸다 `"Path to Your PDF Document"` PDF 파일의 실제 경로를 사용합니다. 이 코드 조각은 `Viewer` 개체는 리소스를 포함하기 위한 HTML 보기 옵션을 구성하고 설정하여 텍스트 선택을 비활성화합니다. `RenderTextAsImage` 재산에 `true`.
## 4단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
PDF 문서를 렌더링한 후, 이 단계에서는 렌더링된 HTML 페이지가 저장된 디렉터리와 함께 성공 메시지가 표시됩니다.

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 PDF 문서의 텍스트 선택을 비활성화하는 방법을 알아보았습니다. 단계별 가이드를 따라 하면 이 기능을 .NET 애플리케이션에 완벽하게 통합하여 문서 보안을 강화하고 사용자 경험을 향상시킬 수 있습니다.
## 자주 묻는 질문
### 렌더링된 HTML 페이지의 출력 디렉토리를 사용자 정의할 수 있나요?
네, 렌더링된 HTML 페이지를 저장할 디렉토리 경로를 지정할 수 있습니다.
### GroupDocs.Viewer for .NET은 다양한 버전의 .NET 프레임워크와 호환됩니까?
네, GroupDocs.Viewer for .NET은 .NET Core 및 .NET Framework를 포함한 다양한 버전의 .NET Framework와 호환됩니다.
### 텍스트 선택을 비활성화하면 PDF 문서의 다른 기능에 영향을 미칩니까?
아니요, 텍스트 선택을 비활성화하면 사용자가 문서에서 텍스트를 선택하고 복사할 수 없게 됩니다. 다른 기능은 그대로 유지됩니다.
### 문서를 렌더링한 후 다시 텍스트 선택을 활성화할 수 있나요?
예, 간단히 설정하여 텍스트 선택을 활성화할 수 있습니다. `RenderTextAsImage` 재산에 `false` HTML 보기 옵션에서.
### GroupDocs.Viewer for .NET의 평가판이 있나요?
예, .NET용 GroupDocs.Viewer의 무료 평가판에 액세스할 수 있습니다. [웹사이트](https://releases.groupdocs.com/).