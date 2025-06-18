---
"description": "GroupDocs.Viewer for .NET을 사용하여 FODG 및 ODG 이미지를 HTML, JPG, PNG, PDF로 렌더링하는 방법을 알아보세요. 문서 처리 능력을 향상시켜 보세요."
"linktitle": "FODG 및 ODG 이미지 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "FODG 및 ODG 이미지 렌더링"
"url": "/ko/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# FODG 및 ODG 이미지 렌더링

## 소개
소프트웨어 개발 분야에서는 문서 형식을 효율적으로 처리하는 것이 무엇보다 중요합니다. GroupDocs.Viewer for .NET은 .NET 애플리케이션에서 FODG 및 ODG 이미지를 렌더링하는 과정을 간소화하도록 설계된 강력한 도구입니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 이러한 이미지를 HTML, JPG, PNG, PDF 등 다양한 형식으로 렌더링하는 데 필요한 단계를 안내합니다.

![.NET용 GroupDocs.Viewer를 사용하여 FODG 및 ODG 이미지 렌더링](/viewer/image-rendering/render-fodg-and--odg-images.png)

## 필수 조건
튜토리얼을 시작하기 전에 다음 필수 조건을 충족하는지 확인하세요.
1. .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요. [여기](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: 시스템에 .NET Framework가 설치되어 있는지 확인하세요.
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 대한 지식이 도움이 됩니다.

## 네임스페이스 가져오기
구현을 시작하기 전에 필요한 네임스페이스를 가져옵니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1단계: 출력 디렉토리 설정
```csharp
string outputDirectory = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` 렌더링된 이미지를 저장할 디렉토리 경로를 입력합니다.
## 2단계: HTML로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
이 단계에서는 FODG 이미지를 HTML 형식으로 렌더링합니다.
## 3단계: JPG로 렌더링
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
여기서는 FODG 이미지를 JPG 포맷으로 렌더링합니다.
## 4단계: PNG로 렌더링
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
이 단계에서는 FODG 이미지를 PNG 형식으로 변환합니다.
## 5단계: PDF로 렌더링
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
마지막으로 FODG 이미지는 PDF 형식으로 렌더링됩니다.

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 FODG 및 ODG 이미지를 다양한 형식으로 렌더링하는 방법을 살펴보았습니다. 이 단계를 따라 하면 문서 렌더링 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET은 모든 버전의 .NET Framework와 호환됩니까?
GroupDocs.Viewer for .NET은 최신 버전을 포함한 다양한 .NET Framework 버전과 호환됩니다.
### GroupDocs.Viewer for .NET을 사용하여 문서를 비동기적으로 렌더링할 수 있나요?
네, GroupDocs.Viewer for .NET은 향상된 성능을 위해 비동기 렌더링 기능을 제공합니다.
### GroupDocs.Viewer for .NET은 암호화된 문서 렌더링을 지원합니까?
네, GroupDocs.Viewer for .NET은 적절한 복호화 키로 암호화된 문서의 렌더링을 지원합니다.
### GroupDocs.Viewer for .NET을 사용하여 렌더링 출력을 사용자 정의할 수 있습니까?
물론입니다. GroupDocs.Viewer for .NET은 사용자의 요구 사항에 맞게 렌더링 출력을 조정할 수 있는 다양한 사용자 정의 옵션을 제공합니다.
### GroupDocs.Viewer for .NET을 사용하여 원격 저장소 위치에서 문서를 렌더링할 수 있나요?
네, GroupDocs.Viewer for .NET은 로컬 및 원격 저장소 위치 모두에서 문서 렌더링을 지원합니다.