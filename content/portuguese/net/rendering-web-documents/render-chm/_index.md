---
title: Renderizar arquivos CHM
linktitle: Renderizar arquivos CHM
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar arquivos CHM em .NET usando GroupDocs.Viewer. Converta CHM em formatos HTML, JPG, PNG e PDF sem esforço.
weight: 10
url: /pt/net/rendering-web-documents/render-chm/
---
## Introdução
Neste tutorial, exploraremos como renderizar arquivos CHM (Ajuda HTML compilado) usando GroupDocs.Viewer para .NET. GroupDocs.Viewer for .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores exibir mais de 170 tipos de documentos em seus aplicativos .NET sem exigir qualquer instalação de software externo.

## Pré-requisitos

Antes de nos aprofundarmos na renderização de arquivos CHM, certifique-se de ter os seguintes pré-requisitos:

### Instalando GroupDocs.Viewer para .NET

 Para começar, você precisa instalar o GroupDocs.Viewer for .NET. Você pode baixar a biblioteca do[Site GroupDocs](https://releases.groupdocs.com/viewer/net/) ou instale-o por meio do Gerenciador de Pacotes NuGet executando o seguinte comando no Console do Gerenciador de Pacotes:

```bash
Install-Package GroupDocs.Viewer
```

## Importando Namespaces

Certifique-se de importar os namespaces necessários para o seu projeto:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora vamos dividir o processo de renderização em várias etapas:

## Etapa 1: definir o diretório de saída

Defina o diretório onde deseja que os arquivos renderizados sejam salvos:

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

    viewer.View(options); //Converta todas as páginas
}
```

## Etapa 3: renderizar para JPG

Para renderizar arquivos CHM em imagens JPG, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converta apenas as páginas 1, 2, 3
}
```

## Etapa 4: renderizar para PNG

Para renderizar arquivos CHM em imagens PNG, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converta apenas as páginas 1, 2, 3
}
```

## Etapa 5: renderizar em PDF

Para renderizar arquivos CHM em um documento PDF, use o seguinte trecho de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Converta todas as páginas
}
```

## Etapa 6: verificar o resultado

Assim que o processo de renderização for concluído, verifique o diretório de saída especificado para os arquivos renderizados:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão

Renderizar arquivos CHM usando GroupDocs.Viewer for .NET é um processo simples. Seguindo as etapas descritas neste tutorial, você pode converter documentos CHM com eficiência em vários formatos, como HTML, imagens (JPG, PNG) e PDF em seus aplicativos .NET.

## Perguntas frequentes

### P1: O GroupDocs.Viewer pode renderizar outros formatos de documento além do CHM?

A1: Sim, GroupDocs.Viewer suporta renderização de mais de 170 formatos de documentos, incluindo PDF, DOCX, XLSX, PPTX e muito mais.

### P2: O GroupDocs.Viewer é compatível com o .NET Core?

A2: Sim, o GroupDocs.Viewer oferece suporte ao .NET Core além do .NET Framework tradicional.

### P3: Posso personalizar as opções de renderização para diferentes formatos de saída?

R3: Sim, o GroupDocs.Viewer oferece várias opções para personalizar o processo de renderização, como especificar números de página, definir qualidade de imagem e configurar caminhos de saída.

### P4: O GroupDocs.Viewer requer alguma dependência externa para renderizar documentos?

R4: Não, GroupDocs.Viewer é uma biblioteca independente e não requer dependências externas ou instalações de software de terceiros.

### P5: Existe uma avaliação gratuita disponível para GroupDocs.Viewer?

 A5: Sim, você pode aproveitar uma avaliação gratuita do GroupDocs.Viewer visitando o[local na rede Internet](https://releases.groupdocs.com/).