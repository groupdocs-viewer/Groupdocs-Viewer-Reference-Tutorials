---
date: '2026-01-18'
description: Dowiedz się, jak obracać strony PDF za pomocą GroupDocs.Viewer dla Javy.
  Ten krok po kroku poradnik obejmuje konfigurację Maven, obracanie stron (w tym obrót
  PDF o 90 stopni) oraz rozwiązywanie problemów.
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: Jak obracać strony PDF przy użyciu GroupDocs.Viewer w Javie – kompleksowy przewodnik
type: docs
url: /pl/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Jak obracać strony PDF przy użyciu GroupDocs.Viewer w Javie

Obracanie konkretnych stron w pliku PDF może być niezbędne do wyrównywania dokumentów lub dostosowywania slajdów prezentacji. **W tym przewodniku dowiesz się, jak programowo obracać strony pdf** przy użyciu GroupDocs.Viewer, niezależnie od tego, czy potrzebujesz obrócić pdf o 90 stopni, odwrócić cały fragment, czy obsłużyć wiele stron w jednym wywołaniu.

![Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Czego się nauczysz:**
- Konfiguracja GroupDocs.Viewer w projekcie Java (w tym konfiguracja Maven GroupDocs Viewer)
- Programowe obracanie konkretnych stron PDF (rotate pdf 90 degrees, 180 degrees, itp.)
- Kluczowe ustawienia dla optymalnego użycia
- Rozwiązywanie typowych problemów podczas implementacji

## Szybkie odpowiedzi
- **What library can rotate PDF pages in Java?** GroupDocs.Viewer for Java.  
- **Can I rotate a single page by 90 degrees?** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **Do I need a license for development?** A temporary license is available for free trial.  
- **Is Maven required?** Maven is the recommended way to manage GroupDocs dependencies.  
- **How do I render the rotated pages?** Use `HtmlViewOptions` and call `viewer.view(...)`.

## Wymagania wstępne

### Wymagane biblioteki i zależności

Aby rozpocząć, upewnij się, że masz:
- Java Development Kit (JDK) w wersji 8 lub nowszej zainstalowany na komputerze.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse.
- Maven do zarządzania zależnościami projektu.

### Wymagania dotyczące konfiguracji środowiska

1. **Maven Configuration**: Dodaj GroupDocs.Viewer do projektu Maven, włączając niezbędne repozytoria i zależności w pliku `pom.xml`.  
2. **License Acquisition**: Uzyskaj tymczasową licencję od GroupDocs, co pozwala na korzystanie ze wszystkich funkcji bez ograniczeń podczas rozwoju. Odwiedź [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) lub złóż wniosek o tymczasową licencję na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Konfiguracja GroupDocs.Viewer dla Javy

Aby zintegrować GroupDocs.Viewer w projekcie Java przy użyciu Maven, zaktualizuj swój `pom.xml`:

**Maven Configuration**  
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

Zainicjalizuj GroupDocs.Viewer, określając katalog dokumentów oraz ścieżki wyjściowe:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Przewodnik implementacji

### Obracanie konkretnych stron przy użyciu GroupDocs.Viewer

**Overview:** Obróć konkretne strony PDF, aby uzyskać lepszą prezentację dokumentu.

#### Krok 1: Konfiguracja obrotu stron

Obróć pierwszą stronę o 90 stopni, a drugą o 180 stopni przy użyciu `HtmlViewOptions`:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### Krok 2: Inicjalizacja Viewer i renderowanie

Utwórz instancję `Viewer` z dokumentem i wyrenderuj wybrane strony:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### Parametry i konfiguracja

- **Rotation**: Użyj `rotatePage` z numerami stron i kątami obrotu. Dostępne obroty: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions**: Konfiguruje konwersję stron PDF do HTML, zapewniając włączenie zasobów osadzonych.  
- **pdf to html java**: Klasa `HtmlViewOptions` obsługuje konwersję PDF‑to‑HTML, zachowując układ.

#### Wskazówki rozwiązywania problemów (troubleshoot pdf rotation)

- Zweryfikuj ścieżki do dokumentu i katalogów wyjściowych.  
- Sprawdź brakujące zależności lub nieprawidłowe wersje bibliotek.  
- Upewnij się, że licencja jest poprawnie zastosowana, jeśli w wersji próbnej występują ograniczenia funkcji.  
- Jeśli występują skoki zużycia pamięci, rozważ renderowanie stron w mniejszych partiach (rotate multiple pdf pages gradually).

## Praktyczne zastosowania

### Przykłady zastosowań w rzeczywistym świecie
1. **Document Alignment** – Obróć zeskanowane dokumenty, aby uzyskać prawidłową orientację cyfrową.  
2. **Presentation Adjustments** – Modyfikuj slajdy prezentacji w PDF przed udostępnieniem.  
3. **Archival Workflows** – Automatycznie dostosowuj orientację historycznych dokumentów podczas digitalizacji.

### Możliwości integracji
Zintegruj GroupDocs.Viewer z systemami zarządzania dokumentami opartymi na Javie, platformami treści lub niestandardowymi rozwiązaniami korporacyjnymi wymagającymi dynamicznych możliwości podglądu.

## Rozważania dotyczące wydajności

- **Resource Management**: Zamknij instancję `Viewer`, aby zwolnić zasoby.  
- **Java Memory Management**: Monitoruj zużycie pamięci przy renderowaniu dużych dokumentów i używaj efektywnych struktur danych.  
- **Best Practices**: Wykorzystuj buforowanie dla często używanych dokumentów lub stron.

## Zakończenie

Ten tutorial omówił **jak obracać pdf** strony przy użyciu GroupDocs.Viewer w Javie, od konfiguracji środowiska po praktyczne zastosowania. Eksperymentuj z dodatkowymi funkcjami, takimi jak znakowanie wodne lub konwersja dokumentów do różnych formatów.

**Next Steps:** Explore more GroupDocs.Viewer features to enhance your document processing capabilities.

## Sekcja FAQ

### Częste pytania
1. **Troubleshooting Rotation Issues**: Verify page numbers and rotation parameters are correct.  
2. **Handling Large PDF Files**: Efficiently process large documents with proper resource management.  
3. **Licensing Requirements**: Use a temporary license for development; purchase a full license for production.  
4. **Rotating Multiple Pages**: Call `rotatePage` multiple times with different page numbers and angles.  
5. **Integration with Java Libraries**: Seamlessly integrate GroupDocs.Viewer within larger applications or frameworks.

## Najczęściej zadawane pytania

**Q: Can I rotate all pages of a PDF at once?**  
A: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)` for each page.

**Q: Does the rotation affect the original PDF file?**  
A: No. Rotation is applied only during the rendering process; the source PDF remains unchanged.

**Q: What if a PDF is password‑protected?**  
A: Provide the password when creating the `Viewer` instance: `new Viewer(path, password)`.

**Q: How do I debug a “null pointer” error when setting up HtmlViewOptions?**  
A: Ensure the output directory exists and that `pageFilePathFormat` resolves correctly.

**Q: Is there a way to rotate pages when converting to other formats (e.g., PNG)?**  
A: Use the same `rotatePage` configuration with the appropriate view options for the target format.

## Zasoby
- **Documentation**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-01-18  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs