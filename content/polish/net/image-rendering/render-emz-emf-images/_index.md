---
title: Renderuj obrazy EMZ i EMF
linktitle: Renderuj obrazy EMZ i EMF
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować obrazy EMZ i EMF do różnych formatów za pomocą GroupDocs.Viewer dla .NET. Łatwy do zrozumienia samouczek dla programistów.
weight: 14
url: /pl/net/image-rendering/render-emz-emf-images/
---
## Wstęp

GroupDocs.Viewer dla .NET to potężny interfejs API do renderowania dokumentów, który umożliwia programistom wyświetlanie różnych typów dokumentów, w tym obrazów EMZ (rozszerzony metaplik systemu Windows) i EMF (rozszerzony metaplik) w aplikacjach .NET. W tym samouczku dowiemy się, jak renderować obrazy EMZ i EMF do różnych formatów, takich jak HTML, JPG, PNG i PDF, przy użyciu programu GroupDocs.Viewer dla platformy .NET.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

1.  GroupDocs.Viewer dla .NET: Bibliotekę można pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane kompatybilne środowisko programistyczne do programowania .NET.
3. Przykładowe obrazy EMZ/EMF: udostępnij do renderowania przykładowe obrazy EMZ i EMF.

## Importuj przestrzenie nazw

Zanim zagłębimy się w kod, zaimportujmy niezbędne przestrzenie nazw:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Podzielmy teraz każdy przykład na wiele kroków w formie przewodnika krok po kroku:

## Renderowanie obrazów EMZ/EMF do formatu HTML

### Krok 1: Ustaw katalog wyjściowy:
```csharp
string outputDirectory = "Your Document Directory";
```
 Zastępować`"Your Document Directory"`ze ścieżką, w której chcesz zapisać wyrenderowany plik HTML.

### Krok 2: Zdefiniuj format ścieżki pliku strony:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Spowoduje to określenie formatu ścieżki pliku dla renderowanego pliku HTML.

### Krok 3: Renderuj do HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Ten kod inicjuje`Viewer` obiekt z przykładowym obrazem EMZ i renderuje go do formatu HTML przy użyciu określonych opcji.

## Renderowanie obrazów EMZ/EMF do formatów JPG, PNG i PDF

Powtórz poniższe kroki, aby renderować do formatów JPG, PNG i PDF:

### Krok 1: Zdefiniuj format ścieżki pliku strony:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Dostosuj nazwę pliku i rozszerzenie zgodnie z żądanym formatem wyjściowym (`jpg`, `png` , Lub`pdf`).

### Krok 2: Renderuj do odpowiedniego formatu:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Dostosuj opcje zgodnie z formatem wyjściowym (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Zastępować`JpgViewOptions` z`PngViewOptions` Lub`PdfViewOptions` w oparciu o żądany format wyjściowy.

## Wniosek

Podsumowując, GroupDocs.Viewer dla .NET zapewnia płynne rozwiązanie do renderowania obrazów EMZ i EMF do różnych formatów w aplikacjach .NET. Wykonując kroki opisane w tym samouczku, programiści mogą bez wysiłku zintegrować możliwości renderowania dokumentów ze swoimi aplikacjami.

## Często zadawane pytania

### P: Czy GroupDocs.Viewer może renderować inne formaty dokumentów oprócz obrazów EMZ i EMF?
O: Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, DOCX, PPTX, XLSX i inne.

### P: Czy dostępna jest bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.groupdocs.com/).

### P: Czy GroupDocs.Viewer oferuje wsparcie dla programistów?
 Odp.: Tak, GroupDocs zapewnia wsparcie za pośrednictwem swojego narzędzia[forum](https://forum.groupdocs.com/c/viewer/9) gdzie programiści mogą zadawać pytania i szukać pomocy.

### P: Czy mogę kupić tymczasową licencję na GroupDocs.Viewer dla .NET?
 Odpowiedź: Tak, można kupić licencje tymczasowe[Tutaj](https://purchase.groupdocs.com/temporary-license/).

### P: Gdzie mogę znaleźć szczegółową dokumentację GroupDocs.Viewer dla .NET?
 Odpowiedź: Możesz zapoznać się z dokumentacją[Tutaj](https://tutorials.groupdocs.com/viewer/net/)aby uzyskać kompleksowe wskazówki dotyczące korzystania z interfejsu API.