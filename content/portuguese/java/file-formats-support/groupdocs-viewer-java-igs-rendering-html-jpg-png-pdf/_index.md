---
date: '2026-02-23'
description: Aprenda a converter IGS para PDF, HTML, JPG e PNG com o GroupDocs.Viewer
  para Java. Siga este guia passo a passo com exemplos de código prontos para executar.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Converter IGS para PDF, HTML, JPG e PNG usando GroupDocs.Viewer Java
type: docs
url: /pt/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

 produce final content.# Converter IGS para PDF, HTML, JPG e PNG usando GroupDocs.Viewer Java

Se você precisa **converter IGS para PDF** (ou para HTML, JPG, PNG) diretamente de uma aplicação Java, você está no lugar certo. Neste tutorial, vamos percorrer tudo o que você precisa — desde a configuração da biblioteca até a renderização do modelo 3‑D no formato que se adequa ao seu projeto. Você verá por que o GroupDocs.Viewer é uma escolha sólida para conversões rápidas e confiáveis e obterá código prático que pode inserir em sua própria solução.

![Converter arquivos IGS para HTML, JPG, PNG e PDF com GroupDocs.Viewer para Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Respostas Rápidas
- **Posso converter IGS para PDF com Java?** Sim, usando `PdfViewOptions` do GroupDocs.Viewer.  
- **Quais formatos de saída são suportados?** HTML, JPG, PNG e PDF.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial; um teste gratuito está disponível para avaliação.  
- **Qual versão do Java é necessária?** JDK 8 ou superior.  
- **O Maven é a única forma de adicionar a biblioteca?** Não, você também pode usar Gradle ou inclusão manual de JAR.  

## O que é “converter IGS para PDF”?
Converter IGS (um formato de arquivo neutro para dados CAD 3‑D) para PDF significa transformar um modelo 3‑D complexo em um documento estático, amplamente visualizável. Isso é útil para compartilhar projetos com partes interessadas que não possuem ferramentas CAD.

## Por que usar o GroupDocs.Viewer para conversões de IGS?
- **Renderização CAD sem código** – a biblioteca cuida do processamento pesado de análise do formato IGS.  
- **Múltiplas opções de saída** – uma chamada de API pode gerar HTML, JPG, PNG ou PDF.  
- **Cross‑platform** – funciona em qualquer SO que suporte Java.  
- **Foco em desempenho** – renderização rápida mesmo para montagens grandes.  

## Pré-requisitos
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** instalado e configurado em sua IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.)  
- Conhecimento básico de Maven (opcional, mas recomendado)  

## Configurando o GroupDocs.Viewer para Java

### Dependência Maven
Adicione o repositório GroupDocs e a dependência Viewer ao seu `pom.xml`:

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
GroupDocs.Viewer offers:
- **Teste gratuito** – uso limitado, ótimo para testes rápidos.  
- **Licença temporária** – conjunto completo de recursos por um curto período de avaliação.  
- **Licença comercial** – uso em produção sem restrições.  

### Inicialização Básica do Viewer
O trecho abaixo mostra como criar uma instância `Viewer` que aponta para seu arquivo IGS:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Renderizando IGS para HTML

### Como converter IGS para HTML?
A saída HTML fornece uma visualização interativa e amigável ao navegador do modelo 3‑D.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Ponto chave:** `HtmlViewOptions.forEmbeddedResources()` incorpora todos os recursos necessários (CSS, imagens) diretamente no arquivo HTML, tornando-o portátil.

## Renderizando IGS para JPG

### Como converter IGS para JPG?
Imagens JPG são perfeitas para miniaturas ou visualizações rápidas.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Você pode ajustar `JpgViewOptions` para controlar a resolução e a qualidade de compressão.

## Renderizando IGS para PNG

### Como converter IGS para PNG?
PNG suporta transparência, o que é útil para sobrepor o modelo em diferentes fundos.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Experimente o `PngViewOptions` para obter o melhor equilíbrio entre tamanho de arquivo e fidelidade visual.

## Renderizando IGS para PDF

### Como converter IGS para PDF?
PDF é o formato padrão para compartilhar documentação de design detalhada. Esta seção aborda diretamente a palavra‑chave principal **converter IGS para PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` permite controlar o layout da página, a qualidade da imagem e se deve incorporar fontes.

## Aplicações Práticas
- **Portais web** – incorpore modelos renderizados em HTML diretamente em configuradores de produtos.  
- **Materiais de marketing** – gere imagens JPG/PNG de alta resolução para brochuras.  
- **Documentação técnica** – inclua renderizações PDF de modelos CAD em manuais do usuário.  
- **Garantia de qualidade** – automatize a geração de miniaturas para grandes lotes de arquivos IGS.  

## Problemas Comuns & Soluções

| Problema | Solução |
|----------|----------|
| **Pasta de saída não encontrada** | Verifique o caminho passado para `Path outputDirectory` e assegure que o processo Java tem permissões de gravação. |
| **Páginas em branco no PDF** | Certifique-se de que o arquivo IGS não está corrompido; tente abri‑lo em um visualizador CAD primeiro. |
| **Renderização lenta para montagens grandes** | Aumente o heap da JVM (`-Xmx2g` ou mais) e considere renderizar página por página usando `viewer.getPageCount()` se necessário. |
| **Fontes ausentes no PDF** | Use `PdfViewOptions` para incorporar as fontes necessárias ou instale as fontes ausentes no servidor. |

## Perguntas Frequentes

**Q: Posso converter múltiplos arquivos IGS em uma única execução?**  
A: Sim. Percorra uma lista de caminhos de arquivos e invoque o método `view` apropriado para cada um.

**Q: É possível personalizar o tamanho da página PDF?**  
A: Absolutamente. `PdfViewOptions` fornece `setPageSize(PageSize.A4)` e métodos semelhantes.

**Q: Preciso de uma licença separada para cada formato de saída?**  
A: Não. Uma única licença do GroupDocs.Viewer cobre todos os formatos suportados.

**Q: Quão grande pode ser um arquivo IGS antes que o desempenho degrade?**  
A: A biblioteca lida com arquivos de até várias centenas de megabytes, mas pode ser necessário alocar mais memória JVM para modelos muito grandes.

**Q: Posso renderizar apenas uma visualização ou orientação específica?**  
A: O GroupDocs.Viewer renderiza a visualização padrão. Para orientações personalizadas, pré‑procese o arquivo IGS com uma ferramenta CAD antes da conversão.

---

**Última atualização:** 2026-02-23  
**Testado com:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs