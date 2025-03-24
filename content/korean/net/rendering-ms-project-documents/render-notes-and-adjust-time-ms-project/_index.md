---
title: 노트 렌더링 및 시간 단위 조정(MS 프로젝트)
linktitle: 노트 렌더링 및 시간 단위 조정(MS 프로젝트)
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 MS 프로젝트 문서를 마스터 렌더링합니다. 노트를 렌더링하고, 시간 단위를 조정하고, 다양한 출력 형식을 쉽게 탐색할 수 있습니다.
weight: 11
url: /ko/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---

# 노트 렌더링 및 시간 단위 조정(MS 프로젝트)

## 소개
.NET용 GroupDocs.Viewer는 개발자가 .NET 응용 프로그램 내에서 다양한 문서 형식을 보고 조작할 수 있는 강력한 문서 렌더링 API입니다. 이 튜토리얼에서는 특히 MS 프로젝트 문서에 대한 노트 렌더링 및 시간 단위 조정에 중점을 둘 것입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer 라이브러리를 다운로드하여 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 지원을 통해 선호하는 개발 환경을 설정하세요.
3. MS 프로젝트 문서: 테스트할 샘플 MS 프로젝트 문서를 준비합니다.
## 네임스페이스 가져오기
먼저 MS 프로젝트 문서 렌더링을 시작하는 데 필요한 네임스페이스를 가져옵니다.
## 1단계: 네임스페이스 가져오기
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
이제 필수 네임스페이스를 가져왔으므로 포괄적인 이해를 위해 각 예를 여러 단계로 나누어 보겠습니다.
## MS 프로젝트 문서를 HTML로 렌더링
MS 프로젝트 문서를 메모가 포함된 HTML 형식으로 렌더링하려면 다음 단계를 따르세요.
### 2단계: 출력 디렉터리 및 파일 형식 설정
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 3단계: 뷰어 개체 초기화 및 옵션 설정
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 4단계: 문서를 HTML로 렌더링
```csharp
viewer.View(options);
```
## MS 프로젝트 문서를 이미지 형식으로 렌더링
MS Project 문서를 JPG 및 PNG와 같은 이미지 형식으로 렌더링할 수도 있습니다. 방법은 다음과 같습니다.
### 5단계: JPG의 출력 디렉터리 및 파일 형식 설정
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 6단계: 뷰어 개체 초기화 및 JPG 옵션 설정
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 7단계: 문서를 JPG로 렌더링
```csharp
viewer.View(options);
```
PNG 및 기타 이미지 형식으로 렌더링하려면 유사한 단계를 반복합니다.
## MS 프로젝트 문서를 PDF로 렌더링
MS 프로젝트 문서를 PDF 형식으로 렌더링하려면 다음을 수행하십시오.
### 8단계: PDF의 출력 디렉터리 및 파일 형식 설정
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 9단계: 뷰어 개체 초기화 및 PDF 옵션 설정
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 10단계: 문서를 PDF로 렌더링
```csharp
viewer.View(options);
```

## 결론
축하해요! .NET용 GroupDocs.Viewer를 사용하여 MS 프로젝트 문서를 렌더링하고 시간 단위를 조정하는 방법을 성공적으로 배웠습니다. 문서 보기 기능을 향상하려면 이 지식을 프로젝트에 통합하세요.
## FAQ
### MS Project 문서를 HTML, 이미지, PDF 이외의 다른 형식으로 렌더링할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 DOCX, XLSX, PPTX 등과 같은 다양한 형식으로의 렌더링을 지원합니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 방문하다[이 링크](https://purchase.groupdocs.com/temporary-license/) 임시면허를 취득하기 위해
### .NET용 GroupDocs.Viewer에 대한 설명서는 어디서 찾을 수 있나요?
 문서를 참조하세요[여기](https://tutorials.groupdocs.com/viewer/net/).
### .NET용 GroupDocs.Viewer와 관련된 지원을 받거나 질문을 할 수 있는 곳은 어디입니까?
 지원 포럼을 방문할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).