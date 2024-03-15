---
title: Renderuj obrazy CDR
linktitle: Renderuj obrazy CDR
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować obrazy CDR do formatu HTML, JPG, PNG i PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Dzięki temu samouczkowi z łatwością przekonwertujesz pliki CorelDRAW.
type: docs
weight: 12
url: /pl/net/image-rendering/render-cdr-images/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces renderowania obrazów CDR (CorelDRAW) przy użyciu programu GroupDocs.Viewer dla .NET. CDR to format pliku kojarzony głównie z programem CorelDRAW, edytorem grafiki wektorowej. Dzięki GroupDocs.Viewer możesz z łatwością konwertować pliki CDR na różne formaty, takie jak HTML, JPG, PNG i PDF.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:
1.  GroupDocs.Viewer dla .NET: Upewnij się, że zainstalowałeś GroupDocs.Viewer dla .NET. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Katalog dokumentów: Przygotuj katalog, w którym chcesz zapisać wyrenderowane obrazy.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest konieczna do zrozumienia przykładów kodu.
## Importuj przestrzenie nazw
Zanim zagłębisz się w przykłady kodu, zaimportuj niezbędne przestrzenie nazw do pliku C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Teraz podzielmy każdy przykład na wiele kroków:
## Renderowanie do HTML
1. Zdefiniuj katalog wyjściowy, w którym chcesz zapisać renderowane pliki HTML:
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
## Renderowanie do pliku PDF
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
3.  Opcjonalnie możesz określić opcje renderowania lub renderować określone strony, przekazując dodatkowe parametry do`viewer.View()` metoda.
## Wniosek
Renderowanie obrazów CDR do różnych formatów, takich jak HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer dla .NET jest prostym procesem. Wykonując kroki opisane w tym samouczku, możesz skutecznie konwertować pliki CDR na różne formaty w zależności od wymagań.
## Często zadawane pytania
### Czy GroupDocs.Viewer dla .NET jest kompatybilny ze wszystkimi wersjami plików CDR?
GroupDocs.Viewer dla .NET obsługuje renderowanie plików CDR utworzonych przez różne wersje programu CorelDRAW.
### Czy mogę dostosować dane wyjściowe renderowanych plików?
Tak, GroupDocs.Viewer dla .NET udostępnia różne opcje dostosowywania wyników, takie jak dostosowywanie jakości obrazu, ustawianie znaku wodnego itp.
### Czy GroupDocs.Viewer dla .NET wymaga jakichkolwiek zewnętrznych zależności?
Nie, GroupDocs.Viewer dla .NET jest samodzielną biblioteką i nie wymaga żadnych zewnętrznych zależności do renderowania dokumentów.
### Czy dostępna jest wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz pobrać bezpłatną wersję próbną GroupDocs.Viewer dla .NET ze strony[Tutaj](https://releases.groupdocs.com/).
### Gdzie mogę uzyskać pomoc dotyczącą GroupDocs.Viewer dla platformy .NET?
 Pomoc można uzyskać na forum społeczności GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9).