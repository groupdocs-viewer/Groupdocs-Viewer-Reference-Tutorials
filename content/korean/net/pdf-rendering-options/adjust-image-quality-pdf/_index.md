---
title: PDF의 이미지 품질 조정
linktitle: PDF의 이미지 품질 조정
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 PDF 문서의 이미지 품질을 조정하는 방법을 알아보세요. 원활한 통합을 위해 단계별 튜토리얼을 따르세요.
type: docs
weight: 10
url: /ko/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## 소개
.NET용 GroupDocs.Viewer는 개발자가 문서 렌더링 기능을 .NET 응용 프로그램에 쉽게 통합할 수 있게 해주는 강력한 라이브러리입니다. 이 라이브러리의 주요 기능 중 하나는 PDF 문서를 렌더링할 때 이미지 품질을 조정하는 기능입니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 이미지 품질을 조정하는 과정을 단계별로 안내합니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. C# 프로그래밍에 대한 기본 지식.
2. 시스템에 Visual Studio가 설치되어 있습니다.
3. .NET 라이브러리용 GroupDocs.Viewer가 다운로드되어 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
먼저 .NET용 GroupDocs.Viewer를 사용하려면 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 렌더링된 HTML 페이지를 저장하려는 경로를 사용하세요.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 이 줄은 렌더링된 각 HTML 페이지의 파일 경로 형식을 정의합니다.`{0}` 페이지 번호에 대한 자리 표시자입니다.
## 3단계: 이미지 품질 조정
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 바꾸다`"Your PDF File Path"` PDF 문서의 경로와 함께.
## 4단계: 출력 경로 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
이 줄은 렌더링된 HTML 페이지가 저장되는 경로를 표시합니다.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서를 렌더링할 때 이미지 품질을 조정하는 방법을 배웠습니다. 위에 설명된 간단한 단계를 따르면 요구 사항에 따라 이미지 품질을 쉽게 사용자 정의할 수 있습니다.
## FAQ
### PDF 외에 다른 문서 형식의 이미지 품질을 조정할 수 있나요?
예, .NET용 GroupDocs.Viewer는 다양한 문서 형식을 지원하며 대부분의 문서 형식에 대해 이미지 품질을 조정할 수 있습니다.
### 사용 가능한 이미지 품질 옵션은 무엇입니까?
.NET용 GroupDocs.Viewer는 낮음, 중간 및 높음 이미지 품질에 대한 옵션을 제공합니다.
### 조정된 이미지 품질로 문서를 렌더링하기 전에 문서를 미리 볼 수 있는 방법이 있습니까?
예, .NET용 GroupDocs.Viewer를 사용하여 다양한 이미지 품질 설정으로 문서 미리보기를 생성할 수 있습니다.
### .NET용 GroupDocs.Viewer를 상업적으로 사용하려면 라이센스가 필요합니까?
 네, 상업적으로 사용하려면 라이센스를 취득해야 합니다. 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.groupdocs.com/buy).
### .NET용 GroupDocs.Viewer에 대한 지원은 어디서 받을 수 있나요?
 GroupDocs.Viewer 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).