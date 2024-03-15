---
title: Renderizar imagens FODG e ODG
linktitle: Renderizar imagens FODG e ODG
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar imagens FODG e ODG em HTML, JPG, PNG e PDF usando GroupDocs.Viewer for .NET. Melhore o manuseio de documentos.
type: docs
weight: 15
url: /pt/net/image-rendering/render-fodg-odg-images/
---
## Introdução
No mundo do desenvolvimento de software, o manuseio eficiente de formatos de documentos é fundamental. GroupDocs.Viewer for .NET é uma ferramenta poderosa projetada para simplificar o processo de renderização de imagens FODG e ODG em aplicativos .NET. Este tutorial orientará você nas etapas necessárias para renderizar essas imagens em vários formatos, como HTML, JPG, PNG e PDF, usando GroupDocs.Viewer for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  GroupDocs.Viewer for .NET: Baixe e instale o GroupDocs.Viewer for .NET em[aqui](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Certifique-se de ter o .NET Framework instalado em seu sistema.
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será útil.

## Importar namespaces
Antes de iniciar a implementação, importe os namespaces necessários:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
 Substituir`"Your Document Directory"`com o caminho do diretório onde você deseja salvar as imagens renderizadas.
## Etapa 2: renderizar para HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Esta etapa renderiza a imagem FODG no formato HTML.
## Etapa 3: renderizar para JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Aqui, a imagem FODG é renderizada no formato JPG.
## Etapa 4: renderizar para PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Esta etapa converte a imagem FODG para o formato PNG.
## Etapa 5: renderizar em PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Finalmente, a imagem FODG é renderizada em formato PDF.

## Conclusão
Neste tutorial, exploramos como renderizar imagens FODG e ODG em vários formatos usando GroupDocs.Viewer for .NET. Seguindo essas etapas, você pode integrar perfeitamente recursos de renderização de documentos em seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer for .NET é compatível com todas as versões do .NET Framework?
GroupDocs.Viewer for .NET é compatível com uma ampla variedade de versões do .NET Framework, incluindo as mais recentes.
### Posso renderizar documentos de forma assíncrona com GroupDocs.Viewer for .NET?
Sim, o GroupDocs.Viewer for .NET fornece recursos de renderização assíncrona para melhorar o desempenho.
### O GroupDocs.Viewer for .NET oferece suporte à renderização de documentos criptografados?
Sim, o GroupDocs.Viewer for .NET oferece suporte à renderização de documentos criptografados com chaves de descriptografia apropriadas.
### É possível personalizar a saída da renderização com GroupDocs.Viewer for .NET?
Com certeza, GroupDocs.Viewer for .NET oferece várias opções de personalização para adaptar a saída da renderização de acordo com suas necessidades.
### Posso renderizar documentos de locais de armazenamento remotos usando GroupDocs.Viewer for .NET?
Sim, o GroupDocs.Viewer for .NET oferece suporte à renderização de documentos de locais de armazenamento locais e remotos.