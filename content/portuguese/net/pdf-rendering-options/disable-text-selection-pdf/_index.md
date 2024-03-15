---
title: Desativar seleção de texto em PDF
linktitle: Desativar seleção de texto em PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda como desabilitar a seleção de texto em PDF usando GroupDocs.Viewer for .NET. Siga nosso guia passo a passo para uma integração perfeita.
type: docs
weight: 13
url: /pt/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Introdução
GroupDocs.Viewer for .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores integrar recursos de visualização de documentos em seus aplicativos .NET sem esforço. Uma das principais funcionalidades fornecidas pelo GroupDocs.Viewer é a capacidade de desabilitar a seleção de texto em documentos PDF. Esse recurso é particularmente útil em cenários onde você precisa impedir que os usuários copiem texto de documentos confidenciais, garantindo a segurança e a integridade dos documentos.
## Pré-requisitos
Antes de mergulharmos no guia passo a passo sobre como desabilitar a seleção de texto em PDF usando GroupDocs.Viewer for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Instalação do GroupDocs.Viewer for .NET: Certifique-se de ter baixado e instalado o GroupDocs.Viewer for .NET a partir do[Link para Download](https://releases.groupdocs.com/viewer/net/).
2. Diretório de documentos: Prepare um diretório onde seus documentos serão armazenados. Você precisará especificar esse diretório no trecho de código para renderizar o documento PDF.

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para acessar as funcionalidades fornecidas pelo GroupDocs.Viewer for .NET. Veja como você pode fazer isso:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos dividir o processo de desabilitar a seleção de texto em um documento PDF usando GroupDocs.Viewer for .NET em várias etapas:
## Etapa 1: especificar o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
 Nesta etapa, substitua`"Your Document Directory"` com o caminho do diretório onde seu documento PDF está localizado.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Esta etapa define o formato dos caminhos de arquivo das páginas HTML renderizadas. Cada página do documento PDF será convertida em um arquivo HTML com um número de página sequencial.
## Etapa 3: Renderizar documento PDF com seleção de texto desativada
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Substituir`"Path to Your PDF Document"` com o caminho real para o seu arquivo PDF. Este trecho de código inicializa um`Viewer` objeto, configura opções de visualização HTML para incorporar recursos e desativa a seleção de texto definindo`RenderTextAsImage` propriedade para`true`.
## Etapa 4: exibir mensagem de sucesso
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Após renderizar o documento PDF, esta etapa exibe uma mensagem de sucesso junto com o diretório onde as páginas HTML renderizadas estão armazenadas.

## Conclusão
Neste tutorial, aprendemos como desabilitar a seleção de texto em documentos PDF usando GroupDocs.Viewer for .NET. Seguindo o guia passo a passo, você pode integrar perfeitamente esse recurso aos seus aplicativos .NET, garantindo a segurança dos documentos e aprimorando a experiência do usuário.
## Perguntas frequentes
### Posso personalizar o diretório de saída para páginas HTML renderizadas?
Sim, você pode especificar qualquer caminho de diretório onde deseja que as páginas HTML renderizadas sejam armazenadas.
### O GroupDocs.Viewer for .NET é compatível com diferentes versões do .NET framework?
Sim, o GroupDocs.Viewer for .NET é compatível com várias versões do .NET framework, incluindo .NET Core e .NET Framework.
### A desativação da seleção de texto afeta outras funcionalidades do documento PDF?
Não, desabilitar a seleção de texto apenas impede que os usuários selecionem e copiem texto do documento. Outras funcionalidades permanecem intactas.
### Posso ativar a seleção de texto novamente após renderizar o documento?
 Sim, você pode ativar a seleção de texto simplesmente definindo o`RenderTextAsImage` propriedade para`false` nas opções de visualização HTML.
### Existe uma versão de teste disponível para GroupDocs.Viewer for .NET?
 Sim, você pode acessar uma avaliação gratuita do GroupDocs.Viewer for .NET no site[local na rede Internet](https://releases.groupdocs.com/).