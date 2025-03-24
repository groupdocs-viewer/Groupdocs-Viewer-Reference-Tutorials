---
title: Renderowanie liczb
linktitle: Renderowanie liczb
second_title: GroupDocs.Viewer API .NET
description: Poznaj możliwości Groupdocs.Viewer dla .NET w płynnym renderowaniu plików Numbers. Bez wysiłku konwertuj do formatu HTML, JPG, PNG i PDF.
weight: 15
url: /pl/net/spreadsheet-rendering-options/rendering-numbers/
---

# Renderowanie liczb

## Wstęp
Witamy w tym samouczku krok po kroku dotyczącym renderowania plików Numbers przy użyciu Groupdocs.Viewer dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy początkującym, ten przewodnik przeprowadzi Cię przez proces konwertowania dokumentów Numbers na różne formaty. Groupdocs.Viewer dla .NET to potężne narzędzie, które pozwala bezproblemowo zintegrować możliwości przeglądania dokumentów z aplikacjami .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Praktyczna znajomość programowania w C# i .NET.
-  Zainstalowana biblioteka Groupdocs.Viewer dla .NET. Możesz go pobrać[Tutaj](https://releases.groupdocs.com/viewer/net/).
- Ścieżka katalogu dokumentów, w którym zostaną zapisane pliki wyjściowe.
## Importuj przestrzenie nazw
Upewnij się, że w projekcie C# zaimportowałeś przestrzenie nazw niezbędne do korzystania z biblioteki Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Skonfiguruj katalog wyjściowy
Przed rozpoczęciem renderowania określ katalog wyjściowy, w którym zostaną zapisane przekonwertowane pliki. Zastąp „Twój katalog dokumentów” rzeczywistą ścieżką:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Renderuj do wielostronicowego kodu HTML
Użyj poniższego kodu, aby przekonwertować plik Numbers na wielostronicowy kod HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 3: Renderuj do JPG
Przekonwertuj plik Numbers na format JPG za pomocą następującego kodu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 4: Renderuj do PNG
Przekształć plik Numbers do formatu PNG, używając następującego kodu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 5: Renderuj do formatu PDF
Na koniec przekonwertuj plik Numbers na format PDF, używając następującego kodu:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Gratulacje! Udało Ci się wyrenderować pliki Numbers do różnych formatów za pomocą Groupdocs.Viewer dla .NET.
## Wniosek
W tym samouczku omówiliśmy podstawy renderowania plików Numbers przy użyciu Groupdocs.Viewer dla .NET. Ta potężna biblioteka zapewnia bezproblemową integrację przeglądania i konwertowania dokumentów w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę używać Groupdocs.Viewer dla .NET z innymi typami dokumentów?
Tak, Groupdocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym Word, Excel, PDF i inne.
### Czy dostępna jest licencja tymczasowa do celów testowych?
 Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.groupdocs.com/temporary-license/) dla testów.
### Gdzie mogę znaleźć pomoc dotyczącą Groupdocs.Viewer dla .NET?
 Odwiedzić[Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za pomoc i dyskusję.
### Jak kupić pełną wersję Groupdocs.Viewer dla .NET?
 Można kupić pełną wersję[Tutaj](https://purchase.groupdocs.com/buy).
### Czy dostępna jest bezpłatna wersja próbna?
 Tak, możesz skorzystać z bezpłatnej wersji próbnej[Tutaj](https://releases.groupdocs.com/).