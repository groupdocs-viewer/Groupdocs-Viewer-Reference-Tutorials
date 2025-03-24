---
title: CHM 파일 렌더링
linktitle: CHM 파일 렌더링
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer를 사용하여 .NET에서 CHM 파일을 렌더링하는 방법을 알아보세요. CHM을 HTML, JPG, PNG 및 PDF 형식으로 쉽게 변환하세요.
weight: 10
url: /ko/net/rendering-web-documents/render-chm/
---

# CHM 파일 렌더링

## 소개
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 CHM(컴파일된 HTML 도움말) 파일을 렌더링하는 방법을 살펴보겠습니다. .NET용 GroupDocs.Viewer는 개발자가 외부 소프트웨어를 설치할 필요 없이 .NET 응용 프로그램 내에서 170개 이상의 문서 유형을 표시할 수 있는 강력한 문서 렌더링 API입니다.

## 전제조건

CHM 파일 렌더링을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### .NET용 GroupDocs.Viewer 설치

 시작하려면 .NET용 GroupDocs.Viewer를 설치해야 합니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[GroupDocs 웹사이트](https://releases.groupdocs.com/viewer/net/) 또는 패키지 관리자 콘솔에서 다음 명령을 실행하여 NuGet 패키지 관리자를 통해 설치합니다.

```bash
Install-Package GroupDocs.Viewer
```

## 네임스페이스 가져오기

필요한 네임스페이스를 프로젝트로 가져와야 합니다.

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 렌더링 프로세스를 여러 단계로 나누어 보겠습니다.

## 1단계: 출력 디렉터리 정의

렌더링된 파일을 저장할 디렉터리를 정의합니다.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2단계: HTML로 렌더링

CHM 파일을 HTML로 렌더링하려면 다음 코드 조각을 사용하십시오.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // 모든 CHM 콘텐츠를 단일 페이지로 변환하려면 true로 설정하세요.

    viewer.View(options); //모든 페이지 변환
}
```

## 3단계: JPG로 렌더링

CHM 파일을 JPG 이미지로 렌더링하려면 다음 코드 조각을 사용하십시오.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1, 2, 3페이지만 변환
}
```

## 4단계: PNG로 렌더링

CHM 파일을 PNG 이미지로 렌더링하려면 다음 코드 조각을 사용하십시오.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1, 2, 3페이지만 변환
}
```

## 5단계: PDF로 렌더링

CHM 파일을 PDF 문서로 렌더링하려면 다음 코드 조각을 사용하십시오.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //모든 페이지 변환
}
```

## 6단계: 출력 확인

렌더링 프로세스가 완료되면 지정된 출력 디렉터리에서 렌더링된 파일을 확인합니다.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론

.NET용 GroupDocs.Viewer를 사용하여 CHM 파일을 렌더링하는 과정은 간단합니다. 이 튜토리얼에 설명된 단계를 따르면 CHM 문서를 .NET 애플리케이션 내에서 HTML, 이미지(JPG, PNG) 및 PDF와 같은 다양한 형식으로 효율적으로 변환할 수 있습니다.

## FAQ

### 질문 1: GroupDocs.Viewer는 CHM 외에 다른 문서 형식을 렌더링할 수 있습니까?

A1: 예, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등을 포함하여 170개 이상의 문서 형식 렌더링을 지원합니다.

### 질문 2: GroupDocs.Viewer는 .NET Core와 호환됩니까?

A2: 예, GroupDocs.Viewer는 기존 .NET Framework 외에도 .NET Core를 지원합니다.

### Q3: 다양한 출력 형식에 대한 렌더링 옵션을 사용자 정의할 수 있습니까?

A3: 예, GroupDocs.Viewer는 페이지 번호 지정, 이미지 품질 설정, 출력 경로 구성 등 렌더링 프로세스를 사용자 정의하기 위한 다양한 옵션을 제공합니다.

### 질문 4: GroupDocs.Viewer에는 문서 렌더링을 위해 외부 종속성이 필요합니까?

A4: 아니요, GroupDocs.Viewer는 독립 실행형 라이브러리이므로 외부 종속성이나 타사 소프트웨어 설치가 필요하지 않습니다.

### Q5: GroupDocs.Viewer에 대한 무료 평가판이 있습니까?

 A5: 예, 다음 사이트를 방문하면 GroupDocs.Viewer 무료 평가판을 이용할 수 있습니다.[웹사이트](https://releases.groupdocs.com/).