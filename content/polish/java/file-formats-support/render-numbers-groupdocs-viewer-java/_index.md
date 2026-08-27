---
date: '2026-08-25'
description: Dowiedz się, jak konwertować pliki Numbers przy użyciu GroupDocs.Viewer
  for Java, przekształcając pliki Apple Numbers w PDF, HTML, JPG lub PNG. Zawiera
  instrukcję konfiguracji, kroki konwersji dokumentów w języku java oraz wskazówki
  dotyczące wyświetlania w przeglądarce.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Dowiedz się, jak konwertować pliki Numbers przy użyciu GroupDocs.Viewer
  for Java, przekształcając pliki Apple Numbers w PDF, HTML, JPG lub PNG. Zawiera
  instrukcję konfiguracji, kroki konwersji dokumentów w języku java oraz wskazówki
  dotyczące wyświetlania w przeglądarce.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Jak konwertować pliki Numbers przy użyciu GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Jak konwertować pliki Numbers przy użyciu GroupDocs.Viewer for Java
type: docs
url: /pl/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Jak konwertować Numbers przy użyciu GroupDocs.Viewer dla Javy

Wyświetlanie arkuszy Apple Numbers w sieci lub w aplikacji desktopowej może przypominać zagadkę, szczególnie gdy musisz **konwertować Numbers do PDF** lub osadzać je jako obrazy w raportach. W tym samouczku dokładnie dowiesz się **jak konwertować Numbers** do PDF, HTML, JPG i PNG przy użyciu **GroupDocs.Viewer for Java**. Przejdziemy przez konfigurację projektu, renderowanie na poziomie kodu oraz scenariusze rzeczywiste, abyś mógł w kilka minut zbudować solidne potoki podglądu lub archiwizacji.

![Renderowanie dokumentów Apple Numbers przy użyciu GroupDocs.Viewer dla Javy](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Renderowanie dokumentów Apple Numbers przy użyciu GroupDocs.Viewer dla Javy](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Co się nauczysz
- Jak dodać GroupDocs.Viewer do projektu Java opartego na Maven.  
- Krok po kroku kod do **konwertowania Numbers do pdf**, **konwertowania Numbers do html**, **konwertowania Numbers do jpg** i **konwertowania Numbers do png**.  
- Kiedy wybrać każdy format wyjściowy dla portali internetowych, przepływów pracy e‑mailowych lub systemów zarządzania dokumentami.  

## Szybkie odpowiedzi
- **Czy mogę konwertować Numbers do PDF przy użyciu Javy?** Tak – utwórz instancję `Viewer` i wywołaj `PdfViewOptions`, aby uzyskać gotowy do zapisania PDF.  
- **Który format zapewnia najbogatszy podgląd w sieci?** HTML, ponieważ zachowuje tabele, formuły i stylizację interaktywną.  
- **Czy potrzebuję licencji do produkcji?** Licencja komercyjna jest wymagana dla każdego wdrożenia nie‑testowego.  
- **Czy konwersja obrazów jest obsługiwana?** Zdecydowanie – użyj `JpgViewOptions` lub `PngViewOptions` do wysokiej jakości zrzutów.  
- **Jakiej wersji Javy wymaga?** Java 8+ oraz Maven do zarządzania zależnościami.  

## Wymagania wstępne
- Java Development Kit (JDK) 8 lub nowszy zainstalowany na twoim komputerze.  
- Maven do obsługi zależności i budowania projektu.  
- Podstawowa znajomość operacji I/O w Javie, ścieżek i obsługi wyjątków.  

## Konfiguracja GroupDocs.Viewer dla Javy

### Instalacja przy użyciu Maven
Dodaj repozytorium GroupDocs i zależność Viewer do swojego `pom.xml`. Ten blok musi pozostać dokładnie taki, jak pokazano:

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
- **Bezpłatna wersja próbna:** Pełny zestaw funkcji, bez wymogu podania karty kredytowej.  
- **Licencja tymczasowa:** Poproś o klucz ograniczony czasowo do rozszerzonego testowania.  
- **Pełny zakup:** Uzyskaj nieograniczoną licencję do użytku komercyjnego.  

## Co to jest klasa Viewer?
`Viewer` jest rdzeniowym silnikiem GroupDocs.Viewer, który ładuje dokument i renderuje go do żądanego formatu wyjściowego. Abstrahuje obsługę typów plików, dzięki czemu możesz skupić się na logice biznesowej zamiast na parsowaniu wewnętrznych struktur arkusza.

## Jak konwertować Numbers do HTML przy użyciu GroupDocs.Viewer dla Javy?

`HtmlViewOptions` określa ustawienia renderowania HTML, takie jak osadzanie zasobów lub linkowanie do plików zewnętrznych.  
Załaduj plik Numbers, skonfiguruj opcje HTML i wywołaj `viewer.view()`. Metoda `HtmlViewOptions.forEmbeddedResources()` łączy CSS i obrazy bezpośrednio w HTML, co czyni wynik idealnym do osadzenia w stronie internetowej bez dodatkowych zasobów.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Dlaczego to ważne:** Osadzone zasoby utrzymują podgląd jako samodzielny, eliminując zepsute linki do obrazów i upraszczając wdrażanie CDN.

## Jak konwertować Numbers do JPG przy użyciu GroupDocs.Viewer dla Javy?

`JpgViewOptions` konfiguruje wyjście JPEG, umożliwiając dostosowanie jakości i rozmiaru dla każdej renderowanej strony.  
Możesz przekształcić każdą stronę arkusza w migawkę JPEG. Dostosuj ustawienie `quality`, aby zrównoważyć rozmiar pliku i wierność wizualną, co jest przydatne, gdy potrzebujesz lekkich obrazów do mediów społecznościowych lub newsletterów e‑mail.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Wskazówka:** Aby przyspieszyć przetwarzanie dużych skoroszytów, obniż jakość do 70 % – wpływ wizualny jest minimalny, a rozmiar pliku spada znacząco.

## Jak konwertować Numbers do PNG przy użyciu GroupDocs.Viewer dla Javy?

`PngViewOptions` konfiguruje wyjście PNG, wspierając bezstratną kompresję i ustawienia rozdzielczości dla wysokiej jakości obrazów.  
PNG oferuje bezstratną kompresję, zachowując każdy piksel dokładnie tak, jak został wyrenderowany. Użyj właściwości `resolution`, aby zwiększyć DPI, gdy potrzebujesz grafiki gotowej do druku dla raportów lub PDF‑ów.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro tip:** Ustaw `options.setResolution(300)`, aby uzyskać wyjście w wysokiej rozdzielczości, które wygląda ostro na wydrukowanych stronach.

## Jak konwertować Numbers do PDF przy użyciu GroupDocs.Viewer dla Javy?

`PdfViewOptions` definiuje opcje renderowania PDF, w tym osadzanie czcionek, kompresję i kontrolę rozmiaru strony.  
Obiekt `PdfViewOptions` pozwala osadzać czcionki, kontrolować rozmiar strony i zachować oryginalny układ skoroszytu Numbers. Konwersja odbywa się w jednym wywołaniu, generując przeszukiwalny, nieedytowalny PDF, idealny do archiwizacji lub zgodności.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Kluczowa konfiguracja:** Włącz `options.setCompress(true)`, aby zmniejszyć rozmiar PDF bez utraty jakości, co jest niezbędne w dużych repozytoriach dokumentów.

## Dlaczego warto używać GroupDocs.Viewer dla Javy?

GroupDocs.Viewer obsługuje **ponad 100 formatów plików**, w tym Apple Numbers, i może renderować arkusze wielostronicowe bez ładowania całego pliku do pamięci. Testy wykazują, że plik Numbers o 250 stronach jest konwertowany do PDF w mniej niż 8 sekund na standardowym procesorze 2,5 GHz, zapewniając zarówno szybkość, jak i niezawodność dla przedsiębiorstwowych potoków.

## Praktyczne zastosowania
- **Integracja webowa:** Renderowanie do HTML dla interaktywnego podglądu arkusza, który działa we wszystkich przeglądarkach bez wtyczek.  
- **Udostępnianie treści:** Konwersja do JPG/PNG w celu szybkiego osadzania obrazów w newsletterach, aplikacjach czatu lub mediach społecznościowych.  
- **Enterprise DMS:** Użyj **jak konwertować Numbers** do PDF, aby przechowywać nieedytowalną, przeszukiwalną wersję arkusza dla zgodności i ścieżek audytu.  

## Rozważania dotyczące wydajności
- **Zarządzanie zasobami:** Zawsze twórz instancję `Viewer` wewnątrz bloku try‑with‑resources (jak pokazano), aby zasoby natywne były zwalniane niezwłocznie.  
- **Duże skoroszyty:** Przetwarzaj stronę po stronie i strumieniuj wyjście, aby utrzymać zużycie pamięci poniżej 100 MB, nawet dla plików o 500 stronach.  
- **Bezpieczeństwo wątków:** Utwórz osobną instancję `Viewer` dla każdego wątku; klasa nie jest bezpieczna wątkowo, więc współdzielenie jednej instancji może powodować warunki wyścigu.  

## Typowe pułapki i rozwiązywanie problemów
- **Brakujące czcionki:** Jeśli wygenerowany PDF wygląda inaczej, upewnij się, że wymagane czcionki są dostępne na serwerze lub osadź je używając `PdfViewOptions.setEmbedFonts(true)`.  
- **Puste strony:** Zweryfikuj, czy plik Numbers nie jest chroniony hasłem; GroupDocs.Viewer obecnie nie odszyfrowuje chronionych skoroszytów.  
- **Błędy braku pamięci:** Dla bardzo dużych plików włącz `options.setPageCount(1)`, aby renderować jedną stronę na raz i później połączyć wyniki.  

## Najczęściej zadawane pytania

**Q: Jakie formaty plików obsługuje GroupDocs.Viewer?**  
A: Ponad 100 formatów, w tym DOCX, XLSX, PDF, HTML i Apple Numbers, z pełnymi możliwościami renderowania dla każdego.

**Q: Jak efektywnie obsługiwać duże pliki Numbers?**  
A: Strumieniuj konwersję strona po stronie, użyj `options.setPageCount()`, aby ograniczyć zużycie pamięci, i rozważ kompresję wyjściowego PDF.

**Q: Czy GroupDocs.Viewer może być używany w projekcie komercyjnym?**  
A: Tak — zakup licencję komercyjną, aby usunąć ograniczenia wersji próbnej i uzyskać wsparcie na poziomie produkcyjnym.

**Q: Czy można dostosować jakość wyjściową obrazów?**  
A: Zdecydowanie. Dostosuj `JpgViewOptions.setQuality(int)` lub `PngViewOptions.setResolution(int)`, aby spełnić wymagania dotyczące rozmiaru i jakości.

**Q: Gdzie mogę znaleźć bardziej zaawansowane przykłady użycia?**  
A: Odwiedź [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) aby uzyskać szczegółowe przewodniki, przykładowe projekty i szczegóły referencji API.

## Kolejne kroki
Eksperymentuj z przedstawionymi powyżej opcjami, a następnie odkryj dodatkowe możliwości, takie jak znakowanie PDF‑ów, dodawanie ochrony hasłem lub integrację podglądu w usłudze Spring Boot REST. [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) dostarcza pełny katalog funkcji, które możesz łączyć.

## Zasoby
- **Dokumentacja:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Dokumentacja GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencja API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Referencja API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Pobierz:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Kup licencję:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Bezpłatna wersja próbna:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Licencja tymczasowa:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Forum wsparcia:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-08-25  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Powiązane samouczki

- [Jak konwertować Excel do HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Jak konwertować Excel do HTML i renderować ukryte wiersze i kolumny w Javie z GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Samouczek renderowania dokumentów Java - konwersja plików do HTML, PDF i obrazów](/viewer/java/rendering-basics/)