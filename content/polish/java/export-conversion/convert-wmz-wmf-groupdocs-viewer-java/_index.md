---
date: '2026-07-19'
description: Dowiedz się, jak konwertować WMZ na PDF, HTML, JPG i PNG przy użyciu
  GroupDocs Viewer for Java. Przewodnik krok po kroku dla konwersji wektorowej grafiki
  w języku java.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Konwertuj WMZ na PDF, HTML, JPG i PNG przy użyciu GroupDocs Viewer
  for Java. Ten tutorial pokazuje krok po kroku konwersję wektorowej grafiki w języku
  java z wysoką wiernością.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Konwertuj WMZ na PDF z GroupDocs Viewer for Java – szybki przewodnik
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Konwertuj WMZ na PDF i inne formaty za pomocą GroupDocs Viewer for Java
type: docs
url: /pl/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Konwertuj WMZ na PDF i inne formaty przy użyciu GroupDocs Viewer dla Javy

Konwertowanie plików WMZ (Web Metafile) i WMF (Windows Metafile) do bardziej dostępnych formatów — szczególnie **convert WMZ to PDF** — może być trudne, ponieważ te formaty grafiki wektorowej przechowują instrukcje rysowania, a nie dane pikselowe. Dzięki **GroupDocs Viewer for Java** możesz renderować dokumenty WMZ/WMF do HTML, JPG, PNG, **PDF** i innych popularnych formatów w zaledwie kilku linijkach kodu, zachowując pierwotną jakość wizualną.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Szybkie odpowiedzi
- **Jakie formaty mogą być konwertowane z WMZ/WMF?** HTML, JPG, PNG i PDF są w pełni obsługiwane.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna usuwa ograniczenia oceny.  
- **Jaka wersja Javy jest wymagana?** Zalecana jest Java 8 lub nowsza.  
- **Czy mogę renderować tylko określone strony?** Tak, możesz określić zakresy stron w opcjach widoku.  
- **Czy zużycie pamięci jest problemem przy dużych plikach?** Użyj try‑with‑resources i renderuj tylko potrzebne strony, aby utrzymać niskie zużycie pamięci.

## Co to jest „convert WMZ to PDF”?
**Convert WMZ to PDF** oznacza wzięcie wektorowego pliku WMZ i osadzenie jego instrukcji rysowania w kontenerze PDF, tworząc dokument powszechnie wyświetlany, przeszukiwalny i drukowalny. Konwersja zachowuje jakość linii i kształtów, więc powstały PDF wygląda identycznie jak oryginalna grafika na każdym urządzeniu.

## Dlaczego używać GroupDocs Viewer dla Javy do konwersji grafiki wektorowej?
GroupDocs Viewer for Java obsługuje renderowanie WMZ i WMF z **wysoką wiernością**, zachowując szczegóły wektorowe niezależnie od tego, czy eksportujesz do PDF, PNG, czy HTML. Biblioteka działa na każdej platformie z JDK, nie wymaga natywnych komponentów Windows i udostępnia API jednokrotnego wywołania, które skaluje się od pojedynczych plików ikon do wielostronicowych rysunków technicznych. W testach wydajności przetwarza **pliki WMZ o ponad 200 stronach w mniej niż 12 sekund** na standardowym serwerze 4‑rdzeniowym.

## Prerequisites
- **GroupDocs.Viewer for Java** – rdzeniowy silnik renderujący.  
- Java Development Kit (JDK) 8 lub nowszy.  
- IDE, takie jak IntelliJ IDEA lub Eclipse (opcjonalne, ale zalecane).  
- Maven (lub Gradle) do zarządzania zależnościami.  

Znajomość Java NIO (`java.nio.file.Path`) oraz podstawowego I/O plików pomoże płynnie śledzić przykłady.

## Setting Up GroupDocs.Viewer for Java
Klasa `Viewer` jest punktem wejścia dla wszystkich operacji renderowania. Reprezentuje ona wątkowo‑bezpieczny silnik, który może być ponownie używany w wielu konwersjach.

Dodaj repozytorium i zależność do swojego `pom.xml` (lub odpowiednika Gradle). Po rozwiązaniu artefaktu przez Maven, możesz utworzyć instancję `Viewer`, która będzie ponownie używana w każdym kroku konwersji.

> **Wskazówka dotycząca licencji:** Użyj darmowej wersji próbnej do oceny, a następnie zastosuj tymczasową lub zakupioną licencję, aby odblokować pełną funkcjonalność.

## Implementation Guide
Poniżej przechodzimy przez cztery scenariusze konwersji — HTML, JPG, PNG i PDF. Każdy scenariusz stosuje ten sam trzyetapowy wzorzec:
1. **Określ katalog wyjściowy**, w którym zostaną zapisane wyrenderowane pliki.  
2. **Utwórz instancję `Viewer`**, wskazującą na źródłowy plik WMZ/WMF.  
3. **Skonfiguruj opcje widoku specyficzne dla formatu** i wywołaj metodę `view`.  

Metoda `view` wykonuje renderowanie na podstawie podanych opcji.

### Rendering WMZ/WMF to HTML
#### Przegląd
Wyjście HTML pozwala osadzić grafikę bezpośrednio w stronach internetowych, ze wszystkimi zasobami (obrazami, CSS) zawartymi w jednym pliku.

**Krok 1: Określ ścieżkę katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Krok 2: Zainicjalizuj Viewer i renderuj do HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendering WMZ/WMF to JPG
#### Przegląd
JPG jest szeroko wspieranym formatem rastrowym, idealnym do szybkich podglądów lub załączników e‑mail.

**Krok 1: Określ ścieżkę katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Krok 2: Zainicjalizuj Viewer i renderuj do JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF to PNG
#### Przegląd
PNG obsługuje przezroczystość, co czyni go idealnym dla grafik, które muszą łączyć się z różnymi tłami.

**Krok 1: Określ ścieżkę katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Krok 2: Zainicjalizuj Viewer i renderuj do PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF to PDF
#### Przegląd
PDF zapewnia platformowo‑niezależny, przeszukiwalny dokument, który zachowuje oryginalny układ.

**Krok 1: Określ ścieżkę katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Krok 2: Zainicjalizuj Viewer i renderuj do PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Typowe problemy i rozwiązania

`PageStreamViewOptions` umożliwia renderowanie określonych stron jako strumienie.  
`PdfViewOptions` konfiguruje ustawienia wyjścia PDF, takie jak zakres stron i DPI.  
`FontSettings` pozwala dostarczyć własne czcionki, gdy dokument źródłowy odwołuje się do brakujących czcionek.

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **OutOfMemoryError** przy dużych plikach WMZ | Viewer ładuje cały dokument do pamięci | Renderuj jedną stronę na raz używając `PageStreamViewOptions` lub zwiększ pamięć JVM (`-Xmx`). |
| **Brakujące czcionki** w PDF | Czcionka nie jest osadzona w źródłowym WMZ | Zainstaluj wymagane czcionki na maszynie hosta lub użyj `FontSettings`, aby dostarczyć własne czcionki. |
| **Pusty wynik PNG** | Nieprawidłowa ścieżka wyjściowa lub niewystarczające uprawnienia do zapisu | Sprawdź, czy `outputDirectory` istnieje i aplikacja ma dostęp do zapisu. |
| **Zasoby HTML nie ładują się** | Użycie `forExternalResources` bez kopiowania plików | Trzymaj się `forEmbeddedResources` dla samodzielnego pliku HTML. |

## Najczęściej zadawane pytania

**P:** Czy mogę konwertować WMF na PNG używając tego samego kodu?  
**O:** Tak. Przykład PNG działa zarówno dla plików WMZ, jak i WMF; wystarczy zamienić `TestFiles.SAMPLE_WMZ` na źródło WMF.

**P:** Czy można konwertować tylko podzbiór stron?  
**O:** Oczywiście. Użyj `PdfViewOptions` (lub odpowiednich opcji dla innych formatów) i wywołaj `setPageNumbers(List<Integer>)` przed renderowaniem.

**P:** Czy potrzebuję osobnej licencji dla każdego formatu wyjściowego?  
**O:** Nie. Jedna licencja GroupDocs Viewer obejmuje wszystkie obsługiwane formaty, w tym HTML, JPG, PNG i PDF.

**P:** Jak „java convert vector graphics” wpływa na wydajność?  
**O:** Konwersja wektor‑do‑raster jest intensywna pod względem CPU. Przy dużych partiach rozważ wielowątkowość i ponowne użycie jednej instancji `Viewer` dla wielu plików.

**P:** Czy PDF zachowa jakość wektorową, czy zostanie zrastrowany?  
**O:** Podczas konwersji WMZ/WMF do PDF, GroupDocs Viewer zachowuje instrukcje wektorowe tam, gdzie to możliwe, co skutkuje skalowalnym PDF.

## Wnioski

Masz teraz kompletny, gotowy do produkcji przewodnik, jak **convert WMZ to PDF** i inne popularne formaty przy użyciu **GroupDocs Viewer for Java**. Niezależnie od tego, czy tworzysz usługę internetową serwującą grafiki w locie, czy narzędzie archiwizujące przechowujące dokumenty jako PDF, powyższe kroki pomogą Ci szybko i niezawodnie osiągnąć cel. Zagłęb się w API, aby dostosować zakresy stron, ustawienia DPI lub znakowanie wodne zgodnie z wymaganiami projektu.

---

**Ostatnia aktualizacja:** 2026-07-19  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

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

## Powiązane samouczki

- [Jak konwertować OBJ do HTML, JPG, PNG i PDF w Javie przy użyciu GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Konwertuj IGS do PDF, HTML, JPG i PNG przy użyciu GroupDocs Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Konwertuj dokumenty do PDF – kompletny przewodnik](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)