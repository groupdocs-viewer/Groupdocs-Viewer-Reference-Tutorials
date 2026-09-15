---
date: '2026-09-15'
description: Dowiedz się, jak konwertować eml na html z niestandardowym formatem datetime
  i przesunięciem strefy czasowej przy użyciu GroupDocs.Viewer dla Java — idealne
  dla email archiving i support portals.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Konwertuj eml na html z niestandardowym formatem datetime i przesunięciem
  strefy czasowej przy użyciu GroupDocs.Viewer dla Java. Postępuj zgodnie z tym przewodnikiem
  krok po kroku, aby uzyskać dokładne renderowanie email.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Konwertuj eml na html z niestandardowym datetime w java przy użyciu GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Konwertuj eml na html z niestandardowym datetime w java przy użyciu GroupDocs.Viewer
type: docs
url: /pl/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Konwertuj EML na HTML z niestandardowym formatem daty i czasu w Javie przy użyciu GroupDocs.Viewer

W nowoczesnych systemach wsparcia i archiwizacji szybka **konwersja eml na html** przy zachowaniu dokładnych znaczników czasu jest niezbędną funkcją. Ten samouczek pokazuje, jak wyrenderować wiadomość EML do HTML, zastosować **niestandardowy format daty i czasu** oraz ustawić **przesunięcie strefy czasowej** przy użyciu GroupDocs.Viewer dla Javy. Po zakończeniu będziesz mieć wielokrotnego użytku fragment kodu, który generuje dokładne, gotowe do wyświetlenia w przeglądarce widoki e‑maili dla każdego procesu **konwersji e‑maili na html**.

