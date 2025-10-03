---
"description": "Bezproblemowa integracja Groupdocs.Viewer for .NET z projektami .NET w celu wydajnego przeglądania dokumentów."
"linktitle": "Anuluj renderowanie za pomocą tokena anulowania"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Anuluj renderowanie za pomocą tokena anulowania"
"url": "/pl/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Anuluj renderowanie za pomocą tokena anulowania

## Wstęp
Groupdocs.Viewer for .NET to potężne narzędzie zaprojektowane w celu uproszczenia przeglądania i przetwarzania dokumentów w aplikacjach .NET. Niezależnie od tego, czy masz do czynienia z plikami PDF, dokumentami Microsoft Office czy innymi popularnymi formatami, ta biblioteka oferuje solidną funkcjonalność, aby bezproblemowo zintegrować możliwości przeglądania dokumentów z projektami .NET.
## Wymagania wstępne
Zanim przejdziesz do integracji Groupdocs.Viewer dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:
1. Instalacja: Pobierz i zainstaluj bibliotekę Groupdocs.Viewer dla .NET z dostarczonego pliku [link do pobrania](https://releases.groupdocs.com/viewer/net/).
   
2. Licencja: Uzyskaj licencję od [Dokumenty grupowe](https://purchase.groupdocs.com/buy) aby odblokować pełny potencjał biblioteki. Alternatywnie możesz zacząć od bezpłatnego okresu próbnego, korzystając z [licencja tymczasowa](https://purchase.groupdocs.com/temporary-license/).
   
3. Środowisko programistyczne: Upewnij się, że masz skonfigurowane zgodne środowisko programistyczne, obejmujące program Visual Studio lub inne wybrane środowisko IDE .NET.

## Importuj przestrzenie nazw
Aby skutecznie wykorzystać Groupdocs.Viewer dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Wykonaj następujące kroki:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Teraz rozbijmy podany przykład na kilka kroków, aby lepiej go zrozumieć i wdrożyć:
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Ten krok ustawia katalog, w którym będą przechowywane wyrenderowane strony dokumentu.
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tutaj definiujemy format ścieżek plików poszczególnych stron dokumentu.
## Krok 3: Zainicjuj CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource służy do generowania instancji CancellationToken, które można wykorzystać do anulowania operacji asynchronicznych.
## Krok 4: Uzyskaj CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Ten krok pobiera token ze źródła CancellationTokenSource, który zostanie użyty do anulowania operacji renderowania.
## Krok 5: Renderuj strony dokumentu
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
Tutaj inicjujemy renderowanie stron dokumentu asynchronicznie za pomocą Task.Run(). Instancja Viewer jest tworzona z określonym plikiem dokumentu (SAMPLE_DOCX), a opcje renderowania są konfigurowane. Następnie proces renderowania jest uruchamiany za pomocą metody View klasy Viewer.
## Krok 6: Ustaw limit czasu renderowania
```csharp
cancellationTokenSource.CancelAfter(10);
```
Ten krok ustawia limit czasu 10 milisekund dla operacji renderowania. Jeśli operacja przekroczy ten limit czasu, zostanie automatycznie anulowana.
## Krok 7: Wyświetl komunikat o powodzeniu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Na koniec wyświetlany jest komunikat informujący o pomyślnym wyrenderowaniu dokumentu.

## Wniosek
tym samouczku omówiliśmy podstawy integracji Groupdocs.Viewer dla .NET z Twoimi projektami. Postępując zgodnie z opisanymi powyżej krokami, możesz bezproblemowo włączyć możliwości przeglądania dokumentów do swoich aplikacji .NET, zwiększając komfort użytkowania i produktywność.
## Najczęściej zadawane pytania
### Czy Groupdocs.Viewer dla .NET jest kompatybilny ze wszystkimi formatami dokumentów?
Groupdocs.Viewer dla platformy .NET obsługuje szeroką gamę formatów dokumentów, w tym pliki PDF, dokumenty pakietu Microsoft Office, obrazy i inne.
### Czy mogę dostosować wygląd renderowanych stron dokumentu?
Tak, możesz dostosować różne aspekty procesu renderowania, w tym rozmiar strony, jakość, znak wodny i inne.
### Czy Groupdocs.Viewer dla .NET wymaga połączenia z Internetem?
Nie, Groupdocs.Viewer dla platformy .NET działa lokalnie w środowisku .NET i nie wymaga połączenia z Internetem w celu przeglądania dokumentów.
### Czy dla Groupdocs.Viewer dla .NET dostępna jest pomoc techniczna?
Tak, pomoc techniczna jest dostępna poprzez [Forum grupy docs](https://forum.groupdocs.com/c/viewer/9), gdzie możesz zadawać pytania, zgłaszać problemy i wchodzić w interakcję ze społecznością.
### Czy mogę wypróbować Groupdocs.Viewer dla .NET przed zakupem?
Tak, możesz rozpocząć bezpłatny okres próbny, korzystając z dostarczonego [wersja próbna](https://releases.groupdocs.com/).