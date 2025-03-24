---
title: PDF에서 텍스트 선택 비활성화
linktitle: PDF에서 텍스트 선택 비활성화
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 PDF에서 텍스트 선택을 비활성화하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 13
url: /ko/net/pdf-rendering-options/disable-text-selection-pdf/
---
## 소개
.NET용 GroupDocs.Viewer는 개발자가 문서 보기 기능을 .NET 응용 프로그램에 손쉽게 통합할 수 있게 해주는 강력한 문서 렌더링 API입니다. GroupDocs.Viewer가 제공하는 주요 기능 중 하나는 PDF 문서에서 텍스트 선택을 비활성화하는 기능입니다. 이 기능은 사용자가 중요한 문서에서 텍스트를 복사하지 못하도록 방지하여 문서 보안과 무결성을 보장해야 하는 시나리오에서 특히 유용합니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하여 PDF에서 텍스트 선택을 비활성화하는 방법에 대한 단계별 가이드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 GroupDocs.Viewer 설치: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치했는지 확인하십시오.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
2. 문서 디렉터리: 문서가 저장될 디렉터리를 준비합니다. PDF 문서를 렌더링하려면 코드 조각에서 이 디렉터리를 지정해야 합니다.

## 네임스페이스 가져오기
먼저, .NET용 GroupDocs.Viewer에서 제공하는 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 텍스트 선택을 비활성화하는 프로세스를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 지정
```csharp
string outputDirectory = "Your Document Directory";
```
 이 단계에서는 교체합니다.`"Your Document Directory"` PDF 문서가 있는 디렉토리 경로를 사용하세요.
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
 바꾸다`"Path to Your PDF Document"` PDF 파일의 실제 경로와 함께. 이 코드 조각은`Viewer` 개체를 포함하고 리소스를 포함하도록 HTML 보기 옵션을 구성하고 설정을 통해 텍스트 선택을 비활성화합니다.`RenderTextAsImage` 재산`true`.
## 4단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
PDF 문서를 렌더링한 후 이 단계에서는 렌더링된 HTML 페이지가 저장된 디렉터리와 함께 성공 메시지를 표시합니다.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 텍스트 선택을 비활성화하는 방법을 배웠습니다. 단계별 가이드를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 보안을 보장하고 사용자 경험을 향상시킬 수 있습니다.
## FAQ
### 렌더링된 HTML 페이지의 출력 디렉터리를 사용자 정의할 수 있습니까?
예, 렌더링된 HTML 페이지를 저장할 디렉터리 경로를 지정할 수 있습니다.
### .NET용 GroupDocs.Viewer는 다른 버전의 .NET Framework와 호환됩니까?
예, .NET용 GroupDocs.Viewer는 .NET Core 및 .NET Framework를 포함하여 다양한 버전의 .NET Framework와 호환됩니다.
### 텍스트 선택을 비활성화하면 PDF 문서의 다른 기능에 영향을 줍니까?
아니요, 텍스트 선택을 비활성화하면 사용자가 문서에서 텍스트를 선택하고 복사할 수 없게 됩니다. 다른 기능은 그대로 유지됩니다.
### 문서를 렌더링한 후 텍스트 선택을 다시 활성화할 수 있습니까?
 예, 간단히 설정하여 텍스트 선택을 활성화할 수 있습니다.`RenderTextAsImage` 재산`false` HTML 보기 옵션에서.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 .NET용 GroupDocs.Viewer 무료 평가판에 액세스할 수 있습니다.[웹사이트](https://releases.groupdocs.com/).