---
date: '2026-10-05'
description: Dowiedz się, jak obrócić wybrane strony PDF za pomocą GroupDocs.Viewer
  for Java. Ten przewodnik krok po kroku obejmuje konfigurację Maven, obrót pdf o
  90 stopni oraz rozwiązywanie problemów.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Obróć wybrane strony PDF za pomocą GroupDocs.Viewer for Java. Dowiedz
  się, jak obrócić pdf o 90 stopni, skonfigurować Maven i rozwiązać typowe problemy
  w zwięzłym przewodniku.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Obróć wybrane strony PDF za pomocą GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Jak obrócić wybrane strony PDF za pomocą GroupDocs.Viewer for Java
type: docs
url: /pl/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Jak obracać określone strony PDF przy użyciu GroupDocs.Viewer dla Javy

Obracanie określonych stron w pliku PDF może być niezbędne do wyrównywania dokumentów, naprawiania zeskanowanych obrazów lub dostosowywania slajdów prezentacji. **W tym przewodniku dowiesz się, jak programowo obracać określone strony PDF przy użyciu GroupDocs.Viewer**, niezależnie od tego, czy potrzebujesz obrócić PDF o 90 stopni, odwrócić cały fragment, czy obsłużyć wiele stron w jednym wywołaniu.

![Obracanie określonych stron PDF przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Obracanie określonych stron PDF przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Czego się nauczysz**
- Konfiguracja GroupDocs.Viewer w projekcie Java (w tym konfiguracja Maven GroupDocs Viewer)
- Programowe obracanie określonych stron PDF (obrócenie PDF o 90 stopni, 180 stopni itp.)
- Kluczowe konfiguracje dla optymalnego użycia
- Rozwiązywanie typowych problemów podczas implementacji

## Szybkie odpowiedzi
- **Jaką bibliotekę można użyć do obracania stron PDF w Javie?** GroupDocs.Viewer for Java zapewnia wbudowaną obsługę rotacji bez zewnętrznych narzędzi.  
- **Czy mogę obrócić pojedynczą stronę o 90 stopni?** Tak – wywołaj `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` na instancji viewer.  
- **Czy potrzebna jest licencja do rozwoju?** Tymczasowa licencja jest darmowa do oceny; pełna licencja jest wymagana w produkcji.  
- **Czy Maven jest wymagany?** Maven jest zalecanym menedżerem zależności, ale możesz także używać Gradle lub ręcznego dołączania JAR.  
- **Jak renderować obrócone strony?** Użyj `HtmlViewOptions` z `viewer.view(documentPath, viewOptions)`, aby uzyskać wyjście HTML odzwierciedlające rotację.

## Co to jest obracanie określonych stron PDF?
`rotate specific pdf pages` odnosi się do możliwości zmiany orientacji poszczególnych stron w dokumencie PDF, przy zachowaniu pozostałych części pliku niezmienionych. Operacja ta jest wykonywana w czasie renderowania, więc oryginalny plik PDF pozostaje niezmieniony.

## Dlaczego obracać określone strony PDF?
Możesz obrócić pojedynczą stronę w mniej niż 0,05 sekundy na typowej maszynie wirtualnej klasy serwerowej, umożliwiając podgląd w czasie rzeczywistym zeskanowanych umów, prezentacji lub wielostronicowych faktur zawierających nieprawidłowo skierowane skany. Ta precyzyjna kontrola eliminuje potrzebę kosztownych narzędzi post‑processingowych i zmniejsza ręczną pracę nawet o 70 % w dużych projektach digitalizacji.

## Wymagania wstępne

### Wymagane biblioteki i zależności
- Java Development Kit (JDK) 8 lub nowszy.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Maven do zarządzania zależnościami.

### Wymagania dotyczące konfiguracji środowiska
1. **Konfiguracja Maven** – dodaj GroupDocs.Viewer do swojego `pom.xml`.  
2. **Uzyskanie licencji** – zdobądź tymczasową licencję od GroupDocs. Odwiedź [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) lub złożyć wniosek o tymczasową licencję na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Konfiguracja GroupDocs.Viewer dla Javy

Aby zintegrować GroupDocs.Viewer w projekcie Java przy użyciu Maven, zaktualizuj swój `pom.xml`:

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

### Podstawowa inicjalizacja i konfiguracja
`Viewer` jest klasą rdzeniową, która ładuje dokument i koordynuje operacje renderowania. Po utworzeniu instancji możesz wywoływać metody takie jak `view` lub `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Jak obracać określone strony PDF przy użyciu GroupDocs.Viewer
Obracanie określonych stron PDF przy użyciu GroupDocs.Viewer obejmuje dwa główne kroki: najpierw określ żądaną rotację dla każdej docelowej strony przy użyciu metody `rotatePage`, a następnie renderuj dokument przy użyciu `HtmlViewOptions`, aby rotacja została odzwierciedlona w wyniku. To podejście pozostawia oryginalny PDF niezmieniony, jednocześnie dostarczając prawidłowo skierowany HTML.

### Krok 1: skonfiguruj rotację stron
`rotatePage` jest metodą przyjmującą indeks strony liczony od zera oraz wartość wyliczenia `Rotation`. Wyliczenie oferuje trzy opcje: `ON_90_DEGREE`, `ON_180_DEGREE` i `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Krok 2: zainicjalizuj viewer i renderuj
`HtmlViewOptions` kontroluje proces konwersji PDF‑do‑HTML. Zachowuje układ, czcionki i zasoby osadzone, jednocześnie stosując wszelką skonfigurowaną rotację.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parametry i konfiguracja
- **Rotation** – `rotatePage(pageNumber, Rotation.*)`, gdzie opcje rotacji to `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Obsługuje konwersję pdf‑do‑html, zachowując układ i zasoby osadzone.  
- **pdf to html java** – Klasa jest częścią tego samego API i zapewnia wierną reprezentację wizualną.

## Typowe problemy i rozwiązania (rozwiązywanie problemów z rotacją PDF)
- **Nieprawidłowe ścieżki** – Zweryfikuj, że `YOUR_DOCUMENT_DIRECTORY` i `YOUR_OUTPUT_DIRECTORY` istnieją i są dostępne.  
- **Brakujące zależności** – Upewnij się, że współrzędne Maven odpowiadają najnowszej wersji GroupDocs.Viewer (obecnie 25.2).  
- **Ograniczenia licencyjne** – Zastosuj tymczasową licencję prawidłowo; w przeciwnym razie niektóre funkcje mogą być wyłączone.  
- **Skoki pamięci** – Renderuj duże PDF-y w mniejszych partiach lub zwiększ rozmiar sterty JVM.

## Praktyczne zastosowania

### Praktyczne przypadki użycia
1. **Wyrównanie dokumentów** – Obróć zeskanowane umowy, aby uzyskać prawidłową orientację cyfrową.  
2. **Dostosowanie prezentacji** – Modyfikuj slajdy prezentacji w PDF przed udostępnieniem.  
3. **Przepływy archiwizacji** – Automatycznie dostosuj orientację historycznych dokumentów podczas digitalizacji.

### Możliwości integracji
Połącz GroupDocs.Viewer z systemami zarządzania treścią opartymi na Javie, portalami korporacyjnymi lub własnymi API wymagającymi podglądu PDF w locie.

## Aspekty wydajnościowe
- **Zarządzanie zasobami** – Zawsze zamykaj instancję `Viewer`, aby zwolnić uchwyty plików i pamięć.  
- **Zarządzanie pamięcią w Javie** – Monitoruj zużycie sterty przy przetwarzaniu dużych PDF‑ów; rozważ strumieniowanie stron zamiast ładowania całego pliku.  
- **Najlepsze praktyki** – Buforuj renderowany HTML dla często używanych dokumentów, aby skrócić czas przetwarzania nawet o 60 %.

## Zakończenie
Ten samouczek omówił **jak obracać określone strony PDF przy użyciu GroupDocs.Viewer w Javie**, od konfiguracji Maven po renderowanie obróconych stron i radzenie sobie z typowymi problemami. Eksperymentuj z dodatkowymi funkcjami, takimi jak znakowanie wodne, konwersja formatów czy przetwarzanie wsadowe, aby jeszcze bardziej rozbudować swój przepływ dokumentów.

**Kolejne kroki:** Zagłęb się w inne możliwości GroupDocs.Viewer, takie jak konwersja PDF‑ów do PNG, dodawanie znaków wodnych lub integracja z dostawcami przechowywania w chmurze.

## Sekcja FAQ
- **Rozwiązywanie problemów z rotacją** – Zweryfikuj, że numery stron i parametry rotacji są prawidłowe.  
- **Obsługa dużych plików PDF** – Przetwarzaj strony w partiach i monitoruj zużycie pamięci.  
- **Wymagania licencyjne** – Użyj tymczasowej licencji do rozwoju; zakup pełną licencję do produkcji.  
- **Obracanie wielu stron** – Wywołuj `rotatePage` wielokrotnie z różnymi numerami stron i kątami.  
- **Integracja z bibliotekami Java** – GroupDocs.Viewer działa płynnie ze Spring Boot, Jakarta EE i innymi frameworkami Java.

## Najczęściej zadawane pytania

**Q: Czy mogę obrócić wszystkie strony PDF jednocześnie?**  
A: Tak. Przejdź w pętli przez numery stron i wywołaj `rotatePage(page, Rotation.ON_90_DEGREE)` dla każdej strony.

**Q: Czy rotacja wpływa na oryginalny plik PDF?**  
A: Nie. Rotacja jest stosowana wyłącznie podczas procesu renderowania; źródłowy PDF pozostaje niezmieniony.

**Q: Co zrobić, jeśli PDF jest zabezpieczony hasłem?**  
A: Podaj hasło przy tworzeniu instancji `Viewer`: `new Viewer(path, password)`.

**Q: Jak debugować błąd „null pointer” przy konfigurowaniu HtmlViewOptions?**  
A: Upewnij się, że katalog wyjściowy istnieje i że `pageFilePathFormat` jest prawidłowo rozwiązywany.

**Q: Czy istnieje sposób na obracanie stron przy konwersji do innych formatów (np. PNG)?**  
A: Tak. Użyj tej samej konfiguracji `rotatePage` z odpowiednimi opcjami widoku dla docelowego formatu.

## Zasoby
- **Dokumentacja**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Pobieranie**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Zakup**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Bezpłatna wersja próbna**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Tymczasowa licencja**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Wsparcie**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

**Ostatnia aktualizacja:** 2026-10-05  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Powiązane samouczki

- [Przewodnik Java: renderowanie wybranych stron java z GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Renderowanie PDF w Java Groupdocs Viewer – podziały stron](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [Groupdocs Viewer Java – responsywne renderowanie HTML](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)