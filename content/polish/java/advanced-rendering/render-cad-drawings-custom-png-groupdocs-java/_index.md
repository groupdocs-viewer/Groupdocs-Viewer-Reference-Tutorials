---
date: '2026-08-30'
description: Dowiedz się, jak przekonwertować DWG na PNG, ustawić kolor tła w Javie
  oraz dostosować rozmiar obrazu przy użyciu GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Konwertuj DWG na PNG przy użyciu GroupDocs.Viewer for Java, ustawiając
  niestandardową szerokość obrazu i kolor tła. Ten przewodnik zawiera instrukcje krok
  po kroku, fragmenty kodu oraz wskazówki rozwiązywania problemów.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Konwertuj DWG na PNG o niestandardowym rozmiarze i kolorze tła w Javie
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Jak przekonwertować DWG na PNG o niestandardowym rozmiarze i kolorze tła przy
  użyciu GroupDocs.Viewer for Java
type: docs
url: /pl/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Jak przekonwertować DWG na PNG z niestandardowym rozmiarem i kolorem tła przy użyciu GroupDocs.Viewer dla Javy

W tym samouczku dowiesz się **jak przekonwertować DWG na PNG** kontrolując wymiary wyjściowe i kolor tła, przy użyciu GroupDocs.Viewer dla Javy. Niezależnie od tego, czy potrzebujesz osadzić rysunki CAD w raporcie, generować miniatury dla portalu internetowego, czy zautomatyzować renderowanie wsadowe, poniższe kroki dają pełną kontrolę nad wyglądem każdego pliku PNG.

## Szybkie odpowiedzi
- **Co oznacza „konwersja DWG na PNG”?** To proces przekształcania pliku CAD DWG w obraz PNG za pomocą kodu, zachowując szczegóły wektorowe jako piksele rastrowe.  
- **Czy mogę ustawić niestandardową szerokość?** Tak – wywołaj `CadOptions.forRenderingByWidth(int width)`, aby określić dokładną wymaganą szerokość w pikselach.  
- **Jak zmienić kolor tła?** Użyj `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` przed renderowaniem.  
- **Jakiej biblioteki wymaga?** GroupDocs.Viewer for Java (wersja 25.2 lub nowsza).  
- **Czy potrzebna jest licencja?** Tymczasowa lub pełna licencja usuwa ograniczenia wersji próbnej i umożliwia nieograniczone renderowanie.

![Renderowanie rysunków CAD jako PNG z niestandardowym rozmiarem i kolorem tła przy użyciu GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Co to jest GroupDocs.Viewer dla Javy?
GroupDocs.Viewer dla Javy to API po stronie serwera, które renderuje ponad 150 formatów plików — w tym pliki CAD — do obrazów, PDF‑ów lub HTML. Działa bez konieczności używania oprogramowania firm trzecich, takiego jak AutoCAD, co czyni go idealnym dla zautomatyzowanych potoków.

## Jak przekonwertować DWG na PNG z niestandardowym rozmiarem i kolorem tła?
Wczytaj plik DWG przy użyciu instancji `Viewer`, skonfiguruj `CadOptions` pod kątem żądanej szerokości i tła, a na koniec wywołaj `viewer.view` z `PngViewOptions`. Ten trzyetapowy przepływ obsługuje operacje I/O, renderowanie i nazewnictwo wyjścia w jednej, pamięcio‑oszczędnej operacji.

Viewer jest główną klasą, która ładuje dokument i wykonuje renderowanie.  
CadOptions konfiguruje ustawienia specyficzne dla CAD, takie jak szerokość obrazu i kolor tła.  
PngViewOptions definiuje format wyjściowy PNG oraz wzorzec nazewnictwa renderowanych stron.

Możesz teraz renderować dowolny rysunek DWG do PNG o dokładnie określonej szerokości oraz wybrać dowolny jednolity (lub przezroczysty) kolor tła, aby dopasować go do swojej marki lub motywu interfejsu użytkownika.

## Dlaczego ustawiać niestandardowy kolor tła?
Ustawienie koloru tła zapewnia, że renderowany PNG płynnie wpasowuje się w otaczające elementy interfejsu, unika niechcianych białych marginesów i może podkreślić szczegóły rysunku, które w przeciwnym razie zginęłyby na domyślnym białym tle. GroupDocs.Viewer obsługuje dowolny `java.awt.Color`, w tym niestandardowe wartości RGB, dając kontrolę na poziomie pojedynczego piksela.

java.awt.Color reprezentuje wartość koloru używaną do renderowania tła.

## Wymagania wstępne
- **Java Development Kit (JDK) 8+** – API jest przeznaczone dla Java 8 i nowszych.  
- **Maven** – do zarządzania zależnościami.  
- **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor, którego preferujesz.  
- **Podstawowa znajomość obsługi plików w Javie** – do odczytu źródłowych plików DWG i zapisu wyjściowych PNG.

## Konfiguracja GroupDocs.Viewer dla Javy
Dodaj repozytorium GroupDocs oraz zależność Viewer do swojego pliku Maven `pom.xml`:

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
Uzyskaj tymczasowy lub pełny klucz licencyjny z portalu GroupDocs i umieść plik `license.lic` w folderze zasobów projektu. Usuwa to ograniczenie 20‑stronicowej wersji próbnej i odblokowuje renderowanie w pełnej rozdzielczości.

### Podstawowa inicjalizacja i konfiguracja
Utwórz instancję `Viewer`, która wskazuje na folder zawierający Twoje pliki DWG:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Funkcja 1: renderowanie rysunków CAD z niestandardowym rozmiarem obrazu i kolorem tła
### Jak zmienić kolor tła CAD
Aby zmienić kolor tła CAD, skonfiguruj obiekt CadOptions przed renderowaniem. Ustaw żądaną szerokość przy pomocy `forRenderingByWidth` i zastosuj nowe tło używając `setBackgroundColor`. Viewer następnie generuje obrazy PNG odzwierciedlające określony kolor, zapewniając spójny styl wizualny we wszystkich plikach wyjściowych.

#### Implementacja krok po kroku

##### Import wymaganych pakietów
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Konfiguracja katalogu wyjściowego i formatu ścieżki pliku
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inicjalizacja viewer z niestandardowymi opcjami renderowania
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
- `PngViewOptions` – definiuje format wyjściowy PNG oraz wzorzec nazewnictwa.  
- `forRenderingByWidth(int width)` – wymusza, aby renderer wygenerował obraz o szerokości odpowiadającej podanej wartości w pikselach; wysokość jest skalowana proporcjonalnie.  
- `setBackgroundColor(Color color)` – nadpisuje domyślne białe tło wybranym kolorem, poprawiając spójność wizualną generowanych zasobów.

#### Porady dotyczące rozwiązywania problemów
- Upewnij się, że katalog wyjściowy istnieje; użyj `Files.createDirectories(outputDir)`, jeśli nie istnieje.  
- Zweryfikuj, czy ścieżka pliku wejściowego jest poprawna i czy aplikacja ma uprawnienia do odczytu.  

## Funkcja 2: ustawianie koloru tła w opcjach renderowania
### Jak ustawić kolor tła PNG
Ustawienie koloru tła PNG polega na utworzeniu instancji Color i przypisaniu jej do CadOptions przed renderowaniem. Zapewnia to, że każdy wygenerowany PNG używa określonego tła, dopasowanego do wytycznych marki lub motywu UI. Możesz używać predefiniowanych stałych lub definiować własne wartości RGB dla precyzyjnej kontroli.

java.awt.Color reprezentuje wartość koloru używaną do renderowania tła.

#### Implementacja krok po kroku

##### Import wymaganych pakietów
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Konfiguracja opcji renderowania z kolorem tła
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
- Dostosuj `forRenderingByWidth(int width)` do różnych wymiarów, np. 800 px dla miniatur internetowych lub 1920 px dla wydruków wysokiej rozdzielczości.  
- Użyj dowolnej predefiniowanej stałej `Color` (np. `Color.LIGHT_GRAY`) lub utwórz własną instancję przy pomocy `new Color(r, g, b)` dla precyzyjnego brandingu.  

## Praktyczne zastosowania
### 1. Dokumentacja inżynierska
Niestandardowe renderowanie zapewnia, że każdy rysunek jest zgodny ze stylem firmy, eliminując ręczną edycję obrazu po eksporcie.

### 2. Wizualizacja architektoniczna
Prezentuj plany z tłem dopasowanym do prezentacji lub portali skierowanych do klientów, poprawiając spójność wizualną.

### 3. Prototypowanie w produkcji
Generuj PNG‑y dla przepływów szybkiego prototypowania, gdzie narzędzia downstream oczekują określonego rozmiaru obrazu i tła.

### Możliwości integracji
Połącz ten potok renderowania z systemem zarządzania dokumentami (np. SharePoint), aby automatycznie generować obrazy podglądu przy każdym przesłaniu pliku DWG.

## Rozważania dotyczące wydajności
### Optymalizacja wydajności
- **Przetwarzanie wsadowe:** Przejdź pętlą przez katalog plików DWG i renderuj każdy kolejno, aby rozłożyć koszty rozgrzewania JVM.  
- **Zarządzanie zasobami:** Dla dużych rysunków (500+ stron) zwiększ pamięć JVM (`-Xmx2g`) lub przetwarzaj pliki w mniejszych partiach, aby uniknąć błędów braku pamięci.

### Wytyczne dotyczące użycia zasobów
Monitoruj użycie CPU i pamięci za pomocą narzędzi takich jak VisualVM; zwalniaj instancje `Viewer` niezwłocznie, używając try‑with‑resources.

### Najlepsze praktyki zarządzania pamięcią w Javie
- Używaj try‑with‑resources (jak pokazano), aby automatycznie zamykać `Viewer`.  
- Unikaj przechowywania dużych obiektów `Path` poza ich natychmiastowym użyciem.  

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|------------|
| Output folder not found | Utwórz katalog wcześniej lub dodaj `Files.createDirectories(outputDirectory);` |
| Blank image | Upewnij się, że `cadOptions.setBackgroundColor` jest wywoływane po `forRenderingByWidth`. |
| Out‑of‑memory errors | Zwiększ opcję JVM `-Xmx` lub przetwarzaj pliki w mniejszych partiach. |

## Najczęściej zadawane pytania
**Q: Czy mogę renderować inne formaty CAD oprócz DWG?**  
A: Tak, GroupDocs.Viewer obsługuje DXF, DWF i kilka dodatkowych formatów CAD.

**Q: Jak użyć niestandardowego koloru RGB zamiast predefiniowanej stałej?**  
A: Utwórz nowy `Color` przy pomocy `new Color(123, 45, 67)` i przekaż go do `setBackgroundColor`.

**Q: Czy można renderować tylko określony układ lub warstwę?**  
A: Możesz określić opcje układu lub warstwy za pomocą `CadOptions` przed wywołaniem `viewer.view`.

**Q: Czy biblioteka obsługuje przezroczyste tła?**  
A: Ustaw kolor tła na `new Color(0,0,0,0)` dla pełnej przezroczystości, jeśli format wyjściowy to obsługuje.

**Q: Jakiej wersji GroupDocs.Viewer wymaga?**  
A: Samouczek używa wersji 25.2, ale nowsze wydania zachowują tę samą powierzchnię API.

---

**Ostatnia aktualizacja:** 2026-08-30  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Powiązane samouczki
- [groupdocs viewer dwg – Jak renderować konkretne rysunki CAD w Javie przy użyciu GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Renderowanie warstw CAD w Javie z GroupDocs.Viewer – Kompletny przewodnik](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Jak przekonwertować PDF na HTML i zoptymalizować jakość obrazu w Javie z GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)