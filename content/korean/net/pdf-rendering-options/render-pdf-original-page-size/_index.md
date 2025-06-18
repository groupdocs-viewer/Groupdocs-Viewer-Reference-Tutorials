---
"description": "GroupDocs.Viewer for .NET을 사용하여 PDF를 원본 페이지 크기로 렌더링하는 방법을 알아보세요. 단계별 가이드를 따라 이 기능을 완벽하게 통합해 보세요."
"linktitle": "원래 페이지 크기로 PDF 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "원래 페이지 크기로 PDF 렌더링"
"url": "/ko/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# 원래 페이지 크기로 PDF 렌더링

## 소개
.NET 개발 분야에서 GroupDocs.Viewer는 PDF를 포함한 다양한 문서 형식을 렌더링하는 강력한 도구로 각광받고 있습니다. 문서 처리에서 일반적으로 요구되는 사항 중 하나는 PDF를 원래 페이지 크기를 유지하면서 렌더링하는 것입니다. 이 작업을 원활하게 수행하려면 .NET용 GroupDocs.Viewer와 그 기능에 대한 포괄적인 이해가 필요합니다.

![GroupDocs.Viewer .NET을 사용하여 원본 페이지 크기로 PDF 렌더링](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## 필수 조건
GroupDocs.Viewer for .NET을 사용하여 원래 페이지 크기로 PDF를 렌더링하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
먼저 웹사이트에서 GroupDocs.Viewer 라이브러리를 다운로드하세요. 제공된 라이브러리를 통해 다운로드할 수 있습니다. [다운로드 링크](https://releases.groupdocs.com/viewer/net/)설명서에 제공된 설치 지침에 따라 .NET 프로젝트에 효과적으로 통합하세요.
### 2. 개발 환경 설정
.NET 개발을 위한 개발 환경이 설정되어 있는지 확인하세요. 여기에는 Visual Studio와 같은 호환 IDE가 설치되어 있어야 하며, C# 프로그래밍에 대한 기본적인 이해가 필요합니다.
### 3. PDF 문서 얻기
GroupDocs.Viewer로 렌더링하려면 샘플 PDF 문서가 필요합니다. 테스트 목적으로는 어떤 PDF 문서든 사용할 수 있습니다. 샘플 PDF가 없다면 다양한 온라인 소스에서 다운로드할 수 있습니다.

## 네임스페이스 가져오기
PDF 렌더링을 진행하기 전에 필요한 네임스페이스를 C# 프로젝트로 가져오는 것이 중요합니다. 이 단계를 통해 GroupDocs.Viewer 라이브러리에서 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 필수 구성 요소를 갖추고 필요한 네임스페이스를 가져왔으므로 GroupDocs.Viewer for .NET을 사용하여 원래 페이지 크기로 PDF를 렌더링하는 프로세스를 간단한 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 페이지를 저장할 디렉터리를 지정하세요. 바꾸기 `"Your Document Directory"` 원하는 디렉토리의 경로를 입력하세요.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
렌더링된 페이지 파일의 이름 형식을 설정합니다. 이 예에서는 페이지가 PNG 이미지로 저장되고 파일 이름은 다음 형식으로 지정됩니다. `"page_1.png"`, `"page_2.png"`, 등등.
## 3단계: 원본 페이지 크기로 PDF 렌더링
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
인스턴스화 `Viewer` PDF 파일 경로가 있는 객체를 만듭니다. 그런 다음 `PngViewOptions` 지정된 페이지 파일 경로 형식으로 설정합니다. `RenderOriginalPageSize` 재산에 `true` 렌더링하는 동안 원래 페이지 크기를 유지합니다.
## 4단계: 렌더링된 문서 위치 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
렌더링이 성공했음을 나타내는 메시지를 인쇄하고 렌더링된 페이지가 저장된 디렉터리를 제공합니다.

## 결론
이 튜토리얼에 설명된 단계를 따르면 GroupDocs.Viewer for .NET을 사용하여 PDF를 원본 페이지 크기로 렌더링하는 것은 매우 간단합니다. 필요한 네임스페이스를 가져오고 단계별 가이드를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer는 PDF 외에 다른 문서 형식을 렌더링할 수 있나요?
네, GroupDocs.Viewer는 Word, Excel, PowerPoint 등 다양한 문서 형식의 렌더링을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환됩니까?
네, GroupDocs.Viewer는 .NET Framework와 .NET Core 환경 모두와 호환됩니다.
### 렌더링된 페이지의 출력 형식을 사용자 정의할 수 있나요?
네, GroupDocs.Viewer에서 제공하는 옵션을 조정하여 출력 형식을 사용자 정의할 수 있습니다. 예를 들어, 다양한 이미지 형식을 설정하거나 사용자 정의 렌더링 옵션을 지정할 수 있습니다.
### GroupDocs.Viewer는 클라우드 기반 문서 렌더링을 지원합니까?
네, GroupDocs.Viewer는 클라우드 기반 문서 렌더링을 위한 API를 제공하므로 클라우드 스토리지 제공업체에서 직접 문서를 렌더링할 수 있습니다.
### GroupDocs.Viewer에 대한 무료 평가판이 있나요?
예, 제공된 사이트를 방문하여 무료 평가판을 통해 GroupDocs.Viewer를 탐색할 수 있습니다. [링크](https://releases.groupdocs.com/).