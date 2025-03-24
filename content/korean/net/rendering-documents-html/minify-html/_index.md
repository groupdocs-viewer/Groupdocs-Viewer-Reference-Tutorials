---
title: 렌더링된 HTML 문서 축소
linktitle: 렌더링된 HTML 문서 축소
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램에서 HTML 문서를 원활하게 렌더링하는 방법을 알아보세요.
weight: 11
url: /ko/net/rendering-documents-html/minify-html/
---

# 렌더링된 HTML 문서 축소

## 소개
.NET용 GroupDocs.Viewer는 개발자가 .NET 응용 프로그램 내에서 HTML 문서를 원활하게 렌더링할 수 있게 해주는 강력한 도구입니다. 직관적인 API와 강력한 기능을 통해 개발자는 문서 보기 기능을 애플리케이션에 쉽게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. C# 및 .NET Framework에 대한 지식
GroupDocs.Viewer for .NET을 효과적으로 활용하려면 C# 프로그래밍 언어와 .NET Framework에 대한 기본적인 이해가 있어야 합니다.
### 2. 비주얼 스튜디오 IDE
시스템에 Visual Studio IDE가 설치되어 있는지 확인하세요. 공식 홈페이지에서 다운로드하실 수 있습니다.
### 3. .NET 라이브러리용 GroupDocs.Viewer
 제공된에서 .NET 라이브러리용 GroupDocs.Viewer를 다운로드합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/) 프로젝트에 포함시키세요.
### 4. 문서 파일
.NET용 GroupDocs.Viewer를 사용하여 렌더링할 문서 파일을 준비합니다. 지원되는 파일 형식에는 DOCX, PDF, PPTX 등이 포함됩니다.
### 5. 임시 라이센스(선택)
 평가판 또는 테스트 환경에서 .NET용 GroupDocs.Viewer를 사용하는 경우 다음에서 임시 라이센스를 얻으세요.[임시 라이센스 페이지](https://purchase.groupdocs.com/temporary-license/).

## 네임스페이스 가져오기
.NET 응용 프로그램에서 .NET용 GroupDocs.Viewer 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 .NET용 GroupDocs.Viewer를 사용하여 렌더링된 HTML 문서를 축소하는 프로세스를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 정의
렌더링된 HTML 페이지를 저장할 디렉터리를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
렌더링된 각 HTML 페이지의 파일 경로 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: HTML 문서 렌더링
Viewer 개체를 인스턴스화하고 렌더링하려는 문서 파일의 경로를 전달합니다.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.Minify = true;
    viewer.View(options);
}
```
## 4단계: 성공 메시지 표시
문서가 성공적으로 렌더링되었음을 나타내는 메시지를 표시합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
결론적으로 .NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 HTML 문서를 렌더링하기 위한 완벽한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 문서 보기 기능을 애플리케이션에 쉽게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer를 사용하여 외부 소스에서 문서를 렌더링할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 로컬 파일, 스트림 및 URL을 포함한 다양한 소스의 문서 렌더링을 지원합니다.
### .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 예, 다음 사이트에서 .NET용 GroupDocs.Viewer 무료 평가판을 구할 수 있습니다.[공식 웹 사이트](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer는 다른 형식으로의 문서 변환을 지원합니까?
예, .NET용 GroupDocs.Viewer는 문서를 PDF, HTML, 이미지 등의 다양한 형식으로 변환하기 위한 API를 제공합니다.
### .NET용 GroupDocs.Viewer에서 문서의 렌더링 옵션을 사용자 정의할 수 있나요?
예, 요구 사항에 따라 페이지 방향, 품질, 워터마킹 등 다양한 렌더링 옵션을 사용자 정의할 수 있습니다.
### .NET용 GroupDocs.Viewer에 대한 지원은 어디서 구할 수 있나요?
 다음에서 지원을 구하고 커뮤니티에 참여할 수 있습니다.[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9).