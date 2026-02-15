---
date: '2026-02-15'
description: Lär dig hur du konverterar pst till html och andra format som JPG, PNG,
  PDF med GroupDocs.Viewer för Java. Denna guide täcker alla steg och nödvändiga konfigurationer.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Konvertera PST till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java
type: docs
url: /sv/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Konvertera PST till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java

Letar du efter att **konvertera pst till html** eller andra format som JPG, PNG eller PDF? Med det kraftfulla GroupDocs.Viewer för Java‑biblioteket är denna uppgift enkel och effektiv. I den här handledningen lär du dig hur du renderar Outlook PST/OST‑filer till webbvänlig HTML, bildfiler eller en enda PDF, vilket gör dina e‑postarkiv enkla att dela och arkivera.

![Konvertera PST/OST till HTML, JPG, PNG, PDF med GroupDocs.Viewer för Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Vad du kommer att lära dig**
- Hur du sätter upp GroupDocs.Viewer för Java i ett Maven‑projekt.  
- Steg‑för‑steg‑instruktioner för **java convert pst**‑filer till HTML, JPG, PNG och PDF.  
- Konfigurationstips för optimal prestanda och vanliga fallgropar.

## Snabba svar
- **Vilket bibliotek hanterar PST‑konvertering?** GroupDocs.Viewer för Java.  
- **Kan jag konvertera PST till PDF direkt?** Ja, med `PdfViewOptions`.  
- **Behövs en licens för produktion?** En giltig GroupDocs‑licens krävs.  
- **Vilken Java‑version stöds?** JDK 8 eller högre.  
- **Måste jag extrahera bilagor manuellt?** Nej, visaren renderar dem automatiskt.

## Hur du konverterar pst till html med GroupDocs.Viewer för Java
Nedan hittar du en kort översikt av konverteringsprocessen innan du dyker ner i de detaljerade kodexemplen.

### Varför välja GroupDocs.Viewer?
- **Hög noggrannhet** vid rendering av e‑postkroppar, bilagor och formatering.  
- **Flera utdataformat** (HTML, JPG, PNG, PDF) från ett enda API.  
- **Inga externa beroenden** – allt körs inom din Java‑applikation.

## Förutsättningar

- **GroupDocs.Viewer för Java** – version 25.2 eller senare.  
- **Java Development Kit (JDK)** – 8 eller nyare.  
- Maven för beroendehantering.  
- Grundläggande kunskaper i Java och erfarenhet av Maven.

## Så här sätter du upp GroupDocs.Viewer för Java

Lägg till GroupDocs‑arkivet och beroendet i din `pom.xml`:

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

### Licensanskaffning
- **Gratis provperiod** – utforska alla funktioner utan kostnad.  
- **Tillfällig licens** – förläng utvärderingstiden om så behövs.  
- **Full licens** – krävs för produktionsdistributioner.

### Grundläggande initiering

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Implementeringsguide

Följande avsnitt går igenom hur du renderar PST/OST‑filer till varje stödformat.

### Rendering av PST/OST‑dokument till HTML

#### Steg 1: Skapa utdatamapp

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Steg 2: Konfigurera Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 3: Initiera Viewer och rendera HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering av PST/OST‑dokument till JPG

#### Steg 1: Skapa utdatamapp

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Steg 2: Konfigurera Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 3: Initiera Viewer och rendera JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering av PST/OST‑dokument till PNG

#### Steg 1: Skapa utdatamapp

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Steg 2: Konfigurera Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 3: Initiera Viewer och rendera PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering av PST/OST‑dokument till PDF

#### Steg 1: Skapa utdatamapp

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Steg 2: Konfigurera Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Steg 3: Initiera Viewer och rendera PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Praktiska tillämpningar

- **E‑postarkivering:** Omvandla stora PST‑arkiv till sökbar HTML eller PDF för efterlevnad.  
- **Dokumenthanteringssystem:** Lagra konverterade filer i system som endast accepterar PDF, PNG eller JPG.  
- **Samarbetsplattformar:** Dela konverterade e‑postmeddelanden som bilder i Slack eller Teams.  
- **Juridisk granskning:** Tillhandahåll domstolar PDF‑versioner av e‑postbevis.  
- **Säkerhetskopieringsstrategier:** Behåll lätta PNG‑ eller JPG‑ögonblicksbilder av kritiska meddelanden.

## Prestandaöverväganden

- **Resurshantering:** Återanvänd `Viewer`‑instanser när du bearbetar flera filer för att minska overhead.  
- **Minnesjustering:** Anpassa `loadOptions.setResourceLoadingTimeout` efter serverkapacitet.  
- **Asynkron bearbetning:** Flytta konverteringen till bakgrundstrådar för responsiva UI‑gränssnitt.  

## Vanliga frågor

**Q: Hur **convert pst to pdf** med samma kodbas?**  
A: Använd `PdfViewOptions` som visas i PDF‑renderingsavsnittet; resten av koden förblir identisk.

**Q: Kan GroupDocs.Viewer hantera krypterade PST‑filer?**  
A: Ja, ange lösenordet via `LoadOptions.setPassword("yourPassword")` innan rendering.

**Q: Vad är skillnaden mellan **java convert pst** till PNG respektive JPG?**  
A: PNG bevarar förlustfri kvalitet, idealiskt för skärmdumpar, medan JPG ger mindre filstorlekar för e‑postförhandsvisningar.

**Q: Finns det ett sätt att **how to convert pst** filer i bulk?**  
A: Omslut renderingslogiken i en loop som itererar över en katalog med PST‑filer; återanvänd samma `Viewer`‑konfiguration för varje fil.

## Slutsats

Du har nu en komplett, produktionsklar guide för att **konvertera pst till html**, JPG, PNG och PDF med GroupDocs.Viewer för Java. Genom att följa stegen ovan kan du integrera e‑postkonvertering i vilket Java‑baserat arbetsflöde som helst, förbättra tillgänglighet och uppfylla efterlevnadskrav.

---

**Senast uppdaterad:** 2026-02-15  
**Testad med:** GroupDocs.Viewer för Java 25.2  
**Författare:** GroupDocs  

---