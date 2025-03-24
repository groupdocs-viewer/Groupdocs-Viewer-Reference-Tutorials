---
title: 사용자 정의 글꼴로 렌더링
linktitle: 사용자 정의 글꼴로 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 사용자 정의 글꼴로 문서를 렌더링하는 방법을 알아보세요. 손쉽게 시각적 프레젠테이션을 향상할 수 있습니다.
weight: 18
url: /ko/net/rendering-options/render-custom-fonts/
---
## 소개
.NET 개발 영역에서 GroupDocs.Viewer는 다양한 형식의 문서를 렌더링하기 위한 강력한 솔루션을 제공합니다. 다양한 기능 중에서 GroupDocs.Viewer를 사용하면 사용자 정의 글꼴로 문서를 렌더링하여 응용 프로그램에 개인화 및 유연성을 추가할 수 있습니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하여 사용자 정의 글꼴로 문서를 렌더링하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
.NET용 GroupDocs.Viewer를 활용하려면 개발 환경에 이를 설치해야 합니다. 제공된 링크에서 필요한 패키지를 다운로드할 수 있습니다.
[.NET용 GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/net/)
### 2. 글꼴 얻기
문서 렌더링에 사용할 사용자 정의 글꼴을 준비합니다. 애플리케이션 환경 내에서 이러한 글꼴에 액세스할 수 있는지 확인하세요.
### 3. 개발 환경 설정
시스템에 작동하는 .NET 개발 환경을 설정하십시오. 필요한 도구와 프레임워크가 설치되어 있는지 확인하세요.
### 4. C#과 .NET의 기본 이해
튜토리얼을 효과적으로 따라하려면 C# 프로그래밍 언어와 .NET 프레임워크 기본 사항을 숙지하세요.

## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer를 사용하여 사용자 정의 글꼴로 문서를 렌더링하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;
```

## 1단계: 글꼴 소스 설정
먼저 문서 렌더링에 사용할 글꼴 소스를 정의합니다. 이 단계를 수행하면 GroupDocs.Viewer가 사용자 정의 글꼴에 액세스할 수 있습니다.
```csharp
FontSettings.SetFontSources(
    new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));
```
## 2단계: 출력 디렉터리 정의
렌더링된 문서를 저장할 디렉터리를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 3단계: 페이지 파일 경로 형식 정의
렌더링된 문서 페이지가 포함된 출력 HTML 파일의 이름을 지정하기 위한 형식을 설정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 4단계: 사용자 정의 글꼴을 사용하여 문서 렌더링
 GroupDocs.Viewer API를 활용하여 사용자 정의 글꼴로 문서를 렌더링합니다. 바꾸다`TestFiles.MISSING_FONT_ODG` 문서의 경로와 함께.
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 5단계: 출력 디렉터리 표시
렌더링된 문서 페이지가 저장되는 위치를 사용자에게 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 사용자 정의 글꼴로 문서를 렌더링하는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 예제를 활용하면 .NET 애플리케이션에서 문서의 시각적 표현을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Q: 웹 응용 프로그램에서 .NET용 GroupDocs.Viewer를 사용하여 사용자 정의 글꼴로 문서를 렌더링할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 사용자 정의 글꼴로 문서를 렌더링하기 위해 데스크톱 및 웹 응용 프로그램 모두에 통합될 수 있습니다.
### 질문: .NET용 GroupDocs.Viewer는 다양한 문서 형식과 호환됩니까?
전적으로! GroupDocs.Viewer는 PDF, Microsoft Office 파일, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### Q: 사용할 수 있는 사용자 정의 글꼴 유형에 제한이 있나요?
응용 프로그램 환경 내에서 사용자 정의 글꼴에 액세스할 수 있는 한, .NET용 GroupDocs.Viewer는 제한 없이 해당 글꼴을 사용하여 문서를 렌더링할 수 있습니다.
### Q: 렌더링된 문서의 출력 형식을 사용자 정의할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 HTML, 이미지 형식, PDF를 포함한 출력 형식을 사용자 정의하는 옵션을 제공합니다.
### Q: .NET용 GroupDocs.Viewer는 개발자를 위한 지원 및 설명서를 제공합니까?
틀림없이! GroupDocs는 개발자가 GroupDocs.Viewer를 효과적으로 활용하는 데 도움이 되는 포괄적인 문서, 지원 포럼 및 리소스를 제공합니다.