---
"description": "Groupdocs.Viewer for .NET을 사용하여 렌더링된 PDF를 암호로 간편하게 보호하세요. 문서를 안전하게 보호하고 기밀을 유지하세요."
"linktitle": "암호로 렌더링된 PDF 보호"
"second_title": "GroupDocs.Viewer .NET API"
"title": "암호로 렌더링된 PDF 보호"
"url": "/ko/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
---

# 암호로 렌더링된 PDF 보호

## 소개
이 튜토리얼에서는 Groupdocs.Viewer for .NET을 사용하여 렌더링된 PDF를 암호로 보호하는 방법을 알아봅니다. 보안 조치를 추가하면 PDF 문서에 대한 액세스를 제어하여 기밀성과 무결성을 보장할 수 있습니다.
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. .NET 라이브러리용 Groupdocs.Viewer: 라이브러리를 다운로드하여 설치하세요. [웹사이트](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 개발을 위해 작동하는 개발 환경이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉토리 및 파일 경로 정의
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2단계: 뷰어 개체 초기화 및 보안 옵션 설정
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## 3단계: PDF 보기 옵션 설정
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## 4단계: 보안 옵션을 사용하여 문서 렌더링
```csharp
    viewer.View(options);
}
```
## 5단계: 렌더링된 문서 확인
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
다음 단계를 따르면 Groupdocs.Viewer for .NET을 사용하여 렌더링된 PDF를 암호로 보호할 수 있습니다. 이렇게 하면 문서가 안전하게 보호되고 권한이 있는 사용자만 액세스할 수 있습니다.

## 결론
PDF 문서 보안은 기밀성과 무결성을 유지하는 데 필수적입니다. Groupdocs.Viewer for .NET을 사용하면 렌더링된 PDF를 암호로 쉽게 보호하고 민감한 정보에 대한 액세스를 제어할 수 있습니다.

## 자주 묻는 질문
### 다양한 수준의 권한으로 PDF를 보호할 수 있나요?
네, PDF를 비밀번호로 보호하면서 보기, 인쇄, 복사 등에 대한 다양한 권한을 지정할 수 있습니다.
### Groupdocs.Viewer는 다양한 파일 형식과 호환됩니까?
물론입니다! Groupdocs.Viewer는 DOCX, XLSX, PPTX, PDF 등 다양한 파일 형식 렌더링을 지원합니다.
### Groupdocs.Viewer를 기존 .NET 애플리케이션에 통합할 수 있나요?
물론입니다! Groupdocs.Viewer는 .NET 애플리케이션과의 원활한 통합을 위한 API를 제공하며, 강력한 문서 보기 기능을 제공합니다.
### Groupdocs.Viewer는 클라우드 스토리지 서비스를 지원합니까?
네, Groupdocs.Viewer는 Dropbox, Google Drive, Amazon S3와 같은 인기 있는 클라우드 스토리지 서비스와의 통합을 지원하여 클라우드에 저장된 문서를 렌더링할 수 있습니다.
### Groupdocs.Viewer의 평가판이 있나요?
예, 무료 평가판 버전에 액세스하여 Groupdocs.Viewer를 시작할 수 있습니다. [웹사이트](https://releases.groupdocs.com/).