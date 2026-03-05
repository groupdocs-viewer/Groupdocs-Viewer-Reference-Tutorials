---
date: '2026-03-05'
description: Aprenda como converter números para PDF e outros formatos como HTML,
  JPG, PNG usando o GroupDocs.Viewer para Java. Este guia cobre configuração, técnicas
  de renderização e aplicações práticas.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: Converter Numbers para PDF com GroupDocs.Viewer para Java
type: docs
url: /pt/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Converter Numbers para PDF (e Outros Formatos) com GroupDocs.Viewer para Java

Exibir documentos Apple Numbers na web ou em aplicativos desktop pode ser complicado, especialmente quando você precisa **converter numbers to pdf** ou incorporá‑los como imagens. Neste tutorial vamos mostrar como usar **GroupDocs.Viewer para Java** para renderizar arquivos Numbers em HTML, JPG, PNG, **e PDF** — oferecendo opções flexíveis para compartilhamento, visualização ou arquivamento de suas planilhas.

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### O que você vai aprender
- Como configurar o GroupDocs.Viewer em um projeto Java baseado em Maven  
- Código passo a passo para **convert numbers to pdf**, **convert numbers to html** e **convert numbers to jpg**  
- Cenários reais onde a conversão de documentos agrega valor a portais web, fluxos de trabalho de e‑mail e integrações DMS  

## Respostas rápidas
- **Posso converter Numbers para PDF com Java?** Sim, usando `PdfViewOptions` no GroupDocs.Viewer.  
- **Qual formato é melhor para visualização na web?** HTML oferece a experiência mais interativa.  
- **Preciso de licença para uso em produção?** Uma licença comercial é necessária para implantações que não sejam de avaliação.  
- **A conversão de imagens é suportada?** Absolutamente — use `JpgViewOptions` ou `PngViewOptions` para obter imagens de alta qualidade.  
- **Qual versão do Java é necessária?** Java 8+ e Maven para gerenciamento de dependências.

## Pré‑requisitos
- Java Development Kit (JDK) 8 ou superior instalado.  
- Maven para gerenciamento de dependências.  
- Familiaridade básica com I/O de arquivos Java e caminhos.  

## Configurando o GroupDocs.Viewer para Java

### Instalação com Maven
Adicione o repositório e a dependência ao seu `pom.xml`. Este bloco deve permanecer exatamente como mostrado:

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
- **Teste gratuito:** Avalie todos os recursos sem custo.  
- **Licença temporária:** Solicite uma chave limitada no tempo para testes prolongados.  
- **Compra:** Obtenha uma licença completa para projetos comerciais.

## Renderizando documento Numbers para HTML  
*Caso de uso: incorporar uma planilha diretamente em uma página web.*

### Etapa 1: Inicializar o Viewer e Configurar as opções HTML
Abaixo está o código exato que você executará. Os comentários explicam cada linha, mas **não modifique o bloco de código**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Por que isso importa:** `HtmlViewOptions.forEmbeddedResources()` agrupa CSS e imagens dentro do HTML, tornando‑o perfeito para visualizações rápidas na web.

## Renderizando documento Numbers para JPG  
*Ideal para compartilhar uma captura de tela de uma planilha nas redes sociais ou por e‑mail.*

### Etapa 1: Configurar o Viewer e as opções JPG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Dica:** Ajuste a qualidade da imagem via `options.setQuality(int)` se precisar de arquivos menores.

## Renderizando documento Numbers para PNG  
*Perfeito quando você precisa de uma imagem sem perdas e de alta resolução para relatórios.*

### Etapa 1: Inicializar e Configurar as opções PNG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Dica de especialista:** Use `options.setResolution(int)` para controlar DPI em imagens prontas para impressão.

## Renderizando documento Numbers para PDF  
*O objetivo principal para muitos desenvolvedores: **convert numbers to pdf** para arquivamento ou distribuição.*

### Etapa 1: Configurar o Viewer para Conversão em PDF
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Configuração chave:** `PdfViewOptions` permite incorporar fontes e controlar o tamanho da página, garantindo que a saída corresponda aos requisitos de sua identidade visual.

## Aplicações práticas
- **Integração web:** Renderize para HTML e ofereça um visualizador interativo de planilhas em seu site.  
- **Compartilhamento de conteúdo:** Converta para JPG/PNG para inserções rápidas de imagem em newsletters ou chats.  
- **DMS corporativo:** Use **convert numbers to pdf** para armazenar uma versão não editável e pesquisável da planilha.  

## Considerações de desempenho
- **Gerenciamento de recursos:** Sempre feche o `Viewer` em um bloco try‑with‑resources (conforme mostrado) para liberar recursos nativos rapidamente.  
- **Arquivos grandes:** Para arquivos Numbers volumosos, considere processar página por página e transmitir os resultados para evitar alto consumo de memória.  
- **Segurança de threads:** Crie uma instância separada de `Viewer` por thread; a classe não é thread‑safe.

## Conclusão
Agora você tem um conjunto completo de ferramentas para **convert numbers to pdf**, bem como para HTML, JPG e PNG, usando o GroupDocs.Viewer para Java. Essas capacidades permitem construir pipelines de documentos flexíveis — seja alimentando um portal web, gerando relatórios ou arquivando planilhas.

### Próximos passos
Explore opções de personalização adicionais na [documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/) e experimente integrar esses recursos em suas próprias aplicações.

## Seção de Perguntas Frequentes

**Q1: Quais formatos de arquivo o GroupDocs.Viewer suporta?**  
A1: Ele suporta uma ampla gama de formatos de documento, incluindo DOCX, XLSX, PDF e muito mais.

**Q2: Como lidar eficientemente com arquivos Numbers grandes?**  
A2: Utilize técnicas de gerenciamento de memória do Java e otimize seu código para tratar arquivos de grande tamanho de forma eficaz.

**Q3: O GroupDocs.Viewer pode ser usado em um projeto comercial?**  
A4: Sim, mas será necessário adquirir uma licença para uso comercial.

**Q4: É possível personalizar a qualidade de saída das imagens?**  
A5: Absolutamente. Você pode ajustar as configurações dentro de `JpgViewOptions` e `PngViewOptions`.

**Q5: Onde encontrar exemplos de uso avançado?**  
A5: Visite a [referência da API](https://reference.groupdocs.com/viewer/java/) para documentação detalhada.

## Perguntas Frequentes

**Q: Como converto um arquivo Numbers para PDF sem perder a formatação?**  
A: Use `PdfViewOptions` como mostrado acima; o viewer preserva layout, fontes e estilos de célula automaticamente.

**Q: Posso converter uma planilha para imagem em uma única chamada?**  
A: Sim, `JpgViewOptions` ou `PngViewOptions` realizam a conversão em um passo, permitindo especificar resolução e qualidade.

**Q: Existe uma forma de processar em lote vários arquivos Numbers?**  
A: Envolva a lógica do viewer em um loop, reinicializando `Viewer` para cada arquivo, e grave cada saída em uma pasta distinta.

**Q: Preciso de licenças separadas para cada formato de saída?**  
A: Não, uma única licença do GroupDocs.Viewer cobre todos os formatos suportados.

**Q: Qual versão do GroupDocs.Viewer é necessária para esses recursos?**  
A: Os exemplos visam a versão 25.2, que inclui suporte total para conversão de Numbers para PDF/HTML/Imagem.

## Recursos
- **Documentação:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **Referência da API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download:** [Obter GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Compra de Licença:** [Comprar Licença](https://purchase.groupdocs.com/buy)
- **Teste Gratuito:** [Iniciar Seu Teste Gratuito](https://releases.groupdocs.com/viewer/java/)
- **Licença Temporária:** [Solicitar Aqui](https://purchase.groupdocs.com/temporary-license/)
- **Fórum de Suporte:** [Participar da Discussão](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-03-05  
**Testado com:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs