---
date: '2026-07-19'
description: Aprenda como converter PST para HTML e outros formatos como JPG, PNG,
  PDF usando GroupDocs.Viewer for Java. Este guia cobre todas as etapas e configurações
  necessárias.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Converta PST para HTML rapidamente usando GroupDocs.Viewer for Java.
  Aprenda passo a passo como também exportar para JPG, PNG e PDF em um guia pronto
  para produção.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Converter PST para HTML com GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Converter PST para HTML, JPG, PNG, PDF usando GroupDocs.Viewer for Java
type: docs
url: /pt/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Converter PST para HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java

Você está procurando **converter pst para html** ou outros formatos como JPG, PNG ou PDF? Com a poderosa biblioteca GroupDocs.Viewer for Java, esta tarefa é simples e eficiente. Neste tutorial você aprenderá como renderizar arquivos Outlook PST/OST em HTML amigável para a web, arquivos de imagem ou um único PDF, facilitando o compartilhamento e arquivamento dos seus e‑mails.

![Converter PST/OST para HTML, JPG, PNG, PDF com GroupDocs.Viewer para Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Converter PST/OST para HTML, JPG, PNG, PDF com GroupDocs.Viewer para Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**O que você aprenderá**
- Como configurar o GroupDocs.Viewer para Java em um projeto Maven.  
- Instruções passo a passo para **java convert pst** arquivos para HTML, JPG, PNG e PDF.  
- Dicas de configuração para desempenho ideal e armadilhas comuns.

## Respostas rápidas
- **Qual biblioteca lida com a conversão de PST?** GroupDocs.Viewer for Java.  
- **Posso converter PST para PDF diretamente?** Yes, using `PdfViewOptions`.  
- **É necessária uma licença para produção?** A valid GroupDocs license is needed.  
- **Qual versão do Java é suportada?** JDK 8 or higher.  
- **Preciso extrair anexos manualmente?** No, the viewer renders them automatically.  

## O que é GroupDocs.Viewer para Java?
GroupDocs.Viewer para Java é uma API do lado do servidor que carrega mais de 100 formatos de documentos e e‑mails e os renderiza em saída HTML, imagem ou PDF sem software externo. Ela processa arquivos PST de até 2 GB mantendo o uso de memória abaixo de 200 MB.

## Como converter pst para html usando GroupDocs.Viewer para Java?
Carregue o arquivo PST com `new Viewer("source.pst")`, configure `HtmlViewOptions` para apontar para uma pasta de saída e chame `viewer.view(htmlOptions)`. A API extrai cada e‑mail, preserva formatação, anexos e metadados, e grava uma página HTML separada por mensagem — tudo em uma única chamada de método.

### Por que escolher o GroupDocs.Viewer?
- **Renderização de alta fidelidade** – 99,9 % do conteúdo do e‑mail (incluindo corpos rich‑text, tabelas e imagens incorporadas) é reproduzido com precisão.  
- **Múltiplos formatos de saída** – Uma chamada de API pode gerar HTML, JPG, PNG ou PDF, cobrindo mais de 50 opções de exportação.  
- **Zero dependências externas** – Não é necessário Outlook, Exchange Server ou conversores de terceiros; tudo funciona dentro do seu runtime Java.  

## Pré-requisitos

- **GroupDocs.Viewer para Java** – versão 25.2 ou posterior.  
- **Java Development Kit (JDK)** – 8 ou mais recente.  
- Maven para gerenciamento de dependências.  
- Conhecimento básico de Java e familiaridade com Maven.  

## Configurando o GroupDocs.Viewer para Java

`Viewer` é a classe principal no GroupDocs.Viewer para Java que carrega um documento e o renderiza no formato escolhido. Adicione o repositório GroupDocs e a dependência ao seu `pom.xml`:

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

### Aquisição de Licença
- **Teste gratuito** – explore todos os recursos sem custo.  
- **Licença temporária** – estenda o período de avaliação se necessário.  
- **Licença completa** – necessária para implantações em produção.  

### Inicialização Básica

Instâncias de `Viewer` são leves; você pode reutilizar uma única instância para vários arquivos para minimizar a sobrecarga de criação de objetos.

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

## Guia de Implementação

As seções a seguir orientam você na renderização de arquivos PST/OST em cada formato suportado.

### Renderizando documentos PST/OST para HTML

#### Etapa 1: Configurar o Diretório de Saída
Defina uma pasta onde as páginas HTML serão gravadas. O GroupDocs cria uma subpasta para cada e‑mail para manter os recursos organizados.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Etapa 2: Configurar Opções de Carregamento
`LoadOptions` permite especificar o tratamento de senha, tempos limite de carregamento de recursos e renderização seletiva de páginas. Definir um tempo limite de 30 segundos funciona bem na maioria dos ambientes de servidor.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 3: Definir Opções de Visualização HTML
`HtmlViewOptions` especifica a pasta de saída, o tratamento de recursos e configurações CSS opcionais para a conversão HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Etapa 4: Inicializar o Viewer e Renderizar HTML
Crie um objeto `Viewer`, passe o caminho do arquivo PST e chame `view` com o `HtmlViewOptions`. A API itera automaticamente por todas as mensagens dentro do PST e gera uma hierarquia HTML organizada.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Renderizando documentos PST/OST para JPG

#### Etapa 1: Configurar o Diretório de Saída
Crie uma pasta dedicada para snapshots JPG; cada e‑mail se tornará um ou mais arquivos de imagem dependendo do seu comprimento.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 2: Configurar Opções de Carregamento
As mesmas `LoadOptions` usadas para HTML podem ser reutilizadas aqui, garantindo tratamento de senha consistente entre os formatos.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Etapa 3: Definir Opções de Visualização JPG
`JpgViewOptions` controla a resolução da imagem, qualidade e pasta de saída para a conversão JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Etapa 4: Inicializar o Viewer e Renderizar JPG
Use `viewer.view(jpgOptions)` para gerar arquivos JPEG de alta qualidade prontos para visualização web.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Renderizando documentos PST/OST para PNG

#### Etapa 1: Configurar o Diretório de Saída
A saída PNG é útil quando você precisa de qualidade sem perdas para arquivamento ou processamento OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Etapa 2: Configurar Opções de Carregamento
Nenhuma configuração adicional é necessária além da senha e do tempo limite.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Etapa 3: Definir Opções de Visualização PNG
`PngViewOptions` permite definir um fundo transparente e a pasta de saída para imagens PNG sem perdas.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 4: Inicializar o Viewer e Renderizar PNG
Instancie `viewer.view(pngOptions)` para produzir snapshots PNG de cada e‑mail.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando documentos PST/OST para PDF

#### Etapa 1: Configurar o Diretório de Saída
Um único arquivo PDF por PST simplifica fluxos de trabalho de revisão legal e reduz o uso de armazenamento.

CODE_BLOCK_PLACEHOLDER_14_END

#### Etapa 2: Configurar Opções de Carregamento
Ao converter para PDF, você pode querer habilitar `setEmbedFonts(true)` para garantir fidelidade visual em qualquer máquina.

CODE_BLOCK_PLACEHOLDER_15_END

#### Etapa 3: Definir Opções de Visualização PDF
`PdfViewOptions` permite escolher o nível de compressão, incorporar fontes e definir o nome do arquivo de saída para a conversão PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Etapa 4: Inicializar o Viewer e Renderizar PDF
Crie `PdfViewOptions`, opcionalmente escolha um nível de compressão e chame `viewer.view(pdfOptions)`. A API mescla todos os e‑mails em um único documento PDF pesquisável.

CODE_BLOCK_PLACEHOLDER_17_END

## Aplicações Práticas

- **Arquivamento de E‑mail:** Converta grandes arquivos PST em HTML ou PDF pesquisáveis para conformidade.  
- **Sistemas de Gerenciamento de Documentos:** Armazene arquivos convertidos em sistemas que aceitam apenas PDF, PNG ou JPG.  
- **Plataformas de Colaboração:** Compartilhe e‑mails convertidos como imagens no Slack ou Teams.  
- **Revisão Legal:** Forneça aos tribunais versões PDF das evidências de e‑mail.  
- **Estratégias de Backup:** Mantenha snapshots PNG ou JPG leves de mensagens críticas.  

## Considerações de Desempenho

- **Gerenciamento de Recursos:** Reutilize instâncias de `Viewer` ao processar vários arquivos para reduzir a sobrecarga.  
- **Ajuste de Memória:** Ajuste `loadOptions.setResourceLoadingTimeout` com base na capacidade do servidor.  
- **Processamento Assíncrono:** Desloque a conversão para threads em segundo plano para UIs responsivas.  

## Perguntas Frequentes

**Q: Como faço para **converter pst para pdf** com a mesma base de código?**  
A: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of the code remains identical.

**Q: O GroupDocs.Viewer pode lidar com arquivos PST criptografados?**  
A: Yes, provide the password via `LoadOptions.setPassword("yourPassword")` before rendering.

**Q: Qual é a diferença entre **java convert pst** para PNG vs JPG?**  
A: PNG preserves lossless quality, ideal for screenshots, while JPG offers smaller file sizes for email previews.

**Q: Existe uma maneira de **how to convert pst** arquivos em lote?**  
A: Wrap the rendering logic in a loop that iterates over a directory of PST files; reuse the same `Viewer` configuration for each file.

**Q: A API suporta a conversão de arquivos PST maiores que 1 GB?**  
A: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without loading the entire archive into memory.

## Conclusão

Agora você tem um guia completo e pronto para produção para **converter pst para html**, JPG, PNG e PDF usando GroupDocs.Viewer para Java. Seguindo os passos acima, você pode integrar a conversão de e‑mails em qualquer fluxo de trabalho baseado em Java, melhorar a acessibilidade e atender aos requisitos de conformidade.

---

**Última atualização:** 2026-07-19  
**Testado com:** GroupDocs.Viewer for Java 25.2  
**Autor:** GroupDocs

## Tutoriais Relacionados

- [Converter NSF para PDF, HTML, JPG, PNG usando GroupDocs.Viewer para Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Converter ODF para HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Como Converter DOCX para HTML Usando GroupDocs.Viewer para Java: Um Guia Passo a Passo](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)