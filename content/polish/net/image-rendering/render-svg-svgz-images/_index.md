---
title: Renderuj obrazy SVG i SVGZ
linktitle: Renderuj obrazy SVG i SVGZ
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować obrazy SVG i SVGZ za pomocą GroupDocs.Viewer dla .NET. Bez wysiłku konwertuj grafikę wektorową do formatu HTML, JPG, PNG i PDF.
weight: 16
url: /pl/net/image-rendering/render-svg-svgz-images/
---
## Wstęp
tym samouczku przeprowadzimy Cię przez proces renderowania obrazów SVG i SVGZ przy użyciu programu GroupDocs.Viewer dla .NET. GroupDocs.Viewer dla .NET to potężny interfejs API do renderowania dokumentów, który umożliwia programistom renderowanie dokumentów w różnych formatach w aplikacjach .NET. SVG i SVGZ to popularne formaty obrazów używane w grafice wektorowej, a dzięki GroupDocs.Viewer dla .NET można z łatwością renderować je do różnych formatów wyjściowych, takich jak HTML, JPG, PNG i PDF.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowane i skonfigurowane następujące wymagania wstępne:
1.  GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: upewnij się, że masz działające środowisko programistyczne do programowania .NET, takie jak Visual Studio.
3. Przykładowy plik SVGZ: przygotuj przykładowy plik SVGZ do testowania.

## Importuj przestrzenie nazw
Zanim zagłębimy się w kod, zaimportujmy niezbędne przestrzenie nazw:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Renderuj SVGZ do HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Krok 2: Renderuj SVGZ do JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Krok 3: Renderuj SVGZ do PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Krok 4: Renderuj SVGZ do formatu PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Wniosek
tym samouczku nauczyliśmy się renderować obrazy SVG i SVGZ za pomocą programu GroupDocs.Viewer dla .NET. W kilku prostych krokach możesz przekonwertować obrazy SVGZ na różne formaty wyjściowe, takie jak HTML, JPG, PNG i PDF, dzięki czemu będą dostępne i widoczne w różnych środowiskach.
## Często zadawane pytania
### Czy GroupDocs.Viewer może renderować inne formaty obrazów?
Tak, GroupDocs.Viewer obsługuje renderowanie różnych formatów obrazów, w tym PNG, JPEG, BMP, TIFF, GIF i innych.
### Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?
Tak, GroupDocs.Viewer jest kompatybilny zarówno z .NET Framework, jak i .NET Core.
### Czy mogę dostosować opcje renderowania?
Tak, GroupDocs.Viewer udostępnia rozbudowane opcje renderowania, umożliwiające dostosowanie wyników do własnych wymagań.
### Czy GroupDocs.Viewer wymaga jakichkolwiek zależności od stron trzecich?
Nie, GroupDocs.Viewer jest samodzielnym interfejsem API i nie wymaga żadnych zależności od stron trzecich do renderowania dokumentów.
### Czy dostępna jest wersja próbna do przetestowania?
Tak, możesz pobrać bezpłatną wersję próbną GroupDocs.Viewer ze strony[Tutaj](https://releases.groupdocs.com/) aby ocenić jego funkcje przed dokonaniem zakupu.