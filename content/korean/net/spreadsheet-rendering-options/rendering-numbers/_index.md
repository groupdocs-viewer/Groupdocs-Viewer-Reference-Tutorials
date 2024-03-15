---
title: 렌더링 번호
linktitle: 렌더링 번호
second_title: GroupDocs.Viewer .NET API
description: Numbers 파일을 원활하게 렌더링하는 데 있어 .NET용 Groupdocs.Viewer의 강력한 기능을 살펴보세요. HTML, JPG, PNG, PDF로 손쉽게 변환하세요.
type: docs
weight: 15
url: /ko/net/spreadsheet-rendering-options/rendering-numbers/
---
## 소개
.NET용 Groupdocs.Viewer를 사용하여 Numbers 파일을 렌더링하는 방법에 대한 단계별 자습서에 오신 것을 환영합니다. 숙련된 개발자이든 초보자이든 이 가이드는 Numbers 문서를 다양한 형식으로 변환하는 과정을 안내합니다. .NET용 Groupdocs.Viewer는 문서 보기 기능을 .NET 응용 프로그램에 완벽하게 통합할 수 있는 강력한 도구입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 및 .NET 개발에 대한 실무 지식.
-  .NET 라이브러리용 Groupdocs.Viewer가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.groupdocs.com/viewer/net/).
- 출력 파일이 저장될 문서 디렉터리 경로입니다.
## 네임스페이스 가져오기
C# 프로젝트에서 Groupdocs.Viewer 라이브러리를 사용하는 데 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 설정
렌더링을 시작하기 전에 변환된 파일이 저장될 출력 디렉터리를 정의합니다. "Your Document Directory"를 실제 경로로 바꾸십시오.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 다중 페이지 HTML로 렌더링
다음 코드를 사용하여 Numbers 파일을 여러 페이지 HTML로 변환합니다.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 3단계: JPG로 렌더링
다음 코드를 사용하여 Numbers 파일을 JPG 형식으로 변환합니다.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 4단계: PNG로 렌더링
다음 코드를 사용하여 Numbers 파일을 PNG 형식으로 변환합니다.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 5단계: PDF로 렌더링
마지막으로 다음 코드를 사용하여 Numbers 파일을 PDF 형식으로 변환합니다.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
축하해요! .NET용 Groupdocs.Viewer를 사용하여 Numbers 파일을 다양한 형식으로 성공적으로 렌더링했습니다.
## 결론
이 튜토리얼에서는 .NET용 Groupdocs.Viewer를 사용하여 Numbers 파일을 렌더링하는 기본 사항을 다루었습니다. 이 강력한 라이브러리는 .NET 애플리케이션에서 문서를 보고 변환하기 위한 완벽한 통합을 제공합니다.
## 자주 묻는 질문
### 다른 문서 유형과 함께 .NET용 Groupdocs.Viewer를 사용할 수 있습니까?
예, Groupdocs.Viewer는 Word, Excel, PDF 등을 포함한 광범위한 문서 형식을 지원합니다.
### 테스트 목적으로 임시 라이센스를 사용할 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.groupdocs.com/temporary-license/) 시험용.
### .NET용 Groupdocs.Viewer에 대한 지원은 어디서 찾을 수 있나요?
 방문하다[Groupdocs.뷰어 포럼](https://forum.groupdocs.com/c/viewer/9) 도움과 토론을 위해.
### .NET용 Groupdocs.Viewer 정식 버전을 구입하려면 어떻게 해야 합니까?
 정식 버전을 구매하실 수 있습니다[여기](https://purchase.groupdocs.com/buy).
### 무료 평가판을 사용할 수 있나요?
 예, 무료 평가판을 사용해 볼 수 있습니다[여기](https://releases.groupdocs.com/).