---
"description": "GroupDocs.Viewer for .NET을 사용하여 RAR 아카이브를 HTML, JPG, PNG 또는 PDF 형식으로 변환하는 방법을 알아보세요. RAR 아카이브의 내용을 쉽게 보고 공유하세요."
"linktitle": "RAR 아카이브 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "RAR 아카이브 렌더링"
"url": "/ko/net/rendering-archive-files/render-rar/"
"weight": 13
type: docs
---
# RAR 아카이브 렌더링

## 소개
RAR 아카이브는 여러 파일과 폴더를 하나의 컨테이너에 압축하고 저장하는 데 널리 사용되는 형식입니다. RAR 아카이브를 HTML, JPG, PNG, PDF 등 다양한 형식으로 렌더링하는 것은 이러한 아카이브의 내용을 보거나 공유하는 데 필수적입니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 RAR 아카이브를 렌더링하는 방법을 살펴보겠습니다.
## 필수 조건
시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.
1. .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer 라이브러리를 설치합니다. [다운로드 링크](https://releases.groupdocs.com/viewer/net/).
2. 샘플 RAR 아카이브: 렌더링을 위해 샘플 RAR 아카이브를 준비하세요.

## 네임스페이스 가져오기
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: HTML로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 3단계: JPG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 4단계: PNG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 5단계: PDF로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 결론
GroupDocs.Viewer for .NET을 사용하면 RAR 아카이브를 다양한 형식으로 간편하게 변환할 수 있습니다. 이 튜토리얼에 설명된 단계를 따라 RAR 아카이브를 HTML, JPG, PNG 또는 PDF 형식으로 손쉽게 변환하여 콘텐츠를 쉽게 보고 공유할 수 있습니다.
## 자주 묻는 질문
### .NET용 GroupDocs.Viewer는 암호화된 RAR 아카이브를 처리할 수 있나요?
네, GroupDocs.Viewer for .NET은 렌더링 프로세스 중에 필요한 암호가 제공되는 경우 암호화된 RAR 아카이브 렌더링을 지원합니다.
### 렌더링된 문서의 출력 모양을 사용자 정의할 수 있나요?
물론입니다! GroupDocs.Viewer for .NET은 사용자가 튜토리얼에 따라 렌더링된 문서의 모양을 조정할 수 있는 광범위한 사용자 지정 옵션을 제공합니다.
### GroupDocs.Viewer for .NET은 RAR 외의 다른 보관 형식 렌더링을 지원합니까?
네, GroupDocs.Viewer for .NET은 ZIP, TAR, 7z 등 다양한 보관 형식 렌더링을 지원합니다.
### GroupDocs.Viewer for .NET을 내 웹 애플리케이션에 통합할 수 있나요?
물론입니다! GroupDocs.Viewer for .NET은 데스크톱 및 웹 애플리케이션 모두에 통합할 수 있는 API를 제공합니다.
### GroupDocs.Viewer for .NET의 평가판이 있나요?
예, .NET용 GroupDocs.Viewer의 무료 평가판을 이용할 수 있습니다. [웹사이트](https://releases.groupdocs.com/).