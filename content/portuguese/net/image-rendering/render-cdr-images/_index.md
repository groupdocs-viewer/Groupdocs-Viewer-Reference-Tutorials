---
"description": "Aprenda a renderizar imagens CDR para HTML, JPG, PNG e PDF usando o GroupDocs.Viewer para .NET. Converta arquivos CorelDRAW facilmente com este tutorial."
"linktitle": "Renderizar imagens CDR"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar imagens CDR"
"url": "/pt/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# Renderizar imagens CDR

## Introdução
Neste tutorial, guiaremos você pelo processo de renderização de imagens CDR (CorelDRAW) usando o GroupDocs.Viewer para .NET. CDR é um formato de arquivo associado principalmente ao CorelDRAW, um editor de gráficos vetoriais. Com o GroupDocs.Viewer, você pode converter facilmente arquivos CDR para vários formatos, como HTML, JPG, PNG e PDF.

![Renderizar imagens CDR com GroupDocs.Viewer para .NET](/viewer/image-rendering/render-cdr-images.png)

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1. GroupDocs.Viewer para .NET: Certifique-se de ter instalado o GroupDocs.Viewer para .NET. Você pode baixá-lo em [aqui](https://releases.groupdocs.com/viewer/net/).
2. Diretório de documentos: prepare um diretório onde você deseja salvar as imagens renderizadas.
3. Conhecimento básico de C#: é necessária familiaridade com a linguagem de programação C# para entender os exemplos de código.
## Importar namespaces
Antes de mergulhar nos exemplos de código, importe os namespaces necessários no seu arquivo C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Agora, vamos dividir cada exemplo em várias etapas:
## Renderização para HTML
1. Defina o diretório de saída onde você deseja salvar os arquivos HTML renderizados:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Especifique o formato do caminho do arquivo para arquivos HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Use a classe Viewer para renderizar o arquivo CDR em HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderização para JPG
1. Defina o formato do caminho do arquivo para arquivos JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Use a classe Viewer para renderizar o arquivo CDR em JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizando para PNG
1. Defina o formato do caminho do arquivo para arquivos PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Use a classe Viewer para renderizar o arquivo CDR para PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderização para PDF
1. Defina o formato do caminho do arquivo para PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Use a classe Viewer para renderizar o arquivo CDR em PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Opcionalmente, você pode especificar opções de renderização ou renderizar páginas específicas passando parâmetros adicionais para o `viewer.View()` método.
## Conclusão
Renderizar imagens CDR para vários formatos, como HTML, JPG, PNG e PDF, usando o GroupDocs.Viewer para .NET é um processo simples. Seguindo os passos descritos neste tutorial, você poderá converter arquivos CDR com eficiência para diferentes formatos, de acordo com suas necessidades.
## Perguntas frequentes
### GroupDocs.Viewer para .NET é compatível com todas as versões de arquivos CDR?
O GroupDocs.Viewer para .NET suporta a renderização de arquivos CDR criados por diferentes versões do CorelDRAW.
### Posso personalizar a saída dos arquivos renderizados?
Sim, o GroupDocs.Viewer para .NET oferece várias opções para personalizar a saída, como ajustar a qualidade da imagem, definir marca d'água, etc.
### O GroupDocs.Viewer para .NET requer alguma dependência externa?
Não, o GroupDocs.Viewer para .NET é uma biblioteca autônoma e não requer nenhuma dependência externa para renderizar documentos.
### Existe uma versão de teste disponível para o GroupDocs.Viewer para .NET?
Sim, você pode baixar uma versão de teste gratuita do GroupDocs.Viewer para .NET em [aqui](https://releases.groupdocs.com/).
### Onde posso obter suporte para o GroupDocs.Viewer para .NET?
Você pode obter suporte no fórum da comunidade GroupDocs.Viewer [aqui](https://forum.groupdocs.com/c/viewer/9).