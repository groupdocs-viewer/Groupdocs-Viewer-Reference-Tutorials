---
"description": "Dowiedz się, jak wyłączyć zaznaczanie tekstu w pliku PDF za pomocą GroupDocs.Viewer dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację."
"linktitle": "Wyłącz zaznaczanie tekstu w pliku PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Wyłącz zaznaczanie tekstu w pliku PDF"
"url": "/pl/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# Wyłącz zaznaczanie tekstu w pliku PDF

## Wstęp
GroupDocs.Viewer dla .NET to potężny interfejs API renderowania dokumentów, który umożliwia deweloperom łatwą integrację możliwości przeglądania dokumentów z aplikacjami .NET. Jedną z kluczowych funkcjonalności oferowanych przez GroupDocs.Viewer jest możliwość wyłączenia zaznaczania tekstu w dokumentach PDF. Ta funkcja jest szczególnie przydatna w scenariuszach, w których trzeba uniemożliwić użytkownikom kopiowanie tekstu z poufnych dokumentów, zapewniając bezpieczeństwo i integralność dokumentu.

![Wyłącz zaznaczanie tekstu w pliku PDF za pomocą GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Wymagania wstępne
Zanim przejdziemy do przewodnika krok po kroku, jak wyłączyć zaznaczanie tekstu w pliku PDF za pomocą GroupDocs.Viewer dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:
1. Instalacja GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś GroupDocs.Viewer dla .NET z [link do pobrania](https://releases.groupdocs.com/viewer/net/).
2. Katalog dokumentów: Przygotuj katalog, w którym będą przechowywane Twoje dokumenty. Będziesz musiał określić ten katalog w fragmencie kodu, aby wyrenderować dokument PDF.

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności dostarczanych przez GroupDocs.Viewer dla .NET. Oto, jak możesz to zrobić:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz podzielimy proces wyłączania zaznaczania tekstu w dokumencie PDF za pomocą GroupDocs.Viewer dla platformy .NET na kilka kroków:
## Krok 1: Określ katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
W tym kroku zastąp `"Your Document Directory"` ze ścieżką do katalogu, w którym znajduje się Twój dokument PDF.
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ten krok definiuje format ścieżek plików renderowanych stron HTML. Każda strona dokumentu PDF zostanie przekonwertowana na plik HTML z kolejnym numerem strony.
## Krok 3: Renderuj dokument PDF z wyłączonym zaznaczaniem tekstu
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Zastępować `"Path to Your PDF Document"` z rzeczywistą ścieżką do pliku PDF. Ten fragment kodu inicjuje `Viewer` obiekt, konfiguruje opcje widoku HTML w celu osadzania zasobów i wyłącza zaznaczanie tekstu poprzez ustawienie `RenderTextAsImage` nieruchomość do `true`.
## Krok 4: Wyświetl komunikat o powodzeniu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po wyrenderowaniu dokumentu PDF na tym etapie wyświetlany jest komunikat o powodzeniu i katalog, w którym przechowywane są wyrenderowane strony HTML.

## Wniosek
W tym samouczku nauczyliśmy się, jak wyłączyć zaznaczanie tekstu w dokumentach PDF za pomocą GroupDocs.Viewer dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz bezproblemowo zintegrować tę funkcję z aplikacjami .NET, zapewniając bezpieczeństwo dokumentów i ulepszając doświadczenia użytkownika.
## Najczęściej zadawane pytania
### Czy mogę dostosować katalog wyjściowy dla renderowanych stron HTML?
Tak, możesz określić dowolną ścieżkę katalogu, w którym mają być przechowywane renderowane strony HTML.
### Czy GroupDocs.Viewer dla .NET jest kompatybilny z różnymi wersjami platformy .NET?
Tak, GroupDocs.Viewer dla .NET jest zgodny z różnymi wersjami platformy .NET, w tym .NET Core i .NET Framework.
### Czy wyłączenie zaznaczania tekstu wpływa na inne funkcjonalności dokumentu PDF?
Nie, wyłączenie zaznaczania tekstu uniemożliwia użytkownikom zaznaczanie i kopiowanie tekstu z dokumentu. Pozostałe funkcjonalności pozostają nienaruszone.
### Czy mogę ponownie włączyć zaznaczanie tekstu po wyrenderowaniu dokumentu?
Tak, możesz włączyć zaznaczanie tekstu, po prostu ustawiając `RenderTextAsImage` nieruchomość do `false` w opcjach widoku HTML.
### Czy jest dostępna wersja próbna GroupDocs.Viewer dla .NET?
Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej GroupDocs.Viewer dla .NET z poziomu [strona internetowa](https://releases.groupdocs.com/).