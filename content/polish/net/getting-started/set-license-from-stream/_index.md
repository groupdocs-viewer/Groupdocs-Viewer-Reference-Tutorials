---
title: Ustaw licencję ze strumienia
linktitle: Ustaw licencję ze strumienia
second_title: GroupDocs.Viewer API .NET
description: Ulepsz swoje aplikacje .NET za pomocą GroupDocs.Viewer, aby zapewnić płynne przeglądanie dokumentów. Postępuj zgodnie z naszym przewodnikiem krok po kroku i bez trudu zintegruj zaawansowane funkcje przeglądania dokumentów.
weight: 11
url: /pl/net/getting-started/set-license-from-stream/
---
## Wstęp
Czy chcesz wyposażyć swoje aplikacje .NET w zaawansowane możliwości przeglądania dokumentów? GroupDocs.Viewer dla .NET oferuje kompleksowe rozwiązanie umożliwiające bezproblemową integrację funkcji przeglądania dokumentów z Twoimi projektami. W tym samouczku zagłębimy się w proces wykorzystania GroupDocs.Viewer dla .NET w celu wzbogacenia aplikacji o zaawansowane możliwości przeglądania dokumentów. 
## Warunki wstępne
Zanim zagłębimy się w proces integracji, upewnij się, że spełnione są następujące wymagania wstępne:
1. Podstawowa wiedza na temat programowania .NET: Znajomość C# i frameworku .NET jest niezbędna do korzystania z tego samouczka.
   
2.  Pakiet GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś pakiet GroupDocs.Viewer dla .NET. Można go uzyskać od[link do pobrania](https://releases.groupdocs.com/viewer/net/).
3.  Dostęp do dokumentacji GroupDocs: Zachowaj plik[dokumentacja](https://tutorials.groupdocs.com/viewer/net/) przydatne w celach informacyjnych podczas procesu integracji.

## Importuj przestrzenie nazw
Na początek zaimportuj niezbędne przestrzenie nazw do swojej aplikacji .NET. Wykonaj następujące kroki:
### Krok 1: Otwórz swój projekt .NET.
Upewnij się, że masz otwarty projekt .NET w preferowanym środowisku programistycznym.
### Krok 2: Dodaj przestrzeń nazw GroupDocs.Viewer.
W pliku kodu dodaj następującą przestrzeń nazw, aby uzyskać dostęp do funkcji GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Ustaw licencję ze strumienia
Następnym krokiem jest ustawienie licencji ze strumienia. Wykonaj następujące szczegółowe kroki:
### Krok 1: Zdefiniuj katalog wyjściowy.
Ustaw katalog, w którym będą przechowywane Twoje dokumenty, definiując katalog wyjściowy:
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Sprawdź istnienie pliku licencji.
Sprawdź, czy plik licencji istnieje w katalogu Twojego projektu:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Krok 3: Ustaw licencję.
Jeśli plik licencji istnieje, ustaw licencję za pomocą dostarczonego strumienia:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Krok 4: Zajmij się brakiem licencji.
Jeśli plik licencji nie zostanie znaleziony, podaj instrukcje dotyczące uzyskania licencji:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://zakup.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://zakup.groupdocs.com/tymczasowa-licencja.”);
}
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się integrować GroupDocs.Viewer for .NET ze swoimi aplikacjami. Dzięki temu potężnemu narzędziu możesz teraz bez wysiłku przeglądać różne formaty dokumentów w projektach .NET, poprawiając wygodę użytkownika i produktywność.
## Często zadawane pytania
### Czy potrzebuję licencji, aby używać GroupDocs.Viewer dla .NET?
Tak, potrzebujesz licencji, aby używać GroupDocs.Viewer dla .NET. Licencję tymczasową lub stałą można uzyskać w witrynie GroupDocs.
### Czy mogę zintegrować GroupDocs.Viewer z moją aplikacją ASP.NET?
Absolutnie! GroupDocs.Viewer dla .NET bezproblemowo integruje się zarówno z aplikacjami stacjonarnymi, jak i internetowymi, w tym ASP.NET.
### Jakie formaty dokumentów są obsługiwane przez GroupDocs.Viewer?
GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, Microsoft Office (Word, Excel, PowerPoint), obrazy i inne.
### Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny zarówno z .NET Framework, jak i .NET Core.
### Czy mogę dostosować interfejs przeglądarki do motywu mojej aplikacji?
Tak, GroupDocs.Viewer zapewnia szerokie możliwości dostosowywania, umożliwiając dostosowanie interfejsu przeglądarki do motywu aplikacji.