---
title: 내장 또는 외부 리소스를 사용하여 렌더링
linktitle: 내장 또는 외부 리소스를 사용하여 렌더링
second_title: GroupDocs.Viewer .NET API
description: 원활한 렌더링을 위해 GroupDocs.Viewer를 사용하여 .NET 문서 보기를 향상시킵니다. 효율적인 통합과 우수한 사용자 경험을 위해 튜토리얼을 따르십시오.
weight: 12
url: /ko/net/rendering-documents-html/render-html-resources/
---

# 내장 또는 외부 리소스를 사용하여 렌더링

## 소개

.NET 개발 세계에서 효율적인 문서 보기는 많은 응용 프로그램의 중요한 측면입니다. .NET용 GroupDocs.Viewer는 포함된 리소스 또는 외부 리소스가 있는 문서를 렌더링하기 위한 강력한 솔루션을 제공합니다. 이 자습서에서는 GroupDocs.Viewer를 활용하여 문서를 원활하게 렌더링하는 방법을 살펴보고 명확성과 이해를 위해 각 단계를 세분화합니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

1. .NET 개발에 대한 기본 이해: C# 프로그래밍 언어 및 .NET 프레임워크에 대한 지식이 필요합니다.
2.  .NET용 GroupDocs.Viewer 설치: 다음 위치에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치합니다.[여기](https://releases.groupdocs.com/viewer/net/).
3. 렌더링할 문서 파일: 렌더링할 샘플 문서 파일(예: DOCX, PDF)을 준비합니다.

## 네임스페이스 가져오기

먼저 .NET 프로젝트에 필요한 네임스페이스를 가져옵니다.

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

이제 내장 또는 외부 리소스가 포함된 문서를 렌더링하는 프로세스를 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 출력 디렉터리 정의

```csharp
string outputDirectory = "Your Document Directory";
```

렌더링된 HTML 페이지를 저장할 디렉터리를 지정합니다.

## 2단계: 페이지 파일 경로 형식 정의

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

렌더링된 각 페이지가 저장될 파일 경로의 형식을 설정합니다.`{0}` 페이지 번호에 대한 자리 표시자입니다.

## 3단계: 뷰어 인스턴스 초기화

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // 뷰어 초기화 코드가 여기에 표시됩니다.
}
```

렌더링할 문서 파일의 경로를 전달하여 뷰어 인스턴스를 만듭니다.

## 4단계: HTML 보기 옵션 구성

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

포함된 리소스의 형식과 페이지 파일 경로 형식을 지정하여 HTML 보기 옵션을 구성합니다.

## 5단계: 문서 렌더링

```csharp
viewer.View(options);
```

 호출`View` 뷰어 인스턴스의 메소드를 사용하여 구성된 HTML 보기 옵션을 전달합니다.

## 6단계: 출력 디렉터리 경로 표시

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

출력 디렉터리의 경로와 함께 성공적인 렌더링을 나타내는 메시지를 인쇄합니다.

## 결론

.NET용 GroupDocs.Viewer는 포함된 리소스 또는 외부 리소스가 있는 문서 렌더링 프로세스를 단순화하여 .NET 응용 프로그램의 문서 보기 기능을 향상시킵니다. 이 튜토리얼에 설명된 단계를 따르면 개발자는 문서 렌더링 기능을 프로젝트에 원활하게 통합하여 사용자에게 원활하고 효율적인 문서 보기 환경을 제공할 수 있습니다.

## FAQ

### 질문: .NET용 GroupDocs.Viewer는 다양한 문서 형식과 호환됩니까?

A: 예, GroupDocs.Viewer는 DOCX, PDF, XLSX 등을 포함한 광범위한 문서 형식을 지원합니다.

### Q: 내 요구 사항에 따라 렌더링 옵션을 사용자 정의할 수 있습니까?

A: 물론, GroupDocs.Viewer는 특정 요구 사항을 충족하도록 렌더링 프로세스를 구성하기 위한 광범위한 옵션을 제공합니다.

### 질문: .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?

 A: 네, 다음 사이트에서 무료 평가판을 이용하실 수 있습니다.[여기](https://releases.groupdocs.com/).

### Q: GroupDocs.Viewer 통합에 대한 지원을 받으려면 어떻게 해야 합니까?

 A: GroupDocs.Viewer 커뮤니티 포럼에서 도움을 구할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).

### Q: 테스트 목적으로 임시 라이센스를 사용할 수 있습니까?

 A: 예, 임시 라이센스는 다음에서 얻을 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).