---
date: '2026-02-28'
description: Aprenda como converter arquivos CDR para HTML, JPG, PNG e PDF usando
  o GroupDocs.Viewer para Java. Inclui configuração, exemplos de código e dicas de
  desempenho.
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: converter cdr para html, jpg, png, pdf com GroupDocs.Viewer Java
type: docs
url: /pt/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# converter cdr para html, jpg, png, pdf com GroupDocs.Viewer Java

Se você precisa **converter CDR para HTML** (ou para JPG, PNG e PDF) de forma rápida e confiável, chegou ao tutorial certo. Neste guia vamos percorrer tudo o que você precisa — desde a instalação do GroupDocs.Viewer para Java até a renderização de arquivos CorelDRAW (CDR) em páginas HTML amigáveis para a web, imagens de alta qualidade e PDFs universalmente legíveis. Ao final, você poderá integrar essas conversões em qualquer aplicação Java com apenas algumas linhas de código.

![Renderizar arquivos CDR com GroupDocs.Viewer para Java](/viewer/file-formats-support/render-cdr-files.png)

## Respostas Rápidas
- **Qual biblioteca converte CDR para HTML?** GroupDocs.Viewer for Java.  
- **Posso também converter CDR para JPG, PNG e PDF?** Sim — mesma API Viewer com diferentes opções de visualização.  
- **Preciso de uma licença?** Um teste gratuito ou licença temporária funciona para testes; uma licença completa é necessária para produção.  
- **Qual versão do Java é necessária?** JDK 8 ou superior.  
- **A conversão em lote é suportada?** Absolutamente — basta percorrer os arquivos usando a mesma instância do Viewer.

## O que é “converter CDR para HTML”?
Converter CDR para HTML significa transformar um arquivo vetorial CorelDRAW em marcação HTML padrão, opcionalmente incorporando imagens e estilos para que o design possa ser visualizado diretamente em um navegador web sem a necessidade do software de design original.

## Por que converter CDR para HTML, JPG, PNG ou PDF?
- **HTML** permite que você incorpore gráficos em portais web e os compartilhe instantaneamente.  
- **JPG** e **PNG** fornecem imagens rasterizadas para galerias, miniaturas ou anexos de e‑mail.  
- **PDF** oferece uma versão imprimível e independente de plataforma para arquivamento ou sistemas de compartilhamento de documentos.  

Ter os quatro formatos à sua disposição significa que você pode servir o tipo de arquivo correto para o público certo, melhorar o desempenho e garantir a longevidade dos seus ativos.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

1. **Bibliotecas e Dependências** – GroupDocs.Viewer adicionado ao seu projeto Maven.  
2. **Java Development Kit (JDK)** – versão 8 ou superior instalada.  
3. **Conhecimento básico de Java** – para entender os trechos de código.

### Bibliotecas Necessárias, Versões e Dependências

Adicione a seguinte configuração Maven ao seu `pom.xml` (mantida exatamente como no tutorial original):

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

### Etapas para Obtenção de Licença

GroupDocs.Viewer oferece um teste gratuito, licenças temporárias para testes ou opções de compra completa:

- **Teste Gratuito** – Baixe a partir da [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **Licença Temporária** – Solicite uma na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Compra** – Obtenha uma licença permanente via [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Configurando GroupDocs.Viewer para Java

### Instalação com Maven
O trecho Maven acima trará todos os JARs necessários automaticamente. Basta executar `mvn clean install` após salvar o arquivo.

### Inicialização da Licença
Inicialize sua licença antes de renderizar quaisquer documentos:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Guia de Implementação

A seguir você encontrará exemplos passo a passo para cada formato de saída. Os blocos de código são idênticos ao tutorial original; adicionamos apenas texto explicativo ao redor deles.

### Como converter CDR para HTML com GroupDocs.Viewer

#### Renderizando Documento CDR para HTML
**Visão geral:** Converta seus arquivos CDR em HTML amigável para a web para fácil compartilhamento.

**Passo 1 – Configurar Caminhos de Arquivo**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Passo 2 – Inicializar Viewer e Renderizar**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Como converter CDR para JPG com GroupDocs.Viewer

#### Renderizando Documento CDR para JPG
**Visão geral:** Produza imagens JPEG de alta qualidade a partir do seu CDR.

**Passo 1 – Configurar Caminhos de Arquivo**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Passo 2 – Inicializar Viewer e Renderizar**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Como converter CDR para PNG com GroupDocs.Viewer

#### Renderizando Documento CDR para PNG
**Visão geral:** Gere imagens PNG sem perdas para arquivamento ou propósitos de design.

**Passo 1 – Configurar Caminhos de Arquivo**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Passo 2 – Inicializar Viewer e Renderizar**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Como converter CDR para PDF com GroupDocs.Viewer

#### Renderizando Documento CDR para PDF
**Visão geral:** Transforme seus arquivos CDR em PDFs universalmente legíveis.

**Passo 1 – Configurar Caminhos de Arquivo**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Passo 2 – Inicializar Viewer e Renderizar**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Aplicações Práticas

- **Portais Web:** Use a conversão para HTML para incorporar designs CDR diretamente no seu site.  
- **Galerias de Imagens:** Implante saídas JPG/PNG para galerias de imagens de carregamento rápido.  
- **Compartilhamento de Documentos:** Forneça PDFs para clientes que precisam de uma versão imprimível e somente‑leitura.  
- **Arquivamento:** Armazene múltiplos formatos para garantir acessibilidade futura.  
- **Integração Multiplataforma:** Alimente os arquivos gerados em outros serviços (ex.: OCR, analytics).

## Considerações de Desempenho

- **Descarte as instâncias do Viewer** prontamente (conforme mostrado com try‑with‑resources) para liberar memória.  
- **Processamento em lote:** Percorra uma coleção de arquivos CDR usando a mesma configuração do Viewer para reduzir a sobrecarga.  
- **Alocação de recursos:** Reserve CPU/RAM suficientes para arquivos CDR grandes ou complexos; ferramentas de monitoramento podem ajudar a ajustar finamente.

## Conclusão

Mostramos como **converter CDR para HTML**, bem como para JPG, PNG e PDF, usando o GroupDocs.Viewer para Java. Seguindo os trechos de código concisos e as dicas de boas práticas, você pode integrar essas conversões em qualquer fluxo de trabalho baseado em Java, entregando saídas flexíveis e de alta qualidade aos seus usuários.

### Próximos Passos
- Experimente opções avançadas de renderização, como tamanhos de página personalizados ou marcas d'água.  
- Combine o pipeline de conversão com uma API REST para oferecer transformação de arquivos sob demanda.  
- Participe da comunidade e faça perguntas no [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## Perguntas Frequentes

**Q: Posso converter arquivos CDR protegidos por senha?**  
A: Sim. Carregue o arquivo com uma instância `Viewer` que aceita um parâmetro de senha (consulte a documentação da API).

**Q: Existe um limite no número de páginas que podem ser convertidas de uma vez?**  
A: Não há limite rígido, mas arquivos muito grandes podem exigir mais memória; considere processar página por página.

**Q: A saída HTML inclui fontes incorporadas?**  
A: Ao usar `HtmlViewOptions.forEmbeddedResources`, as fontes são incorporadas como Base64, garantindo renderização consistente.

**Q: Como controlo a qualidade do JPEG?**  
A: `JpgViewOptions` oferece o método `setQuality(int)` onde você pode especificar um valor de 1‑100.

**Q: Posso converter arquivos CDR em um servidor Linux?**  
A: Absolutamente — o GroupDocs.Viewer é independente de plataforma, desde que o JDK esteja instalado.

**Última atualização:** 2026-02-28  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs