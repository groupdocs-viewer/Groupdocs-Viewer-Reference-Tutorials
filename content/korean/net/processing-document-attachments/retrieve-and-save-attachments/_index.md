---
title: 문서 첨부 파일 검색 및 저장
linktitle: 문서 첨부 파일 검색 및 저장
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer를 사용하여 .NET 애플리케이션 내에서 문서 첨부 파일을 효율적으로 관리합니다. 번거로움 없이 첨부 파일을 검색하고 저장하세요.
weight: 12
url: /ko/net/processing-document-attachments/retrieve-and-save-attachments/
---
## 소개
디지털 시대에는 효율적인 문서 처리가 기업과 개인 모두에게 중요합니다. 이메일 관리, 계약 보기, 보고서 액세스 등 무엇이든 문서 시각화를 위한 안정적인 도구를 갖추는 것이 필수적입니다. .NET용 GroupDocs.Viewer는 강력한 솔루션으로 등장하여 사용자가 .NET 응용 프로그램 내에서 직접 다양한 문서 형식을 쉽게 보고 상호 작용할 수 있도록 해줍니다.
## 전제조건
문서 첨부 파일 검색 및 저장을 위해 .NET용 GroupDocs.Viewer를 활용하기 전에 다음 전제 조건이 있는지 확인하십시오.
1. 운영 환경: .NET Framework로 구성된 작업 환경입니다.
2.  설치: .NET 라이브러리용 GroupDocs.Viewer가 다운로드되어 설치되었습니다. 다음에서 도서관에 접근할 수 있습니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
3. 기본 이해: C# 프로그래밍 언어에 대한 지식.
4. 문서 소스: 데모용 첨부 파일이 포함된 샘플 문서에 액세스합니다.

## 네임스페이스 가져오기
문서 첨부 파일 검색 및 저장을 위해 .NET용 GroupDocs.Viewer 활용을 시작하려면 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
문서에서 검색된 첨부 파일을 저장할 디렉터리를 정의합니다.
## 2단계: 뷰어 개체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
첨부 파일이 포함된 문서의 경로를 사용하여 뷰어 개체를 인스턴스화합니다.
## 3단계: 첨부 파일 검색
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
문서에 있는 첨부 파일 목록을 검색합니다.
## 4단계: 첨부 파일 저장
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
각 첨부 파일을 반복하고, 파일 경로를 정의하고, 첨부 파일을 지정된 디렉터리에 저장합니다.
## 5단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
디렉터리 경로와 함께 첨부 파일이 성공적으로 저장되었음을 나타내는 성공 메시지를 표시합니다.

## 결론
.NET용 GroupDocs.Viewer를 문서 처리 작업 흐름에 통합하면 첨부 파일 관리 프로세스가 간소화되어 효율성과 편의성이 향상됩니다. 위에 설명된 단계별 가이드를 따르면 사용자는 .NET 애플리케이션 내에서 문서 첨부 파일을 원활하게 검색하고 저장할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 다양한 문서 형식을 처리할 수 있습니까?
예, GroupDocs.Viewer는 PDF, Microsoft Office 문서, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer의 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시 라이센스는 다음에서 취득할 수 있습니다.[이 링크](https://purchase.groupdocs.com/temporary-license/).
### .NET용 GroupDocs.Viewer에 대한 설명서는 어디서 찾을 수 있나요?
 포괄적인 문서가 제공됩니다.[여기](https://tutorials.groupdocs.com/viewer/net/).
### .NET용 GroupDocs.Viewer에 어떤 지원 옵션을 사용할 수 있나요?
 커뮤니티 포럼에서 도움을 구할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).