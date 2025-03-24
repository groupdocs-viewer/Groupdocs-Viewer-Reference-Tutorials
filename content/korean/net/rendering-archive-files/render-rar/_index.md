---
title: RAR 아카이브 렌더링
linktitle: RAR 아카이브 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 RAR 아카이브를 HTML, JPG, PNG 또는 PDF 형식으로 렌더링하는 방법을 알아보세요. RAR 아카이브의 내용을 쉽게 보고 공유할 수 있습니다.
weight: 13
url: /ko/net/rendering-archive-files/render-rar/
---

# RAR 아카이브 렌더링

## 소개
RAR 아카이브는 여러 파일과 폴더를 단일 컨테이너로 압축하고 저장하는 데 널리 사용되는 형식입니다. 이러한 아카이브의 내용을 보거나 공유하려면 RAR 아카이브를 HTML, JPG, PNG 또는 PDF와 같은 다양한 형식으로 렌더링하는 것이 필수적일 수 있습니다. 이 튜토리얼에서는 .NET용 GroupDocs.Viewer를 사용하여 RAR 아카이브를 렌더링하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. .NET용 GroupDocs.Viewer: 다음에서 .NET 라이브러리용 GroupDocs.Viewer를 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
2. 샘플 RAR 아카이브: 렌더링할 샘플 RAR 아카이브를 준비합니다.

## 네임스페이스 가져오기
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## 1단계: 출력 디렉터리 정의
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
.NET용 GroupDocs.Viewer를 사용하면 RAR 아카이브를 다양한 형식으로 간단하게 렌더링할 수 있습니다. 이 튜토리얼에 설명된 단계를 따르면 RAR 아카이브를 HTML, JPG, PNG 또는 PDF 형식으로 쉽게 변환하여 해당 콘텐츠를 쉽게 보고 공유할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer가 암호화된 RAR 아카이브를 처리할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 렌더링 프로세스 중에 필요한 암호가 제공되는 경우 암호화된 RAR 아카이브 렌더링을 지원합니다.
### 렌더링된 문서의 출력 모양을 사용자 정의할 수 있습니까?
전적으로! .NET용 GroupDocs.Viewer는 사용자가 자신의 기본 설정에 따라 렌더링된 문서의 모양을 조정할 수 있도록 광범위한 사용자 정의 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer는 RAR 이외의 다른 아카이브 형식 렌더링을 지원합니까?
예, .NET용 GroupDocs.Viewer는 ZIP, TAR, 7z 등을 포함한 다양한 아카이브 형식의 렌더링을 지원합니다.
### .NET용 GroupDocs.Viewer를 내 웹 응용 프로그램에 통합할 수 있나요?
틀림없이! .NET용 GroupDocs.Viewer는 데스크톱 및 웹 응용 프로그램 모두에 통합하는 데 적합한 API를 제공합니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 .NET용 GroupDocs.Viewer 무료 평가판을 이용할 수 있습니다.[웹사이트](https://releases.groupdocs.com/).