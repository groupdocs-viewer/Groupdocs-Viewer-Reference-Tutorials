---
"description": "Dowiedz się, jak renderować obrazy CDR do formatów HTML, JPG, PNG i PDF za pomocą GroupDocs.Viewer dla .NET. Łatwo konwertuj pliki CorelDRAW za pomocą tego samouczka."
"linktitle": "Renderuj obrazy CDR"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj obrazy CDR"
"url": "/pl/net/image-rendering/render-cdr-images/"
"weight": 12
---

# Renderuj obrazy CDR

## Wstęp
tym samouczku przeprowadzimy Cię przez proces renderowania obrazów CDR (CorelDRAW) przy użyciu GroupDocs.Viewer dla .NET. CDR to format pliku kojarzony głównie z CorelDRAW, edytorem grafiki wektorowej. Za pomocą GroupDocs.Viewer możesz łatwo konwertować pliki CDR do różnych formatów, takich jak HTML, JPG, PNG i PDF.

![Renderowanie obrazów CDR za pomocą GroupDocs.Viewer dla .NET](/viewer/image-rendering/render-cdr-images.png)

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Upewnij się, że zainstalowałeś GroupDocs.Viewer dla .NET. Możesz go pobrać z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Katalog dokumentów: Przygotuj katalog, w którym chcesz zapisać wyrenderowane obrazy.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest konieczna do zrozumienia przykładów kodu.
## Importuj przestrzenie nazw
Zanim przejdziesz do przykładów kodu, zaimportuj niezbędne przestrzenie nazw do pliku C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Teraz rozbijmy każdy przykład na kilka kroków:
## Renderowanie do HTML
1. Zdefiniuj katalog wyjściowy, w którym chcesz zapisać wyrenderowane pliki HTML:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Określ format ścieżki pliku dla plików HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Użyj klasy Viewer, aby wyrenderować plik CDR do formatu HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderowanie do JPG
1. Zdefiniuj format ścieżki pliku dla plików JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Użyj klasy Viewer, aby wyrenderować plik CDR do formatu JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderowanie do PNG
1. Zdefiniuj format ścieżki pliku dla plików PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Użyj klasy Viewer, aby wyrenderować plik CDR do formatu PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderowanie do PDF
1. Zdefiniuj format ścieżki pliku dla pliku PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Użyj klasy Viewer, aby wyrenderować plik CDR do formatu PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Opcjonalnie możesz określić opcje renderowania lub renderować konkretne strony, przekazując dodatkowe parametry do `viewer.View()` metoda.
## Wniosek
Renderowanie obrazów CDR do różnych formatów, takich jak HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer dla .NET, to prosty proces. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz skutecznie konwertować pliki CDR do różnych formatów w zależności od swoich wymagań.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi wersjami plików CDR?
GroupDocs.Viewer dla platformy .NET obsługuje renderowanie plików CDR utworzonych w różnych wersjach programu CorelDRAW.
### Czy mogę dostosować dane wyjściowe renderowanych plików?
Tak, GroupDocs.Viewer dla .NET oferuje różne opcje dostosowywania wyników, takie jak dostosowywanie jakości obrazu, ustawianie znaku wodnego itp.
### Czy GroupDocs.Viewer dla .NET wymaga jakichkolwiek zewnętrznych zależności?
Nie, GroupDocs.Viewer dla .NET jest samodzielną biblioteką i nie wymaga żadnych zewnętrznych zależności do renderowania dokumentów.
### Czy jest dostępna wersja próbna GroupDocs.Viewer dla .NET?
Tak, możesz pobrać bezpłatną wersję próbną GroupDocs.Viewer dla .NET ze strony [Tutaj](https://releases.groupdocs.com/).
### Gdzie mogę uzyskać pomoc techniczną dotyczącą GroupDocs.Viewer dla .NET?
Możesz uzyskać pomoc na forum społeczności GroupDocs.Viewer [Tutaj](https://forum.groupdocs.com/c/viewer/9).