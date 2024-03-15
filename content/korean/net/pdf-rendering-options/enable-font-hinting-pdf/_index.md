---
title: PDF에서 글꼴 힌트 활성화
linktitle: PDF에서 글꼴 힌트 활성화
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 글꼴 힌트를 활성화하는 방법을 알아보세요. 원활한 통합을 위해 단계별 튜토리얼을 따르세요.
type: docs
weight: 14
url: /ko/net/pdf-rendering-options/enable-font-hinting-pdf/
---
## 소개
.NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 다양한 문서 형식을 보고 조작하기 위한 강력한 도구입니다. PDF, Microsoft Office 문서, 이미지 또는 기타 형식으로 작업하는 경우 GroupDocs.Viewer는 이러한 파일을 렌더링하고 상호 작용할 수 있는 완벽한 솔루션을 제공합니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하기 전에 다음 사항이 준비되어 있는지 확인하세요.
1. .NET 기본 이해: .NET 프레임워크 및 C# 프로그래밍 언어의 기본 사항을 숙지합니다.
2.  .NET용 GroupDocs.Viewer 설치: .NET용 GroupDocs.Viewer 라이브러리를 다운로드하여 설치합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.groupdocs.com/viewer/net/).
3. 개발 환경: Visual Studio 또는 기타 호환 가능한 IDE를 사용하여 개발 환경을 설정합니다.
4. 샘플 문서: 개발 프로세스 중에 작업할 샘플 문서를 수집합니다.

## 네임스페이스 가져오기
.NET 프로젝트에서 GroupDocs.Viewer 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 설정
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 페이지를 저장할 디렉터리를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
 렌더링된 페이지 파일의 이름을 지정하기 위한 형식을 정의합니다. 이 예에서 페이지는 파일 이름 패턴이 다음과 같은 PNG 이미지로 저장됩니다.`page_1.png`, `page_2.png`, 등등.
## 3단계: 뷰어 개체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.HIEROGLYPHS_1_PDF))
```
렌더링하려는 PDF 문서의 경로를 제공하여 뷰어 개체를 초기화합니다.
## 4단계: 렌더링 옵션 설정
```csharp
PngViewOptions options = new PngViewOptions(pageFilePathFormat);
options.PdfOptions.EnableFontHinting = true;
```
PNG 형식에 대한 렌더링 옵션을 만들고 PDF 옵션에서 글꼴 힌트를 활성화합니다.
## 5단계: 문서 렌더링
```csharp
viewer.View(options, 1);
```
지정된 옵션을 사용하여 문서를 렌더링합니다. 이 예에서는 렌더링이 첫 번째 페이지부터 시작됩니다.
## 6단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
문서가 성공적으로 렌더링되었음을 나타내는 성공 메시지를 표시하고 렌더링된 페이지가 저장되는 출력 디렉터리를 지정합니다.

## 결론
결론적으로 .NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 다양한 문서 형식을 보고 조작하기 위한 포괄적인 솔루션을 제공합니다. 제공된 튜토리얼을 따르고 해당 기능을 활용하면 문서 보기 기능을 .NET 프로젝트에 쉽게 통합할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?
.NET용 GroupDocs.Viewer는 .NET Core 및 .NET Framework를 포함하여 여러 버전의 .NET Framework를 지원합니다.
### 다양한 문서 형식에 대한 렌더링 옵션을 사용자 정의할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 요구 사항에 따라 렌더링 설정을 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, .NET용 GroupDocs.Viewer 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 지원을 받으려면 어떻게 해야 합니까?
 GroupDocs.Viewer 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).
### .NET용 GroupDocs.Viewer에 임시 라이센스를 사용할 수 있습니까?
 예, .NET용 GroupDocs.Viewer에 대한 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).