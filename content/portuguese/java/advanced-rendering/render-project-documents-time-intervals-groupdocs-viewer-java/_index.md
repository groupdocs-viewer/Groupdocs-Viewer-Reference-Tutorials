---
date: '2026-09-25'
description: Aprenda como criar visualização html mpp com GroupDocs Viewer para Java,
  renderizando documentos de projetos por intervalos de tempo com código step‑by‑step.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Crie visualização html mpp com GroupDocs Viewer para Java para renderizar
  arquivos Microsoft Project por intervalos de tempo específicos. Siga a configuração
  step‑by‑step, licenciamento e trechos de código para visualização precisa da linha
  do tempo.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Criar visualização html mpp com GroupDocs Viewer para Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Criar visualização html mpp com GroupDocs Viewer (Java)
type: docs
url: /pt/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Como usar o GroupDocs Viewer para renderizar documentos de projeto por intervalos de tempo em Java

Neste tutorial, você aprenderá como **create html view mpp** com o GroupDocs Viewer para Java, permitindo renderizar apenas as partes de um arquivo Microsoft Project que se enquadram em um intervalo específico de data de início e data de término. Vamos percorrer a configuração do Maven, licenciamento e as chamadas de API exatas que você precisa para incorporar visualizações de cronograma precisas diretamente em suas aplicações.

![Renderizar documentos de projeto por intervalos de tempo com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Para uma pré‑visualização, veja o [Renderizar documentos de projeto por intervalos de tempo com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Respostas rápidas
- **O que a funcionalidade faz?** Ele renderiza apenas a parte de um arquivo Microsoft Project que está entre uma data de início e uma data de término.  
- **Qual formato de saída é usado?** HTML com recursos incorporados, perfeito para integração web.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para avaliação; uma licença completa é necessária para produção.  
- **Posso alterar o intervalo de datas em tempo de execução?** Sim—ajuste os valores `setStartDate` e `setEndDate` nas opções de renderização.  
- **Isso é suportado em todas as versões do Java?** Funciona com Java 8+ desde que você use o GroupDocs.Viewer 25.2 ou mais recente.

## O que é create html view mpp?
`create html view mpp` é o processo de converter um arquivo Microsoft Project (`.mpp` ou `.mpt`) em um conjunto de páginas HTML que representam o cronograma. O GroupDocs Viewer realiza a conversão no lado do servidor, permitindo que você exiba o cronograma em qualquer navegador sem instalar o Microsoft Project.

## Por que renderizar documentos de projeto com intervalos de tempo?
Renderizar apenas o intervalo de tempo necessário reduz o tamanho do HTML gerado, acelera o carregamento da página e permite que você se concentre na fase específica do projeto que precisa analisar. Essa visualização direcionada é ideal para dashboards, relatórios de status ou incorporação em ferramentas de gerenciamento de projetos personalizadas, onde os dados de todo o projeto seriam excessivos.

## Pré-requisitos

- **GroupDocs.Viewer for Java** versão 25.2 ou superior.  
- Java Development Kit (JDK) 8 ou mais recente.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Conhecimento básico de Maven.  

## Configurando o GroupDocs.Viewer para Java

### Dependência Maven

Add the repository and dependency to your `pom.xml`:

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

### Etapas de aquisição de licença

1. **Free trial** – Baixe uma versão de avaliação em [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary license** – Obtenha uma licença temporária para testes estendidos através da [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Para uso de produção sem restrições, compre uma licença na [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Inicialização básica do visualizador

`Viewer` é a classe principal no GroupDocs.Viewer para Java que carrega um documento e fornece recursos de renderização.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Recuperar informações de visualização para arquivos de projeto

`ProjectManagementViewInfo` fornece metadados sobre um arquivo Microsoft Project, incluindo as datas de início e término do cronograma geral.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Configurar opções de renderização HTML (gerar HTML a partir do projeto)

`HtmlViewOptions` configura como o GroupDocs renderiza HTML, permitindo definir o intervalo de datas, incorporar recursos e personalizar a aparência.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Executar o processo de renderização

`viewer.render` executa a conversão com base nas opções fornecidas e grava os arquivos HTML resultantes na pasta de destino.

```java
viewer.view(viewOptions);
```

## Armadilhas comuns e solução de problemas

- **Incorrect file paths** – Verifique novamente se tanto o arquivo `.mpp` de origem quanto o diretório de saída existem.  
- **Unsupported file type** – Certifique-se de que o documento seja um formato de Project suportado (por exemplo, `.mpp`, `.mpt`).  
- **License errors** – Uma licença de avaliação pode impor limites de renderização; troque para uma licença completa para uso sem restrições.  

## Aplicações práticas

1. **Project timeline analysis** – Mostre aos interessados apenas a fase atual.  
2. **Automated reporting** – Gere relatórios HTML com limites de tempo para atualizações de status semanais.  
3. **Integration with dashboards** – Incorpore as páginas renderizadas em ferramentas de BI ou portais personalizados.  
4. **Archival** – Armazene uma captura da agenda do projeto amigável para a web para referência futura.  

## Dicas de desempenho

- Use a opção *embedded resources* para manter cada página HTML autônoma, reduzindo requisições HTTP.  
- Para projetos muito grandes, considere renderizar em blocos de datas menores para manter o uso de memória baixo. Renderizar um recorte de um ano pode reduzir o tamanho do HTML em até 80 % comparado com a exportação de todo o projeto, diminuindo o tempo de carregamento de vários segundos para menos de um segundo em servidores típicos.  
- Limpe arquivos temporários após servi-los para evitar inchaço de disco.  

## Conclusão

Agora você sabe **how to use GroupDocs** Viewer para renderizar documentos de projeto dentro de um intervalo de tempo específico e **generate HTML from project** dados em Java. Essa capacidade simplifica visualizações de cronograma, melhora a eficiência de relatórios e integra-se perfeitamente com aplicações web modernas.

### Próximos passos
- Explore recursos adicionais do Viewer, como marca d'água, proteção por senha ou estilização CSS personalizada.  
- Combine este pipeline de renderização com uma API REST para servir visualizações de cronograma sob demanda.  

## Perguntas frequentes

**Q: Quais formatos de arquivo o GroupDocs.Viewer suporta?**  
A: O GroupDocs.Viewer suporta mais de 100 formatos de entrada, incluindo PDF, DOCX, XLSX, PPTX e arquivos Microsoft Project, permitindo visualização universal de documentos.

**Q: Como começar com uma avaliação gratuita do GroupDocs.Viewer?**  
A: Você pode baixar a versão de avaliação na [GroupDocs Viewer Java download page](https://releases.groupdocs.com/viewer/java/).

**Q: Posso renderizar documentos sem incorporar recursos?**  
A: Sim, você pode escolher uma opção de visualização HTML diferente que referencia recursos externos em vez de incorporá-los.

**Q: E se meu documento for muito grande para renderizar?**  
A: Considere dividir o documento em seções menores ou renderizar apenas o intervalo de datas necessário, como demonstrado acima.

**Q: Como lidar com erros de renderização?**  
A: Verifique todas as configurações, assegure-se de que possui uma licença válida e consulte a documentação do GroupDocs para códigos de erro detalhados.

## Recursos
- **Documentação**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referência da API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Compra**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Teste gratuito**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licença temporária**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Suporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-09-25  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Tutoriais relacionados

- [Como renderizar arquivos MS Project como HTML, JPG, PNG e PDF com notas usando GroupDocs.Viewer para Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Exportação HTML do MS Project: Ajustar unidades de tempo via GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Groupdocs Viewer Java Renderização HTML Responsiva](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)