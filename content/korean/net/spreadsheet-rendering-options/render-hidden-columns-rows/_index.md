---
"description": "GroupDocs.Viewer for .NET을 사용하여 스프레드시트의 숨겨진 데이터를 손쉽게 확인해 보세요. 단계별 가이드를 따라 숨겨진 열과 행을 확인해 보세요."
"linktitle": "숨겨진 열과 행 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "숨겨진 열과 행 렌더링"
"url": "/ko/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
type: docs
---
# 숨겨진 열과 행 렌더링

## 소개
문서 시각화 분야에서 GroupDocs.Viewer for .NET은 다양한 문서 형식을 원활하게 렌더링하는 강력한 도구로 자리매김했습니다. 흥미로운 기능 중 하나는 스프레드시트 내의 숨겨진 열과 행을 표시하는 기능입니다. 이 튜토리얼에서는 이 기능을 활용하고 데이터의 잠재력을 최대한 활용하는 방법을 자세히 살펴보겠습니다.
## 필수 조건
이 여정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- GroupDocs.Viewer for .NET: 최신 버전이 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다. [공식 웹사이트](https://releases.groupdocs.com/viewer/net/).
- 문서 파일: 숨겨진 열과 행을 실험해 보려면 스프레드시트 형식(예: SAMPLE.XLSX)으로 샘플 문서를 준비하세요.
- 개발 환경: .NET 개발에 적합한 Visual Studio나 기타 IDE를 사용하여 작업 환경을 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 GroupDocs.Viewer 기능을 효과적으로 활용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉토리 설정
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
렌더링된 HTML 페이지가 저장될 출력 디렉터리를 정의합니다. 파일 경로 형식을 이에 맞게 조정하세요.
## 2단계: 뷰어 초기화 및 옵션 구성
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
스프레드시트 문서 경로를 제공하여 뷰어 인스턴스를 생성합니다. HTML 보기 옵션을 구성하여 리소스를 포함하고 숨겨진 열과 행을 렌더링할 수 있습니다.
## 3단계: 렌더링 프로세스 실행
```csharp
    viewer.View(options);
}
```
구성된 옵션을 전달하여 viewer 객체의 View 메서드를 호출합니다. 그러면 렌더링 프로세스가 시작됩니다.
## 4단계: 출력 확인
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
소스 문서가 성공적으로 렌더링되었는지 확인하고 지정된 디렉토리에서 출력을 찾습니다.
## 결론
GroupDocs.Viewer for .NET을 사용하면 스프레드시트에서 숨겨진 열과 행을 손쉽게 잠금 해제할 수 있습니다. 이 튜토리얼에서는 숨겨진 데이터를 확인하고 문서를 더욱 포괄적으로 볼 수 있도록 하는 필수 단계를 안내합니다.
## 자주 묻는 질문
### 스프레드시트 외의 다른 문서 형식에서 숨겨진 열과 행을 렌더링할 수 있나요?
네, GroupDocs.Viewer는 스프레드시트 외에도 Word, PDF, PowerPoint 등 다양한 문서 형식을 지원합니다.
### 렌더링할 수 있는 숨겨진 열과 행의 수에 제한이 있습니까?
GroupDocs.Viewer는 다양한 숨겨진 열과 행의 렌더링을 효율적으로 처리합니다. 그러나 숨겨진 데이터가 방대한 극단적인 경우에는 성능에 영향을 미칠 수 있습니다.
### 렌더링된 데이터의 출력 형식을 사용자 정의할 수 있나요?
물론입니다! GroupDocs.Viewer는 출력을 사용자 정의할 수 있는 유연한 옵션을 제공하여 렌더링된 데이터를 특정 요구 사항에 맞게 조정할 수 있습니다.
### GroupDocs.Viewer를 사용할 때 라이선스 고려 사항이 있나요?
네, 사용에 적합한 라이선스가 있는지 확인하세요. 라이선스 옵션은 다음에서 확인하세요. [GroupDocs 구매](https://purchase.groupdocs.com/buy) 또는 얻다 [임시 면허](https://purchase.groupdocs.com/temporary-license/) 테스트용.
### 어디에서 도움을 받거나 GroupDocs 커뮤니티에 연락하여 지원을 받을 수 있나요?
방문하세요 [GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 지원, 토론, 커뮤니티 상호 작용을 위해.