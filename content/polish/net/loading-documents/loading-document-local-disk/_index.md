---
title: Załaduj dokumenty z dysku lokalnego
linktitle: Załaduj dokumenty z dysku lokalnego
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak bezproblemowo renderować dokumenty z dysku lokalnego za pomocą Groupdocs.Viewer dla .NET. Ulepsz swoje aplikacje .NET dzięki wydajnemu dokumentowi.
weight: 10
url: /pl/net/loading-documents/loading-document-local-disk/
---
## Wstęp
dzisiejszej erze cyfrowej wydajne renderowanie dokumentów jest niezbędne w różnych zastosowaniach. Groupdocs.Viewer dla .NET oferuje zaawansowane rozwiązanie do renderowania dokumentów bezpośrednio z dysku lokalnego. W tym samouczku przeprowadzimy Cię przez proces ładowania dokumentów z dysku lokalnego za pomocą Groupdocs.Viewer dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku pomoże Ci bezproblemowo zintegrować renderowanie dokumentów z aplikacjami .NET.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1.  Groupdocs.Viewer dla .NET: Pobierz i zainstaluj najnowszą wersję z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne .NET: Upewnij się, że w systemie skonfigurowane jest działające środowisko programistyczne .NET.
3. Dokumenty lokalne: przechowuj dokumenty, które chcesz renderować, lokalnie na swoim dysku.

## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Groupdocs.Viewer dla .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Załaduj dokumenty z dysku lokalnego
Rozpocznij od skonfigurowania katalogu wyjściowego, w którym będą zapisywane wyrenderowane strony HTML.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 2: Zainicjuj przeglądarkę i renderuj dokumenty
Zainicjuj obiekt Viewer ścieżką dokumentu i renderuj go przy użyciu opcji widoku HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Wyświetl dane wyjściowe
Po zakończeniu renderowania wyświetl komunikat wskazujący pomyślne renderowanie dokumentu źródłowego i lokalizację plików wyjściowych.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się ładować dokumenty z dysku lokalnego za pomocą Groupdocs.Viewer dla .NET. To potężne narzędzie otwiera świat możliwości renderowania dokumentów w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę renderować dokumenty w różnych formatach za pomocą Groupdocs.Viewer dla .NET?
Tak, Groupdocs.Viewer dla .NET obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, XLSX, PPTX i inne.
### Czy Groupdocs.Viewer dla .NET jest kompatybilny ze wszystkimi frameworkami .NET?
Groupdocs.Viewer dla .NET jest kompatybilny z większością platform .NET, w tym .NET Core, .NET Framework i .NET Standard.
### Czy mogę dostosować opcje renderowania moich dokumentów?
Absolutnie! Groupdocs.Viewer dla .NET zapewnia rozbudowane opcje dostosowywania, umożliwiające dostosowanie procesu renderowania do konkretnych wymagań.
### Czy dostępna jest wersja próbna programu Groupdocs.Viewer dla platformy .NET?
Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.groupdocs.com/).
### Gdzie mogę znaleźć pomoc lub dodatkowe zasoby dotyczące Groupdocs.Viewer dla .NET?
 Aby uzyskać pomoc i dodatkowe zasoby, odwiedź Groupdocs.Viewer dla platformy .NET[forum](https://forum.groupdocs.com/c/viewer/9).