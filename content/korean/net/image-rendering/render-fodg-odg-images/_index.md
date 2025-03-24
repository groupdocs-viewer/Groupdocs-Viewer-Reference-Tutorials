---
title: FODG 및 ODG 이미지 렌더링
linktitle: FODG 및 ODG 이미지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 FODG 및 ODG 이미지를 HTML, JPG, PNG 및 PDF로 렌더링하는 방법을 알아보세요. 문서 처리 능력을 강화하세요.
weight: 15
url: /ko/net/image-rendering/render-fodg-odg-images/
---

# FODG 및 ODG 이미지 렌더링

## 소개
소프트웨어 개발 세계에서는 문서 형식을 효율적으로 처리하는 것이 무엇보다 중요합니다. .NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 FODG 및 ODG 이미지 렌더링 프로세스를 단순화하도록 설계된 강력한 도구입니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 이러한 이미지를 HTML, JPG, PNG 및 PDF와 같은 다양한 형식으로 렌더링하는 데 필요한 단계를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1.  .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: 시스템에 .NET Framework가 설치되어 있는지 확인하십시오.
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
구현을 시작하기 전에 필요한 네임스페이스를 가져옵니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1단계: 출력 디렉터리 설정
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"`렌더링된 이미지를 저장할 디렉터리 경로를 사용하세요.
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
여기서 FODG 이미지는 JPG 형식으로 렌더링됩니다.
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
마지막으로 FODG 이미지가 PDF 형식으로 렌더링됩니다.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 FODG 및 ODG 이미지를 다양한 형식으로 렌더링하는 방법을 살펴보았습니다. 다음 단계를 수행하면 문서 렌더링 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 모든 버전의 .NET Framework와 호환됩니까?
.NET용 GroupDocs.Viewer는 최신 버전을 포함하여 다양한 .NET Framework 버전과 호환됩니다.
### .NET용 GroupDocs.Viewer를 사용하여 문서를 비동기적으로 렌더링할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 성능 향상을 위해 비동기 렌더링 기능을 제공합니다.
### .NET용 GroupDocs.Viewer는 암호화된 문서 렌더링을 지원합니까?
예, .NET용 GroupDocs.Viewer는 적절한 암호 해독 키를 사용하여 암호화된 문서 렌더링을 지원합니다.
### .NET용 GroupDocs.Viewer를 사용하여 렌더링 출력을 사용자 정의할 수 있습니까?
물론, .NET용 GroupDocs.Viewer는 요구 사항에 따라 렌더링 출력을 조정할 수 있는 다양한 사용자 정의 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer를 사용하여 원격 저장 위치에서 문서를 렌더링할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 로컬 및 원격 저장 위치 모두에서 문서 렌더링을 지원합니다.