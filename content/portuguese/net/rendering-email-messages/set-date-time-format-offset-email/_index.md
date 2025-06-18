---
"description": "Integre o GroupDocs.Viewer para .NET perfeitamente aos seus aplicativos para obter recursos avançados de visualização de documentos. Aprimore a experiência do usuário com opções personalizáveis."
"linktitle": "Definir formato de data e hora e deslocamento de fuso horário (e-mail)"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Definir formato de data e hora e deslocamento de fuso horário (e-mail)"
"url": "/pt/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Definir formato de data e hora e deslocamento de fuso horário (e-mail)


## Introdução
O GroupDocs.Viewer para .NET é uma ferramenta poderosa que permite aos desenvolvedores integrar perfeitamente recursos de visualização de documentos em seus aplicativos .NET. Com o GroupDocs.Viewer, você pode exibir uma ampla variedade de formatos de documentos, incluindo PDFs, documentos do Microsoft Office, imagens e muito mais, diretamente em seu aplicativo, sem a necessidade de plugins ou visualizadores externos. Neste tutorial abrangente, guiaremos você pelo processo de configuração do GroupDocs.Viewer para .NET, explorando seus recursos e demonstrando como utilizá-lo de forma eficaz para aprimorar os recursos de visualização de documentos do seu aplicativo.
## Pré-requisitos
Antes de começar este tutorial, certifique-se de ter os seguintes pré-requisitos configurados:
1. Visual Studio: Certifique-se de ter o Visual Studio instalado no seu sistema. O GroupDocs.Viewer para .NET é totalmente compatível com o Visual Studio, permitindo integração perfeita com seus projetos .NET.
2. GroupDocs.Viewer para .NET: Baixe e instale o GroupDocs.Viewer para .NET do [link para download](https://releases.groupdocs.com/viewer/net/). Siga as instruções de instalação fornecidas para configurar a biblioteca em seu ambiente de desenvolvimento.
3. .NET Framework: Certifique-se de ter a versão apropriada do .NET Framework instalada. O GroupDocs.Viewer para .NET oferece suporte a várias versões do .NET Framework, incluindo .NET Core e .NET Standard.

## Importar namespaces
Para utilizar o GroupDocs.Viewer para .NET de forma eficaz, você precisa importar os namespaces necessários para o seu projeto. Siga estas etapas para importar os namespaces necessários:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Vamos dividir o exemplo fornecido em várias etapas para entender cada componente e sua funcionalidade.
## Etapa 1: definir o diretório de saída e o caminho do arquivo
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Nesta etapa, definimos o diretório de saída onde o documento renderizado será salvo e especificamos o caminho do arquivo HTML de saída.
## Etapa 2: Instanciar objeto do visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Aqui, criamos uma nova instância do `Viewer` classe, passando o caminho do documento a ser visualizado (neste caso, um arquivo EML de exemplo) como parâmetro.
## Etapa 3: Definir opções de visualização HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Nesta etapa, configuramos as opções de visualização HTML para a renderização do documento, especificando o caminho do arquivo de saída para o documento HTML renderizado.
## Etapa 4: definir o formato de data e hora e o deslocamento do fuso horário
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Aqui, personalizamos o formato de data e hora para mensagens de e-mail e definimos o fuso horário de acordo com o fuso horário desejado.
## Etapa 5: Renderizar documento
```csharp
viewer.View(options);
```
Por fim, chamamos de `View` método do `Viewer` objeto, passando as opções de visualização HTML configuradas para renderizar o documento no formato HTML.
## Etapa 6: Exibir diretório de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Esta etapa simplesmente exibe uma mensagem indicando a renderização bem-sucedida do documento e fornece o caminho para o diretório de saída onde o documento HTML renderizado está localizado.

## Conclusão
O GroupDocs.Viewer para .NET oferece uma solução robusta para integrar recursos de visualização de documentos em seus aplicativos .NET. Seguindo os passos descritos neste tutorial, você pode facilmente configurar o GroupDocs.Viewer, importar os namespaces necessários e utilizar seus recursos para renderizar documentos com opções personalizáveis. Seja trabalhando com PDFs, documentos do Microsoft Office ou outros formatos, o GroupDocs.Viewer simplifica o processo de visualização de documentos, aprimorando a experiência do usuário em seus aplicativos.
## Perguntas frequentes
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, o GroupDocs.Viewer para .NET oferece suporte ao .NET Core, permitindo compatibilidade entre plataformas para seus aplicativos.
### Posso personalizar a aparência dos documentos renderizados?
Com certeza! O GroupDocs.Viewer oferece diversas opções de personalização, incluindo níveis de zoom, rotação de páginas e muito mais, para adaptar a experiência de visualização aos seus tutoriais.
### Existe uma versão de teste disponível para fins de teste?
Sim, você pode baixar uma versão de teste gratuita do GroupDocs.Viewer para .NET no [link do site](https://releases.groupdocs.com/viewer/net/) para avaliar suas características antes de efetuar uma compra.
### O GroupDocs.Viewer suporta renderização de documentos protegidos por senha?
Sim, o GroupDocs.Viewer tem suporte integrado para renderizar documentos protegidos por senha, garantindo a visualização segura de documentos em seus aplicativos.
### Onde posso encontrar suporte ou assistência adicional com o GroupDocs.Viewer?
Para qualquer dúvida técnica ou assistência, você pode visitar o GroupDocs.Viewer [fórum](https://forum.groupdocs.com/c/viewer/9) ou entre em contato com a equipe de suporte para obter ajuda e orientação imediatas.