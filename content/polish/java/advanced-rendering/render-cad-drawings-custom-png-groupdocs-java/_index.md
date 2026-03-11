---
date: '2026-01-08'
description: Dowiedz się, jak renderować rysunki CAD do wysokiej jakości obrazów PNG,
  używając niestandardowych wymiarów i kolorów tła w GroupDocs.Viewer dla Javy.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Jak renderować rysunki CAD jako PNG o niestandardowym rozmiarze i kolorze tła
  przy użyciu GroupDocs.Viewer dla Javy
type: docs
url: /pl/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Jak renderować rysunki CAD jako PNG z niestandardowym rozmiarem i kolorem tła przy użyciu GroupDocs.Viewer dla Javy

Masz problem z konwersją rysunków CAD na obrazy wysokiej jakości, zachowując określone wymiary i estetykę? W tym samouczku pokażemy **jak renderować CAD** pliki jako PNG z niestandardowym rozmiarem i kolorem tła, aby uzyskać dokładnie taki wygląd, jaki potrzebujesz do raportów, prezentacji lub podglądów internetowych.

## Szybkie odpowiedzi
- **Co oznacza „jak renderować CAD”?** Odnosi się to do konwersji plików CAD (np. DWG) na formaty obrazów, takie jak PNG, przy użyciu kodu.  
- **Czy mogę ustawić niestandardową szerokość?** Tak – użyj `CadOptions.forRenderingByWidth(int width)`.  
- **Jak zmienić tło?** Wywołaj `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Jakiej biblioteki wymaga?** GroupDocs.Viewer dla Javy (wersja 25.2 lub nowsza).  
- **Czy potrzebna jest licencja?** Tymczasowa lub zakupiona licencja usuwa ograniczenia wersji próbnej.

![Renderowanie rysunków CAD jako PNG z niestandardowym rozmiarem i kolorem tła przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Jak renderować rysunki CAD – przegląd
Ta sekcja rozwija główny cel: **jak renderować CAD** rysunki do plików PNG przy jednoczesnym kontrolowaniu rozmiaru i tła. Przejdziemy przez pełną konfigurację, fragmenty kodu i praktyczne wskazówki.

## Czego się nauczysz
- Konfigurowanie GroupDocs.Viewer dla Javy w Twoim projekcie  
- **Konwertowanie DWG do PNG** z niestandardowymi wymiarami  
- **Ustawienie koloru tła PNG** podczas renderowania dla wykończonego wyglądu  
- Scenariusze rzeczywiste, w których niestandardowe renderowanie dodaje wartość  

## Wymagania wstępne

### Required Libraries and Dependencies
- Java Development Kit (JDK) 8+  
- Maven do zarządzania zależnościami  

### Environment Setup Requirements
- IDE, takie jak IntelliJ IDEA lub Eclipse  
- Podstawowa znajomość Javy  

### Knowledge Prerequisites
- Znajomość obsługi plików w Javie  

## Konfigurowanie GroupDocs.Viewer dla Javy
Dodaj repozytorium GroupDocs i zależność do swojego pliku Maven `pom.xml`:

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

### License Acquisition
Uzyskaj tymczasową lub pełną licencję, aby usunąć ograniczenia wersji próbnej.

### Basic Initialization and Setup
Utwórz instancję `Viewer`, która wskazuje na Twój plik CAD:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Przewodnik implementacji

### Feature 1: Rendering CAD Drawings with Custom Image Size and Background Color

#### Overview
Ta funkcja pozwala **konwertować DWG do PNG** przy określaniu szerokości obrazu i odcienia tła.

#### Step‑by‑Step Implementation

##### Import Required Packages
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Set Up the Output Directory and File Path Format
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Initialize Viewer with Custom Rendering Options
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Wyjaśnienie parametrów**  
- `PngViewOptions` – definiuje format wyjścia i nazewnictwo.  
- `forRenderingByWidth(int width)` – ustawia niestandardową szerokość obrazu.  
- `setBackgroundColor(Color color)` – **zastosowanie renderowania koloru tła** do PNG.

#### Troubleshooting Tips
- Zweryfikuj, czy folder wyjściowy istnieje; w razie potrzeby go utwórz.  
- Sprawdź dwukrotnie ścieżkę pliku wejściowego i uprawnienia.  

### Feature 2: Setting Background Color in Rendering Options

#### Overview
Tutaj koncentrujemy się na **ustawieniu koloru tła PNG**, aby poprawić spójność wizualną.

#### Step‑by‑Step Implementation

##### Import Required Packages
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configure Rendering Options with Background Color
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Kluczowe opcje konfiguracji**  
- Dostosuj `forRenderingByWidth(int width)` dla różnych wymiarów.  
- Użyj dowolnej stałej `Color` lub własnego `new Color(r,g,b)` dla niestandardowych tł

## Praktyczne zastosowania

### 1. Dokumentacja inżynieryjna
Niestandardowe renderowanie zapewnia, że rysunki inżynieryjne spełniają wytyczne stylu korporacyjnego.

### 2. Wizualizacja architektoniczna
Prezentuj plany z czystym tłem, które pasuje do slajdów prezentacji.

### 3. Prototypowanie w produkcji
Generuj precyzyjne PNG do szybkich procesów prototypowania.

### Możliwości integracji
Połącz ten pipeline renderowania z systemami zarządzania dokumentami, aby zautomatyzować generowanie zasobów wizualnych.

## Rozważania dotyczące wydajności

### Optimizing Performance
- **Przetwarzanie wsadowe:** Renderuj wiele plików CAD w pętli.  
- **Zarządzanie zasobami:** Dostosuj rozmiar sterty JVM dla dużych rysunków.

### Resource Usage Guidelines
Monitoruj CPU i pamięć; zwalniaj instancje `Viewer` niezwłocznie.

### Best Practices for Java Memory Management
- Używaj try‑with‑resources (jak pokazano), aby automatycznie zamykać `Viewer`.  
- Unikaj przechowywania dużych obiektów `Path` dłużej niż to konieczne.

## Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Folder wyjściowy nie znaleziony** | Utwórz katalog wcześniej lub dodaj `Files.createDirectories(outputDirectory);` |
| **Pusty obraz** | Upewnij się, że `cadOptions.setBackgroundColor` jest ustawione po `forRenderingByWidth`. |
| **Błędy braku pamięci** | Zwiększ opcję JVM `-Xmx` lub przetwarzaj pliki w mniejszych partiach. |

## Najczęściej zadawane pytania

**Q: Czy mogę renderować inne formaty CAD oprócz DWG?**  
A: Tak, GroupDocs.Viewer obsługuje DXF, DWF i kilka innych typów plików CAD.

**Q: Jak użyć niestandardowego koloru RGB zamiast predefiniowanej stałej?**  
A: Utwórz nową instancję `Color`, np. `new Color(123, 45, 67)` i przekaż ją do `setBackgroundColor`.

**Q: Czy można renderować tylko określony układ lub warstwę?**  
A: Możesz określić opcje układu lub warstwy za pomocą `CadOptions` przed wywołaniem `viewer.view`.

**Q: Czy biblioteka obsługuje przezroczyste tła?**  
A: Ustaw kolor tła na `new Color(0,0,0,0)` dla pełnej przezroczystości, jeśli docelowy format to obsługuje.

**Q: Jakiej wersji GroupDocs.Viewer wymaga?**  
A: Samouczek używa wersji 25.2, ale nowsze wersje zachowują to samo API.

## Podsumowanie
Teraz wiesz **jak renderować CAD** rysunki do plików PNG z niestandardowymi wymiarami i kolorami tła przy użyciu GroupDocs.Viewer dla Javy. Zastosuj te techniki, aby tworzyć profesjonalnie wyglądające zasoby wizualne dla procesów inżynieryjnych, architektonicznych lub produkcyjnych.

### Kolejne kroki
- Eksperymentuj z różnymi szerokościami obrazu i kolorami.  
- Zintegruj kod renderowania z usługą przetwarzania wsadowego.  
- Odkryj dodatkowe opcje Viewer, takie jak konwersja do PDF lub renderowanie wielostronicowe.

---

**Ostatnia aktualizacja:** 2026-01-08  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs