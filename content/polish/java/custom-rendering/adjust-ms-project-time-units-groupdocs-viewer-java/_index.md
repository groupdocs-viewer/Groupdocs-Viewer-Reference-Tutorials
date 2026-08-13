---
date: '2026-05-21'
description: Dowiedz się, jak wykonać eksport HTML z MS Project z dostosowanymi jednostkami
  czasu przy użyciu GroupDocs Viewer for Java. Przewodnik krok po kroku z wymaganiami
  wstępnymi, konfiguracją i rozwiązywaniem problemów.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Eksport HTML z MS Project: Dostosuj jednostki czasu za pomocą GroupDocs Java'
type: docs
url: /pl/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Eksport HTML MS Project: Dostosowanie jednostek czasu za pomocą GroupDocs Java

Eksportowanie pliku **MS Project** do HTML jest powszechnym wymaganiem dla pulpitów zarządzania projektami, portali raportów statusowych i narzędzi współpracy przeglądowej. Domyślnie przeglądarka renderuje dane czasowe w minutach, co może zaśmiecać układ wizualny i utrudniać odczyt codziennych raportów. Dzięki **GroupDocs Viewer for Java** możesz programowo ustawić jednostkę czasu na **days**, uzyskując czysty *ms project html export*, który odpowiada typowym oczekiwaniom interesariuszy. W tym samouczku dowiesz się, jak skonfigurować przeglądarkę, dostosować jednostkę czasu i renderować projekt do HTML w kilku prostych krokach.

![Dostosowanie jednostek czasu w MS Project za pomocą GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Szybkie odpowiedzi
- **Jaką bibliotekę renderuje pliki MS Project?** GroupDocs Viewer for Java.  
- **Jaką jednostkę czasu mogę ustawić dla eksportu HTML?** Days, using `TimeUnit.DAYS`.  
- **Czy potrzebuję licencji do produkcji?** Tak — wymagana jest stała licencja; wersja próbna działa w celach oceny. Możesz rozpocząć od [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Jakie IDE działa najlepiej?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Czy Maven jest obowiązkowy?** Maven upraszcza zarządzanie zależnościami, ale możesz również użyć Gradle lub ręcznego dołączania plików JAR.  
- **Gdzie mogę dokonać zakupu?** Odwiedź [strona zakupu](https://purchase.groupdocs.com/buy) for pricing.

## Czym jest GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** jest zestawem SDK w języku Java, który konwertuje ponad 150 formatów dokumentów — w tym MS Project — do przyjaznego dla sieci HTML, PNG, JPEG lub PDF.  
Abstrahuje logikę parsowania, pozwala kontrolować opcje renderowania takie jak jednostki czasu i działa na każdej platformie wspierającej Java 8 lub wyższą.  

## Dlaczego dostosować jednostki czasu przy eksporcie HTML MS Project?
Ustawienie jednostki czasu na **days** (dni) redukuje szum wizualny, odpowiada większości cykli raportowania i poprawia czasy ładowania stron, ponieważ generowane jest mniej drobnych znaczników czasu. W liczbach, renderowanie w dniach zamiast minut może zmniejszyć rozmiar wygenerowanego HTML o nawet **45 %** dla typowych projektów 30‑dniowych i przyspieszyć renderowanie po stronie klienta o około **30 %**.

## Wymagania wstępne
- **Java Development Kit (JDK) 8 lub nowszy** zainstalowany na Twoim komputerze.  
- **Maven** (lub Gradle) do zarządzania zależnościami.  
- Plik **MS Project (.mpp)**, który chcesz wyeksportować.  
- Dostęp do licencji **GroupDocs Viewer for Java** (wersja próbna lub stała).  

### Wymagane biblioteki
Dodaj następującą zależność do swojego `pom.xml` (lub równoważny fragment Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Wskazówka:** Utrzymuj numer wersji aktualny; nowsze wydania dodają obsługę formatów i ulepszenia wydajności.

## Jak skonfigurować GroupDocs Viewer for Java?
Zainicjalizuj przeglądarkę, tworząc instancję `Viewer`, która wskazuje na Twój plik MS Project. Klasa `Viewer` jest punktem wejścia dla wszystkich operacji renderowania. Ładuje dokument źródłowy, przygotowuje struktury wewnętrzne i udostępnia metody takie jak `view()` i `viewToHtml()`, aby generować żądane formaty wyjściowe.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definicja:** Klasa `Viewer` jest podstawowym komponentem GroupDocs Viewer, który ładuje dokument źródłowy i udostępnia metody renderowania takie jak `view()` i `viewToHtml()`.

## Jak mogę dostosować jednostki czasu przy eksporcie HTML?
Aby zmienić szczegółowość czasu, utwórz obiekt `ViewOptions`, skonfiguruj jego `ProjectOptions`, aby używał `TimeUnit.DAYS`, i przekaż go do przeglądarki. `ViewOptions` definiuje ustawienia renderowania dokumentu, natomiast enum `TimeUnit` określa jednostkę (minutes, hours, days) dla danych czasowych. Po ustawieniu tych opcji wywołaj `viewer.view(options)`, aby wygenerować HTML z dziennymi znacznikami.

Załaduj swój plik MS Project przy użyciu `new Viewer("file.mpp")`, utwórz obiekt `ViewOptions`, ustaw `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, a następnie wywołaj `viewer.view(options)`. Ten trzyetapowy przepływ zmienia jednostkę czasu z minut na dni i generuje pliki HTML wyświetlające wyłącznie dzienne przedziały.

### Krok 1: Zdefiniuj folder wyjściowy
Wybierz zapisywalny katalog, w którym zostaną zapisane strony HTML, na przykład `output/`.

### Krok 2: Utwórz opcje widoku z osadzonymi zasobami
Osadzone zasoby (CSS, JavaScript) zapewniają, że strony HTML są samodzielne.

### Krok 3: Ustaw jednostkę czasu na dni
Użyj `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, aby zmienić szczegółowość.

### Krok 4: Renderuj dokument
Wywołaj `viewer.view(options)`; przeglądarka zapisuje jeden plik HTML na każdą stronę projektu w folderze wyjściowym.

### Krok 5: Zweryfikuj wynik
Otwórz wygenerowany `index.html` w przeglądarce; powinieneś zobaczyć paski zadań wyrównane do znaczników dni zamiast znaczników minut.

## Typowe pułapki i rozwiązywanie problemów
- **Nieprawidłowa ścieżka wyjściowa** – Upewnij się, że katalog istnieje i proces Java ma uprawnienia do zapisu.  
- **Brak licencji** – Bez ważnej licencji przeglądarka przełącza się w tryb próbny i może dodawać znaki wodne.  
- **Duże pliki (> 500 MB)** – Rozważ zwiększenie rozmiaru sterty JVM (`-Xmx2g`) lub renderowanie z `options.setRenderLimit(1000)`, aby przetwarzać strony w partiach.  

## Praktyczne zastosowania eksportu HTML z dostosowaną jednostką czasu
1. **Pulpity wykonawcze** – Dzienna szczegółowość odpowiada większości wizualizacji KPI.  
2. **Automatyczne e‑maile statusowe** – Osadź wygenerowany HTML bezpośrednio w treści e‑maili dla szybkich aktualizacji.  
3. **Portale projektowe** – Udostępnij HTML na stronie intranetowej, gdzie członkowie zespołu mogą filtrować zadania według dnia.  

## Wskazówki dotyczące wydajności przy dużych plikach MS Project
- **Zarządzanie pamięcią** – Użyj flag garbage collectora Javy (`-XX:+UseG1GC`), aby szybko zwalniać nieużywane obiekty.  
- **Selektywne renderowanie** – Jeśli potrzebujesz tylko wykresu Gantta, wyłącz renderowanie innych zasobów za pomocą `options.getProjectOptions().setRenderGantt(true)` i `setRenderResources(false)`.  
- **Przetwarzanie równoległe** – Przy konwersjach wsadowych twórz osobne obiekty `Viewer` dla każdego pliku i uruchamiaj je w puli wątków, aby wykorzystać wielordzeniowe procesory.

## Podsumowanie
Masz teraz kompletny, gotowy do produkcji przepływ pracy do wykonywania **ms project html export** z jednostkami czasu ustawionymi na dni przy użyciu GroupDocs Viewer for Java. To podejście zmniejsza rozmiar HTML, przyspiesza renderowanie po stronie klienta i dostarcza przyjazny dla interesariuszy widok harmonogramów projektów. Poznaj dodatkowe opcje renderowania — takie jak eksport do PDF lub migawki obrazu — aby rozszerzyć integrację o szersze kanały raportowania.

## Najczęściej zadawane pytania

**Q: Czy mogę renderować inne widoki Project (np. Resource Sheet) do HTML?**  
A: Tak, obiekt `ProjectOptions` pozwala włączać lub wyłączać konkretne widoki, takie jak Gantt, Resource Sheet i Calendar, przed renderowaniem.

**Q: Czy można dostosować CSS generowanego HTML?**  
A: Oczywiście. Podaj ścieżkę do własnego arkusza stylów za pomocą `options.setStyleSheetPath("path/to/custom.css")`, a przeglądarka osadzi go w każdej stronie.

**Q: Jakie limity rozmiaru pliku obsługuje GroupDocs Viewer dla MS Project?**  
A: SDK może obsługiwać pliki do **500 MB** bez konieczności ładowania całego dokumentu do pamięci, dzięki architekturze strumieniowej.

**Q: Czy muszę instalować Microsoft Project na serwerze?**  
A: Nie. GroupDocs Viewer parsuje format .mpp bezpośrednio i nie wymaga Microsoft Project ani żadnej instalacji Office.

**Q: Jak licencjonować przeglądarkę w środowisku produkcyjnym?**  
A: Kup stałą licencję w sklepie GroupDocs; zastosuj plik licencji w czasie wykonywania za pomocą `License license = new License(); license.setLicense("path/to/license.lic");`. W przypadku krótkoterminowych potrzeb możesz uzyskać [temporary license](https://purchase.groupdocs.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-05-21  
**Testowano z:** GroupDocs Viewer Java 25.2  
**Autor:** GroupDocs  

**Zasoby**  
- [Dokumentacja](https://docs.groupdocs.com/viewer/java/)  
- [Referencja API](https://reference.groupdocs.com/viewer/java/)  
- [Pobierz GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Kup licencję](https://purchase.groupdocs.com/buy)  

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Powiązane samouczki

- [Jak renderować pliki MS Project jako HTML, JPG, PNG i PDF z notatkami przy użyciu GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Jak używać GroupDocs Viewer do renderowania dokumentów projektowych według przedziałów czasowych w Javie](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Jak ustawić licencje w GroupDocs.Viewer Java: przewodnik po konfiguracji pliku i URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)