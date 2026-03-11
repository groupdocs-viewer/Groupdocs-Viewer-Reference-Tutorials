---
date: '2026-01-10'
description: Aprenda a converter EML para HTML com formato de data e hora personalizado
  e definir o deslocamento de fuso horário em Java usando o GroupDocs.Viewer. Ideal
  para arquivamento de e‑mails e sistemas de suporte.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Converter EML para HTML com Data/Hora Personalizada em Java usando GroupDocs.Viewer
type: docs
url: /pt/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Converter EML para HTML com DateTime Personalizado em Java Usando GroupDocs.Viewer

## Introdução

No mundo digital acelerado de hoje, ser capaz de **converter EML para HTML** rapidamente e com a apresentação correta de data‑hora é essencial para arquivamento, portais de suporte e conformidade legal. Este tutorial orienta você na renderização de mensagens de e‑mail em HTML aplicando um **formato de datetime personalizado** e um **deslocamento de fuso horário** usando o GroupDocs.Viewer para Java. Ao final, você terá uma solução reutilizável que mantém os timestamps precisos e legíveis.

![Renderizar e‑mails com DateTime personalizado com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**O que você aprenderá**
- Como configurar o GroupDocs.Viewer em um projeto Java  
- Como renderizar e‑mails em HTML com recursos incorporados  
- Como **personalizar o formato de data‑hora** das suas mensagens de e‑mail (custom datetime format java)  
- Como **definir o deslocamento de fuso horário** para timestamps corretos (set timezone offset java)  

## Respostas Rápidas
- **O GroupDocs.Viewer pode converter EML para HTML?** Sim, ele renderiza arquivos EML diretamente para HTML.  
- **Preciso de uma licença?** Um teste gratuito funciona para testes; uma licença paga é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior.  
- **Como altero o formato de data exibido?** Use `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Posso ajustar o fuso horário?** Sim, com `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## O que é “converter EML para HTML”?
Converter um arquivo EML para HTML transforma o e‑mail bruto (incluindo cabeçalhos, corpo e anexos) em um formato amigável à web que os navegadores podem exibir sem plugins adicionais. Isso facilita a incorporação de e‑mails em aplicações web, arquivos ou painéis de suporte.

## Por que usar o GroupDocs.Viewer para esta tarefa?
- **Renderização sem dependências** – não é necessário Outlook ou analisadores de e‑mail externos.  
- **Suporte embutido para recursos incorporados** (imagens, anexos).  
- **Controle granular** sobre formatação de data‑hora e manipulação de fuso horário.  

## Pré-requisitos

- **GroupDocs.Viewer for Java** versão 25.2 ou posterior.  
- **Java Development Kit (JDK)** 8+ e uma IDE (IntelliJ IDEA, Eclipse, etc.).  
- Conhecimento básico de Java e familiaridade com Maven.

## Configurando o GroupDocs.Viewer para Java

### Configuração do Maven
Add the GroupDocs repository and dependency to your `pom.xml`:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Comece com um teste gratuito ou solicite uma licença temporária para testes prolongados. Adquira uma licença completa para uso em produção.

### Inicialização Básica
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Converter EML para HTML com DateTime Personalizado em Java

O guia passo a passo a seguir mostra como **converter EML para HTML** aplicando um formato de datetime personalizado e um deslocamento de fuso horário.

### Etapa 1: Configurar Diretório de Saída e Caminho do Arquivo
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Explicação:* `Path.of()` cria uma referência para a pasta onde o HTML será salvo. `resolve()` acrescenta o nome do arquivo.

### Etapa 2: Inicializar o Viewer com o Arquivo de E‑mail
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Explicação:* A instância `Viewer` aponta para o arquivo EML que você deseja converter.

### Etapa 3: Configurar HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Explicação:* `forEmbeddedResources()` agrupa imagens e outros recursos diretamente na saída HTML.

### Etapa 4: Definir Formato de DateTime Personalizado *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Explicação:* Este padrão exibe o mês, dia, ano, hora, minuto, marcador AM/PM e o deslocamento de fuso horário (`zzz`).

### Etapa 5: Definir Deslocamento de Fuso Horário *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Explicação:* Ajusta os timestamps renderizados para o fuso horário desejado. Substitua `"GMT+1"` por qualquer identificador de zona válido.

### Etapa 6: Renderizar Documento
```java
viewer.view(options);
```
*Explicação:* Executa a conversão, produzindo um arquivo HTML com suas configurações de data‑hora personalizadas.

## Dicas de Solução de Problemas
- **FileNotFoundException:** Verifique novamente os caminhos usados em `Viewer` e `Path.of()`.  
- **Timestamps incorretos:** Verifique se o ID do `TimeZone` corresponde à sua região alvo.  
- **Imagens ausentes:** Certifique-se de usar `HtmlViewOptions.forEmbeddedResources()`; caso contrário, recursos externos podem não ser incluídos.  

## Aplicações Práticas
1. **Arquivamento de E‑mail:** Armazene snapshots HTML pesquisáveis de e‑mails para conformidade.  
2. **Portais de Suporte ao Cliente:** Exiba tickets recebidos com horários locais precisos.  
3. **Documentação Legal:** Produza registros de e‑mail prontos para o tribunal com timestamps padronizados.  

## Considerações de Desempenho
- Implante em um servidor dedicado para conversões em lote.  
- Monitore o uso de heap do Java; aumente `-Xmx` se encontrar `OutOfMemoryError`.  
- Cache o HTML renderizado quando o mesmo e‑mail for solicitado repetidamente.  

## Conclusão
Agora você tem um método completo e pronto para produção para **converter EML para HTML** com um formato de datetime personalizado e deslocamento de fuso horário usando o GroupDocs.Viewer para Java. Isso melhora a legibilidade, garante a precisão dos timestamps e se integra perfeitamente a fluxos de trabalho de arquivamento ou suporte.

**Próximos passos:** Explore opções adicionais do Viewer, como estilização CSS, paginação ou conversão para PDF, para adaptar ainda mais a saída às suas necessidades.

## Perguntas Frequentes

**Q: Como eu lido com arquivos EML com anexos?**  
A: Os anexos são incorporados automaticamente quando você usa `HtmlViewOptions.forEmbeddedResources()`. Você também pode extraí‑los via API do Viewer, se necessário.

**Q: Posso mudar o modelo HTML ou adicionar CSS personalizado?**  
A: Sim, após a renderização você pode editar o arquivo HTML gerado ou injetar CSS programaticamente antes de salvar.

**Q: É possível renderizar vários arquivos EML em lote?**  
A: Envolva a lógica de renderização em um loop e reutilize a mesma instância de `HtmlViewOptions` para cada arquivo.

**Q: E se eu precisar suportar outros formatos de e‑mail como MSG?**  
A: O GroupDocs.Viewer também suporta MSG, PST e outros contêineres de e‑mail — basta mudar a extensão do arquivo no construtor `Viewer`.

**Q: Preciso de uma licença separada para cada servidor?**  
A: A licença é por implantação; consulte o guia de licenciamento do GroupDocs para cenários multi‑servidor.

## Recursos

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-01-10  
**Testado com:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs  

---