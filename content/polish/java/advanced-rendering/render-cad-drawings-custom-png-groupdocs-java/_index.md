---
date: '2026-03-16'
description: Dowiedz się, jak konwertować pliki DWG na PNG o niestandardowym rozmiarze
  i kolorze tła przy użyciu GroupDocs.Viewer dla Javy.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Jak przekonwertować plik DWG na PNG o niestandardowym rozmiarze i kolorze tła
  przy użyciu GroupDocs.Viewer dla Javy
type: docs
url: /pl/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Jak przekonwertować DWG na PNG z niestandardowym rozmiarem i kolorem tła przy użyciu GroupDocs.Viewer dla Javy

Jeśli chcesz **convert DWG to PNG** zachowując pełną kontrolę nad wymiarami obrazu i stylizacją tła, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez renderowanie plików CAD jako PNG, dostosowywanie szerokości oraz zmianę koloru tła, tak aby wynik pasował do Twojego raportu, prezentacji lub wymagań podglądu w sieci.

## Szybkie odpowiedzi
- **Co oznacza „convert DWG to PNG”?** To proces zamiany pliku DWG CAD na obraz PNG przy użyciu kodu.  
- **Czy mogę ustawić niestandardową szerokość?** Tak – użyj `CadOptions.forRenderingByWidth(int width)`.  
- **Jak zmienić kolor tła?** Wywołaj `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Jakiej biblioteki wymaga?** GroupDocs.Viewer for Java (wersja 25.2 lub nowsza).  
- **Czy potrzebna jest licencja?** Tymczasowa lub zakupiona licencja usuwa ograniczenia wersji ewaluacyjnej.

![Renderowanie rysunków CAD jako PNG z niestandardowym rozmiarem i kolorem tła przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Jak przekonwertować DWG na PNG – przegląd
W tej sekcji rozwijamy główny cel: **how to convert DWG to PNG** przy kontrolowaniu rozmiaru i tła. Zobaczysz pełną konfigurację, dokładny kod, którego potrzebujesz, oraz praktyczne wskazówki, jak uniknąć typowych pułapek.

## Czego się nauczysz
- Konfiguracja GroupDocs.Viewer dla Javy w projekcie Maven  
- **Convert DWG to PNG** z niestandardowymi wymiarami  
- **Change CAD background color** podczas renderowania dla eleganckiego wyglądu  
- Rzeczywiste scenariusze, w których niestandardowe renderowanie dodaje wartość  

## Wymagania wstępne

### Wymagane biblioteki i zależności
- Java Development Kit (JDK) 8+  
- Maven do zarządzania zależnościami  

### Wymagania dotyczące konfiguracji środowiska
- IDE, takie jak IntelliJ IDEA lub Eclipse  
- Podstawowa znajomość Javy  

### Wymagania wiedzy
- Znajomość obsługi plików w Javie  

## Konfiguracja GroupDocs.Viewer dla Javy
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

### Uzyskanie licencji
Uzyskaj tymczasową lub pełną licencję, aby usunąć ograniczenia wersji ewaluacyjnej.

### Podstawowa inicjalizacja i konfiguracja
Utwórz instancję `Viewer`, która wskazuje na Twój plik CAD:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Funkcja 1: Renderowanie rysunków CAD z niestandardowym rozmiarem obrazu i kolorem tła

### Jak zmienić kolor tła CAD
Ta funkcja pozwala na **convert DWG to PNG** przy określaniu niestandardowej szerokości i zastosowaniu nowego odcienia tła.

#### Implementacja krok po kroku

##### Import wymaganych pakietów
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Skonfiguruj katalog wyjściowy i format ścieżki pliku
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Zainicjalizuj Viewer z niestandardowymi opcjami renderowania
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
- `setBackgroundColor(Color color)` – **set PNG background color** aby poprawić spójność wizualną.

#### Wskazówki dotyczące rozwiązywania problemów
- Zweryfikuj, czy folder wyjściowy istnieje; w razie potrzeby go utwórz.  
- Podwójnie sprawdź ścieżkę pliku wejściowego oraz uprawnienia.  

## Funkcja 2: Ustawianie koloru tła w opcjach renderowania

### Jak ustawić kolor tła PNG
Tutaj koncentrujemy się na opcji **set background color PNG**, aby zapewnić, że każdy renderowany obraz pasuje do palety Twojej marki.

#### Implementacja krok po kroku

##### Import wymaganych pakietów
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Skonfiguruj opcje renderowania z kolorem tła
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
- Użyj dowolnej stałej `Color` lub własnego `new Color(r,g,b)` dla indywidualnych teł.  

## Praktyczne zastosowania

### 1. Dokumentacja inżynieryjna
Niestandardowe renderowanie zapewnia, że rysunki inżynieryjne spełniają wytyczne stylu korporacyjnego.

### 2. Wizualizacja architektoniczna
Prezentuj plany z czystym tłem, które pasuje do slajdów prezentacji.

### 3. Prototypowanie w produkcji
Generuj precyzyjne pliki PNG dla szybkich przepływów pracy prototypowania.

### Możliwości integracji
Połącz ten pipeline renderowania z systemami zarządzania dokumentami, aby automatyzować generowanie zasobów wizualnych.

## Rozważania dotyczące wydajności

### Optymalizacja wydajności
- **Batch Processing:** Renderuj wiele plików CAD w pętli.  
- **Resource Management:** Dostosuj rozmiar sterty JVM dla dużych rysunków.

### Wytyczne dotyczące użycia zasobów
Monitoruj CPU i pamięć; zwalniaj instancje `Viewer` niezwłocznie.

### Najlepsze praktyki zarządzania pamięcią w Javie
- Używaj try‑with‑resources (jak pokazano), aby automatycznie zamykać `Viewer`.  
- Unikaj przechowywania dużych obiektów `Path` dłużej niż to konieczne.

## Częste problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Folder wyjściowy nie znaleziony** | Utwórz katalog wcześniej lub dodaj `Files.createDirectories(outputDirectory);` |
| **Pusty obraz** | Upewnij się, że `cadOptions.setBackgroundColor` jest ustawiony po `forRenderingByWidth`. |
| **Błędy braku pamięci** | Zwiększ opcję JVM `-Xmx` lub przetwarzaj pliki w mniejszych partiach. |

## Najczęściej zadawane pytania

**Q: Czy mogę renderować inne formaty CAD oprócz DWG?**  
A: Tak, GroupDocs.Viewer obsługuje DXF, DWF i kilka innych typów plików CAD.

**Q: Jak użyć własnego koloru RGB zamiast predefiniowanej stałej?**  
A: Utwórz nową instancję `Color`, np. `new Color(123, 45, 67)` i przekaż ją do `setBackgroundColor`.

**Q: Czy można renderować tylko określony układ lub warstwę?**  
A: Możesz określić opcje układu lub warstwy za pomocą `CadOptions` przed wywołaniem `viewer.view`.

**Q: Czy biblioteka obsługuje przezroczyste tła?**  
A: Ustaw kolor tła na `new Color(0,0,0,0)` dla pełnej przezroczystości, jeśli docelowy format to obsługuje.

**Q: Jakiej wersji GroupDocs.Viewer wymaga?**  
A: Samouczek używa wersji 25.2, ale nowsze wersje zachowują to samo API.

---

**Ostatnia aktualizacja:** 2026-03-16  
**Testowane z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs