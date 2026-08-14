---
date: '2026-06-30'
description: Zjistěte, jak efektivně načíst a uložit přílohy dokumentů v Java aplikacích
  pomocí java file output stream a výkonného GroupDocs.Viewer API.
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: Jak načíst a uložit přílohy dokumentů pomocí java file output stream s GroupDocs.Viewer
  pro Java
type: docs
url: /cs/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Jak načíst a uložit přílohy dokumentů pomocí java file output stream s GroupDocs.Viewer pro Java

## Úvod

Hledáte způsob, jak programově extrahovat a spravovat přílohy dokumentů ve svých Java aplikacích pomocí **java file output stream**? S rostoucím významem digitálního spravování dokumentů je klíčové mít nástroje, které tyto procesy efektivně zjednoduší. Představujeme GroupDocs.Viewer pro Java — vaše řešení pro bezproblémové načítání a ukládání příloh dokumentů.

![Načíst a uložit přílohy dokumentů s GroupDocs.Viewer pro Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[Načíst a uložit přílohy dokumentů s GroupDocs.Viewer pro Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

Cílem tohoto tutoriálu je ukázat, jak využít sílu GroupDocs.Viewer k načtení příloh z dokumentů a jejich uložení do vámi zvoleného adresáře. Po absolvování získáte praktické dovednosti v efektivní správě dat dokumentů v prostředí Java a přesně uvidíte **jak uložit soubory příloh** pomocí standardního `java file output stream`.

## Rychlé odpovědi
- **Co dělá java file output stream?** Zapíše bajtové proudy přímo do souborů, což umožňuje ukládat binární data (např. přílohy) na disk.  
- **Které API načítá přílohy?** `Viewer.getAttachments()` vrací seznam metadat příloh.  
- **Mohu specifikovat výstupní složku?** Ano — použijte `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; pro produkční nasazení je vyžadována placená licence.  
- **Je tento přístup thread‑safe?** Vytvořte samostatnou instanci `Viewer` pro každý vlákno nebo synchronizujte přístup.

## Co je java file output stream?
`java.io.FileOutputStream` je základní třída Javy, která zapisuje surové bajty do souboru. Je ideální, když potřebujete uložit binární obsah, jako jsou e‑mailové přílohy, obrázky nebo jakákoli ne‑textová data extrahovaná z dokumentu. Podporuje efektivní zápis malých i velkých souborů a může být kombinována s bufferovanými proudy pro lepší výkon, čímž zajišťuje spolehlivé ukládání binárních dat na disk.

## Proč používat java file output stream s GroupDocs.Viewer?
Použití `java.io.FileOutputStream` spolu s GroupDocs.Viewer umožňuje vývojářům zapisovat bajty příloh přímo na disk bez jakýchkoli mezikroků konverze, čímž zachovává integritu původního souboru. Tento přístup snižuje spotřebu paměti, urychluje zpracování velkých příloh a zjednodušuje kód díky využití standardního Java I/O spolu s výkonnými extrakčními schopnostmi GroupDocs.Viewer.

- **Přímá manipulace s binárními daty** — není potřeba mezikroková konverze; bajty přílohy jsou zapsány přesně tak, jak jsou ve zdrojovém souboru.  
- **Výkon** — streamované zápisy minimalizují paměťovou zátěž, zejména u velkých příloh.  
- **Jednoduchost** — API se čistě integruje se standardním Java I/O, což usnadňuje čitelnost a údržbu kódu.

## Požadavky
- **Požadované knihovny a závislosti**: Přidejte knihovnu GroupDocs.Viewer do svého projektu (viz Maven úryvek níže).  
- **Nastavení prostředí**: Java IDE (IntelliJ IDEA, Eclipse atd.) s nainstalovaným JDK 8+.  
- **Předpoklady znalostí**: Znalost Java I/O, zejména `FileOutputStream`, a základní používání Maven.

## Nastavení GroupDocs.Viewer pro Java
Abyste mohli začít používat API GroupDocs.Viewer ve svém projektu, musíte jej nainstalovat pomocí Maven. Přidejte následující konfiguraci do souboru `pom.xml`:

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

**License Acquisition Steps:**
- **Free Trial**: Začněte s bezplatnou zkušební verzí a prozkoumejte funkce.  
- **Temporary License**: Získejte dočasnou licenci pro prodloužené zkušební období.  
- **Purchase**: Pro produkční použití budete potřebovat zakoupenou licenci.

### Základní inicializace a nastavení
Jakmile je GroupDocs.Viewer přidán jako závislost do vašeho projektu, inicializujte jej ve své Java aplikaci. Zde je postup:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Toto základní nastavení inicializuje GroupDocs.Viewer a připraví jej pro načítání příloh.

## Průvodce implementací

### Načtení příloh pomocí java file output stream
Rozebráme, jak můžete načíst přílohy pomocí GroupDocs.Viewer. Tato funkce umožňuje extrahovat metadata o každé příloze obsažené v dokumentu.

#### Přehled
Načítání příloh zahrnuje volání metody `getAttachments`, která vrací seznam objektů `Attachment` obsahujících podrobnosti jako název souboru a velikost. **Attachment** představuje soubor vložený do zdrojového dokumentu, například obrázek nebo vložený soubor.

#### Kroky implementace
1. **Vytvořte instanci Viewer**  
`Viewer` je hlavní třída GroupDocs.Viewer, která načítá a zpracovává dokumenty pro vykreslování a extrakci. Inicializujte třídu `Viewer` s cestou k vašemu dokumentu:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Načtěte přílohy**  
Použijte metodu `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Porozumění parametrům a metodám**  
- `Viewer`: Přijímá cestu k souboru nebo stream dokumentu.  
- `getAttachments()`: Vrací seznam připojených souborů a poskytuje podrobnosti jako názvy.

### Uložení příloh dokumentu do adresáře
Nyní, když jste se naučili, jak načíst přílohy, uložte je do vámi požadovaného adresáře pomocí API GroupDocs.Viewer a **java file output stream**.

#### Přehled
Tato funkce zahrnuje uložení každého načteného souboru přílohy do určeného výstupního adresáře.

#### Kroky implementace
1. **Definujte výstupní adresář**  
Nastavte cestu `outputDirectory`, kam budou soubory uloženy:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Uložte přílohy**  
Použijte smyčku k uložení každé přílohy pomocí metody `saveAttachment`. **saveAttachment** zapisuje binární obsah `Attachment` do poskytnutého `OutputStream`.

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Vysvětlení parametrů a metod**  
- `saveAttachment`: Přijímá objekt `Attachment` a výstupní stream souboru pro uložení přílohy.  
- `FileOutputStream`: Spravuje zápis dat do souborů pomocí **java file output stream** sémantiky.

## Jak uložit přílohu pomocí java file output stream?
Nahrajte každý objekt `Attachment`, otevřete `FileOutputStream` pro cílový soubor a streamujte bajty přílohy přímo na disk. Tento přístup zapisuje přesný binární payload bez transformace a zaručuje, že uložený soubor odpovídá původní příloze bajt po bajtu. Pro velké přílohy obalte stream do `BufferedOutputStream`, aby se zvýšila propustnost a snížil počet I/O volání. **BufferedOutputStream** bufferuje zápisy, čímž snižuje počet I/O operací a zlepšuje výkon u velkých souborů.

### Časté problémy a řešení
- **Missing Dependencies**: Ujistěte se, že všechny Maven závislosti jsou správně přidány.  
- **File Path Errors**: Dvakrát zkontrolujte cesty jak pro dokumenty, tak pro výstupní adresáře.  
- **Access Permissions**: Ověřte, že vaše aplikace má potřebná oprávnění pro čtení/zápis.  

## Praktické aplikace
Použití GroupDocs.Viewer v Javě může být neocenitelné v různých scénářích:

1. **Email Clients** — Automaticky extrahujte přílohy z archivů e‑mailů pro zpracování nebo archivaci.  
2. **Document Management Systems** — Vylepšete DMS načítáním a organizací připojených souborů.  
3. **Legal Departments** — Bezpečně extrahujte přílohy související s důkazy z právních dokumentů.

Možnosti integrace s CRM, ERP nebo vlastními workflow enginy mohou dále zefektivnit obchodní procesy, což umožní bezproblémové zpracování příloh napříč odděleními.

## Úvahy o výkonu
Aby se optimalizoval výkon při používání GroupDocs.Viewer:

- **Optimalizace manipulace se soubory** — Používejte bufferované proudy pro velké soubory a rychle uvolňujte zdroje.  
- **Správa paměti** — Okamžitě uvolňujte instance `Viewer` (try‑with‑resources), aby nedocházelo k únikům paměti.  
- **Měřitelný přínos** — GroupDocs.Viewer dokáže zpracovat dokumenty až do 500 MB a zvládnout až 200 příloh na soubor při zachování využití paměti pod 150 MB na standardním 8 GB JVM.

Dodržování osvědčených postupů v Javě výrazně zvýší efektivitu vašeho pipeline pro zpracování příloh.

## Závěr
Nyní jste se seznámili, jak načíst a uložit přílohy dokumentů pomocí **java file output stream** s GroupDocs.Viewer pro Java. Toto výkonné API zjednodušuje správu dat dokumentů a je nezbytným nástrojem pro vývojáře pracující s digitálními dokumenty. Pro další objevování možností GroupDocs.Viewer vyzkoušejte jeho další funkce — například vykreslování stránek, konverzi formátů nebo extrakci textu. Pokud máte otázky nebo potřebujete podporu, neváhejte kontaktovat oficiální zdroje.

## Často kladené otázky

**Q: Jak nainstaluji GroupDocs.Viewer do svého Java projektu?**  
A: Přidejte Maven závislost uvedenou výše; URL repozitáře a verze jsou vše, co potřebujete pro rychlý start.

**Q: Dokáže GroupDocs.Viewer zpracovat všechny typy dokumentů?**  
A: Podporuje více než 50 vstupních a výstupních formátů — včetně PDF, DOCX, PPTX, MSG a mnoha typů obrázků — takže většina běžných obchodních souborů je pokryta.

**Q: Co dělat, když narazím na chyby při ukládání příloh?**  
A: Ověřte, že výstupní cesta je správná, adresář existuje a váš proces má oprávnění k zápisu. Také se ujistěte, že používáte `FileOutputStream` správně, jak je ukázáno.

**Q: Je licence vyžadována pro produkční použití?**  
A: Ano, pro produkční nasazení je vyžadována platná licence GroupDocs.Viewer. Pro hodnocení je k dispozici bezplatná zkušební verze.

**Q: Funguje tento přístup s velkými soubory příloh?**  
A: Použití `java file output stream` s bufferovaným I/O efektivně zvládá velké binární soubory; sledujte využití paměti a zvažte streamování po částech pro soubory větší než 200 MB.

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs  

## Související tutoriály

- [Jak načíst přílohy a vytisknout přílohy dokumentu s GroupDocs.Viewer pro Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Vykreslení příloh dokumentu do HTML pomocí GroupDocs.Viewer Java: krok za krokem](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [Vlastní renderovací handler Java — GroupDocs Viewer tutoriál](/viewer/java/custom-rendering/)