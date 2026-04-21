---
date: '2026-03-24'
description: Aprenda como converter e‑mail para HTML e renomear campos de e‑mail usando
  o GroupDocs Viewer para Java. Este guia mostra como renderizar e‑mail como HTML
  com cabeçalhos personalizados.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Converter Email para HTML e Renomear Campos – GroupDocs Viewer Java
type: docs
url: /pt/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Converter Email para HTML e Renomear Campos – GroupDocs Viewer Java

Se você precisa **converter email para HTML** enquanto dá aos cabeçalhos de email um visual personalizado, está no lugar certo. Neste tutorial vamos percorrer passo a passo como renomear campos de email, **converter email para HTML** e personalizar os cabeçalhos de email usando o GroupDocs.Viewer para Java. Ao final, você terá uma representação HTML limpa com os nomes de cabeçalho que preferir, facilitando a leitura e a integração nos seus aplicativos.

![Renomear campos de email ao converter emails para HTML com GroupDocs.Viewer para Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### O que você aprenderá
- Como usar o GroupDocs.Viewer para Java para **converter email para HTML**.  
- Técnicas para **renomear campos de email** como “From”, “To”, “Sent” e “Subject”.  
- Melhores práticas para configurar Maven e licenciamento.  
- Cenários reais onde **personalizar cabeçalhos de email** agrega valor.

## Respostas Rápidas
- **O que significa “converter email para HTML”?** Significa renderizar um arquivo de email (MSG/EML) como um documento HTML pronto para a web.  
- **Qual biblioteca realiza a conversão?** GroupDocs.Viewer para Java (v25.2+).  
- **Preciso de licença?** Uma avaliação funciona para testes; uma licença completa é necessária para produção.  
- **Posso mudar qualquer nome de cabeçalho?** Sim, qualquer cabeçalho padrão de email pode ser remapeado via `fieldTextMap`.  
- **A saída é HTML ou recursos incorporados?** Você pode escolher recursos incorporados para um único arquivo autônomo.

## O que significa “converter email para HTML” no contexto do GroupDocs.Viewer?
Converter email para HTML significa pegar um arquivo de email bruto e produzir uma página HTML que exibe o corpo da mensagem junto com seus metadados. Quando você também **renomeia campos de email**, os rótulos padrão (por exemplo, “From”) são substituídos por texto personalizado (por exemplo, “Remetente”), o que ajuda a alinhar a terminologia corporativa ou melhorar a consistência da UI.

## Por que converter email para HTML e renomear campos de email?
- **Branding consistente:** Alinha a saída com a linguagem da sua organização.  
- **Melhor indexação:** Cabeçalhos personalizados podem ser indexados de forma mais eficaz em sistemas de arquivamento.  
- **Integração UI aprimorada:** Adapte o trecho HTML para se encaixar perfeitamente em portais web ou painéis de suporte.

## Pré-requisitos

### Bibliotecas, versões e dependências necessárias
- **GroupDocs.Viewer para Java** – versão 25.2 ou posterior.  
- **Java Development Kit (JDK)** – versão 8+.

### Requisitos de configuração do ambiente
- **Maven** para gerenciamento de dependências.  
- Uma IDE como IntelliJ IDEA, Eclipse ou VS Code.

### Pré-requisitos de conhecimento
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

### Etapas para aquisição de licença
- **Teste gratuito:** Baixe um teste gratuito em [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
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

## Como converter email para HTML e renomear campos – Passo a passo

### 1. Configurar o caminho do diretório de saída
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Substitua `"YOUR_OUTPUT_DIRECTORY"` pela pasta onde deseja salvar os arquivos HTML.*

### 2. Definir o formato do caminho do arquivo de página
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` será substituído pelo número da página durante a renderização.*

### 3. Criar um mapeamento dos campos de email para novos nomes
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
*Aqui alteramos os rótulos padrão para nomes personalizados.*

### 4. Configurar opções de visualização HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` agrupa CSS/JS dentro do HTML, enquanto `setFieldTextMap` aplica os nomes de cabeçalho personalizados.*

### 5. Renderizar o email para HTML
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

## Aplicações práticas
1. **Relatórios de email personalizados:** Alinhe os cabeçalhos de email com a terminologia corporativa para relatórios mais claros.  
2. **Sistemas de arquivamento de email:** Melhore a indexação usando nomes de cabeçalho padronizados.  
3. **Plataformas de suporte ao cliente:** Apresente tickets com rótulos de cabeçalho personalizados para melhorar a experiência do agente.

## Considerações de desempenho
- Libere objetos `Viewer` com try‑with‑resources para liberar memória rapidamente.  
- Perfis de lotes grandes e considere processar emails em streams paralelos, se necessário.

## Conclusão
Agora você sabe **como converter email para HTML** enquanto **renomeia campos de email** e **personaliza cabeçalhos de email** com o GroupDocs.Viewer para Java. Essa técnica oferece controle total sobre a apresentação dos metadados de email nas saídas HTML.

### Próximos passos
- Experimente mapeamentos adicionais de campos (por exemplo, CC, BCC).  
- Explore outros formatos de renderização como PDF ou PNG.  
- Visite a [Documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/) para aprofundar o conhecimento da API.

## Perguntas Frequentes

**Q: Esse método funciona com outros formatos de email, como EML?**  
A: Sim, o GroupDocs.Viewer suporta arquivos MSG e EML; a mesma lógica de mapeamento de campos se aplica.

**Q: Posso gerar o HTML sem recursos incorporados?**  
A: Você pode usar `HtmlViewOptions.forExternalResources(...)` se preferir arquivos CSS/JS separados.

**Q: Qual versão do GroupDocs.Viewer foi testada?**  
A: O código foi testado com o GroupDocs.Viewer **25.2**.

**Q: É possível mudar a fonte ou o estilo dos cabeçalhos personalizados?**  
A: A estilização pode ser aplicada via CSS após a renderização, ou você pode injetar CSS personalizado usando `HtmlViewOptions.getResourcesPath()`.

**Q: Como obter programaticamente o caminho do arquivo HTML gerado?**  
A: O caminho segue o padrão definido em `pageFilePathFormat`; você pode construí‑lo usando `String.format` com o número da página.

## Recursos
- **Documentação:** Guias completos estão disponíveis em [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referência da API:** Informações detalhadas da API podem ser encontradas em [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download do GroupDocs.Viewer:** Acesse a versão mais recente através da [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Last Updated:** 2026-03-24  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs