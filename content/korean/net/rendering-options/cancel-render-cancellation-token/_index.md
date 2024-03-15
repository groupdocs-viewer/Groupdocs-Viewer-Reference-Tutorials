---
title: 취소 토큰으로 렌더링 취소
linktitle: 취소 토큰으로 렌더링 취소
second_title: GroupDocs.Viewer .NET API
description: 효율적인 문서 보기를 위해 Groupdocs.Viewer for .NET을 .NET 프로젝트에 완벽하게 통합하세요.
type: docs
weight: 11
url: /ko/net/rendering-options/cancel-render-cancellation-token/
---
## 소개
.NET용 Groupdocs.Viewer는 .NET 응용 프로그램 내에서 문서 보기 및 처리를 단순화하도록 설계된 강력한 도구입니다. PDF, Microsoft Office 문서 또는 기타 일반적인 형식을 처리하는 경우 이 라이브러리는 문서 보기 기능을 .NET 프로젝트에 원활하게 통합하는 강력한 기능을 제공합니다.
## 전제조건
.NET용 Groupdocs.Viewer 통합을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  설치: 제공된 라이브러리에서 Groupdocs.Viewer for .NET 라이브러리를 다운로드하여 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
   
2.  라이센스: 다음에서 라이센스를 얻습니다.[그룹 문서](https://purchase.groupdocs.com/buy) 도서관의 잠재력을 최대한 활용합니다. 또는 다음을 사용하여 무료 평가판으로 시작할 수 있습니다.[임시 면허증](https://purchase.groupdocs.com/temporary-license/).
   
3. 개발 환경: Visual Studio 또는 원하는 다른 .NET IDE를 포함하여 호환 가능한 개발 환경이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기
.NET용 Groupdocs.Viewer를 효과적으로 활용하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 다음과 같이하세요:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

이제 더 나은 이해와 구현을 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
이 단계에서는 렌더링된 문서 페이지가 저장될 디렉터리를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
여기서는 개별 문서 페이지의 파일 경로 형식을 정의합니다.
## 3단계: CancellationTokenSource 초기화
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource는 비동기 작업을 취소하는 데 사용할 수 있는 CancellationToken 인스턴스를 생성하는 데 사용됩니다.
## 4단계: CancellationToken 획득
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
이 단계에서는 렌더링 작업을 취소하는 데 사용되는 CancellationTokenSource에서 토큰을 검색합니다.
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
여기서는 Task.Run()을 사용하여 문서 페이지 렌더링을 비동기적으로 시작합니다. 지정된 문서 파일(SAMPLE_DOCX)로 뷰어 인스턴스가 생성되고 렌더링 옵션이 구성됩니다. 그런 다음 Viewer 클래스의 View 메서드를 사용하여 렌더링 프로세스가 시작됩니다.
## 6단계: 렌더링 시간 초과 설정
```csharp
cancellationTokenSource.CancelAfter(10);
```
이 단계에서는 렌더링 작업에 대한 시간 제한을 10밀리초로 설정합니다. 작업이 이 시간 초과를 초과하면 자동으로 취소됩니다.
## 7단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로 문서가 성공적으로 렌더링되었음을 나타내는 성공 메시지가 표시됩니다.

## 결론
이 자습서에서는 .NET용 Groupdocs.Viewer를 프로젝트에 통합하는 기본 사항을 다루었습니다. 위에 설명된 단계를 수행하면 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## FAQ
### .NET용 Groupdocs.Viewer는 모든 문서 형식과 호환됩니까?
.NET용 Groupdocs.Viewer는 PDF, Microsoft Office 문서, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### 렌더링된 문서 페이지의 모양을 사용자 정의할 수 있습니까?
예, 페이지 크기, 품질, 워터마킹 등을 포함하여 렌더링 프로세스의 다양한 측면을 사용자 정의할 수 있습니다.
### .NET용 Groupdocs.Viewer에는 인터넷 연결이 필요합니까?
아니요, .NET용 Groupdocs.Viewer는 .NET 환경 내에서 로컬로 작동하며 문서를 보기 위해 인터넷 연결이 필요하지 않습니다.
### .NET용 Groupdocs.Viewer에 대한 기술 지원이 제공됩니까?
 예, 기술 지원은 다음을 통해 제공됩니다.[Groupdocs 포럼](https://forum.groupdocs.com/c/viewer/9)에서 질문하고, 문제를 보고하고, 커뮤니티와 상호 작용할 수 있습니다.
### 구매하기 전에 .NET용 Groupdocs.Viewer를 사용해 볼 수 있나요?
 예, 제공된 도구를 사용하여 무료 평가판으로 시작할 수 있습니다.[평가판](https://releases.groupdocs.com/).