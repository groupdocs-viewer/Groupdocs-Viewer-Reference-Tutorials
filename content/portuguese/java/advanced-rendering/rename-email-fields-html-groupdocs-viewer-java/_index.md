---
date: '2026-01-05'
description: Aprenda a renomear campos de e‑mail, converter e‑mail para HTML e personalizar
  cabeçalhos de e‑mail usando o GroupDocs.Viewer para Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Como Renomear Campos de Email ao Renderizar Emails em HTML com GroupDocs.Viewer
  Java
type: docs
url: /pt/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Como Renomear Campos de Email ao Renderizar Emails para HTML com GroupDocs.Viewer Java

Você está se perguntando **como renomear email** campos ao converter um email para HTML? Neste guia, percorreremos os passos exatos para renomear campos de email, **converter email para HTML**, e **personalizar cabeçalhos de email** usando GroupDocs.Viewer para Java. Ao final, você terá uma representação HTML limpa com os nomes de cabeçalho preferidos, facilitando a leitura e a integração da saída em suas aplicações.

![Renomear Campos de Email ao Converter Emails para HTML com GroupDocs.Viewer para Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### O que você aprenderá
- Como usar o GroupDocs.Viewer para Java para **converter email para HTML**.  
- Técnicas para **renomear campos de email** como “From”, “To”, “Sent” e “Subject”.  
- Melhores práticas para configurar Maven e licenciamento.  
- Cenários do mundo real onde **personalizar cabeçalhos de email** agrega valor.

## Respostas Rápidas
- **O que significa “how to rename email”?** Refere‑se ao mapeamento dos nomes padrão dos cabeçalhos de email para rótulos personalizados durante a renderização.  
- **Qual biblioteca lida com a conversão?** GroupDocs.Viewer para Java (v25.2+).  
- **Preciso de uma licença?** Uma versão de avaliação funciona para testes; uma licença completa é necessária para produção.  
- **Posso mudar qualquer nome de cabeçalho?** Sim, qualquer cabeçalho padrão de email pode ser remapeado via `fieldTextMap`.  
- **A saída é HTML ou recursos incorporados?** Você pode escolher recursos incorporados para um único arquivo autônomo.

## O que é “How to Rename Email” no contexto do GroupDocs.Viewer?
Renomear campos de email significa substituir os rótulos padrão (por exemplo, “From”) por texto personalizado (por exemplo, “Sender”) quando o email é renderizado para HTML. Isso é útil para alinhar a saída com a terminologia corporativa ou melhorar a legibilidade para o usuário final.

## Por que converter email para HTML e personalizar cabeçalhos de email?
- **Branding consistente:** Alinhe a linguagem da sua organização em todas as comunicações.  
- **Melhor capacidade de busca:** Cabeçalhos personalizados podem ser indexados de forma mais eficaz em sistemas de arquivamento.  
- **Integração de UI aprimorada:** Ajuste o trecho HTML para se encaixar perfeitamente em portais web ou painéis de suporte.

## Pré‑requisitos

### Bibliotecas, versões e dependências necessárias
- **GroupDocs.Viewer for Java** – versão 25.2 ou posterior.  
- **Java Development Kit (JDK)** – versão 8+.

### Requisitos de configuração do ambiente
- **Maven** para gerenciamento de dependências.  
- Uma IDE como IntelliJ IDEA, Eclipse ou VS Code.

### Pré‑requisitos de conhecimento
Familiaridade básica com Java e Maven ajudará a acompanhar rapidamente.

## Configurando o GroupDocs.Viewer para Java

### Configuração do Maven
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
- **Teste gratuito:** Baixe uma versão de teste em [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licença temporária:** Obtenha uma licença temporária para explorar todos os recursos sem limitações em [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Compra:** Para uso contínuo, considere adquirir uma licença através de [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inicialização e configuração básicas
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Ajuste o caminho do arquivo para apontar para o seu arquivo `.msg`.

## Guia de Implementação

### Renomeando Campos de Email – Passo a Passo

#### 1. Configurar o caminho do diretório de saída
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Substitua `"YOUR_OUTPUT_DIRECTORY"` pela pasta onde deseja salvar os arquivos HTML.*

#### 2. Definir o formato do caminho do arquivo de página
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` será substituído pelo número da página durante a renderização.*

#### 3. Criar um mapeamento dos campos de email para novos nomes
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Aqui alteramos os rótulos padrão para personalizados.*

#### 4. Configurar opções de visualização HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` agrupa CSS/JS dentro do HTML, enquanto `setFieldTextMap` aplica os nomes de cabeçalho personalizados.*

#### 5. Renderizar o email para HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Substitua `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` pelo caminho real do seu arquivo MSG.*

#### Dicas de solução de problemas
- Verifique se o diretório de saída tem permissão de gravação.  
- Certifique‑se de que o arquivo MSG de entrada existe e o caminho está correto.  
- Use a mesma versão do GroupDocs.Viewer (25.2) declarada no Maven.

## Aplicações Práticas
1. **Relatórios de Email Personalizados:** Alinhe os cabeçalhos de email com a terminologia corporativa para relatórios mais claros.  
2. **Sistemas de Arquivamento de Email:** Melhore a capacidade de busca usando nomes de cabeçalho padronizados.  
3. **Plataformas de Suporte ao Cliente:** Apresente tickets com rótulos de cabeçalho personalizados para melhorar a experiência dos agentes.

## Considerações de Performance
- Libere objetos `Viewer` usando try‑with‑resources para liberar memória rapidamente.  
- Faça profiling de lotes grandes e considere processar emails em streams paralelos, se necessário.

## Conclusão
Agora você sabe **como renomear campos de email** ao **converter email para HTML** e **personalizar cabeçalhos de email** com o GroupDocs.Viewer para Java. Essa técnica oferece controle total sobre a apresentação dos metadados de email nas saídas HTML.

### Próximos passos
- Experimente mapeamentos adicionais de campos (por exemplo, CC, BCC).  
- Explore outros formatos de renderização como PDF ou PNG.  
- Visite [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) para obter insights mais profundos da API.

## Seção de Perguntas Frequentes
1. **Posso renomear todos os cabeçalhos de email usando este método?**  
   - Sim, você pode mapear qualquer cabeçalho padrão de email para um novo nome conforme suas necessidades.  
2. **É possível usar o GroupDocs.Viewer sem licença?**  
   - Uma versão de teste está disponível para avaliação, mas a versão completa requer uma licença válida.  
3. **Como lidar com grandes volumes de emails de forma eficiente com o GroupDocs.Viewer?**  
   - Considere o processamento em lote e otimize os recursos do sistema para gerenciar conjuntos de dados maiores de forma eficaz.  
4. **Posso integrar esta solução em uma aplicação Java existente?**  
   - Absolutamente, a integração é simples usando dependências Maven.  
5. **Onde posso encontrar suporte se encontrar problemas?**  
   - Visite o [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) para assistência da comunidade e oficial.

## Perguntas Frequentes

**Q: Essa abordagem funciona com outros formatos de email como EML?**  
A: Sim, o GroupDocs.Viewer suporta arquivos MSG e EML; a mesma lógica de mapeamento de campos se aplica.

**Q: Posso gerar o HTML sem recursos incorporados?**  
A: Você pode usar `HtmlViewOptions.forExternalResources(...)` se preferir arquivos CSS/JS separados.

**Q: Qual versão do GroupDocs.Viewer foi testada?**  
A: O código foi testado com o GroupDocs.Viewer **25.2**.

**Q: É possível alterar a fonte ou o estilo dos cabeçalhos personalizados?**  
A: A estilização pode ser aplicada via CSS após a renderização, ou você pode injetar CSS personalizado usando `HtmlViewOptions.getResourcesPath()`.

**Q: Como recuperar programaticamente o caminho do arquivo HTML gerado?**  
A: O caminho do arquivo segue o padrão definido em `pageFilePathFormat`; você pode construí‑lo usando `String.format` com o número da página.

## Recursos
- **Documentação:** Guias abrangentes estão disponíveis em [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referência da API:** Informações detalhadas da API podem ser encontradas em [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download do GroupDocs.Viewer:** Acesse a versão mais recente através da [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Última atualização:** 2026-01-05  
**Testado com:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs  

---