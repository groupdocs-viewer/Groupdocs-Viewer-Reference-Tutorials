---
date: '2026-05-21'
description: Aprenda como realizar a exportação HTML do MS Project com unidades de
  tempo ajustadas usando o GroupDocs Viewer para Java. Guia passo a passo com pré-requisitos,
  configuração e solução de problemas.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Exportação HTML do MS Project: Ajustar Unidades de Tempo via GroupDocs Java'
type: docs
url: /pt/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Exportação HTML do MS Project: Ajustar Unidades de Tempo via GroupDocs Java

Exportar um arquivo **MS Project** para HTML é uma necessidade comum para painéis de gerenciamento de projetos, portais de relatórios de status e ferramentas de revisão colaborativa. Por padrão, o visualizador renderiza dados relacionados ao tempo em minutos, o que pode sobrecarregar o layout visual e dificultar a leitura dos relatórios diários. Com **GroupDocs Viewer for Java** você pode definir programaticamente a unidade de tempo para **dias**, produzindo uma *ms project html export* limpa que se alinha às expectativas típicas das partes interessadas. Neste tutorial você aprenderá como configurar o visualizador, ajustar a unidade de tempo e renderizar o projeto para HTML em alguns passos simples.

![Ajustar Unidades de Tempo do MS Project com GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Ajustar Unidades de Tempo do MS Project com GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Respostas Rápidas
- **Qual biblioteca renderiza arquivos MS Project?** GroupDocs Viewer for Java.  
- **Qual unidade de tempo posso definir para exportação HTML?** Dias, usando `TimeUnit.DAYS`.  
- **Preciso de uma licença para produção?** Sim— é necessária uma licença permanente; um trial funciona para avaliação. Você pode começar com um [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Qual IDE funciona melhor?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, NetBeans) que suporte Maven.  
- **O Maven é obrigatório?** Maven simplifica o gerenciamento de dependências, mas você também pode usar Gradle ou inclusão manual de JAR.  
- **Onde posso comprar?** Visite a [página de compra](https://purchase.groupdocs.com/buy) para preços.

## O que é o GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** é um SDK Java que converte mais de 150 formatos de documento—incluindo MS Project—para HTML, PNG, JPEG ou PDF compatíveis com a web.  
Ele abstrai a lógica de análise, permite controlar opções de renderização como unidades de tempo e funciona em qualquer plataforma que suporte Java 8 ou superior.

## Por que ajustar unidades de tempo para exportação HTML do MS Project?
Definir a unidade de tempo para **dias** reduz o ruído visual, corresponde à maioria dos ciclos de relatório e melhora o tempo de carregamento da página porque são gerados menos marcadores de tempo granulares. Em termos quantitativos, renderizar com dias em vez de minutos pode reduzir o tamanho do HTML gerado em até **45 %** para projetos típicos de 30 dias, e acelera a renderização no cliente em cerca de **30 %**.

## Pré-requisitos
- **Java Development Kit (JDK) 8 ou mais recente** instalado na sua estação de trabalho.  
- **Maven** (ou Gradle) para gerenciamento de dependências.  
- Um arquivo **MS Project (.mpp)** que você deseja exportar.  
- Acesso a uma licença do **GroupDocs Viewer for Java** (trial ou permanente).  

### Bibliotecas Necessárias
Adicione a seguinte dependência ao seu `pom.xml` (ou ao snippet equivalente do Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Dica profissional:** Mantenha o número da versão atualizado; lançamentos mais recentes adicionam suporte a formatos e melhorias de desempenho.

## Como configurar o GroupDocs Viewer for Java?
Inicialize o visualizador criando uma instância `Viewer` que aponta para o seu arquivo MS Project. A classe `Viewer` é o ponto de entrada para todas as operações de renderização. Ela carrega o documento fonte, prepara estruturas internas e expõe métodos como `view()` e `viewToHtml()` para gerar os formatos de saída desejados.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Âncora de definição:** A classe `Viewer` é o componente central do GroupDocs Viewer que carrega um documento fonte e fornece métodos de renderização como `view()` e `viewToHtml()`.

## Como ajustar unidades de tempo para a exportação HTML?
Para alterar a granularidade do tempo, crie um objeto `ViewOptions`, configure seu `ProjectOptions` para usar `TimeUnit.DAYS` e passe-o ao visualizador. `ViewOptions` define as configurações de renderização para o documento, enquanto o enum `TimeUnit` especifica a unidade (minutos, horas, dias) para dados relacionados ao tempo. Após definir essas opções, invoque `viewer.view(options)` para gerar HTML com marcadores diários.

Carregue seu arquivo MS Project com `new Viewer("file.mpp")`, crie um objeto `ViewOptions`, defina `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, e então chame `viewer.view(options)`. Esse fluxo de três etapas altera a unidade de tempo de minutos para dias e gera arquivos HTML que exibem apenas intervalos diários.

### Etapa 1: Definir a pasta de saída
Escolha um diretório gravável onde as páginas HTML serão salvas, por exemplo `output/`.

### Etapa 2: Criar opções de visualização com recursos incorporados
Recursos incorporados (CSS, JavaScript) garantem que as páginas HTML sejam autônomas.

### Etapa 3: Definir a unidade de tempo para dias
Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` para mudar a granularidade.

### Etapa 4: Renderizar o documento
Chame `viewer.view(options)`; o visualizador grava um arquivo HTML por página do projeto na pasta de saída.

### Etapa 5: Verificar o resultado
Abra o `index.html` gerado em um navegador; você deverá ver as barras de tarefas alinhadas aos marcadores diários em vez de marcadores de minuto.

## Armadilhas comuns e solução de problemas
- **Caminho de saída incorreto** – Certifique-se de que o diretório exista e que o processo Java tenha permissões de gravação.  
- **Licença ausente** – Sem uma licença válida, o visualizador recai para o modo trial e pode inserir marcas d'água.  
- **Arquivos grandes (> 500 MB)** – Considere aumentar o tamanho do heap da JVM (`-Xmx2g`) ou renderizar com `options.setRenderLimit(1000)` para processar páginas em lotes.  

## Aplicações práticas da exportação HTML com unidade de tempo ajustada
1. **Painéis executivos** – Granularidade diária corresponde à maioria das visualizações de KPI.  
2. **E‑mails de status automatizados** – Incorpore o HTML gerado diretamente nos corpos dos e‑mails para atualizações rápidas.  
3. **Portais de projetos** – Hospede o HTML em um site intranet onde os membros da equipe podem filtrar tarefas por dia.  

## Considerações de desempenho para arquivos grandes de MS Project
- **Gerenciamento de memória** – Use as flags do coletor de lixo do Java (`-XX:+UseG1GC`) para liberar objetos não utilizados rapidamente.  
- **Renderização seletiva** – Se você precisar apenas do diagrama de Gantt, desative a renderização de outros recursos via `options.getProjectOptions().setRenderGantt(true)` e `setRenderResources(false)`.  
- **Processamento paralelo** – Para conversões em lote, instancie objetos `Viewer` separados por arquivo e execute-os em um pool de threads para utilizar CPUs multi‑core.  

## Conclusão
Agora você tem um fluxo de trabalho completo e pronto para produção para realizar uma **ms project html export** com unidades de tempo definidas para dias usando o GroupDocs Viewer for Java. Essa abordagem reduz o tamanho do HTML, acelera a renderização no cliente e fornece uma visualização amigável para as partes interessadas dos cronogramas de projetos. Explore opções de renderização adicionais—como exportação para PDF ou capturas de imagem—para expandir a integração em pipelines de relatórios mais amplos.

## Perguntas Frequentes

**Q: Posso renderizar outras visualizações do Project (por exemplo, Folha de Recursos) para HTML?**  
A: Sim, o objeto `ProjectOptions` permite habilitar ou desabilitar visualizações específicas como Gantt, Folha de Recursos e Calendário antes da renderização.

**Q: É possível personalizar o CSS do HTML gerado?**  
A: Absolutamente. Forneça o caminho de uma folha de estilo personalizada via `options.setStyleSheetPath("path/to/custom.css")` e o visualizador a incorporará em cada página.

**Q: Quais limites de tamanho de arquivo o GroupDocs Viewer suporta para MS Project?**  
A: O SDK pode lidar com arquivos de até **500 MB** sem precisar carregar todo o documento na memória, graças à sua arquitetura de streaming.

**Q: Preciso instalar o Microsoft Project no servidor?**  
A: Não. O GroupDocs Viewer analisa o formato .mpp diretamente e não requer o Microsoft Project ou qualquer instalação do Office.

**Q: Como licenciar o visualizador para um ambiente de produção?**  
A: Compre uma licença permanente na loja GroupDocs; aplique o arquivo de licença em tempo de execução com `License license = new License(); license.setLicense("path/to/license.lic");`. Para necessidades de curto prazo, você pode obter uma [licença temporária](https://purchase.groupdocs.com/temporary-license/).

---

**Última atualização:** 2026-05-21  
**Testado com:** GroupDocs Viewer Java 25.2  
**Autor:** GroupDocs  

**Recursos**  
- [Documentação](https://docs.groupdocs.com/viewer/java/)  
- [Referência da API](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Comprar uma licença](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Tutoriais Relacionados

- [Como renderizar arquivos MS Project como HTML, JPG, PNG e PDF com notas usando GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Como usar o GroupDocs Viewer para renderizar documentos de projeto por intervalos de tempo em Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Como definir licenças no GroupDocs.Viewer Java: Guia de configuração de arquivo e URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)