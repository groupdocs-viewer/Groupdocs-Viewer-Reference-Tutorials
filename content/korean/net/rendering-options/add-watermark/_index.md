---
title: 문서에 워터마크 추가
linktitle: 문서에 워터마크 추가
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 문서에 워터마크를 원활하게 추가하는 방법을 알아보세요. 따라하기 쉬운 튜토리얼을 통해 문서 보안과 브랜딩을 강화하세요.
weight: 10
url: /ko/net/rendering-options/add-watermark/
---

# 문서에 워터마크 추가

## 소개
오늘날의 디지털 시대에 다양한 문서 형식을 원활하게 관리하고 보는 것은 많은 기업과 개인 모두에게 필수입니다. 다행히 .NET용 GroupDocs.Viewer와 같은 도구를 사용하면 문서 처리가 매우 쉬워집니다. 이 강력한 .NET 라이브러리를 사용하면 개발자는 문서 보기 기능을 응용 프로그램에 쉽게 통합할 수 있으므로 사용자는 문서를 생성한 원본 소프트웨어 없이도 문서를 볼 수 있습니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하여 문서에 워터마크를 추가하기 전에 다음 사항이 있는지 확인하세요.
1. 환경 설정: .NET Framework 또는 .NET Core가 설치된 개발 환경을 설정합니다.
2.  .NET용 GroupDocs.Viewer: 다음에서 .NET 라이브러리용 GroupDocs.Viewer를 다운로드하고 설치합니다.[다운로드 페이지](https://releases.groupdocs.com/viewer/net/).
3. 문서 파일: DOCX, PDF 등 작업하려는 문서 파일을 준비합니다.
4. C#에 대한 기본 지식: 코드 예제를 구현하려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.

## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer를 사용하여 문서에 워터마크를 추가하기 전에 C# 코드에서 필수 네임스페이스를 가져와야 합니다. 이 단계를 통해 라이브러리에서 제공하는 클래스와 메서드에 원활하게 액세스할 수 있습니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 .NET용 GroupDocs.Viewer를 사용하여 문서에 워터마크를 추가하는 과정을 살펴보겠습니다. 워터마킹 기능을 애플리케이션에 원활하게 통합하려면 다음 단계를 따르세요.
## 1단계: 출력 디렉터리 설정
```csharp
string outputDirectory = "Your Document Directory";
```
워터마크를 적용한 후 출력 파일을 저장할 디렉터리를 지정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
렌더링된 페이지의 파일 경로 형식을 설정합니다. 이 예에서는 페이지 번호가 포함된 HTML 파일이 생성됩니다.
## 3단계: 뷰어 개체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // 코드는 다음 단계에서 계속됩니다...
}
```
문서 파일의 경로를 매개변수로 전달하여 Viewer 클래스의 인스턴스를 만듭니다. 이 예에서는 샘플 DOCX 파일을 사용하고 있습니다.
## 4단계: HTML 보기 옵션 구성
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
문서에 추가할 워터마크 텍스트를 포함하여 HTML 보기 옵션을 구성합니다.
## 5단계: 워터마크가 있는 문서 보기
```csharp
viewer.View(options);
```
구성된 옵션을 전달하여 Viewer 개체의 View 메서드를 호출합니다. 그러면 지정된 워터마크가 포함된 문서가 렌더링됩니다.
## 6단계: 출력 디렉터리 경로 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
사용자에게 문서가 성공적으로 렌더링되었음을 알리고 출력 파일이 저장되는 디렉터리를 지정합니다.

## 결론
.NET용 GroupDocs.Viewer는 프로그래밍 방식으로 문서에 워터마크를 추가하는 편리한 방법을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 워터마킹 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 보안 및 브랜딩을 강화할 수 있습니다.
## FAQ
### 워터마크의 모양을 사용자 정의할 수 있나요?
예, 텍스트, 글꼴, 색상, 크기, 위치 등 워터마크의 다양한 속성을 사용자 정의할 수 있습니다.
### GroupDocs.Viewer는 원격 소스의 문서 보기를 지원합니까?
예, GroupDocs.Viewer는 로컬 저장소와 원격 URL의 문서 보기를 지원합니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/).
### 문서의 여러 페이지에 워터마크를 추가할 수 있나요?
물론, GroupDocs.Viewer를 사용하면 문서의 개별 페이지 또는 모든 페이지에 워터마크를 추가할 수 있습니다.
### 문제가 발생하면 어떻게 지원을 받을 수 있나요?
 GroupDocs 커뮤니티 포럼에서 도움과 지원을 구할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).