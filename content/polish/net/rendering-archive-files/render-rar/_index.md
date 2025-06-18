---
"description": "Dowiedz się, jak renderować archiwa RAR do formatów HTML, JPG, PNG lub PDF za pomocą GroupDocs.Viewer dla .NET. Łatwo przeglądaj i udostępniaj zawartość archiwów RAR."
"linktitle": "Renderuj archiwa RAR"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj archiwa RAR"
"url": "/pl/net/rendering-archive-files/render-rar/"
"weight": 13
---

# Renderuj archiwa RAR

## Wstęp
Archiwa RAR to popularny format kompresji i przechowywania wielu plików i folderów w jednym kontenerze. Renderowanie archiwów RAR do różnych formatów, takich jak HTML, JPG, PNG lub PDF, może być niezbędne do przeglądania lub udostępniania zawartości tych archiwów. W tym samouczku pokażemy, jak renderować archiwa RAR za pomocą GroupDocs.Viewer dla .NET.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Zainstaluj bibliotekę GroupDocs.Viewer dla .NET z [link do pobrania](https://releases.groupdocs.com/viewer/net/).
2. Przykładowe archiwum RAR: Przygotuj przykładowe archiwum RAR do renderowania.

## Importuj przestrzenie nazw
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Renderowanie do HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 3: Renderowanie do JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 4: Renderowanie do PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Krok 5: Renderowanie do PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Wniosek
Renderowanie archiwów RAR do różnych formatów jest proste dzięki GroupDocs.Viewer dla .NET. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz bez wysiłku przekonwertować archiwa RAR do formatów HTML, JPG, PNG lub PDF, umożliwiając łatwe przeglądanie i udostępnianie ich zawartości.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer dla .NET obsługuje szyfrowane archiwa RAR?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie zaszyfrowanych archiwów RAR pod warunkiem podania niezbędnych haseł w trakcie procesu renderowania.
### Czy można dostosować wygląd wyjściowy renderowanych dokumentów?
Oczywiście! GroupDocs.Viewer dla .NET oferuje rozbudowane opcje dostosowywania, pozwalające użytkownikom dostosować wygląd renderowanych dokumentów zgodnie z ich ptutorialss.
### Czy GroupDocs.Viewer dla .NET obsługuje renderowanie innych formatów archiwów niż RAR?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie różnych formatów archiwów, w tym ZIP, TAR, 7z i innych.
### Czy mogę zintegrować GroupDocs.Viewer dla .NET z moją aplikacją internetową?
Oczywiście! GroupDocs.Viewer dla .NET udostępnia API, które nadają się do integracji zarówno z aplikacjami desktopowymi, jak i internetowymi.
### Czy jest dostępna wersja próbna GroupDocs.Viewer dla .NET?
Tak, możesz skorzystać z bezpłatnej wersji próbnej GroupDocs.Viewer dla .NET na stronie [strona internetowa](https://releases.groupdocs.com/).