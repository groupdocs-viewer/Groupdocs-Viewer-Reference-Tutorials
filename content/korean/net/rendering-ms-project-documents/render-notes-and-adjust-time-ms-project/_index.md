---
"description": "GroupDocs.Viewer for .NET을 사용하여 MS Project 문서를 완벽하게 렌더링하세요. 메모를 렌더링하고, 시간 단위를 조정하고, 다양한 출력 형식을 손쉽게 탐색해 보세요."
"linktitle": "렌더링 노트 및 시간 단위 조정(MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "렌더링 노트 및 시간 단위 조정(MS Project)"
"url": "/ko/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# 렌더링 노트 및 시간 단위 조정(MS Project)

## 소개
GroupDocs.Viewer for .NET은 개발자가 .NET 애플리케이션에서 다양한 문서 형식을 보고 조작할 수 있도록 지원하는 강력한 문서 렌더링 API입니다. 이 튜토리얼에서는 MS Project 문서의 메모 렌더링 및 시간 단위 조정에 중점을 둡니다.
## 필수 조건
시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.
1. .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer 라이브러리를 다운로드하여 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 지원을 통해 원하는 개발 환경을 설정하세요.
3. MS Project 문서: 테스트를 위해 샘플 MS Project 문서를 준비하세요.
## 네임스페이스 가져오기
먼저, MS Project 문서 렌더링을 시작하기 위해 필요한 네임스페이스를 가져오겠습니다.
## 1단계: 네임스페이스 가져오기
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
이제 필요한 네임스페이스를 가져왔으니, 포괄적으로 이해하기 위해 각 예를 여러 단계로 나누어 보겠습니다.
## MS Project 문서를 HTML로 렌더링
메모를 포함한 MS Project 문서를 HTML 형식으로 변환하려면 다음 단계를 따르세요.
### 2단계: 출력 디렉토리 및 파일 형식 설정
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
## MS Project 문서를 이미지 형식으로 렌더링
MS Project 문서를 JPG 및 PNG와 같은 이미지 형식으로 렌더링할 수도 있습니다. 방법은 다음과 같습니다.
### 5단계: JPG에 대한 출력 디렉토리 및 파일 형식 설정
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
PNG 및 기타 이미지 형식으로 렌더링하는 경우에도 비슷한 단계를 반복합니다.
## MS Project 문서를 PDF로 렌더링
MS Project 문서를 PDF 형식으로 변환하려면 다음과 같이 진행하세요.
### 8단계: PDF에 대한 출력 디렉토리 및 파일 형식 설정
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
축하합니다! GroupDocs.Viewer for .NET을 사용하여 MS Project 문서를 렌더링하고 시간 단위를 조정하는 방법을 성공적으로 익히셨습니다. 이 지식을 프로젝트에 적용하여 문서 보기 기능을 향상시키세요.
## 자주 묻는 질문
### MS Project 문서를 HTML, 이미지, PDF 외의 다른 형식으로 렌더링할 수 있나요?
네, GroupDocs.Viewer for .NET은 DOCX, XLSX, PPTX 등 다양한 형식으로의 렌더링을 지원합니다.
### GroupDocs.Viewer for .NET의 평가판이 있나요?
네, 무료 체험판을 받으실 수 있습니다. [여기](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET에 대한 임시 라이선스를 받으려면 어떻게 해야 하나요?
방문하다 [이 링크](https://purchase.groupdocs.com/temporary-license/) 임시 면허를 취득하다.
### .NET용 GroupDocs.Viewer에 대한 문서는 어디에서 찾을 수 있나요?
문서를 참조하세요 [여기](https://tutorials.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET과 관련된 지원이나 질문은 어디에서 받을 수 있나요?
지원 포럼을 방문할 수 있습니다 [여기](https://forum.groupdocs.com/c/viewer/9).