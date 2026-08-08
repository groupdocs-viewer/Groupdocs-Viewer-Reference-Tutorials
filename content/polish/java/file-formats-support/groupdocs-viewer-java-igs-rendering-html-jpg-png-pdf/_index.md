---
date: '2026-08-08'
description: Dowiedz się, jak konwertować IGS do PDF, HTML, JPG i PNG przy użyciu
  GroupDocs.Viewer dla Java. Przewodnik krok po kroku, wymagania wstępne i rozwiązywanie
  problemów dla programistów Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Konwertuj IGS do PDF, HTML, JPG i PNG przy użyciu GroupDocs.Viewer
  dla Java. Szczegółowa konfiguracja, fragmenty kodu i rozwiązywanie problemów dla
  programistów Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Konwertuj IGS do PDF, HTML, JPG i PNG za pomocą GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Konwertuj IGS do PDF, HTML, JPG i PNG za pomocą GroupDocs.Viewer Java
type: docs
url: /pl/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Konwertuj IGS do PDF, HTML, JPG i PNG za pomocą GroupDocs.Viewer Java

Jeśli potrzebujesz **konwertować IGS do PDF** (lub do HTML, JPG, PNG) bezpośrednio z aplikacji Java, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez wszystko, czego potrzebujesz — od instalacji biblioteki po renderowanie modelu 3‑D w formacie pasującym do Twojego projektu. Zrozumiesz, dlaczego GroupDocs.Viewer jest solidnym wyborem dla szybkich, niezawodnych konwersji i otrzymasz gotowe fragmenty kodu, które możesz wstawić do własnego rozwiązania.

![Konwertuj pliki IGS do HTML, JPG, PNG i PDF za pomocą GroupDocs.Viewer dla Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Szybkie odpowiedzi
- **Czy mogę konwertować IGS do PDF w Javie?** Tak, użyj `PdfViewOptions` wraz z API `Viewer`.  
- **Jakie formaty wyjściowe są obsługiwane?** HTML, JPG, PNG i PDF są obsługiwane natywnie.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna; darmowa wersja próbna pozwala przetestować podstawowe funkcje.  
- **Jakiej wersji Javy wymaga?** JDK 8 lub wyższy; biblioteka działa również na Java 11, 17 i nowszych.  
- **Czy Maven jest jedynym sposobem dodania biblioteki?** Nie, możesz również użyć Gradle lub ręcznie dodać pliki JAR do classpath.

## Co to jest konwersja IGS do PDF?
Konwersja IGS do PDF oznacza przekształcenie neutralnego pliku CAD 3‑D w statyczny, uniwersalnie wyświetlany dokument. Umożliwia to udostępnianie wizualizacji projektu interesariuszom, którzy nie posiadają narzędzi CAD, osadzanie renderingu w raportach lub archiwizowanie modelu w celach zgodności.

## Dlaczego warto używać GroupDocs.Viewer do konwersji IGS?
GroupDocs.Viewer przetwarza pliki IGS bez konieczności używania zewnętrznego oprogramowania CAD. Obsługuje **ponad 50 formatów wejściowych i wyjściowych**, może renderować zestawy zawierające **setki części**, utrzymując zużycie pamięci poniżej **200 MB**, i dostarcza wyniki w czasie krótszym niż **2 sekundy** dla typowych modeli na standardowym serwerze. Te wymierne korzyści czynią go wysokowydajnym, opłacalnym wyborem dla przepływów pracy w przedsiębiorstwach.

## Wymagania wstępne
- **GroupDocs.Viewer for Java** ≥ 25.2 (najnowsze stabilne wydanie).  
- **JDK 8+** zainstalowane i skonfigurowane w Twoim IDE (IntelliJ IDEA, Eclipse, NetBeans itp.).  
- Podstawowa znajomość Maven (opcjonalna, ale zalecana do zarządzania zależnościami).  

## Konfiguracja GroupDocs.Viewer dla Java

### Zależność Maven
Dodaj repozytorium GroupDocs oraz zależność Viewer do swojego `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Uzyskanie licencji
GroupDocs.Viewer oferuje trzy opcje licencjonowania:
- **Darmowa wersja próbna** – ograniczone użycie, idealna do szybkich testów proof‑of‑concept.  
- **Licencja tymczasowa** – pełny zestaw funkcji na krótki okres oceny, idealna do projektów pilotażowych.  
- **Licencja komercyjna** – nieograniczone użycie w produkcji, zawiera wsparcie priorytetowe i aktualizacje.

### Podstawowa inicjalizacja przeglądarki
Klasa `Viewer` jest punktem wejścia dla wszystkich operacji renderowania. Ładuje plik źródłowy, parsuje format i udostępnia metody do generowania żądanego wyjścia.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Renderowanie IGS do HTML

### Jak przekonwertować IGS do HTML?
Wczytaj plik IGS przy użyciu instancji `Viewer` i przekaż obiekt `HtmlViewOptions`, który osadza wszystkie wymagane zasoby. Wywołanie zwraca pojedynczy plik HTML zawierający pełny widok 3‑D, co ułatwia osadzanie go na stronach internetowych. Możesz również dostosować renderowanie, ustawiając opcje takie jak rozmiar strony, kolor tła oraz czy uwzględnić interaktywne kontrolki.  
`HtmlViewOptions` konfiguruje sposób generowania wyjścia HTML, w tym osadzanie zasobów i układ strony.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Renderowanie IGS do JPG

### Jak przekonwertować IGS do JPG?
Utwórz obiekt `JpgViewOptions`, skonfiguruj żądaną rozdzielczość i jakość kompresji, a następnie pozwól `Viewer` wygenerować obrazy rastrowe dla każdej strony modelu. Wygenerowane pliki JPG mogą być zapisane w określonym katalogu, a parametr jakości można dostosować, aby zrównoważyć rozmiar pliku z jakością wizualną, co jest przydatne przy miniaturkach lub wydrukach wysokiej rozdzielczości.  
`JpgViewOptions` określa ustawienia generowania obrazów JPG, takie jak rozdzielczość, jakość i katalog wyjściowy.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Renderowanie IGS do PNG

### Jak przekonwertować IGS do PNG?
Klasa `PngViewOptions` pozwala tworzyć obrazy bezstratne z opcjonalną przezroczystością. Ten format jest idealny do nakładania modelu na kolorowe tła w materiałach marketingowych. Możesz również określić rozdzielczość i kolor tła, aby dopasować je do wytycznych marki, zapewniając spójny wygląd wszystkich generowanych zasobów.  
`PngViewOptions` definiuje parametry renderowania PNG, w tym rozdzielczość, przezroczystość i kolor tła.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Renderowanie IGS do PDF

### Jak przekonwertować IGS do PDF?
Użyj `PdfViewOptions`, aby stworzyć stronicowany PDF zachowujący układ wizualny modelu 3‑D. Możesz również osadzić czcionki i kontrolować rozmiar strony, aby spełnić wytyczne brandingowe firmy. Dodatkowe ustawienia pozwalają określić jakość obrazu, poziom kompresji oraz czy uwzględnić spis treści dla zestawów wielostronicowych.  
`PdfViewOptions` kontroluje tworzenie PDF, umożliwiając konfigurację rozmiaru strony, jakości obrazu i osadzania czcionek.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Praktyczne zastosowania
- **Portale internetowe** – osadzaj modele renderowane w HTML bezpośrednio w konfiguratorach produktów, umożliwiając klientom obracanie i przybliżanie bez instalowania wtyczek.  
- **Materiały marketingowe** – generuj obrazy JPG/PNG wysokiej rozdzielczości do broszur, prezentacji i postów w mediach społecznościowych.  
- **Dokumentacja techniczna** – dołącz renderingi PDF modeli CAD w podręcznikach użytkownika, zapewniając inżynierom możliwość przeglądania projektów offline.  
- **Kontrola jakości** – automatyzuj tworzenie miniatur dla tysięcy plików IGS, przyspieszając przepływy pracy związane z inspekcją wizualną.

## Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Nie znaleziono folderu wyjściowego** | Sprawdź ścieżkę przekazaną do `Path outputDirectory` i upewnij się, że proces Java ma uprawnienia do zapisu w docelowym katalogu. |
| **Puste strony w PDF** | Upewnij się, że źródłowy plik IGS nie jest uszkodzony; najpierw otwórz go w natywnym przeglądarce CAD. |
| **Wolne renderowanie dużych zestawów** | Zwiększ przydział pamięci JVM (`-Xmx2g` lub więcej) i rozważ renderowanie strona po stronie przy użyciu `viewer.getPageCount()`, aby przetwarzać partie. |
| **Brakujące czcionki w PDF** | Użyj `PdfViewOptions` do osadzenia wymaganych czcionek lub zainstaluj brakujące czcionki na serwerze obsługującym usługę konwersji. |

## Najczęściej zadawane pytania

**Q: Czy mogę konwertować wiele plików IGS w jednym uruchomieniu?**  
A: Tak. Iteruj po kolekcji ścieżek do plików i wywołaj odpowiednią metodę `view` dla każdego pliku w tej samej instancji `Viewer`.

**Q: Czy można dostosować rozmiar strony PDF?**  
A: Oczywiście. `PdfViewOptions` oferuje `setPageSize(PageSize.A4)`, `PageSize.Letter` oraz niestandardowe wymiary poprzez `setCustomSize(width, height)`.

**Q: Czy potrzebuję osobnej licencji dla każdego formatu wyjściowego?**  
A: Nie. Jedna licencja GroupDocs.Viewer obejmuje wszystkie obsługiwane formaty, w tym HTML, JPG, PNG i PDF.

**Q: Jak duży może być plik IGS, zanim wydajność spadnie?**  
A: Biblioteka niezawodnie przetwarza pliki do **500 MB**; dla modeli większych niż 200 MB przydziel dodatkową pamięć JVM i rozważ renderowanie w partiach.

**Q: Czy mogę renderować tylko określony widok lub orientację?**  
A: GroupDocs.Viewer renderuje domyślną orientację zdefiniowaną w pliku IGS. Aby uzyskać niestandardowe widoki, wstępnie przetwórz plik przy użyciu narzędzia CAD lub dostosuj model przed konwersją.

**Ostatnia aktualizacja:** 2026-08-08  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Powiązane samouczki

- [konwertuj cdr do html, jpg, png, pdf za pomocą GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Jak konwertować pdf do html i optymalizować jakość obrazu w Javie przy użyciu GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)