![Renderowanie e‑maili z niestandardową datą i czasem przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Szybkie odpowiedzi
- **Czy GroupDocs.Viewer może konwertować EML na HTML?** Tak – API renderuje pliki EML bezpośrednio do HTML bez użycia zewnętrznych klientów poczty.  
- **Czy potrzebuję licencji do produkcji?** Bezpłatna wersja próbna wystarczy do testów; płatna licencja jest wymagana przy wdrożeniach produkcyjnych.  
- **Która wersja Javy jest wspierana?** Java 8 lub nowsza jest w pełni obsługiwana.  
- **Jak zmienić wyświetlany format daty?** Wywołaj `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **Czy mogę dostosować strefę czasową?** Tak, użyj `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Czym jest „konwersja eml na html”?
`Convert eml to html` to proces przekształcania pliku e‑mailowego EML w dokument HTML do renderowania w przeglądarce. Konwersja pliku EML na HTML zamienia surową wiadomość (w tym nagłówki, treść i załączniki) w przyjazny dla sieci format, który przeglądarki mogą wyświetlać bez dodatkowych wtyczek. Umożliwia to łatwe osadzanie e‑maili w aplikacjach webowych, archiwach lub pulpitach wsparcia.

## Dlaczego warto używać GroupDocs.Viewer do tego zadania?
GroupDocs.Viewer obsługuje **ponad 50 formatów wejściowych i wyjściowych**, w tym EML, MSG, PST i PDF, i może renderować e‑maile o setkach stron bez ładowania całego pliku do pamięci. Jego silnik bez zależności eliminuje potrzebę używania Outlooka lub parserów firm trzecich, dając pełną kontrolę nad **niestandardowym formatem daty i czasu** i **przesunięciem strefy czasowej**, przy jednoczesnym niskim zużyciu zasobów.

## Wymagania wstępne
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ i środowisko IDE Java (IntelliJ IDEA, Eclipse, VS Code)  
- Maven do zarządzania zależnościami  

## Konfiguracja GroupDocs.Viewer dla Javy

### Konfiguracja Maven
Dodaj repozytorium GroupDocs oraz zależność Viewer do pliku `pom.xml`.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Rozpocznij od bezpłatnej wersji próbnej lub poproś o tymczasową licencję do rozszerzonych testów. Kup pełną licencję do użytku produkcyjnego.

### Podstawowa inicjalizacja
Utwórz instancję `Viewer`, która wskazuje na plik EML, który chcesz skonwertować.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Konwertuj EML na HTML z niestandardowym formatem daty i czasu w Javie

Poniższe kroki przeprowadzą Cię przez renderowanie pliku EML do HTML przy zastosowaniu niestandardowego formatu daty i czasu oraz przesunięcia strefy czasowej.

### Krok 1: skonfiguruj katalog wyjściowy i ścieżkę pliku
Określ, gdzie zostanie zapisany wygenerowany plik HTML.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Explanation:* `Path.of()` tworzy odwołanie do folderu, w którym zostanie zapisany HTML. `resolve()` dołącza nazwę pliku.

### Krok 2: zainicjalizuj viewer z plikiem e‑mail
Zainstaluj klasę `Viewer` dla docelowego pliku EML.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Explanation:* Instancja `Viewer` wskazuje na plik EML, który chcesz skonwertować.

### Krok 3: skonfiguruj HtmlViewOptions
Utwórz obiekt `HtmlViewOptions`, który włącza obrazy i inne zasoby bezpośrednio do wyjścia HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Explanation:* `forEmbeddedResources()` włącza obrazy i inne zasoby bezpośrednio do wyjścia HTML.

### Krok 4: ustaw niestandardowy format daty i czasu *(custom datetime java)*
`setDateTimeFormat` ustawia wzorzec daty i czasu używany przy renderowaniu znaczników czasu e‑maili.  
Określ wzorzec, który będzie używany dla wszystkich znaczników czasu w renderowanym HTML.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Explanation:* Ten wzorzec wyświetla miesiąc, dzień, rok, godzinę, minutę, oznaczenie AM/PM oraz przesunięcie strefy czasowej (`zzz`).

### Krok 5: ustaw przesunięcie strefy czasowej *(timezone offset java)*
`setTimeZoneOffset` określa strefę czasową, która zostanie zastosowana do wszystkich znaczników czasu e‑maili.  
Dostosuj znaczniki czasu do żądanej strefy czasowej.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Explanation:* Dostosowuje renderowane znaczniki czasu do wybranej strefy czasowej. Zastąp `"GMT+1"` dowolnym prawidłowym identyfikatorem strefy.

### Jak dostosować strefę czasową e‑maila w Javie
Jeśli musisz **dostosować strefę czasową e‑maila** poza prostymi przesunięciami — na przykład obsługując zmiany czasu letniego — możesz pobrać odpowiedni obiekt `TimeZone` z API `java.util.TimeZone` używając identyfikatorów regionów takich jak `"Europe/Paris"` lub `"America/New_York"` i przekazać go do `setTimeZoneOffset`. Zapewnia to, że znaczniki czasu e‑maili zawsze odzwierciedlają właściwy lokalny czas.

### Krok 6: renderuj dokument
Wykonaj konwersję i wygeneruj końcowy plik HTML.

```java
viewer.view(options);
```
*Explanation:* Wykonuje konwersję, tworząc plik HTML z Twoimi niestandardowymi ustawieniami daty i czasu.

## Jak niestandardowy format daty i czasu wpływa na renderowany HTML?
Niestandardowy format daty i czasu określa, jak każdy znacznik czasu e‑maila pojawia się w wygenerowanym HTML, wpływając na czytelność i zgodność z lokalizacją.  
Podając wzorzec taki jak `"MMM dd, yyyy hh:mm a zzz"`, zapewniasz spójne wyświetlanie każdej daty, w tym skrót miesiąca, dzień, rok, godzinę, minutę, oznaczenie AM/PM oraz wyraźne przesunięcie strefy czasowej, co jest kluczowe dla globalnych zespołów wsparcia.

## Jakie formaty plików obsługuje GroupDocs.Viewer przy renderowaniu e‑maili?
GroupDocs.Viewer może renderować pliki **EML, MSG, PST, MBOX i EMLX** do HTML, PDF, PNG i JPEG.  
Obsługuje ponad 50 formatów dokumentów i obrazów, umożliwiając konwersję e‑maili do dowolnego z najpopularniejszych formatów przyjaznych sieci bez dodatkowych konwerterów.

## Jak mogę konwertować wiele plików eml jednocześnie?
Umieść wszystkie pliki EML w jednym katalogu, przeiteruj każdy plik przy użyciu konstrukcji `for` lub `foreach`, ponownie użyj tej samej instancji `HtmlViewOptions` i wywołaj `viewer.view` dla każdego pliku. Takie podejście minimalizuje narzut tworzenia obiektów i przyspiesza konwersje hurtowe.

## Wskazówki rozwiązywania problemów
- **FileNotFoundException:** Zweryfikuj ścieżki użyte w `Viewer` i `Path.of()`.  
- **Nieprawidłowe znaczniki czasu:** Upewnij się, że identyfikator `TimeZone` odpowiada docelowemu regionowi.  
- **Brakujące obrazy:** Upewnij się, że użyłeś `HtmlViewOptions.forEmbeddedResources()`; w przeciwnym razie zasoby zewnętrzne mogą zostać pominięte.  

## Praktyczne zastosowania
1. **Archiwizacja e‑maili:** Przechowuj przeszukiwalne migawki HTML e‑maili do audytów zgodności.  
2. **Portale wsparcia klienta:** Wyświetlaj przychodzące zgłoszenia z dokładnym lokalnym czasem dla agentów na całym świecie.  
3. **Dokumentacja prawna:** Twórz gotowe do sądu rekordy e‑maili ze standardowymi znacznikami czasu.  

## Uwagi dotyczące wydajności
- Wdrożenie na dedykowanym serwerze dla konwersji hurtowych.  
- Monitoruj zużycie sterty Javy; zwiększ `-Xmx`, jeśli napotkasz `OutOfMemoryError`.  
- Cache'uj renderowany HTML, gdy ten sam e‑mail jest wielokrotnie żądany, aby zmniejszyć obciążenie CPU.  

## Podsumowanie
Masz teraz kompletną, gotową do produkcji metodę **konwersji eml na html** z niestandardowym formatem daty i czasu oraz przesunięciem strefy czasowej przy użyciu GroupDocs.Viewer dla Javy. To rozwiązanie poprawia czytelność, zapewnia dokładność znaczników czasu i płynnie integruje się z procesami archiwizacji, wsparcia lub dokumentacji prawnej.  

**Kolejne kroki:** Zapoznaj się z dodatkowymi opcjami Viewer, takimi jak wstrzykiwanie własnego CSS, paginacja lub konwersja do PDF, aby jeszcze lepiej dostosować wyjście do potrzeb Twojej aplikacji.

## Najczęściej zadawane pytania

**Q:** Jak obsłużyć pliki eml z załącznikami?  
**A:** Załączniki są automatycznie wbudowywane, gdy używasz `HtmlViewOptions.forEmbeddedResources()`. Możesz je również wyodrębnić za pomocą API Viewer, jeśli potrzebujesz osobnych plików.

**Q:** Czy mogę zmienić szablon HTML lub dodać własny CSS?  
**A:** Tak, po renderowaniu możesz edytować wygenerowany plik HTML lub wstrzyknąć CSS programowo przed zapisaniem.

**Q:** Czy można renderować wiele plików eml w partii?  
**A:** Umieść logikę renderowania w pętli i ponownie użyj tej samej instancji `HtmlViewOptions` dla każdego pliku.

**Q:** Co zrobić, jeśli muszę obsługiwać inne formaty e‑maili, takie jak msg?  
**A:** GroupDocs.Viewer obsługuje również MSG, PST i inne kontenery e‑maili — wystarczy zmienić rozszerzenie pliku w konstruktorze `Viewer`.

**Q:** Czy potrzebuję osobnej licencji na każdy serwer?  
**A:** Licencjonowanie jest przypisane do wdrożenia; zapoznaj się z przewodnikiem licencyjnym GroupDocs w przypadku scenariuszy wieloserwerowych.

## Zasoby

- [Dokumentacja](https://docs.groupdocs.com/viewer/java/)
- [Referencja API](https://reference.groupdocs.com/viewer/java/)
- [Pobierz](https://releases.groupdocs.com/viewer/java/)
- [Zakup](https://purchase.groupdocs.com/buy)
- [Bezpłatna wersja próbna](https://releases.groupdocs.com/viewer/java/)
- [Licencja tymczasowa](https://purchase.groupdocs.com/temporary-license/)
- [Forum wsparcia](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-09-15  
**Testowano z:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs

## Powiązane samouczki

- [Konwertuj e‑mail na HTML i zmień nazwy pól – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java konwertuj msg na pdf – Optymalizacja renderowania e‑maili do PDF przy użyciu GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java Responsywne renderowanie HTML](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
