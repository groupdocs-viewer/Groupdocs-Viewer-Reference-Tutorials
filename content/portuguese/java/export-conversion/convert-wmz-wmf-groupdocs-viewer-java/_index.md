---
date: '2026-07-19'
description: Aprenda como converter WMZ para PDF, HTML, JPG e PNG com GroupDocs Viewer
  for Java. Guia passo a passo para java convert vector graphics.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Converter WMZ para PDF, HTML, JPG e PNG usando GroupDocs Viewer for
  Java. Este tutorial mostra passo a passo java convert vector graphics com alta fidelidade.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Converter WMZ para PDF com GroupDocs Viewer for Java – Guia rápido
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Converter WMZ para PDF e Outros Formatos Usando GroupDocs Viewer for Java
type: docs
url: /pt/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Converter WMZ para PDF e Outros Formatos Usando GroupDocs Viewer para Java

Converter arquivos WMZ (Web Metafile) e WMF (Windows Metafile) para formatos mais acessíveis—especialmente **convert WMZ to PDF**—pode ser complicado porque esses formatos de gráfico vetorial armazenam instruções de desenho em vez de dados de pixel. Com **GroupDocs Viewer for Java**, você pode renderizar documentos WMZ/WMF para HTML, JPG, PNG, **PDF**, e outros formatos populares em apenas algumas linhas de código, tudo enquanto mantém a fidelidade visual original.

![Converter Documentos WMZ/WMF com GroupDocs.Viewer para Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Converter Documentos WMZ/WMF com GroupDocs.Viewer para Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Respostas Rápidas
- **Quais formatos WMZ/WMF podem ser convertidos?** HTML, JPG, PNG e PDF são totalmente suportados.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença comercial remove os limites de avaliação.  
- **Qual versão do Java é necessária?** Java 8 ou superior é recomendada.  
- **Posso renderizar apenas páginas específicas?** Sim, você pode especificar intervalos de páginas nas opções de visualização.  
- **O uso de memória é uma preocupação para arquivos grandes?** Use try‑with‑resources e renderize apenas as páginas necessárias para manter a memória baixa.

## O que é “convert WMZ to PDF”?
**Convert WMZ to PDF** significa pegar um arquivo vetorial WMZ e incorporar suas instruções de desenho dentro de um contêiner PDF, produzindo um documento visualizável universalmente, pesquisável e imprimível. A conversão preserva a qualidade das linhas e formas, de modo que o PDF resultante parece idêntico ao gráfico original em qualquer dispositivo.

## Por que usar GroupDocs Viewer para Java para converter gráficos vetoriais?
GroupDocs Viewer para Java lida com a renderização de WMZ e WMF com **high fidelity**, preservando detalhes vetoriais seja qual for o formato de saída, como PDF, PNG ou HTML. A biblioteca funciona em qualquer plataforma com JDK, não requer componentes nativos do Windows e fornece uma API de chamada única que escala de arquivos de ícone único a desenhos técnicos de várias páginas. Em testes de benchmark, processa **arquivos WMZ de mais de 200 páginas em menos de 12 segundos** em um servidor padrão de 4 núcleos.

## Pré-requisitos

- **GroupDocs.Viewer for Java** – motor central de renderização.  
- Java Development Kit (JDK) 8 ou mais recente.  
- Uma IDE como IntelliJ IDEA ou Eclipse (opcional, mas recomendada).  
- Maven (ou Gradle) para gerenciamento de dependências.  

Familiaridade com Java NIO (`java.nio.file.Path`) e I/O básico de arquivos ajudará a seguir os exemplos sem problemas.

## Configurando GroupDocs.Viewer para Java

A classe `Viewer` é o ponto de entrada para todas as operações de renderização. Ela representa um mecanismo thread‑safe que pode ser reutilizado em várias conversões.

Adicione o repositório e a dependência ao seu `pom.xml` (ou ao equivalente Gradle). Após o Maven resolver o artefato, você pode criar uma instância `Viewer` que será reutilizada para cada etapa de conversão.

> **Dica de licença:** Use um teste gratuito para avaliação, depois aplique uma licença temporária ou comprada para desbloquear a funcionalidade completa.

## Guia de Implementação

A seguir, percorremos quatro cenários de conversão—HTML, JPG, PNG e PDF. Cada cenário segue o mesmo padrão de três etapas:

1. **Defina o diretório de saída** onde os arquivos renderizados serão salvos.  
2. **Crie uma instância `Viewer`** apontando para o arquivo fonte WMZ/WMF.  
3. **Configure as opções de visualização específicas do formato** e invoque o método `view`.

O método `view` realiza a renderização com base nas opções fornecidas.

### Renderizando WMZ/WMF para HTML

#### Visão geral
A saída HTML permite incorporar o gráfico diretamente em páginas web, com todos os recursos (imagens, CSS) contidos em um único arquivo.

**Etapa 1: Defina o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Etapa 2: Inicialize o Viewer e Renderize para HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Renderizando WMZ/WMF para JPG

#### Visão geral
JPG é um formato raster amplamente suportado, perfeito para pré-visualizações rápidas ou anexos de e‑mail.

**Etapa 1: Defina o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Etapa 2: Inicialize o Viewer e Renderize para JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando WMZ/WMF para PNG

#### Visão geral
PNG suporta transparência, tornando-o ideal para gráficos que precisam se mesclar com diferentes fundos.

**Etapa 1: Defina o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Etapa 2: Inicialize o Viewer e Renderize para PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando WMZ/WMF para PDF

#### Visão geral
PDF fornece um documento independente de plataforma, pesquisável, que mantém o layout original.

**Etapa 1: Defina o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Etapa 2: Inicialize o Viewer e Renderize para PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problemas Comuns e Soluções

`PageStreamViewOptions` permite renderizar páginas específicas como streams.  
`PdfViewOptions` configura as definições de saída PDF, como intervalo de páginas e DPI.  
`FontSettings` permite fornecer fontes personalizadas quando o documento fonte referencia fontes ausentes.

| Problema | Causa | Solução |
|----------|-------|----------|
| **OutOfMemoryError** em arquivos WMZ grandes | Viewer carrega todo o documento na memória | Renderize uma página por vez usando `PageStreamViewOptions` ou aumente o heap da JVM (`-Xmx`). |
| **Missing fonts** no PDF | Fonte não incorporada no WMZ fonte | Instale as fontes necessárias na máquina host ou use `FontSettings` para fornecer fontes personalizadas. |
| **Blank PNG output** | Caminho de saída incorreto ou permissões de gravação insuficientes | Verifique se `outputDirectory` existe e se a aplicação tem permissão de escrita. |
| **HTML resources not loading** | Usando `forExternalResources` sem copiar arquivos | Use `forEmbeddedResources` para um arquivo HTML autocontido. |

## Perguntas Frequentes

**Q: Posso converter WMF para PNG usando o mesmo código?**  
A: Sim. O exemplo PNG funciona tanto para arquivos WMZ quanto WMF; basta substituir `TestFiles.SAMPLE_WMZ` pelo seu fonte WMF.

**Q: É possível converter apenas um subconjunto de páginas?**  
A: Absolutamente. Use `PdfViewOptions` (ou as opções correspondentes para outros formatos) e chame `setPageNumbers(List<Integer>)` antes da renderização.

**Q: Preciso de uma licença separada para cada formato de saída?**  
A: Não. Uma única licença do GroupDocs Viewer cobre todos os formatos suportados, incluindo HTML, JPG, PNG e PDF.

**Q: Como “java convert vector graphics” impacta o desempenho?**  
A: A conversão de vetor para raster é intensiva em CPU. Para lotes grandes, considere multithreading e reutilize uma única instância `Viewer` entre arquivos.

**Q: O PDF manterá a qualidade vetorial ou será rasterizado?**  
A: Ao converter WMZ/WMF para PDF, o GroupDocs Viewer preserva as instruções vetoriais quando possível, resultando em um PDF escalável.

## Conclusão

Agora você tem um guia completo e pronto para produção para **convert WMZ to PDF** e outros formatos comuns usando **GroupDocs Viewer para Java**. Seja construindo um serviço web que entrega gráficos em tempo real ou uma ferramenta de arquivamento que armazena documentos como PDFs, os passos acima o ajudarão a chegar lá de forma rápida e confiável. Explore a API mais a fundo para personalizar intervalos de páginas, configurações de DPI ou marca d'água conforme as necessidades do seu projeto.

---

**Última atualização:** 2026-07-19  
**Testado com:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs

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

## Tutoriais Relacionados

- [Como Converter OBJ para HTML, JPG, PNG e PDF em Java Usando GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Converter IGS para PDF, HTML, JPG & PNG usando GroupDocs.Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Converter Documentos para PDF – Guia Completo](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)