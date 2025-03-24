---
title: 렌더링 텍스트 파일(.txt)
linktitle: 렌더링 텍스트 파일(.txt)
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 텍스트 파일을 다양한 형식으로 원활하게 변환하는 방법을 살펴보세요. 문서 관리 기능을 손쉽게 향상하세요.
weight: 10
url: /ko/net/rendering-text-files/render-txt/
---
## 소개
문서 관리 및 조작 영역에서 .NET용 GroupDocs.Viewer는 다양한 문서 형식을 효율적으로 렌더링할 수 있는 다양한 기능을 제공하는 강력한 도구로 부각되고 있습니다. 이 기사에서는 .NET용 GroupDocs.Viewer를 활용하여 텍스트 파일(.txt)을 여러 형식으로 렌더링하는 복잡한 과정을 살펴봅니다. 텍스트 파일을 HTML, JPG, PNG 또는 PDF로 변환하려는 경우 GroupDocs.Viewer는 이러한 작업을 원활하게 수행하는 데 필요한 도구를 제공합니다.
## 전제조건
변환 프로세스를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
 개발 환경에 .NET용 GroupDocs.Viewer가 설치되어 있는지 확인하세요. 필요한 파일은 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework에 대한 기본 지식
프로젝트를 설정하고 코드베이스 내에서 라이브러리를 활용하는 방법을 포함하여 .NET 프레임워크의 기본 사항을 숙지하세요.
### 3. 샘플 텍스트 파일
변환하려는 샘플 텍스트 파일(.txt)을 준비합니다. 이러한 파일은 변환 프로세스의 입력 역할을 합니다.

## 네임스페이스 가져오기
변환 프로세스를 시작하기 전에 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이를 통해 .NET용 GroupDocs.Viewer가 제공하는 기능에 원활하게 액세스할 수 있습니다.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
변환 프로세스를 효과적으로 안내하기 위해 각 예를 여러 단계로 나누어 보겠습니다.

## 1단계: HTML 출력 경로 정의
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
HTML 출력 파일의 전체 경로를 지정합니다.
## 2단계: 텍스트 파일을 다중 페이지 HTML로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 인스턴스화`Viewer` 텍스트 파일의 경로가 있는 개체입니다. 구성`HtmlViewOptions` 포함된 리소스의 경우 텍스트 파일을 여러 페이지 HTML로 렌더링합니다.
## 3단계: 단일 페이지 HTML 출력 경로 정의
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
단일 페이지 HTML 출력 파일의 전체 경로를 지정합니다.
## 4단계: 텍스트 파일을 단일 페이지 HTML로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 인스턴스화`Viewer` 텍스트 파일의 경로가 있는 개체입니다. 구성`HtmlViewOptions` 임베디드 리소스 및 세트의 경우`RenderToSinglePage` 사실로. 텍스트 파일을 단일 페이지 HTML로 렌더링합니다.
## 5단계: JPG 출력 경로 정의
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
JPG 출력 파일의 전체 경로를 지정합니다.
## 6단계: 텍스트 파일을 JPG로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 인스턴스화`Viewer` 텍스트 파일의 경로가 있는 개체입니다. 구성`JpgViewOptions` 출력 경로에 대해 텍스트 파일을 JPG 형식으로 렌더링합니다.
## 7단계: PNG 출력 경로 정의
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
PNG 출력 파일의 전체 경로를 지정합니다.
## 8단계: 텍스트 파일을 PNG로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 인스턴스화`Viewer` 텍스트 파일의 경로가 있는 개체입니다. 구성`PngViewOptions` 출력 경로에 대해 텍스트 파일을 PNG 형식으로 렌더링합니다.
## 9단계: PDF 출력 경로 정의
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
PDF 출력 파일의 전체 경로를 지정합니다.
## 10단계: 텍스트 파일을 PDF로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 인스턴스화`Viewer` 텍스트 파일의 경로가 있는 개체입니다. 구성`PdfViewOptions` 출력 경로를 지정하고 텍스트 파일을 PDF 형식으로 렌더링합니다.

## 결론
결론적으로, .NET용 GroupDocs.Viewer를 사용하면 개발자가 텍스트 파일을 HTML, JPG, PNG 및 PDF를 포함한 다양한 형식으로 손쉽게 렌더링할 수 있습니다. 이 문서에 설명된 단계별 가이드를 따르면 GroupDocs.Viewer를 .NET 응용 프로그램에 원활하게 통합하여 문서 관리 기능을 향상시킬 수 있습니다.
## FAQ
### Q: .NET용 GroupDocs.Viewer는 모든 버전의 .NET 프레임워크와 호환됩니까?
예, .NET용 GroupDocs.Viewer는 광범위한 .NET 프레임워크 버전과 호환되도록 설계되어 개발 시 다양성과 유연성을 보장합니다.
### Q: 렌더링된 문서의 출력 모양을 사용자 정의할 수 있습니까?
전적으로! GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 제공하므로 개발자는 자신의 기본 설정 및 요구 사항에 따라 렌더링된 문서의 모양을 조정할 수 있습니다.
### 질문: .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 제공되는 무료 평가판에 액세스하여 .NET용 GroupDocs.Viewer의 기능을 탐색할 수 있습니다.[웹사이트]( https://releases.groupdocs.com/).
### 질문: .NET용 GroupDocs.Viewer에 대한 지원을 받으려면 어떻게 해야 합니까?
 .NET용 GroupDocs.Viewer에 관한 질문, 지원 또는 지원이 필요한 경우 전용 지원 포럼을 방문하세요.[여기](https://forum.groupdocs.com/c/viewer/9).
### 질문: .NET용 GroupDocs.Viewer의 임시 라이센스를 구입할 수 있습니까?
예, 임시 라이센스를 구매할 수 있으므로 사용자는 특정 기간 동안 .NET용 GroupDocs.Viewer를 유연하고 편리하게 활용할 수 있습니다.