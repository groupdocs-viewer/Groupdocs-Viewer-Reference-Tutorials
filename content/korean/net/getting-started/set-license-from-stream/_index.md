---
"description": "GroupDocs.Viewer로 .NET 애플리케이션을 더욱 강화하여 원활한 문서 보기를 경험해 보세요. 단계별 가이드를 따라 강력한 문서 보기 기능을 손쉽게 통합하세요."
"linktitle": "스트림에서 라이센스 설정"
"second_title": "GroupDocs.Viewer .NET API"
"title": "스트림에서 라이센스 설정"
"url": "/ko/net/getting-started/set-license-from-stream/"
"weight": 11
---

# 스트림에서 라이센스 설정

## 소개
.NET 애플리케이션에 고급 문서 보기 기능을 추가하고 싶으신가요? GroupDocs.Viewer for .NET은 문서 보기 기능을 프로젝트에 완벽하게 통합하는 포괄적인 솔루션을 제공합니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 활용하여 강력한 문서 보기 기능으로 애플리케이션을 강화하는 방법을 자세히 살펴보겠습니다. 

![GroupDocs.Viewer for .NET을 사용하여 Stream에서 라이선스 설정](/viewer/getting-started/set-license-from-stream.png)

## 필수 조건
통합 과정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET 개발에 대한 기본 지식: 이 튜토리얼을 따라가려면 C# 및 .NET 프레임워크에 대한 지식이 필수입니다.
   
2. .NET용 GroupDocs.Viewer 패키지: .NET용 GroupDocs.Viewer 패키지를 다운로드하여 설치했는지 확인하세요. [다운로드 링크](https://releases.groupdocs.com/viewer/net/).
3. GroupDocs 문서에 대한 액세스: 다음을 유지하세요. [선적 서류 비치](https://tutorials.groupdocs.com/viewer/net/) 통합 과정 중 튜토리얼에 유용합니다.

## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 .NET 애플리케이션으로 가져오세요. 다음 단계를 따르세요.
### 1단계: .NET 프로젝트를 엽니다.
선호하는 개발 환경에서 .NET 프로젝트가 열려 있는지 확인하세요.
### 2단계: GroupDocs.Viewer 네임스페이스를 추가합니다.
코드 파일에서 다음 네임스페이스를 추가하여 GroupDocs.Viewer 기능에 액세스하세요.
```csharp
using System;
using System.IO;
```
## 스트림에서 라이센스 설정
다음 단계는 스트림에서 라이선스를 설정하는 것입니다. 다음의 자세한 단계를 따르세요.
### 1단계: 출력 디렉토리 정의
출력 디렉토리를 정의하여 문서가 저장될 디렉토리를 설정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
### 2단계: 라이선스 파일 존재 여부 확인
프로젝트 디렉토리에 라이선스 파일이 있는지 확인하세요.
```csharp
if (File.Exists(Utils.LicensePath))
```
### 3단계: 라이센스 설정
라이선스 파일이 있으면 제공된 스트림을 사용하여 라이선스를 설정합니다.
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 4단계: 면허 부재 처리
라이선스 파일을 찾을 수 없는 경우 라이선스를 얻기 위한 지침을 제공하세요.
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://구매.그룹문서.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://구매.그룹문서.com/임시-라이센스.");
}
```

## 결론
축하합니다! GroupDocs.Viewer for .NET을 애플리케이션에 통합하는 방법을 성공적으로 익히셨습니다. 이 강력한 도구를 사용하면 .NET 프로젝트에서 다양한 문서 형식을 손쉽게 확인하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET을 사용하려면 라이선스가 필요합니까?
네, GroupDocs.Viewer for .NET을 사용하려면 라이선스가 필요합니다. GroupDocs 웹사이트에서 임시 또는 영구 라이선스를 받으실 수 있습니다.
### GroupDocs.Viewer를 ASP.NET 애플리케이션에 통합할 수 있나요?
물론입니다! GroupDocs.Viewer for .NET은 ASP.NET을 포함한 데스크톱 및 웹 애플리케이션 모두에 완벽하게 통합됩니다.
### GroupDocs.Viewer는 어떤 문서 형식을 지원합니까?
GroupDocs.Viewer는 PDF, Microsoft Office(Word, Excel, PowerPoint), 이미지 등 다양한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환됩니까?
네, GroupDocs.Viewer for .NET은 .NET Framework와 .NET Core 모두와 호환됩니다.
### 내 애플리케이션 테마에 맞게 뷰어 인터페이스를 사용자 정의할 수 있나요?
네, GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 제공하므로 뷰어 인터페이스를 애플리케이션 테마에 완벽하게 맞춰 조정할 수 있습니다.