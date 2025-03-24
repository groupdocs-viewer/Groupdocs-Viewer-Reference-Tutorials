---
title: AI 이미지 렌더링
linktitle: AI 이미지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램에서 AI 이미지를 손쉽게 렌더링하는 방법을 알아보세요. 원활한 통합을 위해 단계별 튜토리얼을 따르세요.
weight: 10
url: /ko/net/image-rendering/render-ai-images/
---
## 소개
.NET용 GroupDocs.Viewer는 개발자가 .NET 응용 프로그램 내에서 다양한 문서 형식을 손쉽게 렌더링할 수 있게 해주는 강력한 라이브러리입니다. AI 이미지, PDF 또는 기타 문서 유형을 표시해야 하는 경우 GroupDocs.Viewer는 프로젝트에 원활하게 통합할 수 있도록 다양한 출력 형식을 제공하여 프로세스를 단순화합니다. 이 튜토리얼에서는 .NET용 GroupDocs.Viewer를 사용하여 AI 이미지를 렌더링하는 과정을 단계별로 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. Visual Studio: 시스템에 Visual Studio IDE를 설치합니다.
2.  .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
3. C#에 대한 기본 지식: 코드 예제를 이해하려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.

## 네임스페이스 가져오기
C# 프로젝트에서 .NET용 GroupDocs.Viewer의 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

.NET용 GroupDocs.Viewer를 사용하여 AI 이미지를 렌더링하려면 각 단계가 특정 출력 형식에 맞는 여러 단계가 필요합니다. 아래에서는 명확성을 위해 프로세스를 개별 단계로 분류하겠습니다.
## 1단계: 출력 디렉터리 지정
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: HTML로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 3단계: JPG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 4단계: PNG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 5단계: PDF로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 결론
.NET용 GroupDocs.Viewer는 .NET 애플리케이션 내에서 AI 이미지와 다양한 문서 형식을 렌더링하기 위한 완벽한 솔루션을 제공합니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 개발자는 문서 렌더링 기능을 프로젝트에 쉽게 통합할 수 있습니다.
## FAQ
### AI 이미지를 렌더링할 때 출력 모양을 사용자 정의할 수 있나요?
예, .NET용 GroupDocs.Viewer는 페이지 크기, 이미지 품질 등을 포함하여 출력 모양을 사용자 정의하기 위한 다양한 옵션을 제공합니다.
### 테스트 목적으로 사용할 수 있는 평가판이 있습니까?
 예, GroupDocs에서 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/) 구매하기 전에 라이브러리의 기능을 평가합니다.
### GroupDocs.Viewer는 암호화된 AI 이미지 렌더링을 지원합니까?
예, .NET용 GroupDocs.Viewer는 제공된 적절한 암호 해독 키를 사용하여 암호화된 AI 이미지 렌더링을 지원합니다.
### URL에서 직접 AI 이미지를 렌더링할 수 있나요?
예, .NET용 GroupDocs.Viewer를 사용하면 로컬 파일 경로 대신 URL 경로를 지정하여 URL에서 AI 이미지를 렌더링할 수 있습니다.
### .NET용 GroupDocs.Viewer에 대한 기술 지원이 제공됩니까?
 예, GroupDocs를 통해 기술 지원을 받을 수 있습니다.[법정](https://forum.groupdocs.com/c/viewer/9)에서 질문하고, 문제를 보고하고, 커뮤니티에 도움을 요청할 수 있습니다.