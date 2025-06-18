---
"description": "Aprenda a renderizar arquivos CHM em .NET usando o GroupDocs.Viewer. Converta CHM para os formatos HTML, JPG, PNG e PDF sem esforço."
"linktitle": "Renderizar arquivos CHM"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar arquivos CHM"
"url": "/pt/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Renderizar arquivos CHM

## Introdução
Neste tutorial, exploraremos como renderizar arquivos CHM (Ajuda HTML Compilada) usando o GroupDocs.Viewer para .NET. O GroupDocs.Viewer para .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores exibir mais de 170 tipos de documentos em seus aplicativos .NET sem exigir nenhuma instalação de software externo.

## Pré-requisitos

Antes de começarmos a renderizar arquivos CHM, certifique-se de ter os seguintes pré-requisitos:

### Instalando o GroupDocs.Viewer para .NET

Para começar, você precisa instalar o GroupDocs.Viewer para .NET. Você pode baixar a biblioteca do [Site do GroupDocs](https://releases.groupdocs.com/viewer/net/) ou instale-o por meio do Gerenciador de Pacotes NuGet executando o seguinte comando no Console do Gerenciador de Pacotes:

```bash
Install-Package GroupDocs.Viewer
```

## Importando namespaces

Certifique-se de importar os namespaces necessários para o seu projeto:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora vamos dividir o processo de renderização em várias etapas:

## Etapa 1: definir diretório de saída

Defina o diretório onde você deseja que os arquivos renderizados sejam salvos:

```csharp
string outputDirectory = "Your Document Directory";
```

## Etapa 2: renderizar para HTML

Para renderizar arquivos CHM em HTML, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Defina como verdadeiro para converter todo o conteúdo CHM em uma única página

    viewer.View(options); // Converter todas as páginas
}
```

## Etapa 3: renderizar para JPG

Para renderizar arquivos CHM em imagens JPG, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converter apenas as páginas 1, 2, 3
}
```

## Etapa 4: renderizar para PNG

Para renderizar arquivos CHM em imagens PNG, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converter apenas as páginas 1, 2, 3
}
```

## Etapa 5: Renderizar para PDF

Para renderizar arquivos CHM em um documento PDF, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Converter todas as páginas
}
```

## Etapa 6: Verifique a saída

Após a conclusão do processo de renderização, verifique o diretório de saída especificado para os arquivos renderizados:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão

Renderizar arquivos CHM usando o GroupDocs.Viewer para .NET é um processo simples. Seguindo os passos descritos neste tutorial, você poderá converter documentos CHM com eficiência para diversos formatos, como HTML, imagens (JPG, PNG) e PDF, dentro de seus aplicativos .NET.

## Perguntas frequentes

### Q1: O GroupDocs.Viewer pode renderizar outros formatos de documento além do CHM?

R1: Sim, o GroupDocs.Viewer suporta renderização de mais de 170 formatos de documentos, incluindo PDF, DOCX, XLSX, PPTX e mais.

### T2: O GroupDocs.Viewer é compatível com o .NET Core?

R2: Sim, o GroupDocs.Viewer suporta o .NET Core, além do tradicional .NET Framework.

### P3: Posso personalizar as opções de renderização para diferentes formatos de saída?

R3: Sim, o GroupDocs.Viewer oferece várias opções para personalizar o processo de renderização, como especificar números de página, definir a qualidade da imagem e configurar caminhos de saída.

### Q4: O GroupDocs.Viewer requer alguma dependência externa para renderizar documentos?

R4: Não, o GroupDocs.Viewer é uma biblioteca autônoma e não requer nenhuma dependência externa ou instalação de software de terceiros.

### P5: Existe um teste gratuito disponível para o GroupDocs.Viewer?

R5: Sim, você pode aproveitar uma avaliação gratuita do GroupDocs.Viewer visitando o [site](https://releases.groupdocs.com/).