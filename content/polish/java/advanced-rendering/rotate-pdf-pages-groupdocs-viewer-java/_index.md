---
date: '2026-04-04'
description: Dowiedz się, jak obracać wybrane strony PDF za pomocą GroupDocs.Viewer
  for Java. Ten przewodnik krok po kroku obejmuje konfigurację Maven, obrót PDF o
  90 stopni oraz rozwiązywanie problemów.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: Jak obrócić wybrane strony PDF za pomocą GroupDocs.Viewer dla Javy
type: docs
url: /pl/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Jak obracać określone strony PDF za pomocą GroupDocs.Viewer dla Javy

Obracanie określonych stron w pliku PDF może być niezbędne do wyrównywania dokumentów, naprawiania zeskanowanych obrazów lub dostosowywania slajdów prezentacji. **W tym przewodniku dowiesz się, jak programowo obracać określone strony pdf za pomocą GroupDocs.Viewer**, niezależnie od tego, czy musisz obrócić pdf o 90 stopni, odwrócić cały sekcję, czy obsłużyć wiele stron w jednym wywołaniu.

![Obróć określone strony PDF za pomocą GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Co się nauczysz**
- Konfiguracja GroupDocs.Viewer w projekcie Java (w tym konfiguracja Maven GroupDocs Viewer)
- Programowe obracanie określonych stron PDF (obrót pdf o 90 stopni, 180 stopni itp.)
- Kluczowe konfiguracje dla optymalnego użycia
- Rozwiązywanie typowych problemów podczas implementacji

## Szybkie odpowiedzi
- **Jaka biblioteka może obracać strony PDF w Javie?** GroupDocs.Viewer for Java.  
- **Czy mogę obrócić pojedynczą stronę o 90 stopni?** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **Czy potrzebuję licencji do rozwoju?** A temporary license is available for free trial.  
- **Czy Maven jest wymagany?** Maven is the recommended way to manage GroupDocs dependencies.  
- **Jak renderować obrócone strony?** Use `HtmlViewOptions` and call `viewer.view(...)`.

## Wymagania wstępne

### Wymagane biblioteki i zależności
- Java Development Kit (JDK) 8 lub nowszy.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Maven do zarządzania zależnościami.

### Wymagania dotyczące konfiguracji środowiska
1. **Konfiguracja Maven** – add GroupDocs.Viewer to your `pom.xml`.  
2. **Uzyskanie licencji** – obtain a temporary license from GroupDocs. Visit [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) or apply for a temporary license on the [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Konfiguracja GroupDocs.Viewer dla Javy

Aby zintegrować GroupDocs.Viewer ze swoim projektem Java przy użyciu Maven, zaktualizuj swój `pom.xml`:

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
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Jak obracać określone strony PDF za pomocą GroupDocs.Viewer
### Przegląd
Obracanie określonych stron PDF daje precyzyjną kontrolę nad prezentacją dokumentu bez zmiany oryginalnego pliku.

### Krok 1: Konfiguracja obrotu stron
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Krok 2: Inicjalizacja Viewer i renderowanie
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parametry i konfiguracja
- **Rotation** – `rotatePage(pageNumber, Rotation.*)`, gdzie opcje obrotu to `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Obsługuje konwersję PDF‑do‑HTML zachowując układ i osadzone zasoby.  
- **pdf to html java** – Klasa jest częścią tego samego API i zapewnia wierną reprezentację wizualną.

## Dlaczego obracać określone strony PDF?
- **Wyrównanie dokumentu** – Poprawna orientacja zeskanowanych umów lub faktur.  
- **Dostosowanie prezentacji** – Dostosuj slajdy wyeksportowane jako PDF.  
- **Spójność archiwizacji** – Standaryzuj orientację stron podczas masowej digitalizacji.

## Typowe problemy i rozwiązania (rozwiązywanie problemów z obrotem pdf)
- **Nieprawidłowe ścieżki** – Zweryfikuj, że `YOUR_DOCUMENT_DIRECTORY` i `YOUR_OUTPUT_DIRECTORY` istnieją i są dostępne.  
- **Brakujące zależności** – Upewnij się, że współrzędne Maven odpowiadają najnowszej wersji GroupDocs.Viewer.  
- **Ograniczenia licencji** – Zastosuj tymczasową licencję prawidłowo; w przeciwnym razie niektóre funkcje mogą być wyłączone.  
- **Wzrost zużycia pamięci** – Renderuj duże PDF-y w mniejszych partiach lub zwiększ rozmiar sterty JVM.

## Praktyczne zastosowania

### Przykłady zastosowań w rzeczywistym świecie
1. **Wyrównanie dokumentu** – Obróć zeskanowane dokumenty w celu uzyskania prawidłowej orientacji cyfrowej.  
2. **Dostosowanie prezentacji** – Zmodyfikuj slajdy prezentacji w PDF-ach przed udostępnieniem.  
3. **Procesy archiwizacji** – Automatycznie dostosuj orientację historycznych dokumentów podczas digitalizacji.

### Możliwości integracji
Połącz GroupDocs.Viewer z systemami zarządzania treścią opartymi na Javie, portalami korporacyjnymi lub własnymi API, które wymagają podglądu PDF‑ów w locie.

## Względy wydajnościowe
- **Zarządzanie zasobami** – Zawsze zamykaj instancję `Viewer`, aby zwolnić uchwyty plików i pamięć.  
- **Zarządzanie pamięcią w Javie** – Monitoruj użycie sterty przy przetwarzaniu dużych PDF‑ów; rozważ strumieniowanie stron zamiast ładowania całego pliku.  
- **Najlepsze praktyki** – Buforuj renderowany HTML dla często używanych dokumentów, aby skrócić czas przetwarzania.

## Zakończenie
Ten samouczek omówił **jak obracać określone strony pdf przy użyciu GroupDocs.Viewer w Javie**, od konfiguracji Maven po renderowanie obróconych stron i radzenie sobie z typowymi problemami. Eksperymentuj z dodatkowymi funkcjami, takimi jak znakowanie wodą, konwersja formatów czy przetwarzanie wsadowe, aby dalej rozszerzyć swój przepływ pracy z dokumentami.

**Kolejne kroki:** Zanurz się w inne możliwości GroupDocs.Viewer, takie jak konwersja PDF‑ów do PNG, dodawanie znaków wodnych lub integracja z dostawcami przechowywania w chmurze.

## Sekcja FAQ
- **Rozwiązywanie problemów z obrotem** – Zweryfikuj, że numery stron i parametry obrotu są prawidłowe.  
- **Obsługa dużych plików PDF** – Przetwarzaj strony w partiach i monitoruj zużycie pamięci.  
- **Wymagania licencyjne** – Użyj tymczasowej licencji do rozwoju; zakup pełną licencję do produkcji.  
- **Obracanie wielu stron** – Wywołuj `rotatePage` wielokrotnie z różnymi numerami stron i kątami.  
- **Integracja z bibliotekami Java** – GroupDocs.Viewer współpracuje płynnie ze Spring Boot, Jakarta EE i innymi frameworkami Java.

## Najczęściej zadawane pytania

**Q: Czy mogę obrócić wszystkie strony PDF jednocześnie?**  
A: Tak. Przejdź w pętli przez numery stron i wywołaj `rotatePage(page, Rotation.ON_90_DEGREE)` dla każdej strony.

**Q: Czy obrót wpływa na oryginalny plik PDF?**  
A: Nie. Obrót jest stosowany tylko podczas procesu renderowania; źródłowy PDF pozostaje niezmieniony.

**Q: Co zrobić, jeśli PDF jest chroniony hasłem?**  
A: Podaj hasło przy tworzeniu instancji `Viewer`: `new Viewer(path, password)`.

**Q: Jak debugować błąd „null pointer” przy konfigurowaniu HtmlViewOptions?**  
A: Upewnij się, że katalog wyjściowy istnieje i że `pageFilePathFormat` jest poprawnie rozwiązywany.

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

---

**Ostatnia aktualizacja:** 2026-04-04  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs