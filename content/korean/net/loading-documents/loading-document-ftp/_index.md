---
"description": "GroupDocs.Viewer for .NET을 애플리케이션에 완벽하게 통합하여 효율적인 문서 보기를 지원합니다. FTP에서 문서를 손쉽게 렌더링할 수 있습니다."
"linktitle": "FTP에서 문서 로드(고급)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "FTP에서 문서 로드(고급)"
"url": "/ko/net/loading-documents/loading-document-ftp/"
"weight": 13
type: docs
---
# FTP에서 문서 로드(고급)

## 소개
GroupDocs.Viewer for .NET은 개발자가 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합할 수 있도록 지원하는 강력한 API입니다. PDF, Microsoft Office 문서 또는 기타 널리 사용되는 파일 형식 등 어떤 형식으로 작업하든 GroupDocs.Viewer는 문서 표시 과정을 간소화하여 사용자에게 풍부한 보기 환경을 더욱 쉽게 제공할 수 있도록 지원합니다.

![GroupDocs.Viewer .NET을 사용하여 FTP에서 문서 로드](/viewer/loading-documents/load-documents-from-ftp.png)

## 필수 조건
GroupDocs.Viewer for .NET을 사용하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. 개발 환경: Visual Studio와 .NET Framework가 설치된 개발 환경을 설정합니다.
2. GroupDocs.Viewer 설치: .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요. [웹사이트](https://releases.groupdocs.com/viewer/net/).
3. 라이선스: GroupDocs.Viewer에 대한 유효한 라이선스를 취득하세요. 라이선스는 다음에서 구매할 수 있습니다. [GroupDocs 웹사이트](https://purchase.groupdocs.com/buy) 또는 테스트 목적으로 임시 라이센스를 활용합니다.[임시 면허](https://purchase.groupdocs.com/temporary-license/)).
4. .NET에 대한 기본 이해: C# 구문과 스트림 작업을 포함하여 .NET 개발의 기본 사항을 익혀보세요.

## 네임스페이스 가져오기
애플리케이션에서 GroupDocs.Viewer for .NET을 사용하려면 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using System.Net;
using GroupDocs.Viewer.Options;
```
#이제 제공된 예를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 HTML 페이지를 저장할 출력 디렉토리를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
생성될 HTML 페이지의 이름 지정 형식을 지정합니다.
## 3단계: 문서 파일 경로 설정
```csharp
string filePath = ""; // 예: ftp://localhost/sample.doc
```
로드할 문서 파일의 경로를 입력하세요. 로컬 파일 경로 또는 URL일 수 있습니다.
## 4단계: 파일 경로 확인
```csharp
if (string.IsNullOrEmpty(filePath))
{
    Console.WriteLine("\n[LoadDocumentFromFtp] Please make sure to set a proper path to the file.");
    return;
}
```
파일 경로가 비어 있거나 null이 아닌지 확인하세요.
## 5단계: FTP에서 문서 로드
```csharp
Stream stream = GetFileFromFtp(filePath);
```
FTP 서버에서 문서 파일을 검색합니다.
## 6단계: 문서 렌더링
```csharp
using (Viewer viewer = new Viewer(stream))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
새로운 Viewer 인스턴스를 만들고 HTML 보기 옵션을 사용하여 문서를 렌더링합니다.
## 7단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
문서가 성공적으로 렌더링되었음을 사용자에게 알리고 출력 디렉토리를 지정합니다.

## 결론
결론적으로, GroupDocs.Viewer for .NET은 개발자에게 문서 보기 기능을 .NET 애플리케이션에 통합할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 FTP 서버에서 문서를 빠르게 로드하고 렌더링하여 표시할 수 있으므로 애플리케이션의 사용자 경험이 향상됩니다.
## 자주 묻는 질문
### FTP 외의 다른 소스에서 문서를 렌더링하기 위해 GroupDocs.Viewer for .NET을 사용할 수 있나요?
네, GroupDocs.Viewer는 로컬 파일 시스템, URL, 스트림 등 다양한 소스의 문서 렌더링을 지원합니다.
### GroupDocs.Viewer for .NET을 사용하려면 라이센스가 필요합니까?
네, GroupDocs.Viewer를 프로덕션 환경에서 사용하려면 유효한 라이선스가 필요합니다. 하지만 테스트 목적으로 임시 라이선스를 받으실 수도 있습니다.
### 문서의 렌더링 옵션을 사용자 정의할 수 있나요?
물론입니다! GroupDocs.Viewer는 페이지 회전, 워터마킹 등 렌더링 프로세스를 사용자 지정할 수 있는 다양한 옵션을 제공합니다.
### GroupDocs.Viewer는 모든 문서 형식을 지원합니까?
GroupDocs.Viewer는 PDF, Microsoft Office 문서, 이미지 등 다양한 문서 형식을 지원합니다.
### GroupDocs.Viewer for .NET에 대한 기술 지원을 받을 수 있나요?
예, 다음을 통해 기술 지원 및 리소스에 액세스할 수 있습니다. [GroupDocs 포럼](https://forum.groupdocs.com/c/viewer/9) 질문이나 문제가 있을 경우 도움을 드리겠습니다.