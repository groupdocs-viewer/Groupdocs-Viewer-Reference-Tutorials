---
date: '2026-01-18'
description: Aprenda a girar a página 90 graus em Java usando o GroupDocs Viewer,
  incluindo configuração, código e dicas de desempenho.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Gire a página 90 graus com o GroupDocs Viewer para Java
type: docs
url: /pt/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Rotacionar página 90 graus com GroupDocs Viewer para Java

Quando você precisa **rotacionar página 90 graus** em um documento—seja ele um PDF, um arquivo Word ou uma planilha—fazer isso programaticamente economiza tempo e elimina erros manuais. Neste guia avançado, vamos percorrer os passos exatos para rotacionar a primeira página de qualquer documento suportado usando **GroupDocs Viewer para Java**. Ao final, você terá um trecho reutilizável que pode inserir em seus próprios projetos.

![Rotacionar a Primeira Página de um Documento com GroupDocs.Viewer para Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Quick Answers
- **O que significa “rotacionar página 90 graus”?** Ele gira a página selecionada no sentido horário em um quarto de volta.  
- **Qual biblioteca lida com a rotação?** O GroupDocs Viewer para Java fornece o método `rotatePage`.  
- **Posso rotacionar páginas PDF com Java?** Sim—use a mesma chamada `rotatePage`; funciona para PDF, DOCX, XLSX e outros.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença paga é necessária para produção.  
- **A operação consome muita memória?** Não quando você fecha a instância `Viewer` prontamente; veja as dicas de desempenho abaixo.

## O que é “rotacionar página 90 graus”?
Rotacionar uma página 90 graus reorienta a página de retrato para paisagem (ou vice‑versa) sem alterar o conteúdo subjacente. Isso é especialmente útil para apresentações, impressão de gráficos apenas em paisagem ou correção de documentos escaneados que foram capturados de lado.

## Por que rotacionar páginas com GroupDocs Viewer para Java?
O GroupDocs Viewer abstrai as complexidades de lidar com dezenas de formatos de arquivo. Ele permite aplicar transformações ao nível da página—como rotação—mantendo o arquivo original intacto. A API é fluente, thread‑safe e funciona em qualquer runtime Java 8+.

## Prerequisites

- **GroupDocs.Viewer for Java** (latest version)
- **JDK 8** or newer
- **Maven** (or Gradle) for dependency management
- An IDE such as IntelliJ IDEA or Eclipse
- Basic familiarity with Java I/O

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

### License acquisition
- **Teste gratuito** – faça o download no site da GroupDocs.  
- **Licença temporária** – solicite se precisar de um período de avaliação estendido.  
- **Licença completa** – compre para implantações em produção.

### Basic Viewer initialization
O código a seguir mostra a forma mínima de criar uma instância `Viewer`. Mantenha exatamente como mostrado:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Implementação Passo a Passo: Rotacionar a Primeira Página 90 Graus

### 1. Importe os pacotes necessários
Essas importações dão acesso às opções de renderização PDF e ao enum de rotação.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Defina os locais de saída e crie o Viewer
Substitua os caminhos de placeholder pelos seus diretórios reais.

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
O método `rotatePage` recebe o número da página (baseado em 1) e um valor do enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderize o documento
Finalmente, chame `view` para gerar o PDF rotacionado.

```java
viewer.view(viewOptions);
```

#### Como funciona
- **PdfViewOptions** informa ao Viewer para gerar um arquivo PDF.  
- **rotatePage(int, Rotation)** rotaciona apenas a página que você especificar, deixando as demais intactas.  
- O método suporta `ON_90_DEGREE`, `ON_180_DEGREE` e `ON_270_DEGREE`.

## Common Issues and Solutions
| Sintoma | Causa Provável | Solução |
|---------|----------------|---------|
| **FileNotFoundException** | Caminho incorreto ou pasta ausente | Verifique se `YOUR_OUTPUT_DIRECTORY` e `YOUR_DOCUMENT_DIRECTORY` existem e são legíveis. |
| **Unsupported file format** | Tentando rotacionar um formato não suportado pelo Viewer | Verifique a página [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Usando o número de página errado (baseado em 0) | Lembre-se de que `rotatePage` usa indexação **baseada em 1**. |
| **Out‑of‑memory errors on large docs** | Renderizando muitos arquivos grandes em uma única thread | Processar documentos sequencialmente ou usar um pool de threads com concorrência limitada. |

## Aplicações Práticas

1. **Ajustes de apresentação** – Converta um slide em retrato para paisagem em tempo real.  
2. **Correção em massa de documentos** – Automatize a correção de PDFs escaneados que foram capturados de lado.  
3. **Saída pronta para impressão** – Garanta que gráficos em paisagem imprimam corretamente em papel orientado em retrato.

## Dicas de Desempenho

- **Feche recursos prontamente** – O bloco `try‑with‑resources` descarta automaticamente o `Viewer`.  
- **Processamento em lote** – Ao lidar com muitos arquivos, reutilize uma única instância `Viewer` por thread para reduzir a sobrecarga.  
- **Monitore a memória** – Para documentos maiores que 100 MB, considere transmitir a saída para disco ao invés de mantê-la na memória.

## Perguntas Frequentes

**P: Posso rotacionar várias páginas de uma vez?**  
**R: Sim—chame `rotatePage()` para cada número de página que precisar rotacionar.**

**P: Existe uma maneira de desfazer a rotação após a renderização?**  
**R: Não diretamente. Você precisaria renderizar o documento novamente sem as opções de rotação.**

**P: Quais formatos de arquivo suportam rotação de página no GroupDocs Viewer?**  
**R: DOCX, PDF, PPTX, XLSX e muitos outros formatos listados na documentação oficial.**

**P: Como posso rotacionar páginas em um lote de documentos automaticamente?**  
**R: Envolva o código em um loop que itere sobre uma coleção de caminhos de arquivos, aplicando a mesma lógica `rotatePage` a cada um.**

**P: Qual a melhor prática para lidar com erros durante a rotação?**  
**R: Envolva o uso do Viewer em um bloco `try‑catch`, registre a exceção e, opcionalmente, continue processando o próximo arquivo.**

## Recursos

- **Documentação**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referência da API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Obter GroupDocs Viewer para Java**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Comprar uma Licença**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Teste Gratuito**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Solicitar Licença Temporária**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Fórum GroupDocs**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-01-18  
**Testado com:** GroupDocs Viewer 25.2 para Java  
**Autor:** GroupDocs  

---