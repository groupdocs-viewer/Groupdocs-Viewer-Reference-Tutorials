---
title: Anuluj renderowanie za pomocą tokena anulowania
linktitle: Anuluj renderowanie za pomocą tokena anulowania
second_title: GroupDocs.Viewer API .NET
description: Bezproblemowo zintegruj Groupdocs.Viewer for .NET z projektami .NET, aby efektywnie przeglądać dokumenty.
weight: 11
url: /pl/net/rendering-options/cancel-render-cancellation-token/
---
## Wstęp
Groupdocs.Viewer dla .NET to potężne narzędzie zaprojektowane w celu uproszczenia przeglądania i przetwarzania dokumentów w aplikacjach .NET. Niezależnie od tego, czy masz do czynienia z plikami PDF, dokumentami Microsoft Office czy innymi popularnymi formatami, ta biblioteka oferuje solidną funkcjonalność, która pozwala bezproblemowo integrować możliwości przeglądania dokumentów z projektami .NET.
## Warunki wstępne
Przed przystąpieniem do integracji Groupdocs.Viewer dla .NET upewnij się, że spełnione są następujące wymagania wstępne:
1.  Instalacja: Pobierz i zainstaluj bibliotekę Groupdocs.Viewer for .NET z dostarczonej biblioteki[link do pobrania](https://releases.groupdocs.com/viewer/net/).
   
2.  Licencja: Uzyskaj licencję od[Dokumenty grupowe](https://purchase.groupdocs.com/buy) aby uwolnić pełny potencjał biblioteki. Alternatywnie możesz rozpocząć od bezpłatnego okresu próbnego, korzystając z[licencja tymczasowa](https://purchase.groupdocs.com/temporary-license/).
   
3. Środowisko programistyczne: Upewnij się, że masz skonfigurowane kompatybilne środowisko programistyczne, w tym Visual Studio lub dowolne inne wybrane środowisko .NET IDE.

## Importuj przestrzenie nazw
Aby efektywnie wykorzystać Groupdocs.Viewer dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Wykonaj następujące kroki:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Podzielmy teraz podany przykład na wiele kroków, aby lepiej zrozumieć i wdrożyć:
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Ten krok ustawia katalog, w którym będą przechowywane renderowane strony dokumentu.
## Krok 2: Zdefiniuj format ścieżki pliku strony
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tutaj definiujemy format ścieżek plików poszczególnych stron dokumentu.
## Krok 3: Zainicjuj źródło tokenu anulowania
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource służy do generowania instancji CancellationToken, których można użyć do anulowania operacji asynchronicznych.
## Krok 4: Uzyskaj token anulowania
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Ten krok pobiera token z CancellationTokenSource, który będzie używany do anulowania operacji renderowania.
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
Tutaj inicjujemy renderowanie stron dokumentu asynchronicznie za pomocą Task.Run(). Instancja Viewer jest tworzona z określonym plikiem dokumentu (SAMPLE_DOCX) i konfigurowane są opcje renderowania. Następnie rozpoczyna się proces renderowania przy użyciu metody View klasy Viewer.
## Krok 6: Ustaw limit czasu renderowania
```csharp
cancellationTokenSource.CancelAfter(10);
```
Ten krok ustawia limit czasu operacji renderowania na 10 milisekund. Jeśli operacja przekroczy ten limit czasu, zostanie automatycznie anulowana.
## Krok 7: Wyświetl komunikat o powodzeniu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Na koniec zostanie wyświetlony komunikat o powodzeniu, wskazujący, że dokument został pomyślnie wyrenderowany.

## Wniosek
W tym samouczku omówiliśmy podstawy integracji Groupdocs.Viewer dla .NET z Twoimi projektami. Wykonując czynności opisane powyżej, można bezproblemowo włączyć funkcje przeglądania dokumentów do aplikacji .NET, zwiększając komfort użytkownika i produktywność.
## Często zadawane pytania
### Czy Groupdocs.Viewer dla .NET jest kompatybilny ze wszystkimi formatami dokumentów?
Groupdocs.Viewer dla .NET obsługuje szeroką gamę formatów dokumentów, w tym PDF, dokumenty Microsoft Office, obrazy i inne.
### Czy mogę dostosować wygląd renderowanych stron dokumentu?
Tak, możesz dostosować różne aspekty procesu renderowania, w tym rozmiar strony, jakość, znak wodny i inne.
### Czy Groupdocs.Viewer dla .NET wymaga połączenia z Internetem?
Nie, Groupdocs.Viewer dla .NET działa lokalnie w środowisku .NET i nie wymaga połączenia z Internetem do przeglądania dokumentów.
### Czy dostępna jest pomoc techniczna dla Groupdocs.Viewer dla .NET?
 Tak, pomoc techniczna jest dostępna za pośrednictwem[Forum Groupdocs](https://forum.groupdocs.com/c/viewer/9), gdzie możesz zadawać pytania, zgłaszać problemy i wchodzić w interakcje ze społecznością.
### Czy przed zakupem mogę wypróbować Groupdocs.Viewer dla .NET?
 Tak, możesz rozpocząć od bezpłatnego okresu próbnego, korzystając z dostarczonego oprogramowania[wersja próbna](https://releases.groupdocs.com/).