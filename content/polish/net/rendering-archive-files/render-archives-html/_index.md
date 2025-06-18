---
"description": "Dowiedz się, jak renderować archiwa do stron HTML za pomocą GroupDocs.Viewer dla .NET. Bezproblemowo integruj możliwości przeglądania dokumentów z aplikacjami .NET."
"linktitle": "Renderuj archiwa do pojedynczych lub wielu stron HTML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj archiwa do pojedynczych lub wielu stron HTML"
"url": "/pl/net/rendering-archive-files/render-archives-html/"
"weight": 12
---

# Renderuj archiwa do pojedynczych lub wielu stron HTML

## Wstęp
GroupDocs.Viewer dla .NET to potężna biblioteka renderowania dokumentów, która umożliwia deweloperom bezproblemową integrację możliwości przeglądania dokumentów z ich aplikacjami .NET. Niezależnie od tego, czy musisz renderować archiwa do pojedynczych czy wielu stron HTML, ten samouczek przeprowadzi Cię przez ten proces krok po kroku.
## Wymagania wstępne
Zanim przejdziesz do tego samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Upewnij się, że biblioteka jest zainstalowana w projekcie. Możesz ją pobrać z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Przygotuj działające środowisko programistyczne do tworzenia oprogramowania .NET.
3. Katalog dokumentów: Przygotuj katalog, w którym będą przechowywane Twoje dokumenty.
4. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

## Importuj przestrzenie nazw
W kodzie C# pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Aby renderować archiwa do pojedynczych lub wielu stron HTML przy użyciu GroupDocs.Viewer dla platformy .NET, wykonaj następujące kroki:
## Krok 1: Ustaw katalog wyjściowy
Zdefiniuj katalog, w którym mają być zapisywane renderowane strony HTML:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku
Określ format ścieżki pliku dla stron HTML. Do renderowania pojedynczej strony:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Do renderowania wielostronicowego:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Krok 3: Renderowanie do jednostronicowego HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Krok 4: Renderowanie na wielu stronach HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Ustaw elementy na stronę
    viewer.View(options);
}
```
## Krok 5: Sprawdź wynik
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Renderowanie archiwów do stron HTML przy użyciu GroupDocs.Viewer dla .NET to prosty proces. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz bezproblemowo zintegrować możliwości przeglądania dokumentów z aplikacjami .NET.
## Najczęściej zadawane pytania
### Czy mogę renderować inne formaty dokumentów oprócz archiwów?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, DOCX, XLSX, PPTX i inne.
### Czy GroupDocs.Viewer nadaje się zarówno do zastosowań desktopowych, jak i internetowych?
Oczywiście, GroupDocs.Viewer można bez problemu wykorzystywać zarówno w aplikacjach komputerowych, jak i internetowych.
### Czy GroupDocs.Viewer oferuje opcje dostosowywania interfejsu przeglądarki?
Tak, możesz dostosować interfejs przeglądarki do swoich potrzeb.
### Czy mogę renderować dokumenty asynchronicznie za pomocą GroupDocs.Viewer?
Tak, GroupDocs.Viewer oferuje możliwości asynchronicznego renderowania, co poprawia wydajność.
### Czy GroupDocs.Viewer obsługuje adnotacje dokumentów?
Tak, GroupDocs.Viewer pozwala użytkownikom na efektywne przeglądanie i zarządzanie adnotacjami dokumentów.