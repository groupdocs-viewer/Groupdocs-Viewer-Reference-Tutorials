---
date: '2026-09-30'
description: Aprenda como girar a página 90 graus em Java usando o GroupDocs Viewer,
  incluindo configuração, código e dicas de desempenho.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Gire a página 90 graus em Java usando o GroupDocs Viewer. Guia passo
  a passo, dicas de desempenho e casos de uso reais para desenvolvedores.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Gire a página 90 graus com o GroupDocs Viewer para Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Gire a página 90 graus com o GroupDocs Viewer para Java
type: docs
url: /pt/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Rotacionar página 90 graus com GroupDocs Viewer para Java

Se você precisar **rotacionar página 90 graus** em um documento—seja ele PDF, arquivo Word ou planilha—fazer isso programaticamente em Java economiza tempo, elimina erros manuais e permite incorporar a operação em pipelines automatizados. Neste guia avançado você aprenderá como rotacionar a primeira página de qualquer documento suportado usando **GroupDocs Viewer para Java**, por que essa capacidade é importante em projetos reais e como manter o processo leve e eficiente em memória.

![Rotacionar a primeira página de um documento com GroupDocs.Viewer para Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Respostas rápidas
- **O que significa “rotate page 90 degrees”?** Ele gira a página selecionada no sentido horário em um quarto de volta.  
- **Qual biblioteca lida com a rotação?** GroupDocs Viewer para Java fornece o método `rotatePage`.  
- **Posso rotacionar páginas PDF com Java?** Sim—use a mesma chamada `rotatePage`; funciona para PDF, DOCX, XLSX e mais.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença paga é necessária para produção.  
- **A operação consome muita memória?** Não, quando você fecha a instância `Viewer` prontamente; veja as dicas de desempenho abaixo.

## O que é “rotate page 90 degrees”?
Rotacionar uma página 90 graus reorienta a página de retrato para paisagem (ou vice‑versa) sem alterar o conteúdo subjacente. Isso é útil para apresentações, impressão de gráficos apenas em paisagem ou correção de documentos escaneados que foram capturados de lado. A rotação é aplicada no momento da renderização, deixando o arquivo original inalterado.

## Por que rotacionar páginas programaticamente com GroupDocs Viewer para Java?
GroupDocs Viewer suporta **mais de 50 formatos de entrada e saída**—incluindo PDF, DOCX, PPTX, XLSX e muitos tipos de imagem—para que você possa renderizar qualquer documento sem conversores externos. A API é fluente, thread‑safe e roda em qualquer runtime Java 8+, tornando‑a uma escolha confiável para automação de nível empresarial que deve lidar com dezenas de tipos de arquivo de forma consistente.

## Pré-requisitos

- GroupDocs Viewer for Java (versão mais recente)
- JDK 8 ou superior
- Maven (ou Gradle) para gerenciamento de dependências
- Uma IDE como IntelliJ IDEA ou Eclipse
- Familiaridade básica com Java I/O

## Configurando GroupDocs.Viewer para Java

Adicione o repositório GroupDocs e a dependência ao seu `pom.xml`. Este trecho permanece inalterado em relação ao tutorial original:

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

### Aquisição de licença
- **Teste gratuito** – download do site da GroupDocs.  
- **Licença temporária** – solicite se precisar de um período de avaliação estendido.  
- **Licença completa** – compre para implantações de produção.

### Inicialização básica do Viewer
A classe `Viewer` é o ponto de entrada que carrega um documento e expõe métodos de renderização e transformação. Mantenha o código exatamente como mostrado:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Como rotacionar página PDF Java com GroupDocs Viewer
Carregue o arquivo alvo com `Viewer`, especifique o número da página e chame `rotatePage`. O método funciona para PDF, DOCX, PPTX, XLSX e qualquer outro formato suportado pela biblioteca. Após a rotação, você pode renderizar o documento para um novo PDF ou transmiti‑lo diretamente ao cliente, garantindo que o arquivo original permaneça intacto.

## Implementação passo a passo: rotacionar a primeira página 90 graus

### 1. Importe os pacotes necessários
`PdfViewOptions` indica ao Viewer que a saída será um arquivo PDF, enquanto o enum `Rotation` define o ângulo. Ambas as classes pertencem ao pacote `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Defina os locais de saída e crie o Viewer
Substitua os caminhos de placeholder pelos seus diretórios reais. O construtor `Viewer` aceita um objeto `File` que aponta para o documento fonte.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configure as opções de visualização PDF e aplique a rotação
O método `rotatePage(int, Rotation)` recebe um índice de página **baseado em 1** e um valor do enum `Rotation`. Neste exemplo usamos `Rotation.ON_90_DEGREE` para girar a primeira página no sentido horário.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderize o documento
Chamando `view` com as opções configuradas grava o PDF rotacionado na pasta de saída.

```java
viewer.view(viewOptions);
```

#### Como funciona
- **PdfViewOptions** direciona o Viewer a gerar um arquivo PDF de saída.  
- **rotatePage(int, Rotation)** rotaciona apenas a página especificada, deixando todas as outras páginas inalteradas.  
- O método suporta três constantes de rotação: `ON_90_DEGREE`, `ON_180_DEGREE` e `ON_270_DEGREE`.

## Problemas comuns e soluções

| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| **FileNotFoundException** | Caminho incorreto ou pasta ausente | Verifique se `YOUR_OUTPUT_DIRECTORY` e `YOUR_DOCUMENT_DIRECTORY` existem e são legíveis. |
| **Unsupported file format** | Tentando rotacionar um formato não suportado pelo Viewer | Consulte a página [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Usando o número de página errado (baseado em 0) | Lembre‑se de que `rotatePage` usa indexação **baseada em 1**. |
| **Out‑of‑memory errors on large docs** | Renderizando muitos arquivos grandes em uma única thread | Processar documentos sequencialmente ou usar um pool de threads com concorrência limitada. |

## Aplicações práticas

1. **Ajustes de apresentação** – Converta um slide em retrato para paisagem em tempo real para melhor impacto visual.  
2. **Correção em lote de documentos** – Automatize a correção de PDFs escaneados que foram capturados de lado, economizando horas de trabalho manual.  
3. **Saída pronta para impressão** – Garanta que gráficos em paisagem imprimam corretamente em papel orientado em retrato sem rotação manual no driver da impressora.  

## Dicas de desempenho

- **Feche recursos prontamente** – O bloco `try‑with‑resources` descarta automaticamente o `Viewer`, liberando memória.  
- **Processamento em lote** – Reutilize uma única instância `Viewer` por thread para reduzir a sobrecarga de inicialização.  
- **Monitore a memória** – Para documentos maiores que 100 MB, faça streaming da saída para disco em vez de manter o arquivo inteiro na memória; o GroupDocs Viewer pode processar arquivos de 200 MB usando menos de 250 MB de RAM.  

## Perguntas frequentes

**Q: Posso rotacionar várias páginas de uma vez?**  
A: Sim—chame `rotatePage()` para cada número de página que precisar rotacionar, seja em um loop ou encadeando chamadas.

**Q: Existe uma maneira de desfazer a rotação após a renderização?**  
A: Não diretamente. Você precisaria renderizar o documento novamente sem as opções de rotação.

**Q: Quais formatos de arquivo suportam rotação de página no GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX e muitos outros formatos listados na documentação oficial.

**Q: Como posso rotacionar páginas em um lote de documentos automaticamente?**  
A: Envolva a lógica de rotação em um loop que itere sobre uma coleção de caminhos de arquivos, aplicando a mesma configuração `rotatePage` a cada arquivo.

**Q: Qual a melhor prática para lidar com erros durante a rotação?**  
A: Envolva o uso do Viewer em um bloco `try‑catch`, registre os detalhes da exceção e, opcionalmente, continue processando o próximo arquivo para evitar que uma única falha interrompa todo o lote.

## Recursos

- **Documentação**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referência da API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Compra**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Teste gratuito**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licença temporária**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Suporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-09-30  
**Testado com:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriais Relacionados

- [Como rotacionar páginas PDF específicas com GroupDocs.Viewer para Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Carregar documento a partir de URL em Java – Tutorial GroupDocs.Viewer](/viewer/java/document-loading/)
- [Visualizações de documentos do GroupDocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)