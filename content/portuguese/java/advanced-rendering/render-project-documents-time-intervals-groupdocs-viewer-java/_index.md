---
date: '2026-01-15'
description: Aprenda a usar o GroupDocs Viewer para gerar HTML a partir de documentos
  de projetos em intervalos de tempo específicos. Este guia cobre a configuração,
  o código e casos de uso reais.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Como usar o GroupDocs Viewer para renderizar documentos de projeto por intervalos
  de tempo em Java
type: docs
url: /pt/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Como Usar o GroupDocs Viewer para Renderizar Documentos de Projeto por Intervalos de Tempo em Java

Se você está procurando **como usar o GroupDocs** para renderizar cronogramas de projetos em uma janela de tempo focada, você está no lugar certo. Neste tutorial, percorreremos todo o processo — desde a configuração do Maven até a geração de HTML a partir de documentos de projeto — para que você possa incorporar visualizações de linha do tempo precisas diretamente em suas aplicações.

![Renderizar Documentos de Projeto por Intervalos de Tempo com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Respostas Rápidas
- **O que a funcionalidade faz?** Ela renderiza apenas a parte de um arquivo Microsoft Project que está entre uma data de início e uma data de término.  
- **Qual formato de saída é usado?** HTML com recursos incorporados, perfeito para integração web.  
- **Preciso de uma licença?** Um teste gratuito funciona para avaliação; uma licença completa é necessária para produção.  
- **Posso alterar o intervalo de datas em tempo de execução?** Sim — ajuste os valores `setStartDate` e `setEndDate` nas opções de renderização.  
- **Isso é suportado em todas as versões do Java?** Funciona com Java 8+ desde que você use o GroupDocs.Viewer 25.2 ou mais recente.

## O Que Significa “Como Usar o GroupDocs” Neste Contexto?
GroupDocs Viewer é uma biblioteca Java que converte mais de 100 formatos de arquivo em representações amigáveis para a web. Quando você **como usar o GroupDocs** para arquivos de projeto, ganha a capacidade de extrair, visualizar e compartilhar dados de cronograma sem precisar do Microsoft Project no lado do cliente.

## Por Que Renderizar Documentos de Projeto com Intervalos de Tempo?
- **Análise focada:** Mostre apenas a fase que você deseja (por exemplo, Q3 2024).  
- **Desempenho:** Saída HTML menor significa carregamento de página mais rápido.  
- **Integração:** Incorpore visualizações de linha do tempo em dashboards, portais de relatórios ou ferramentas de gerenciamento de projetos personalizadas.  

## Pré-requisitos

- **GroupDocs.Viewer for Java** versão 25.2 ou superior.  
- Java Development Kit (JDK) 8 ou mais recente.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Conhecimento básico de Maven.  

## Configurando o GroupDocs.Viewer para Java

### Dependência Maven

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

### Etapas de Aquisição de Licença

1. **Teste Gratuito** – Baixe uma versão de teste a partir da [página de download do GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Licença Temporária** – Obtenha uma licença temporária para testes estendidos via [este link](https://purchase.groupdocs.com/temporary-license/).  
3. **Compra** – Para uso de produção sem restrições, compre uma licença na [Página de Compra do GroupDocs](https://purchase.groupdocs.com/buy).

### Inicialização Básica do Viewer

O trecho a seguir mostra como criar uma instância `Viewer` que aponta para um arquivo Microsoft Project (`.mpp`):

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

## Guia de Implementação Passo a Passo

### 1. Defina o Diretório de Saída

Crie uma pasta onde as páginas HTML geradas serão salvas:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Por quê?* Manter os arquivos renderizados organizados facilita servi‑los a partir de um servidor web ou incorporá‑los em uma interface.

### 2. Inicialize o Viewer com Seu Arquivo de Projeto

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Por quê?* Carregar o documento prepara o analisador interno e torna os metadados específicos do projeto acessíveis.

### 3. Recupere Informações de Visualização para Arquivos de Projeto

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Por quê?* `ProjectManagementViewInfo` fornece as datas de início e término do cronograma, que você usará posteriormente para limitar o escopo da renderização.

### 4. Configure Opções de Renderização HTML (Gerar HTML a partir do Projeto)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Por quê?* Definir `StartDate` e `EndDate` indica ao GroupDocs para **gerar HTML a partir do projeto** apenas dentro desse intervalo.

### 5. Execute o Processo de Renderização

```java
viewer.view(viewOptions);
```

*Por quê?* Esta chamada produz uma série de páginas HTML autônomas que representam o segmento de tempo selecionado do seu cronograma de projeto.

## Armadilhas Comuns & Solução de Problemas

- **Caminhos de arquivo incorretos** – Verifique se tanto o arquivo fonte `.mpp` quanto o diretório de saída existem.  
- **Tipo de arquivo não suportado** – Certifique-se de que o documento está em um formato de Project suportado (por exemplo, `.mpp`, `.mpt`).  
- **Erros de licença** – Uma licença de teste pode impor limites de renderização; troque para uma licença completa para uso sem restrições.  

## Aplicações Práticas

1. **Análise da Linha do Tempo do Projeto** – Mostre aos interessados apenas a fase atual.  
2. **Relatórios Automatizados** – Gere relatórios HTML com limite de tempo para atualizações de status semanais.  
3. **Integração com Dashboards** – Incorpore as páginas renderizadas em ferramentas de BI ou portais personalizados.  
4. **Arquivamento** – Armazene uma captura da agenda do projeto em formato web‑amigável para referência futura.  

## Dicas de Desempenho

- Use a opção de *recursos incorporados* para manter cada página HTML autônoma, reduzindo requisições HTTP.  
- Para projetos muito grandes, considere renderizar em blocos de datas menores para manter o uso de memória baixo.  
- Limpe arquivos temporários após o serviço para evitar inchaço de disco.  

## Conclusão

Agora você sabe **como usar o GroupDocs** Viewer para renderizar documentos de projeto dentro de um intervalo de tempo específico e **gerar HTML a partir do projeto** em Java. Essa capacidade simplifica visualizações de linhas do tempo, melhora a eficiência de relatórios e integra-se perfeitamente com aplicações web modernas.

### Próximos Passos
- Explore recursos adicionais do Viewer, como marca d'água, proteção por senha ou estilização CSS personalizada.  
- Combine este pipeline de renderização com uma API REST para servir visualizações de linha do tempo sob demanda.  

## Perguntas Frequentes

**Q: Quais formatos de arquivo o GroupDocs.Viewer suporta?**  
A: O GroupDocs.Viewer suporta uma ampla variedade de formatos, incluindo Microsoft Project (MPP), PDF, Word, Excel, PowerPoint e muitos outros.

**Q: Como começar com um teste gratuito do GroupDocs.Viewer?**  
A: Você pode baixar a versão de teste a partir de [aqui](https://releases.groupdocs.com/viewer/java/).

**Q: Posso renderizar documentos sem incorporar recursos?**  
A: Sim, você pode escolher uma opção de visualização HTML diferente que referencia recursos externos em vez de incorporá‑los.

**Q: E se meu documento for muito grande para renderizar?**  
A: Considere dividir o documento em seções menores ou renderizar apenas o intervalo de datas necessário, como demonstrado acima.

**Q: Como lidar com erros de renderização?**  
A: Verifique todas as configurações, assegure‑se de que possui uma licença válida e consulte a documentação do GroupDocs para códigos de erro detalhados.

## Recursos
- **Documentação**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referência de API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Compra**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Teste Gratuito**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licença Temporária**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Suporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-01-15  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs