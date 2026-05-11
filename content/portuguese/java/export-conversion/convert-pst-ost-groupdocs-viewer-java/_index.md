---
date: '2026-02-15'
description: Aprenda como converter pst para html e outros formatos como JPG, PNG,
  PDF usando o GroupDocs.Viewer para Java. Este guia cobre todas as etapas e configurações
  necessárias.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Converter PST para HTML, JPG, PNG, PDF usando o GroupDocs.Viewer para Java
type: docs
url: /pt/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Converter PST para HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java

Você está procurando **converter pst para html** ou outros formatos como JPG, PNG ou PDF? Com a poderosa biblioteca GroupDocs.Viewer for Java, essa tarefa é simples e eficiente. Neste tutorial, você aprenderá como renderizar arquivos Outlook PST/OST em HTML amigável para a web, arquivos de imagem ou um único PDF, facilitando o compartilhamento e arquivamento dos seus e‑mails.

![Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**O que você aprenderá**
- Como configurar o GroupDocs.Viewer para Java em um projeto Maven.  
- Instruções passo a passo para **java convert pst** arquivos para HTML, JPG, PNG e PDF.  
- Dicas de configuração para desempenho ideal e armadilhas comuns.

## Respostas Rápidas
- **Qual biblioteca lida com a conversão de PST?** GroupDocs.Viewer for Java.  
- **Posso converter PST para PDF diretamente?** Sim, usando `PdfViewOptions`.  
- **É necessária uma licença para produção?** É necessária uma licença válida da GroupDocs.  
- **Qual versão do Java é suportada?** JDK 8 ou superior.  
- **Preciso extrair anexos manualmente?** Não, o visualizador os renderiza automaticamente.

## Como converter pst para html usando GroupDocs.Viewer para Java
Abaixo você encontrará uma visão geral concisa do processo de conversão antes de mergulhar nos exemplos de código detalhados.

### Por que escolher o GroupDocs.Viewer?
- **Alta fidelidade** na renderização de corpos de e‑mail, anexos e formatação.  
- **Múltiplos formatos de saída** (HTML, JPG, PNG, PDF) a partir de uma única API.  
- **Sem dependências externas** – tudo roda dentro da sua aplicação Java.

## Pré-requisitos

- **GroupDocs.Viewer for Java** – versão 25.2 ou posterior.  
- **Java Development Kit (JDK)** – 8 ou mais recente.  
- Maven para gerenciamento de dependências.  
- Conhecimento básico de Java e familiaridade com Maven.

## Configurando o GroupDocs.Viewer para Java

Adicione o repositório GroupDocs e a dependência ao seu `pom.xml`:

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
- **Licença temporária** – estenda o período de avaliação, se necessário.  
- **Licença completa** – necessária para implantações em produção.

### Inicialização Básica

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

#### Etapa 1: Configurar o diretório de saída

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Etapa 2: Configurar opções de carregamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 3: Inicializar o Viewer e renderizar HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando documentos PST/OST para JPG

#### Etapa 1: Configurar o diretório de saída

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Etapa 2: Configurar opções de carregamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 3: Inicializar o Viewer e renderizar JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando documentos PST/OST para PNG

#### Etapa 1: Configurar o diretório de saída

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Etapa 2: Configurar opções de carregamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 3: Inicializar o Viewer e renderizar PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando documentos PST/OST para PDF

#### Etapa 1: Configurar o diretório de saída

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Etapa 2: Configurar opções de carregamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Etapa 3: Inicializar o Viewer e renderizar PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Aplicações Práticas

- **Arquivamento de e‑mail:** Converta grandes arquivos PST em HTML ou PDF pesquisáveis para conformidade.  
- **Sistemas de Gerenciamento de Documentos:** Armazene arquivos convertidos em sistemas que aceitam apenas PDF, PNG ou JPG.  
- **Plataformas de Colaboração:** Compartilhe e‑mails convertidos como imagens no Slack ou Teams.  
- **Revisão Legal:** Forneça aos tribunais versões em PDF das evidências de e‑mail.  
- **Estratégias de Backup:** Mantenha snapshots leves em PNG ou JPG de mensagens críticas.

## Considerações de Desempenho

- **Gerenciamento de recursos:** Reutilize instâncias de `Viewer` ao processar vários arquivos para reduzir a sobrecarga.  
- **Ajuste de memória:** Ajuste `loadOptions.setResourceLoadingTimeout` com base na capacidade do servidor.  
- **Processamento assíncrono:** Desloque a conversão para threads em segundo plano para interfaces responsivas.

## Perguntas Frequentes

**Q: Como faço para **convert pst to pdf** com a mesma base de código?**  
A: Use `PdfViewOptions` como mostrado na seção de renderização PDF; o restante do código permanece idêntico.

**Q: O GroupDocs.Viewer pode lidar com arquivos PST criptografados?**  
A: Sim, forneça a senha via `LoadOptions.setPassword("yourPassword")` antes da renderização.

**Q: Qual é a diferença entre **java convert pst** para PNG vs JPG?**  
A: PNG preserva qualidade sem perdas, ideal para capturas de tela, enquanto JPG oferece tamanhos de arquivo menores para pré‑visualizações de e‑mail.

**Q: Existe uma maneira de **how to convert pst** arquivos em lote?**  
A: Envolva a lógica de renderização em um loop que itere sobre um diretório de arquivos PST; reutilize a mesma configuração de `Viewer` para cada arquivo.

## Conclusão

Agora você tem um guia completo e pronto para produção para **convert pst to html**, JPG, PNG e PDF usando o GroupDocs.Viewer para Java. Seguindo os passos acima, você pode integrar a conversão de e‑mail em qualquer fluxo de trabalho baseado em Java, melhorar a acessibilidade e atender aos requisitos de conformidade.

---

**Última atualização:** 2026-02-15  
**Testado com:** GroupDocs.Viewer for Java 25.2  
**Autor:** GroupDocs