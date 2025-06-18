---
"description": "GroupDocs.Viewer를 사용하여 .NET에서 CHM 파일을 렌더링하는 방법을 알아보세요. CHM 파일을 HTML, JPG, PNG, PDF 형식으로 손쉽게 변환할 수 있습니다."
"linktitle": "CHM 파일 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CHM 파일 렌더링"
"url": "/ko/net/rendering-web-documents/render-chm/"
"weight": 10
---

# CHM 파일 렌더링

## 소개
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 CHM(컴파일된 HTML 도움말) 파일을 렌더링하는 방법을 살펴보겠습니다. GroupDocs.Viewer for .NET은 개발자가 외부 소프트웨어를 설치하지 않고도 .NET 애플리케이션 내에서 170개 이상의 문서 유형을 표시할 수 있도록 해주는 강력한 문서 렌더링 API입니다.

## 필수 조건

CHM 파일 렌더링에 들어가기 전에 다음 필수 구성 요소가 있는지 확인하세요.

### .NET용 GroupDocs.Viewer 설치

시작하려면 .NET용 GroupDocs.Viewer를 설치해야 합니다. 라이브러리는 다음에서 다운로드할 수 있습니다. [GroupDocs 웹사이트](https://releases.groupdocs.com/viewer/net/) 또는 패키지 관리자 콘솔에서 다음 명령을 실행하여 NuGet 패키지 관리자를 통해 설치하세요.

```bash
Install-Package GroupDocs.Viewer
```

## 네임스페이스 가져오기

프로젝트에 필요한 네임스페이스를 가져오세요.

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 렌더링 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: 출력 디렉토리 정의

렌더링된 파일을 저장할 디렉토리를 정의합니다.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2단계: HTML로 렌더링

CHM 파일을 HTML로 렌더링하려면 다음 코드 조각을 사용하세요.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // 모든 CHM 콘텐츠를 단일 페이지로 변환하려면 true로 설정합니다.

    viewer.View(options); // 모든 페이지 변환
}
```

## 3단계: JPG로 렌더링

CHM 파일을 JPG 이미지로 변환하려면 다음 코드 조각을 사용하세요.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1, 2, 3페이지만 변환
}
```

## 4단계: PNG로 렌더링

CHM 파일을 PNG 이미지로 렌더링하려면 다음 코드 조각을 사용하세요.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1, 2, 3페이지만 변환
}
```

## 5단계: PDF로 렌더링

CHM 파일을 PDF 문서로 변환하려면 다음 코드 조각을 사용하세요.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // 모든 페이지 변환
}
```

## 6단계: 출력 확인

렌더링 프로세스가 완료되면 지정된 출력 디렉토리에서 렌더링된 파일을 확인하세요.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론

GroupDocs.Viewer for .NET을 사용하여 CHM 파일을 렌더링하는 것은 간단한 과정입니다. 이 튜토리얼에 설명된 단계를 따르면 .NET 애플리케이션에서 CHM 문서를 HTML, 이미지(JPG, PNG), PDF 등 다양한 형식으로 효율적으로 변환할 수 있습니다.

## 자주 묻는 질문

### 질문 1: GroupDocs.Viewer는 CHM 외의 다른 문서 형식을 렌더링할 수 있나요?

A1: 네, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등 170개 이상의 문서 형식 렌더링을 지원합니다.

### 질문 2: GroupDocs.Viewer는 .NET Core와 호환됩니까?

A2: 네, GroupDocs.Viewer는 기존 .NET Framework 외에도 .NET Core를 지원합니다.

### 질문 3: 다양한 출력 형식에 맞게 렌더링 옵션을 사용자 지정할 수 있나요?

A3: 네, GroupDocs.Viewer는 페이지 번호 지정, 이미지 품질 설정, 출력 경로 구성 등 렌더링 프로세스를 사용자 정의하기 위한 다양한 옵션을 제공합니다.

### 질문 4: GroupDocs.Viewer는 문서 렌더링을 위해 외부 종속성이 필요합니까?

A4: 아니요, GroupDocs.Viewer는 독립형 라이브러리이므로 외부 종속성이나 타사 소프트웨어 설치가 필요하지 않습니다.

### 질문 5: GroupDocs.Viewer에 대한 무료 평가판이 있나요?

A5: 예, GroupDocs.Viewer의 무료 평가판을 이용하려면 다음 사이트를 방문하세요. [웹사이트](https://releases.groupdocs.com/).