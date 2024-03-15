---
title: Definir formato de data e hora e deslocamento de fuso horário (e-mail)
linktitle: Definir formato de data e hora e deslocamento de fuso horário (e-mail)
second_title: API GroupDocs.Viewer .NET
description: Integre o GroupDocs.Viewer for .NET perfeitamente em seus aplicativos para obter recursos avançados de visualização de documentos. Aprimore a experiência do usuário com opções personalizáveis.
type: docs
weight: 11
url: /pt/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Introdução
GroupDocs.Viewer for .NET é uma ferramenta poderosa que permite aos desenvolvedores integrar perfeitamente recursos de visualização de documentos em seus aplicativos .NET. Com GroupDocs.Viewer, você pode exibir uma ampla variedade de formatos de documentos, incluindo PDFs, documentos do Microsoft Office, imagens e muito mais diretamente em seu aplicativo, sem a necessidade de plug-ins ou visualizadores externos. Neste tutorial abrangente, orientaremos você no processo de configuração do GroupDocs.Viewer para .NET, explorando seus recursos e demonstrando como utilizá-lo de maneira eficaz para aprimorar os recursos de visualização de documentos do seu aplicativo.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter os seguintes pré-requisitos configurados:
1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema. GroupDocs.Viewer for .NET é totalmente compatível com Visual Studio, permitindo integração perfeita em seus projetos .NET.
2.  GroupDocs.Viewer for .NET: Baixe e instale o GroupDocs.Viewer for .NET a partir do[Link para Download](https://releases.groupdocs.com/viewer/net/). Siga as instruções de instalação fornecidas para configurar a biblioteca em seu ambiente de desenvolvimento.
3. .NET Framework: certifique-se de ter a versão apropriada do .NET Framework instalada. GroupDocs.Viewer for .NET oferece suporte a várias versões do .NET Framework, incluindo .NET Core e .NET Standard.

## Importar namespaces
Para utilizar o GroupDocs.Viewer for .NET de maneira eficaz, você precisa importar os namespaces necessários para o seu projeto. Siga estas etapas para importar os namespaces necessários:

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
## Etapa 2: instanciar o objeto visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Aqui, criamos uma nova instância do`Viewer` class, passando o caminho do documento a ser visualizado (neste caso, um arquivo EML de amostra) como parâmetro.
## Etapa 3: definir opções de visualização HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Nesta etapa, configuramos as opções de visualização HTML para a renderização do documento, especificando o caminho do arquivo de saída para o documento HTML renderizado.
## Etapa 4: definir formato de data e hora e deslocamento de fuso horário
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Aqui, personalizamos o formato de data e hora para mensagens de e-mail e definimos o deslocamento do fuso horário de acordo com o fuso horário desejado.
## Etapa 5: renderizar documento
```csharp
viewer.View(options);
```
 Por fim, chamamos o`View` método do`Viewer` objeto, passando as opções de visualização HTML configuradas para renderizar o documento no formato HTML.
## Etapa 6: Exibir diretório de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Esta etapa simplesmente exibe uma mensagem indicando a renderização bem-sucedida do documento e fornece o caminho para o diretório de saída onde o documento HTML renderizado está localizado.

## Conclusão
GroupDocs.Viewer for .NET oferece uma solução robusta para integração de recursos de visualização de documentos em seus aplicativos .NET. Seguindo as etapas descritas neste tutorial, você pode configurar facilmente o GroupDocs.Viewer, importar os namespaces necessários e utilizar seus recursos para renderizar documentos com opções personalizáveis. Esteja você trabalhando com PDFs, documentos do Microsoft Office ou outros formatos, o GroupDocs.Viewer simplifica o processo de visualização de documentos, aprimorando a experiência do usuário em seus aplicativos.
## Perguntas frequentes
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, o GroupDocs.Viewer for .NET oferece suporte ao .NET Core, permitindo compatibilidade entre plataformas para seus aplicativos.
### Posso personalizar a aparência dos documentos renderizados?
Absolutamente! GroupDocs.Viewer oferece várias opções de personalização, incluindo níveis de zoom, rotação de página e muito mais para personalizar a experiência de visualização de acordo com suas preferências.
### Existe uma versão de teste disponível para fins de teste?
 Sim, você pode baixar uma versão de avaliação gratuita do GroupDocs.Viewer for .NET no site[link do site](https://releases.groupdocs.com/viewer/net/) para avaliar suas características antes de fazer uma compra.
### O GroupDocs.Viewer oferece suporte à renderização de documentos protegidos por senha?
Sim, o GroupDocs.Viewer possui suporte integrado para renderização de documentos protegidos por senha, garantindo a visualização segura de documentos em seus aplicativos.
### Onde posso encontrar suporte ou assistência adicional com GroupDocs.Viewer?
 Para qualquer dúvida técnica ou assistência, você pode visitar o GroupDocs.Viewer[fórum](https://forum.groupdocs.com/c/viewer/9) ou entre em contato com a equipe de suporte para obter ajuda e orientação imediata.