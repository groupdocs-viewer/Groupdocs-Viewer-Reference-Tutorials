---
date: '2026-03-29'
description: Aprenda como criar visualização HTML de arquivos MPP usando o GroupDocs
  Viewer em Java, renderizando documentos de projeto por intervalos de tempo com código
  passo a passo.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Criar visualização HTML de MPP com GroupDocs Viewer (Java)
type: docs
url: /pt/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Como Usar o GroupDocs Viewer para Renderizar Documentos de Projeto por Intervalos de Tempo em Java

Neste tutorial você aprenderá como **create html view mpp** com o GroupDocs Viewer para Java, permitindo renderizar apenas as partes de um arquivo Microsoft Project que se enquadram em um intervalo de tempo específico. Vamos percorrer a configuração do Maven, a configuração do código e cenários do mundo real para que você possa incorporar visualizações de linha do tempo precisas diretamente em suas aplicações.

![Renderizar Documentos de Projeto por Intervalos de Tempo com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Respostas Rápidas
- **O que a funcionalidade faz?** Ele renderiza apenas a parte de um arquivo Microsoft Project que está entre uma data de início e uma data de término.  
- **Qual formato de saída é usado?** HTML com recursos incorporados, perfeito para integração web.  
- **Preciso de uma licença?** Um teste gratuito funciona para avaliação; uma licença completa é necessária para produção.  
- **Posso alterar o intervalo de datas em tempo de execução?** Sim—ajuste os valores `setStartDate` e `setEndDate` nas opções de renderização.  
- **Isso é suportado em todas as versões do Java?** Funciona com Java 8+ desde que você use o GroupDocs.Viewer 25.2 ou mais recente.

## Como criar html view mpp para Documentos de Projeto
O GroupDocs Viewer pode converter arquivos Microsoft Project (`.mpp`, `.mpt`) em páginas HTML. Ao configurar as datas de início e término nas opções de renderização, você limita a saída ao intervalo de tempo desejado, o que reduz o tamanho do arquivo e acelera o carregamento das páginas.

## O Que Significa “How to Use GroupDocs” Neste Contexto?
O GroupDocs Viewer é uma biblioteca Java que converte mais de 100 formatos de arquivo para representações amigáveis à web. Quando você **how to use GroupDocs** para arquivos de projeto, ganha a capacidade de extrair, visualizar e compartilhar dados de cronograma sem exigir o Microsoft Project no lado do cliente.

## Por Que Renderizar Documentos de Projeto com Intervalos de Tempo?
- **Análise focada:** Mostre apenas a fase que lhe interessa (por exemplo, Q3 2024).  
- **Desempenho:** Saída HTML menor significa carregamento de página mais rápido.  
- **Integração:** Incorpore visualizações de linha do tempo em painéis, portais de relatórios ou ferramentas PM personalizadas.  

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

### Etapas para Obtenção de Licença

1. **Free Trial** – Baixe uma versão de teste em [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Obtenha uma licença temporária para testes estendidos via [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Para uso de produção sem restrições, compre uma licença em [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

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

### 4. Configure as Opções de Renderização HTML (Gerar HTML a partir do Projeto)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Por quê?* Definir `StartDate` e `EndDate` indica ao GroupDocs para **generate html view mpp** apenas dentro desse intervalo.

### 5. Execute o Processo de Renderização

```java
viewer.view(viewOptions);
```

*Por quê?* Esta chamada produz uma série de páginas HTML autônomas que representam o segmento de tempo selecionado do cronograma do seu projeto.

## Armadilhas Comuns & Solução de Problemas
- **Caminhos de arquivo incorretos** – Verifique novamente se tanto o arquivo `.mpp` de origem quanto o diretório de saída existem.  
- **Tipo de arquivo não suportado** – Certifique-se de que o documento esteja em um formato de Project suportado (por exemplo, `.mpp`, `.mpt`).  
- **Erros de licença** – Uma licença de teste pode impor limites de renderização; troque para uma licença completa para uso sem restrições.  

## Aplicações Práticas
1. **Análise da Linha do Tempo do Projeto** – Mostre aos interessados apenas a fase atual.  
2. **Relatórios Automatizados** – Gere relatórios HTML com limite de tempo para atualizações de status semanais.  
3. **Integração com Painéis** – Incorpore as páginas renderizadas em ferramentas de BI ou portais personalizados.  
4. **Arquivamento** – Armazene uma captura web‑amigável do cronograma do projeto para referência futura.  

## Dicas de Desempenho
- Use a opção de *embedded resources* para manter cada página HTML autônoma, reduzindo solicitações HTTP.  
- Para projetos muito grandes, considere renderizar em blocos de datas menores para manter o uso de memória baixo.  
- Limpe arquivos temporários após servi‑los para evitar inchaço de disco.  

## Conclusão
Agora você sabe **how to use GroupDocs** Viewer para renderizar documentos de projeto dentro de um intervalo de tempo específico e **generate HTML from project** dados em Java. Essa capacidade simplifica visualizações de linha do tempo, melhora a eficiência de relatórios e integra‑se suavemente com aplicações web modernas.

### Próximos Passos
- Explore recursos adicionais do Viewer, como marca d'água, proteção por senha ou estilização CSS personalizada.  
- Combine este pipeline de renderização com uma API REST para servir visualizações de linha do tempo sob demanda.  

## Perguntas Frequentes

**Q: Quais formatos de arquivo o GroupDocs.Viewer suporta?**  
A: O GroupDocs.Viewer suporta uma ampla variedade de formatos, incluindo Microsoft Project (MPP), PDF, Word, Excel, PowerPoint e muitos outros.

**Q: Como começar com uma versão de teste gratuita do GroupDocs.Viewer?**  
A: Você pode baixar a versão de teste em [aqui](https://releases.groupdocs.com/viewer/java/).

**Q: Posso renderizar documentos sem incorporar recursos?**  
A: Sim, você pode escolher uma opção de visualização HTML diferente que referencia recursos externos em vez de incorporá‑los.

**Q: E se meu documento for muito grande para renderizar?**  
A: Considere dividir o documento em seções menores ou renderizar apenas o intervalo de datas necessário, como demonstrado acima.

**Q: Como lidar com erros de renderização?**  
A: Verifique todas as configurações, assegure que você possui uma licença válida e consulte a documentação do GroupDocs para códigos de erro detalhados.

## Recursos
- **Documentação**: [Documentação do GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)  
- **Referência de API**: [Referência de API do GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Downloads do GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Compra**: [Comprar Licença do GroupDocs](https://purchase.groupdocs.com/buy)  
- **Teste Gratuito**: [Experimentar a Versão Gratuita](https://releases.groupdocs.com/viewer/java/)  
- **Licença Temporária**: [Obter uma Licença Temporária](https://purchase.groupdocs.com/temporary-license/)  
- **Suporte**: [Fórum do GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Última Atualização:** 2026-03-29  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

---