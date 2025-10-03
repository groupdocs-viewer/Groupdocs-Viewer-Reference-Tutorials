---
"description": "Aprimore a experiência de visualização de documentos com o GroupDocs.Viewer para .NET. Renderize e personalize e-mails perfeitamente."
"linktitle": "Renomear campos de e-mail durante a renderização"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renomear campos de e-mail durante a renderização"
"url": "/pt/net/rendering-email-messages/rename-email-fields/"
"weight": 12
type: docs
---
# Renomear campos de e-mail durante a renderização

## Introdução

Na era digital atual, gerenciar e visualizar documentos com eficiência é essencial para empresas e indivíduos. Sejam contratos, relatórios ou e-mails, ter a capacidade de navegar por esses documentos sem interrupções pode aumentar significativamente a produtividade. É aí que o GroupDocs.Viewer para .NET entra em ação. Esta poderosa biblioteca permite que desenvolvedores integrem recursos de visualização de documentos diretamente em seus aplicativos .NET, oferecendo uma ampla gama de recursos para renderizar diversos formatos de documentos.

## Pré-requisitos

Antes de mergulhar no tutorial sobre como renomear campos de e-mail durante a renderização usando o GroupDocs.Viewer para .NET, certifique-se de ter os seguintes pré-requisitos:

1. Biblioteca GroupDocs.Viewer para .NET: Baixe e instale a biblioteca GroupDocs.Viewer para .NET em [aqui](https://releases.groupdocs.com/viewer/net/).

2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento adequado configurado para o desenvolvimento .NET, como o Visual Studio.

3. Noções básicas de C#: familiarize-se com os conceitos básicos da linguagem de programação C#, pois o tutorial envolverá trechos de código C#.

4. Diretório de documentos: prepare um diretório onde os documentos a serem renderizados serão armazenados.

## Importar namespaces

Para usar as funcionalidades do GroupDocs.Viewer em seu aplicativo .NET, você precisa importar os namespaces necessários.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora vamos dividir o processo de renomeação de campos de e-mail durante a renderização usando o GroupDocs.Viewer para .NET em várias etapas:

## Etapa 1: definir diretório de saída

Primeiro, especifique o diretório onde as páginas HTML renderizadas serão salvas.

```csharp
string outputDirectory = "Your Document Directory";
```

## Etapa 2: Definir o formato do caminho do arquivo de página

Defina o formato dos caminhos de arquivo das páginas HTML renderizadas. Cada página será salva como um arquivo HTML separado.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Etapa 3: Inicializar objeto do visualizador

Crie uma instância da classe Viewer e passe o caminho do documento a ser visualizado como parâmetro.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Etapa 4: Configurar opções de visualização HTML

Configure as opções para visualização em HTML, incluindo a especificação do formato do arquivo de saída e a configuração de mapeamentos de campos de e-mail.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Etapa 5: Renderizar documento

Chame o método View do objeto Viewer, passando as opções de visualização HTML configuradas.

```csharp
viewer.View(options);
```

## Etapa 6: Exibir mensagem de sucesso

Informe ao usuário que o documento foi renderizado com sucesso.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão

Concluindo, o GroupDocs.Viewer para .NET oferece uma solução integrada para a renderização de documentos em aplicativos .NET. Seguindo os passos descritos neste tutorial, você pode renomear facilmente os campos de e-mail durante a renderização, melhorando a legibilidade e a usabilidade dos documentos de e-mail. Com sua API intuitiva e recursos abrangentes, o GroupDocs.Viewer capacita os desenvolvedores a otimizar os processos de visualização de documentos de forma eficaz.

## Perguntas frequentes

### P: Posso renderizar documentos que não sejam e-mails usando o GroupDocs.Viewer para .NET?

R: Sim, o GroupDocs.Viewer suporta renderização de vários formatos de documentos, incluindo PDF, documentos do Microsoft Office, imagens e muito mais.

### P: O GroupDocs.Viewer é compatível com o .NET Core?

R: Sim, o GroupDocs.Viewer suporta o .NET Core e o .NET Framework tradicional.

### P: Posso personalizar a aparência dos documentos renderizados?

R: Com certeza, o GroupDocs.Viewer oferece amplas opções de personalização para controlar a aparência e o comportamento dos documentos renderizados.

### P: O GroupDocs.Viewer suporta streaming de documentos?

R: Sim, o GroupDocs.Viewer permite transmitir documentos diretamente para o navegador do cliente sem a necessidade de armazená-los no servidor.

### P: O GroupDocs.Viewer é adequado para aplicativos de nível empresarial?

R: Certamente, o GroupDocs.Viewer foi projetado para atender às demandas de aplicativos de nível empresarial com sua escalabilidade, confiabilidade e conjunto robusto de recursos.