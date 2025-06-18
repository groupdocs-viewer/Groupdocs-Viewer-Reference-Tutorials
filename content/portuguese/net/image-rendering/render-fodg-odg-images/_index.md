---
"description": "Aprenda a renderizar imagens FODG e ODG para HTML, JPG, PNG e PDF usando o GroupDocs.Viewer para .NET. Aprimore seu processamento de documentos."
"linktitle": "Renderizar imagens FODG e ODG"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar imagens FODG e ODG"
"url": "/pt/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# Renderizar imagens FODG e ODG

## Introdução
No mundo do desenvolvimento de software, o manuseio eficiente de formatos de documentos é fundamental. O GroupDocs.Viewer para .NET é uma ferramenta poderosa projetada para simplificar o processo de renderização de imagens FODG e ODG em aplicativos .NET. Este tutorial guiará você pelas etapas necessárias para renderizar essas imagens em vários formatos, como HTML, JPG, PNG e PDF, usando o GroupDocs.Viewer para .NET.

![Renderizar imagens FODG e ODG com GroupDocs.Viewer para .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Pré-requisitos
Antes de começar o tutorial, certifique-se de ter os seguintes pré-requisitos:
1. GroupDocs.Viewer para .NET: Baixe e instale o GroupDocs.Viewer para .NET em [aqui](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: certifique-se de ter o .NET Framework instalado no seu sistema.
3. Conhecimento básico de C#: familiaridade com a linguagem de programação C# será útil.

## Importar namespaces
Antes de iniciar a implementação, importe os namespaces necessários:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Etapa 1: definir diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Substituir `"Your Document Directory"` com o caminho do diretório onde você deseja salvar as imagens renderizadas.
## Etapa 2: renderizar para HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Esta etapa renderiza a imagem FODG para o formato HTML.
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
## Etapa 5: Renderizar para PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Por fim, a imagem FODG é renderizada no formato PDF.

## Conclusão
Neste tutorial, exploramos como renderizar imagens FODG e ODG em vários formatos usando o GroupDocs.Viewer para .NET. Seguindo esses passos, você poderá integrar perfeitamente os recursos de renderização de documentos aos seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer para .NET é compatível com todas as versões do .NET Framework?
O GroupDocs.Viewer para .NET é compatível com uma ampla variedade de versões do .NET Framework, incluindo as mais recentes.
### Posso renderizar documentos de forma assíncrona com o GroupDocs.Viewer para .NET?
Sim, o GroupDocs.Viewer para .NET fornece recursos de renderização assíncrona para melhor desempenho.
### O GroupDocs.Viewer para .NET suporta renderização de documentos criptografados?
Sim, o GroupDocs.Viewer para .NET suporta a renderização de documentos criptografados com chaves de descriptografia apropriadas.
### É possível personalizar a saída de renderização com o GroupDocs.Viewer para .NET?
Com certeza, o GroupDocs.Viewer para .NET oferece diversas opções de personalização para adaptar a saída de renderização de acordo com suas necessidades.
### Posso renderizar documentos de locais de armazenamento remotos usando o GroupDocs.Viewer para .NET?
Sim, o GroupDocs.Viewer para .NET suporta a renderização de documentos de locais de armazenamento locais e remotos.