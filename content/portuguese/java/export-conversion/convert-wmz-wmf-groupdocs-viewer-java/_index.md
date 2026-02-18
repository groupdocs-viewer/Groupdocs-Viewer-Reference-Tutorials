---
date: '2026-02-18'
description: Aprenda como converter arquivos WMZ e WMF para PDF, HTML, JPG e PNG usando
  o GroupDocs Viewer para Java. Este guia cobre o GroupDocs Viewer Java e a conversão
  de gráficos vetoriais em Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Como converter WMZ para PDF e outros formatos usando o GroupDocs Viewer para
  Java
type: docs
url: /pt/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Como Converter WMZ para PDF e Outros Formatos Usando GroupDocs Viewer for Java

Converter arquivos WMZ (Web Metafile) e WMF (Windows Metafile) para formatos mais acessíveis—especialmente **convert WMZ to PDF**—pode ser complicado porque esses formatos de gráfico vetorial armazenam instruções de desenho em vez de dados de pixel. Com **GroupDocs Viewer for Java**, você pode renderizar documentos WMZ/WMF para HTML, JPG, PNG, **PDF**, e outros formatos populares em apenas algumas linhas de código.

![Converter Documentos WMZ/WMF com GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

Neste tutorial você aprenderá como configurar a biblioteca, renderizar arquivos WMZ/WMF para a saída desejada e lidar com armadilhas comuns. Ao final, você poderá integrar **groupdocs viewer java** em suas aplicações Java para **java convert vector graphics** rápida e confiavelmente.

## Quick Answers
- **Quais formatos WMZ/WMF podem ser convertidos?** HTML, JPG, PNG e PDF são totalmente suportados.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para avaliação; uma licença comercial remove as limitações de avaliação.  
- **Qual versão do Java é necessária?** Java 8 ou superior é recomendado.  
- **Posso renderizar apenas páginas específicas?** Sim, você pode especificar intervalos de páginas nas opções de visualização.  
- **O uso de memória é uma preocupação para arquivos grandes?** Use try‑with‑resources e renderize apenas as páginas necessárias para manter a memória baixa.

## O que é “convert WMZ to PDF”?
Converter WMZ para PDF significa pegar o arquivo WMZ baseado em vetor e rasterizá‑lo (ou preservar seus dados vetoriais) dentro de um contêiner PDF. PDF é universalmente visualizável, pesquisável e imprimível, tornando‑o ideal para arquivar e compartilhar gráficos WMZ.

## Por que usar GroupDocs Viewer for Java para converter gráficos vetoriais?
- **Alta fidelidade**: A biblioteca preserva a qualidade original do desenho, seja ao gerar PDF ou PNG.  
- **Zero dependências externas**: Não há necessidade de bibliotecas nativas do Windows; tudo funciona em qualquer plataforma com JDK.  
- **API simples**: Uma instância `Viewer` e uma única chamada `view` lidam com toda a conversão.  
- **Escalável**: Funciona igualmente bem para ícones de página única e desenhos técnicos de várias páginas.

## Prerequisites

### Required Libraries
- **GroupDocs.Viewer for Java** – o motor central de renderização.  
- Java Development Kit (JDK) 8+.

### Environment Setup
- IDE como IntelliJ IDEA ou Eclipse.  
- Maven para gerenciamento de dependências (ou Gradle, se preferir).

### Knowledge Prerequisites
- Familiaridade com Java file I/O (`java.nio.file.Path`).  
- Compreensão básica de como visualizadores de documentos renderizam conteúdo.

## Setting Up GroupDocs.Viewer for Java

Adicione o repositório e a dependência ao seu `pom.xml`:

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

> **Dica de licença:** Use um teste gratuito para avaliação, depois aplique uma licença temporária ou comprada para desbloquear a funcionalidade completa.

Depois que a dependência for resolvida, você pode criar uma instância `Viewer` que será reutilizada para cada etapa de conversão.

## Implementation Guide

We'll walk through four conversion scenarios: HTML, JPG, PNG, and PDF. Each example follows the same pattern—define an output path, instantiate `Viewer` with the source WMZ file, configure the appropriate view options, and call `view`.

### Rendering WMZ/WMF to HTML

#### Overview
A saída HTML permite incorporar o gráfico diretamente em páginas web, com todos os recursos (imagens, CSS) contidos em um único arquivo.

**Passo 1: Definir o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Passo 2: Inicializar o Viewer e Renderizar para HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendering WMZ/WMF to JPG

#### Overview
JPG é um formato raster amplamente suportado, perfeito para visualizações rápidas ou anexos de e‑mail.

**Passo 1: Definir o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Passo 2: Inicializar o Viewer e Renderizar para JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF to PNG

#### Overview
PNG suporta transparência, tornando‑o ideal para gráficos que precisam se mesclar com diferentes fundos.

**Passo 1: Definir o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Passo 2: Inicializar o Viewer e Renderizar para PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF to PDF

#### Overview
PDF fornece um documento independente de plataforma, pesquisável, que mantém o layout original.

**Passo 1: Definir o Caminho do Diretório de Saída**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Passo 2: Inicializar o Viewer e Renderizar para PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Common Issues and Solutions

| Problema | Causa | Solução |
|----------|-------|----------|
| **OutOfMemoryError** em arquivos WMZ grandes | Viewer carrega todo o documento na memória | Renderize uma página por vez usando `PageStreamViewOptions` ou aumente o heap da JVM (`-Xmx`). |
| **Fontes ausentes** no PDF | Fonte não incorporada no WMZ de origem | Instale as fontes necessárias na máquina host ou use `FontSettings` para fornecer fontes personalizadas. |
| **Saída PNG em branco** | Caminho de saída incorreto ou permissões de gravação insuficientes | Verifique se `outputDirectory` existe e se a aplicação tem acesso de gravação. |
| **Recursos HTML não carregando** | Uso de `forExternalResources` sem copiar arquivos | Mantenha `forEmbeddedResources` para um arquivo HTML auto‑contido. |

## Frequently Asked Questions

**P: Posso converter WMF para PNG usando o mesmo código?**  
R: Sim. O exemplo PNG funciona tanto para arquivos WMZ quanto WMF; basta substituir `TestFiles.SAMPLE_WMZ` pelo seu arquivo WMF.

**P: É possível converter apenas um subconjunto de páginas?**  
R: Absolutamente. Use `PdfViewOptions` (ou as opções correspondentes para outros formatos) e chame `setPageNumbers(List<Integer>)` antes de renderizar.

**P: Preciso de uma licença separada para cada formato de saída?**  
R: Não. Uma única licença do GroupDocs Viewer cobre todos os formatos suportados, incluindo HTML, JPG, PNG e PDF.

**P: Como “java convert vector graphics” impacta o desempenho?**  
R: A conversão de vetor para raster é intensiva em CPU. Para lotes grandes, considere multithreading e reutilizar uma única instância `Viewer` entre arquivos.

**P: O PDF manterá a qualidade vetorial ou será rasterizado?**  
R: Ao converter WMZ/WMF para PDF, o GroupDocs Viewer preserva as instruções vetoriais quando possível, resultando em um PDF escalável.

## Conclusion

Agora você tem um guia completo e pronto para produção para **convert WMZ to PDF** e outros formatos comuns usando **GroupDocs Viewer for Java**. Seja construindo um serviço web que entrega gráficos em tempo real ou uma ferramenta de arquivamento que armazena documentos como PDFs, os passos acima ajudarão você a chegar lá rapidamente.

---

**Last Updated:** 2026-02-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs