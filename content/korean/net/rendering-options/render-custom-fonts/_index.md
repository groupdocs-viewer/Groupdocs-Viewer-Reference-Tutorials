---
"description": "GroupDocs.Viewer for .NET을 사용하여 사용자 지정 글꼴로 문서를 렌더링하는 방법을 알아보세요. 시각적 프레젠테이션을 손쉽게 향상시켜 보세요."
"linktitle": "사용자 정의 글꼴로 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "사용자 정의 글꼴로 렌더링"
"url": "/ko/net/rendering-options/render-custom-fonts/"
"weight": 18
type: docs
---
# 사용자 정의 글꼴로 렌더링

## 소개
.NET 개발 분야에서 GroupDocs.Viewer는 다양한 형식의 문서를 렌더링하는 강력한 솔루션을 제공합니다. 다양한 기능 중에서도 GroupDocs.Viewer는 사용자 지정 글꼴을 사용하여 문서를 렌더링할 수 있도록 지원하여 애플리케이션의 개인화 및 유연성을 높여줍니다.
## 필수 조건
GroupDocs.Viewer for .NET을 사용하여 사용자 지정 글꼴이 포함된 문서를 렌더링하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
GroupDocs.Viewer for .NET을 사용하려면 개발 환경에 설치되어 있어야 합니다. 제공된 링크에서 필요한 패키지를 다운로드할 수 있습니다.
[.NET용 GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/net/)
### 2. 글꼴 얻기
문서 렌더링에 사용할 사용자 지정 글꼴을 준비하세요. 애플리케이션 환경에서 이러한 글꼴을 사용할 수 있는지 확인하세요.
### 3. 개발 환경 설정
시스템에 .NET 개발 환경을 구축하고, 필요한 도구와 프레임워크가 설치되어 있는지 확인하세요.
### 4. C# 및 .NET에 대한 기본 이해
튜토리얼을 효과적으로 따라가려면 C# 프로그래밍 언어와 .NET 프레임워크 기본 사항에 익숙해지세요.

## 네임스페이스 가져오기
GroupDocs.Viewer for .NET을 사용하여 사용자 지정 글꼴이 적용된 문서를 렌더링하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;
```

## 1단계: 글꼴 소스 설정
먼저, 문서 렌더링에 사용할 글꼴 소스를 정의합니다. 이 단계를 통해 GroupDocs.Viewer가 사용자 지정 글꼴에 접근할 수 있습니다.
```csharp
FontSettings.SetFontSources(
    new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));
```
## 2단계: 출력 디렉토리 정의
렌더링된 문서를 저장할 디렉토리를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 3단계: 페이지 파일 경로 형식 정의
렌더링된 문서 페이지가 포함된 출력 HTML 파일의 이름 형식을 설정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 4단계: 사용자 정의 글꼴로 문서 렌더링
GroupDocs.Viewer API를 활용하여 사용자 지정 글꼴로 문서를 렌더링합니다. 바꾸기 `TestFiles.MISSING_FONT_ODG` 문서 경로를 포함합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 5단계: 출력 디렉토리 표시
렌더링된 문서 페이지가 저장된 위치를 사용자에게 알려줍니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 사용자 지정 글꼴로 문서를 렌더링하는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 예제를 활용하면 .NET 애플리케이션에서 문서의 시각적 표현을 향상시킬 수 있습니다.
## 자주 묻는 질문
### 질문: 웹 애플리케이션에서 GroupDocs.Viewer for .NET을 사용하여 사용자 지정 글꼴이 적용된 문서를 렌더링할 수 있나요?
네, GroupDocs.Viewer for .NET은 사용자 정의 글꼴로 문서를 렌더링하기 위해 데스크톱과 웹 애플리케이션에 모두 통합될 수 있습니다.
### 질문: GroupDocs.Viewer for .NET은 다양한 문서 형식과 호환됩니까?
물론입니다! GroupDocs.Viewer는 PDF, Microsoft Office 파일, 이미지 등 다양한 문서 형식을 지원합니다.
### 질문: 사용할 수 있는 사용자 정의 글꼴의 유형에 제한이 있나요?
사용자 정의 글꼴을 애플리케이션 환경 내에서 사용할 수 있는 한, .NET용 GroupDocs.Viewer는 아무런 제한 없이 해당 글꼴을 사용하여 문서를 렌더링할 수 있습니다.
### 질문: 렌더링된 문서의 출력 형식을 사용자 정의할 수 있나요?
네, .NET용 GroupDocs.Viewer는 HTML, 이미지 형식, PDF 등 출력 형식을 사용자 정의하는 옵션을 제공합니다.
### 질문: GroupDocs.Viewer for .NET은 개발자에게 지원과 설명서를 제공합니까?
물론입니다! GroupDocs는 개발자가 GroupDocs.Viewer를 효과적으로 활용할 수 있도록 포괄적인 문서, 지원 포럼, 리소스를 제공합니다.