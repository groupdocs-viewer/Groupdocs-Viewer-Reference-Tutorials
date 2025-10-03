---
"description": "Dowiedz się, jak płynnie renderować dokumenty z dysku lokalnego za pomocą Groupdocs.Viewer dla platformy .NET. Ulepsz swoje aplikacje .NET dzięki wydajnemu przetwarzaniu dokumentów."
"linktitle": "Załaduj dokumenty z dysku lokalnego"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Załaduj dokumenty z dysku lokalnego"
"url": "/pl/net/loading-documents/loading-document-local-disk/"
"weight": 10
type: docs
---
# Załaduj dokumenty z dysku lokalnego

## Wstęp
W dzisiejszej erze cyfrowej wydajne renderowanie dokumentów jest niezbędne dla różnych aplikacji. Groupdocs.Viewer dla .NET oferuje potężne rozwiązanie do renderowania dokumentów bezpośrednio z dysku lokalnego. W tym samouczku przeprowadzimy Cię przez proces ładowania dokumentów z dysku lokalnego za pomocą Groupdocs.Viewer dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku pomoże Ci bezproblemowo zintegrować renderowanie dokumentów z aplikacjami .NET.

![Ładowanie dokumentów z dysku lokalnego za pomocą GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. Groupdocs.Viewer dla .NET: Pobierz i zainstaluj najnowszą wersję z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne .NET: Upewnij się, że w systemie skonfigurowano działające środowisko programistyczne .NET.
3. Dokumenty lokalne: przechowuj dokumenty, które chcesz renderować, lokalnie na swoim dysku.

## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Groupdocs.Viewer dla .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Załaduj dokumenty z dysku lokalnego
Zacznij od skonfigurowania katalogu wyjściowego, w którym będą zapisywane renderowane strony HTML.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 2: Zainicjuj przeglądarkę i renderuj dokumenty
Zainicjuj obiekt Viewer ścieżką dokumentu i wyrenderuj go za pomocą opcji widoku HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Wyświetlanie wyników
Po zakończeniu renderowania wyświetl komunikat informujący o pomyślnym wyrenderowaniu dokumentu źródłowego i lokalizacji plików wyjściowych.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Gratulacje! Udało Ci się nauczyć, jak ładować dokumenty z dysku lokalnego za pomocą Groupdocs.Viewer dla .NET. To potężne narzędzie otwiera świat możliwości renderowania dokumentów w aplikacjach .NET.
## Najczęściej zadawane pytania
### Czy mogę renderować dokumenty w różnych formatach za pomocą Groupdocs.Viewer dla .NET?
Tak, Groupdocs.Viewer dla platformy .NET obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, XLSX, PPTX i inne.
### Czy Groupdocs.Viewer dla .NET jest kompatybilny ze wszystkimi platformami .NET?
Groupdocs.Viewer dla platformy .NET jest zgodny z większością platform .NET, w tym .NET Core, .NET Framework i .NET Standard.
### Czy mogę dostosować opcje renderowania moich dokumentów?
Oczywiście! Groupdocs.Viewer dla .NET zapewnia rozbudowane opcje dostosowywania, pozwalające dostosować proces renderowania do Twoich konkretnych wymagań.
### Czy jest dostępna wersja próbna Groupdocs.Viewer dla .NET?
Tak, możesz pobrać bezpłatną wersję próbną ze strony [Tutaj](https://releases.groupdocs.com/).
### Gdzie mogę znaleźć pomoc lub dodatkowe zasoby dotyczące Groupdocs.Viewer dla platformy .NET?
Aby uzyskać pomoc i dodatkowe zasoby, odwiedź witrynę Groupdocs.Viewer dla platformy .NET [forum](https://forum.groupdocs.com/c/viewer/9).