---
"description": "Groupdocs.Viewer for .NET을 .NET 프로젝트에 원활하게 통합하여 효율적으로 문서를 볼 수 있습니다."
"linktitle": "취소 토큰을 사용하여 렌더링 취소"
"second_title": "GroupDocs.Viewer .NET API"
"title": "취소 토큰을 사용하여 렌더링 취소"
"url": "/ko/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# 취소 토큰을 사용하여 렌더링 취소

## 소개
Groupdocs.Viewer for .NET은 .NET 애플리케이션 내에서 문서 보기 및 처리를 간소화하도록 설계된 강력한 도구입니다. PDF, Microsoft Office 문서 또는 기타 일반적인 형식을 다루는 경우, 이 라이브러리는 문서 보기 기능을 .NET 프로젝트에 원활하게 통합하는 강력한 기능을 제공합니다.
## 필수 조건
.NET용 Groupdocs.Viewer 통합을 시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. 설치: 제공된 .NET 라이브러리용 Groupdocs.Viewer를 다운로드하여 설치하세요. [다운로드 링크](https://releases.groupdocs.com/viewer/net/).
   
2. 라이센스: 라이센스를 얻으세요 [그룹닥스](https://purchase.groupdocs.com/buy) 라이브러리의 잠재력을 최대한 활용하세요. 또는 무료 체험판을 통해 시작할 수 있습니다. [임시 면허](https://purchase.groupdocs.com/temporary-license/).
   
3. 개발 환경: Visual Studio나 원하는 다른 .NET IDE를 포함하여 호환 가능한 개발 환경이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기
Groupdocs.Viewer for .NET을 효과적으로 활용하려면 필요한 네임스페이스를 프로젝트에 가져와야 합니다. 다음 단계를 따르세요.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

이제 더 나은 이해와 구현을 위해 제공된 예를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
이 단계에서는 렌더링된 문서 페이지가 저장될 디렉토리를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
여기서는 개별 문서 페이지의 파일 경로에 대한 형식을 정의합니다.
## 3단계: CancellationTokenSource 초기화
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource는 비동기 작업을 취소하는 데 사용할 수 있는 CancellationToken 인스턴스를 생성하는 데 사용됩니다.
## 4단계: CancellationToken 얻기
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
이 단계에서는 렌더링 작업을 취소하는 데 사용될 CancellationTokenSource에서 토큰을 검색합니다.
## 5단계: 문서 페이지 렌더링
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
여기서는 Task.Run()을 사용하여 문서 페이지 렌더링을 비동기적으로 시작합니다. 지정된 문서 파일(SAMPLE_DOCX)을 사용하여 Viewer 인스턴스를 생성하고 렌더링 옵션을 구성합니다. 그런 다음 Viewer 클래스의 View 메서드를 사용하여 렌더링 프로세스를 시작합니다.
## 6단계: 렌더링 시간 초과 설정
```csharp
cancellationTokenSource.CancelAfter(10);
```
이 단계에서는 렌더링 작업에 10밀리초의 시간 제한을 설정합니다. 작업이 이 시간 제한을 초과하면 자동으로 취소됩니다.
## 7단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로, 문서가 성공적으로 렌더링되었음을 나타내는 성공 메시지가 표시됩니다.

## 결론
이 튜토리얼에서는 Groupdocs.Viewer for .NET을 프로젝트에 통합하는 기본 사항을 다루었습니다. 위에 설명된 단계를 따르면 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Groupdocs.Viewer for .NET은 모든 문서 형식과 호환됩니까?
.NET용 Groupdocs.Viewer는 PDF, Microsoft Office 문서, 이미지 등 다양한 문서 형식을 지원합니다.
### 렌더링된 문서 페이지의 모양을 사용자 정의할 수 있나요?
네, 페이지 크기, 품질, 워터마킹 등 렌더링 프로세스의 다양한 측면을 사용자 지정할 수 있습니다.
### Groupdocs.Viewer for .NET을 사용하려면 인터넷 연결이 필요합니까?
아니요, Groupdocs.Viewer for .NET은 .NET 환경 내에서 로컬로 작동하며 문서 보기에 인터넷 연결이 필요하지 않습니다.
### Groupdocs.Viewer for .NET에 대한 기술 지원을 받을 수 있나요?
예, 기술 지원은 다음을 통해 제공됩니다. [Groupdocs 포럼](https://forum.groupdocs.com/c/viewer/9)질문을 하고, 문제점을 보고하고, 커뮤니티와 소통할 수 있는 곳입니다.
### 구매하기 전에 Groupdocs.Viewer for .NET을 사용해 볼 수 있나요?
네, 제공된 무료 체험판을 사용하여 시작할 수 있습니다. [체험판](https://releases.groupdocs.com/).