---
title: Renderuj archiwa na jednej lub wielu stronach HTML
linktitle: Renderuj archiwa na jednej lub wielu stronach HTML
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować archiwa na stronach HTML za pomocą GroupDocs.Viewer dla .NET. Bezproblemowo integruj możliwości przeglądania dokumentów z aplikacjami .NET.
weight: 12
url: /pl/net/rendering-archive-files/render-archives-html/
---

# Renderuj archiwa na jednej lub wielu stronach HTML

## Wstęp
GroupDocs.Viewer dla .NET to potężna biblioteka do renderowania dokumentów, która umożliwia programistom bezproblemową integrację funkcji przeglądania dokumentów z aplikacjami .NET. Niezależnie od tego, czy chcesz renderować archiwa na jedną, czy na wiele stron HTML, ten samouczek przeprowadzi Cię przez ten proces krok po kroku.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
1.  GroupDocs.Viewer dla .NET: Upewnij się, że masz zainstalowaną bibliotekę w swoim projekcie. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Skonfiguruj działające środowisko programistyczne do programowania w platformie .NET.
3. Katalog dokumentów: Przygotuj katalog, w którym przechowywane są Twoje dokumenty.
4. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

## Importuj przestrzenie nazw
W kodzie C# pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Wykonaj poniższe kroki, aby renderować archiwa na jednej lub wielu stronach HTML przy użyciu GroupDocs.Viewer dla .NET:
## Krok 1: Ustaw katalog wyjściowy
Zdefiniuj katalog, w którym mają być zapisywane renderowane strony HTML:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku
Określ format ścieżki pliku dla stron HTML. W przypadku renderowania pojedynczej strony:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
W przypadku renderowania wielostronicowego:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Krok 3: Renderuj do pojedynczej strony HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Krok 4: Renderuj do kodu HTML wielu stron
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Ustaw elementy na stronę
    viewer.View(options);
}
```
## Krok 5: Sprawdź dane wyjściowe
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Renderowanie archiwów na strony HTML za pomocą GroupDocs.Viewer dla .NET jest prostym procesem. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zintegrować możliwości przeglądania dokumentów z aplikacjami .NET.
## Często zadawane pytania
### Czy mogę renderować dokumenty w innych formatach niż archiwa?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, DOCX, XLSX, PPTX i inne.
### Czy GroupDocs.Viewer nadaje się zarówno do aplikacji komputerowych, jak i internetowych?
Oczywiście GroupDocs.Viewer może być bezproblemowo używany zarówno w aplikacjach komputerowych, jak i internetowych.
### Czy GroupDocs.Viewer oferuje opcje dostosowywania interfejsu przeglądarki?
Tak, możesz dostosować interfejs przeglądarki do swoich wymagań.
### Czy mogę renderować dokumenty asynchronicznie za pomocą GroupDocs.Viewer?
Tak, GroupDocs.Viewer zapewnia możliwości renderowania asynchronicznego w celu zwiększenia wydajności.
### Czy GroupDocs.Viewer obsługuje adnotacje w dokumentach?
Tak, GroupDocs.Viewer umożliwia użytkownikom efektywne przeglądanie adnotacji w dokumentach i zarządzanie nimi.