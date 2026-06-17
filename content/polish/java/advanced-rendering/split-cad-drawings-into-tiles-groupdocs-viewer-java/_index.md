---
date: '2026-04-01'
description: Dowiedz się, jak podzielić rysunki CAD na kafelki przy użyciu GroupDocs
  Viewer for Java, zwiększając wydajność renderowania i upraszczając obsługę dużych
  plików.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Jak podzielić rysunki CAD na kafelki przy użyciu GroupDocs Viewer
type: docs
url: /pl/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Jak podzielić rysunki CAD na kafelki przy użyciu GroupDocs Viewer

Jeśli zastanawiasz się **jak podzielić CAD** na mniejsze, łatwiejsze do zarządzania części, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez dokładne kroki potrzebne do podzielenia dużych rysunków CAD na kafelki przy użyciu **GroupDocs Viewer for Java**. Po zakończeniu będziesz mieć gotowe rozwiązanie, które przyspiesza renderowanie, zmniejsza zużycie pamięci i ułatwia wyświetlanie rysunków w aplikacjach internetowych lub mobilnych.

![Rysunki CAD podzielone przy użyciu GroupDocs.Viewer dla Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Szybkie odpowiedzi
- **Co osiąga „dzielenie CAD”?** Rozdziela ogromny rysunek na mniejsze obrazy (kafelki), które ładują się szybciej i zużywają mniej pamięci.  
- **Jaki format jest używany dla kafelków?** Domyślnie generowane są pliki PNG, ale inne formaty są obsługiwane poprzez opcje Viewer.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w środowisku deweloperskim; płatna licencja jest wymagana w produkcji.  
- **Czy mogę zmienić rozmiar kafelka?** Tak – dostosuj obliczenia `tileWidth` i `tileHeight` do swoich potrzeb.  
- **Czy to podejście jest wątkowo‑bezpieczne?** Renderowanie każdego kafelka w osobnej instancji `Viewer` przy użyciu try‑with‑resources jest bezpieczne przy równoczesnym wykonywaniu.

## Co to jest „dzielenie CAD”?
Dzielenie CAD odnosi się do podziału pojedynczego, często ogromnego rysunku CAD na wiele prostokątnych sekcji (kafelków). Każdy kafelek jest renderowany niezależnie, co pozwala ładować tylko te części, które faktycznie potrzebuje użytkownik — idealne rozwiązanie dla map internetowych, portali dokumentów i przeglądarek mobilnych.

## Dlaczego używać GroupDocs Viewer dla Java?
GroupDocs Viewer zapewnia natychmiastowe wsparcie dla ponad 100 formatów plików, w tym DWG, DXF i DWF. Jego API kafelków pozwala określić dokładne współrzędne, dzięki czemu możesz renderować dokładnie interesujący Cię obszar bez konieczności przetwarzania całego pliku najpierw. To oszczędza cykle CPU, zmniejsza zużycie pasma i zapewnia płynniejsze wrażenia użytkownika.

## Wymagania wstępne
- **Biblioteki**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Dowolny nowoczesny Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse lub inne IDE kompatybilne z Javą.  
- **Narzędzie budowania**: Maven (inne narzędzia budowania działają, o ile dodano zależność).  

## Konfiguracja GroupDocs.Viewer dla Java
Add the GroupDocs repository and dependency to your `pom.xml`:

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
GroupDocs.Viewer offers a free trial license for evaluation:

- **Bezpłatna wersja próbna**: Odwiedź [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/), aby pobrać bibliotekę.  
- **Licencja tymczasowa**: Złóż wniosek na [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Pełna licencja**: Kup licencję produkcyjną na [Purchase Page](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja
Create a simple `Viewer` instance to verify that the library loads correctly:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Przewodnik krok po kroku: podział rysunków CAD na kafelki

### Krok 1: Zdefiniuj katalog wyjściowy
We’ll store each tile as a separate PNG file. Using a utility method keeps the path logic clean and reusable.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Krok 2: Skonfiguruj opcje widoku
Set the rendering format to PNG and tell the viewer not to preload every page (which saves memory).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Krok 3: Oblicz wymiary kafelków
First we obtain the drawing’s original width and height, then split it into four equal quadrants.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Krok 4: Renderuj i zapisz kafelki
Add the calculated tiles to the rendering options and let the `Viewer` generate the PNG files.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Wskazówki rozwiązywania problemów
- **Ścieżka kompilacji** – Upewnij się, że pliki JAR GroupDocs znajdują się na classpath.  
- **Uprawnienia** – Folder wyjściowy musi być zapisywalny przez proces Java.  
- **Wyjątki** – Jeśli pojawi się `ViewerException`, sprawdź ponownie, czy plik DWG nie jest uszkodzony i czy zastosowano prawidłową licencję.

## Typowe przypadki użycia podziału kafelków CAD
1. **Mapowanie internetowe** – Ładuj tylko widoczną część planu piętra, gdy użytkownik przesuwa lub przybliża.  
2. **Zarządzanie dokumentami** – Przechowuj każdy kafelek osobno, aby szybciej generować podglądy.  
3. **Przeglądanie mobilne** – Zmniejsz zużycie pasma, pobierając jedynie kafelki potrzebne dla aktualnego ekranu.

## Uwagi dotyczące wydajności
- **Rozmiar kafelka** – Większe kafelki oznaczają mniej plików, ale wolniejsze renderowanie; znajdź kompromis w zależności od potrzeb interfejsu.  
- **Monitorowanie pamięci** – Używaj narzędzi profilujących Javy (np. VisualVM), aby obserwować zużycie sterty przy przetwarzaniu bardzo dużych rysunków.  
- **Czyszczenie zasobów** – Wzorzec try‑with‑resources przedstawiony powyżej automatycznie zwalnia zasoby natywne.

## Najczęściej zadawane pytania

**P: Czy mogę podzielić inne typy plików (PDF, obrazy) na kafelki przy użyciu tego samego podejścia?**  
O: Tak. GroupDocs Viewer obsługuje wiele formatów; wystarczy użyć odpowiedniej klasy opcji (np. `PdfViewOptions`).

**P: Jak zmienić jakość wyjściowego obrazu?**  
O: Dostosuj `viewOptions.setResolution(int dpi)` lub ustaw parametry kompresji w obiekcie `PngOptions`.

**P: Moja aplikacja wyczerpuje pamięć przy bardzo dużych plikach DWG — co mogę zrobić?**  
O: Zmniejsz wymiary kafelków, zwiększ przydział pamięci JVM (`-Xmx`) lub renderuj kafelki kolejno w osobnych instancjach `Viewer`.

**P: Czy można renderować kafelki asynchronicznie?**  
O: Oczywiście. Owiń każde wywołanie renderowania kafelka w `CompletableFuture` lub użyj usługi executor, aby równolegle przetwarzać zadania.

**P: Czy potrzebuję osobnej licencji na każdy kafelek?**  
O: Nie. Jedna ważna licencja GroupDocs Viewer obejmuje wszystkie operacje renderowania w Twojej aplikacji.

## Zasoby
- [Dokumentacja](https://docs.groupdocs.com/viewer/java/)
- [Referencja API](https://reference.groupdocs.com/viewer/java/)
- [Pobierz GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Kup licencję](https://purchase.groupdocs.com/buy)
- [Bezpłatna wersja próbna](https://releases.groupdocs.com/viewer/java/)
- [Licencja tymczasowa](https://purchase.groupdocs.com/temporary-license/)
- [Forum wsparcia](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-04-01  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs