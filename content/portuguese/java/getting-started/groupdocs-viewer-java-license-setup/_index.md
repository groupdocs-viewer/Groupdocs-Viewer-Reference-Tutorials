---
date: '2026-03-08'
description: Aprenda como obter uma licença temporária, configurar o GroupDocs.Viewer
  para Java usando arquivos locais ou URLs e verificar a disponibilidade do caminho
  da licença.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: Como obter licença temporária e definir licenças no GroupDocs.Viewer Java
type: docs
url: /pt/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

 ensure we keep markdown formatting.

Check for any shortcodes: none.

Make sure we keep code block placeholders unchanged.

Now produce final content.# Como obter licença temporária e definir licenças no GroupDocs.Viewer Java

Gerenciar licenças de forma eficiente é crucial ao integrar bibliotecas de terceiros como **GroupDocs.Viewer for Java** em suas aplicações. Este guia mostra **como obter uma licença temporária**, configurá‑la a partir de um arquivo local ou de uma URL HTTP, e verificar se o caminho da licença está correto. Ao final deste tutorial você terá uma configuração de licenciamento confiável e pronta para produção, que mantém seu aplicativo em conformidade e com bom desempenho.

![File and URL Setup with GroupDocs.Viewer for Java](/viewer/getting-started/file-and-url-setup-png.png)

## Respostas Rápidas
- **Como obtenho uma licença temporária?** Solicite uma na página de licença temporária da GroupDocs e faça o download do arquivo *.lic*.  
- **Posso carregar a licença a partir de uma URL?** Sim – basta apontar `License.setLicense` para um endereço HTTP que retorne um arquivo de licença válido.  
- **O que acontece se o caminho da licença estiver ausente?** Implemente uma verificação para exibir orientações e impedir que o visualizador seja iniciado.  
- **Preciso reiniciar o aplicativo após mudar a licença?** Não, `License.setLicense` pode ser chamado em tempo de execução.  
- **Qual versão do Java é necessária?** Recomenda‑se JDK 8 ou superior.

## O que é uma licença temporária?
Uma **licença temporária** é uma chave de tempo limitado emitida pela GroupDocs que permite avaliar o produto sem comprar uma licença completa. Ela se comporta exatamente como uma licença permanente enquanto for válida, permitindo que você teste todos os recursos em um ambiente real.

## Por que obter uma licença temporária?
- **Avaliação rápida:** Obtenha funcionalidade completa instantaneamente para projetos de prova de conceito.  
- **Sem compromisso financeiro:** Teste antes de comprar.  
- **Integração fácil:** Funciona com as mesmas chamadas de API de uma licença permanente.

## Pré‑requisitos
1. **Java Development Kit (JDK):** Versão 8 ou superior.  
2. **IDE:** IntelliJ IDEA, Eclipse ou qualquer IDE compatível com Java.  
3. **Biblioteca GroupDocs.Viewer for Java:** Adicionada ao seu projeto (veja a configuração Maven abaixo).  
4. **Conhecimento básico de Java:** Familiaridade com classes, imports e tratamento de exceções.

## Configurando o GroupDocs.Viewer para Java
Para começar, inclua a biblioteca em seu projeto Maven.

### Configuração Maven
Add the following configuration to your `pom.xml` file:
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

### Obtendo uma Licença
Para usar o GroupDocs.Viewer, obtenha uma licença:
- **Teste gratuito:** Baixe no [site da GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Licença temporária:** Solicite uma na [página de licença temporária](https://purchase.groupdocs.com/temporary-license/).  
- **Compra:** Para uma solução permanente, considere comprar uma licença na [página de compra da GroupDocs](https://purchase.groupdocs.com/buy).

### Inicialização Básica
Once the library is added, you can initialize the viewer:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## Como obter licença temporária e configurá‑la a partir de um arquivo
### Visão Geral
Configurar uma licença a partir de um arquivo local é a abordagem mais simples e funciona mesmo quando a aplicação está offline.

### Etapas de Implementação
1. **Defina o caminho da licença** – aponte para o arquivo *.lic* que você recebeu após solicitar uma licença temporária:
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **Aplique a licença** – use a classe `License` para carregá‑la:
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Dicas:**  
- Verifique se o caminho do arquivo é absoluto ou relativo ao diretório de trabalho.  
- Garanta que o arquivo tenha permissões de leitura para o usuário que executa a JVM.

## Como lidar com uma URL de licença
### Visão Geral
Uma licença baseada em URL é útil para implantações em nuvem onde o arquivo de licença está em um bucket de armazenamento seguro.

### Etapas de Implementação
1. **Defina a URL da licença** – substitua o placeholder pelo seu endpoint real:
```java
final String licensePath = "http://example.com/license.lic";
```
2. **Detecte e registre o uso da URL** – o exemplo abaixo simplesmente notifica que uma URL foi fornecida:
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**Dicas:**  
- Em produção, você faria o download do arquivo (por exemplo, com `java.net.HttpURLConnection`) e então chamaria `license.setLicense(stream)`.  
- Adicione lógica de repetição e tratamento de timeout para lidar com problemas de rede transitórios.

## Como verificar a disponibilidade da licença (verificar caminho da licença)
### Visão Geral
Antes de tentar carregar uma licença, é uma boa prática **verificar a disponibilidade da licença** para que você possa orientar desenvolvedores ou usuários a obter uma licença temporária quando necessário.

### Etapas de Implementação
1. **Simule um caminho de licença ausente**:
```java
final String licensePath = null;
```
2. **Forneça orientações claras se o caminho estiver ausente**:
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Dicas:**  
- Registre esta mensagem na inicialização para que as equipes de operações saibam que uma licença está ausente.  
- Considere encerrar a aplicação ou desabilitar recursos do visualizador até que uma licença válida seja fornecida.

## Aplicações Práticas
Entender como **obter uma licença temporária**, configurá‑la a partir de um arquivo ou URL, e **verificar a disponibilidade do caminho da licença** desbloqueia vários cenários reais:
1. **Sistemas de Gerenciamento de Documentos** – incorpore um visualizador que valida automaticamente sua licença a cada inicialização.  
2. **Plataformas SaaS em Nuvem** – armazene a licença em um blob storage protegido e carregue‑a via URL para atualizações sem tempo de inatividade.  
3. **Implantações Corporativas** – use uma licença temporária durante fases piloto antes de comprar uma licença em escala total.

## Considerações de Desempenho
- **Uso de recursos:** Carregue a licença uma vez na inicialização da aplicação; chamadas repetidas adicionam I/O desnecessário.  
- **Gerenciamento de memória:** O objeto `License` mantém estado mínimo, mas sempre feche streams se você baixar a licença manualmente.

## Conclusão
Seguindo as etapas acima, você pode **obter uma licença temporária**, configurar o GroupDocs.Viewer para Java usando um arquivo local ou uma URL HTTP, e **verificar a disponibilidade da licença** para manter sua aplicação em conformidade. Essa base sólida de licenciamento previne erros em tempo de execução e oferece a flexibilidade de transitar entre ambientes de desenvolvimento, teste e produção com confiança.

### Perguntas Frequentes

1. **Como configuro um arquivo de licença local no GroupDocs.Viewer Java?**  

   Use `license.setLicense("path/to/license.lic")` com o caminho correto do arquivo para aplicar uma licença local.

2. **Posso carregar uma licença diretamente de uma URL?**  

   Sim, mas assegure que seu código trate o acesso à URL, potencialmente baixando a licença em tempo de execução ou gerenciando problemas de rede.

3. **O que devo fazer se o caminho da licença for inválido ou estiver ausente?**  

   Implemente verificações para caminhos nulos ou inválidos e forneça orientações ou prompts de fallback para obter uma licença válida.

4. **É possível alternar entre arquivo de licença e URL dinamicamente?**  

   Absolutamente, adicionando lógica condicional para lidar com ambos os cenários com base no seu ambiente ou parâmetros de tempo de execução.

5. **Quais são as melhores práticas para gerenciamento de licenças em produção?**  

   Armazene licenças com segurança, verifique sua validade regularmente e implemente tratamento de erros para questões de licença a fim de garantir serviço ininterrupto.

## Perguntas Frequentes

**Q: Quanto tempo dura uma licença temporária?**  
A: Normalmente 30 dias, após os quais você pode solicitar uma renovação ou upgrade para uma licença permanente.

**Q: Preciso de conexão à internet para usar uma licença baseada em arquivo?**  
A: Não. Um arquivo *.lic* local funciona completamente offline depois de carregado.

**Q: Posso criptografar o arquivo de licença para maior segurança?**  
A: O arquivo de licença já é assinado pela GroupDocs; criptografia adicional é opcional, mas não obrigatória.

**Q: O que acontece se a licença expirar enquanto o aplicativo está em execução?**  
A: As operações do visualizador começarão a lançar exceções de licenciamento; recomenda‑se verificar a expiração na inicialização.

**Q: É seguro armazenar a URL da licença no controle de versão?**  
A: Evite commitar URLs sensíveis; use variáveis de ambiente ou armazenamentos de configuração seguros.

---

**Última atualização:** 2026-03-08  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs