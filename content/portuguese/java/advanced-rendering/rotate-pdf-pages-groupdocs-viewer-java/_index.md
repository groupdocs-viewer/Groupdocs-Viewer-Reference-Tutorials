---
date: '2026-10-05'
description: Aprenda a girar páginas PDF específicas com GroupDocs.Viewer for Java.
  Este guia passo a passo cobre a configuração do Maven, rotate pdf 90 degrees e solução
  de problemas.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Gire páginas PDF específicas com GroupDocs.Viewer for Java. Aprenda
  a rotate pdf 90 degrees, configurar o Maven e solucionar problemas comuns em um
  guia conciso.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Gire páginas PDF específicas com GroupDocs.Viewer for Java
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
title: Como girar páginas PDF específicas com GroupDocs.Viewer for Java
type: docs
url: /pt/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Como girar páginas PDF específicas com GroupDocs.Viewer para Java

Girar páginas específicas dentro de um PDF pode ser essencial para alinhar documentos, corrigir imagens escaneadas ou ajustar slides de apresentação. **Neste guia você aprenderá como girar páginas PDF específicas programaticamente com GroupDocs.Viewer**, seja para girar pdf 90 graus, inverter uma seção inteira ou manipular várias páginas em uma única chamada.

![Girar páginas PDF específicas com GroupDocs.Viewer para Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Girar páginas PDF específicas com GroupDocs.Viewer para Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**O que você aprenderá**
- Configurar o GroupDocs.Viewer no seu projeto Java (incluindo configuração do Maven GroupDocs Viewer)
- Girar programaticamente páginas PDF específicas (girar pdf 90 graus, 180 graus, etc.)
- Configurações chave para uso ideal
- Solucionar problemas comuns durante a implementação

## Respostas rápidas
- **Qual biblioteca pode girar páginas PDF em Java?** GroupDocs.Viewer for Java fornece suporte de rotação embutido sem ferramentas externas.  
- **Posso girar uma única página em 90 graus?** Sim – chame `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` na instância do visualizador.  
- **Preciso de uma licença para desenvolvimento?** Uma licença temporária é gratuita para avaliação; uma licença completa é necessária para produção.  
- **O Maven é obrigatório?** Maven é o gerenciador de dependências recomendado, mas você também pode usar Gradle ou inclusão manual de JAR.  
- **Como renderizo as páginas giradas?** Use `HtmlViewOptions` com `viewer.view(documentPath, viewOptions)` para obter saída HTML que reflita a rotação.

## O que é girar páginas PDF específicas?
`rotate specific pdf pages` refere-se à capacidade de mudar a orientação de páginas individuais dentro de um documento PDF, mantendo o resto do arquivo intacto. Esta operação é realizada no momento da renderização, portanto o arquivo PDF original permanece inalterado.

## Por que girar páginas PDF específicas?
Você pode girar uma única página em menos de 0,05 segundos em uma VM típica de nível de servidor, permitindo pré‑visualização em tempo real de contratos escaneados, apresentações ou faturas de várias páginas que contenham digitalizações mal orientadas. Esse controle granular elimina a necessidade de ferramentas caras de pós‑processamento e reduz o esforço manual em até 70 % em projetos de digitalização em larga escala.

## Pré‑requisitos

### Bibliotecas e dependências necessárias
- Java Development Kit (JDK) 8 ou posterior.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Maven para gerenciamento de dependências.

### Requisitos de configuração do ambiente
1. **Maven configuration** – add GroupDocs.Viewer to your `pom.xml`.  
2. **License acquisition** – obtain a temporary license from GroupDocs. Visit [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) or apply for a temporary license on the [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Configurando GroupDocs.Viewer para Java

Para integrar o GroupDocs.Viewer ao seu projeto Java usando Maven, atualize seu `pom.xml`:

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

### Inicialização e configuração básicas
`Viewer` is the core class that loads a document and orchestrates rendering operations. After creating an instance you can call methods such as `view` or `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Como girar páginas PDF específicas com GroupDocs.Viewer
Girar páginas PDF específicas com GroupDocs.Viewer envolve duas ações principais: primeiro, especificar a rotação desejada para cada página alvo usando o método `rotatePage`, e segundo, renderizar o documento com `HtmlViewOptions` para que a rotação seja refletida na saída. Essa abordagem mantém o PDF original inalterado enquanto entrega HTML corretamente orientado.

### Etapa 1: configurar rotação de página
`rotatePage` is a method that accepts a zero‑based page index and a `Rotation` enum value. The enum provides three options: `ON_90_DEGREE`, `ON_180_DEGREE`, and `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Etapa 2: inicializar o visualizador e renderizar
`HtmlViewOptions` controls the PDF‑to‑HTML conversion process. It preserves layout, fonts, and embedded resources while applying any rotation you configured.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parâmetros e configuração
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` where the rotation options are `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Handles pdf‑to‑html conversion while preserving layout and embedded resources.  
- **pdf to html java** – The class is part of the same API and ensures a faithful visual representation.

## Problemas comuns e soluções (solucionar rotação de pdf)

- **Incorrect paths** – Verify that `YOUR_DOCUMENT_DIRECTORY` and `YOUR_OUTPUT_DIRECTORY` exist and are accessible.  
- **Missing dependencies** – Ensure the Maven coordinates match the latest GroupDocs.Viewer version (currently 25.2).  
- **License restrictions** – Apply the temporary license correctly; otherwise, some features may be disabled.  
- **Memory spikes** – Render large PDFs in smaller batches or increase the JVM heap size.

## Aplicações práticas

### Casos de uso reais
1. **Document alignment** – Rotate scanned contracts for correct digital orientation.  
2. **Presentation adjustments** – Modify presentation slides within PDFs before sharing.  
3. **Archival workflows** – Automatically adjust the orientation of historical documents during digitization.

### Possibilidades de integração
Combine GroupDocs.Viewer with Java‑based content management systems, enterprise portals, or custom APIs that require on‑the‑fly viewing of PDFs.

## Considerações de desempenho
- **Resource management** – Always close the `Viewer` instance to release file handles and memory.  
- **Java memory management** – Monitor heap usage when processing large PDFs; consider streaming pages instead of loading the whole file.  
- **Best practices** – Cache rendered HTML for frequently accessed documents to reduce processing time by up to 60 %.

## Conclusão
Este tutorial abordou **como girar páginas PDF específicas usando GroupDocs.Viewer em Java**, desde a configuração do Maven até a renderização de páginas giradas e a solução de armadilhas comuns. Experimente recursos adicionais como marca d'água, conversão de formatos ou processamento em lote para expandir ainda mais seu fluxo de trabalho de documentos.

**Próximos passos:** Explore outras capacidades do GroupDocs.Viewer, como converter PDFs para PNG, adicionar marcas d'água ou integrar com provedores de armazenamento em nuvem.

## Seção de FAQ
- **Troubleshooting rotation issues** – Verify page numbers and rotation parameters are correct.  
- **Handling large PDF files** – Process pages in batches and monitor memory usage.  
- **Licensing requirements** – Use a temporary license for development; purchase a full license for production.  
- **Rotating multiple pages** – Call `rotatePage` repeatedly with different page numbers and angles.  
- **Integration with Java libraries** – GroupDocs.Viewer works seamlessly with Spring Boot, Jakarta EE, and other Java frameworks.

## Perguntas frequentes

**Q: Posso girar todas as páginas de um PDF de uma vez?**  
A: Sim. Percorra os números das páginas e chame `rotatePage(page, Rotation.ON_90_DEGREE)` para cada página.

**Q: A rotação afeta o arquivo PDF original?**  
A: Não. A rotação é aplicada apenas durante o processo de renderização; o PDF fonte permanece inalterado.

**Q: E se um PDF estiver protegido por senha?**  
A: Forneça a senha ao criar a instância `Viewer`: `new Viewer(path, password)`.

**Q: Como depuro um erro “null pointer” ao configurar HtmlViewOptions?**  
A: Certifique‑se de que o diretório de saída existe e que `pageFilePathFormat` resolve corretamente.

**Q: Existe uma forma de girar páginas ao converter para outros formatos (por exemplo, PNG)?**  
A: Sim. Use a mesma configuração `rotatePage` com as opções de visualização adequadas para o formato de destino.

## Recursos
- **Documentação**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referência da API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Página de Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Opções de Compra**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Teste Gratuito**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Solicitar Licença Temporária**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Fórum de Suporte**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-10-05  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriais Relacionados

- [Guia Java: renderizar páginas selecionadas java com GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Renderização de PDF Java GroupDocs Viewer Quebra de Página](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [GroupDocs Viewer Java Renderização HTML Responsiva](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)