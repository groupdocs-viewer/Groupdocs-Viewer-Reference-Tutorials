---
title: Renderizar imagens CDR
linktitle: Renderizar imagens CDR
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar imagens CDR em HTML, JPG, PNG e PDF usando GroupDocs.Viewer for .NET. Converta facilmente arquivos CorelDRAW com este tutorial.
type: docs
weight: 12
url: /pt/net/image-rendering/render-cdr-images/
---
## Introdução
Neste tutorial, orientaremos você no processo de renderização de imagens CDR (CorelDRAW) usando GroupDocs.Viewer for .NET. CDR é um formato de arquivo associado principalmente ao CorelDRAW, um editor de gráficos vetoriais. Com GroupDocs.Viewer, você pode converter facilmente arquivos CDR em vários formatos como HTML, JPG, PNG e PDF.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1.  GroupDocs.Viewer for .NET: Certifique-se de ter instalado o GroupDocs.Viewer for .NET. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Diretório de Documentos: Prepare um diretório onde deseja salvar as imagens renderizadas.
3. Conhecimento básico de C#: É necessária familiaridade com a linguagem de programação C# para entender os exemplos de código.
## Importar namespaces
Antes de mergulhar nos exemplos de código, importe os namespaces necessários em seu arquivo C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Agora, vamos dividir cada exemplo em várias etapas:
## Renderizando para HTML
1. Defina o diretório de saída onde deseja salvar os arquivos HTML renderizados:
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
## Renderizando para JPG
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
2. Use a classe Viewer para renderizar o arquivo CDR em PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizando para PDF
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
3.  Opcionalmente, você pode especificar opções de renderização ou renderizar páginas específicas passando parâmetros adicionais para o`viewer.View()` método.
## Conclusão
Renderizar imagens CDR em vários formatos como HTML, JPG, PNG e PDF usando GroupDocs.Viewer for .NET é um processo simples. Seguindo as etapas descritas neste tutorial, você pode converter arquivos CDR com eficiência em diferentes formatos com base em suas necessidades.
## Perguntas frequentes
### O GroupDocs.Viewer for .NET é compatível com todas as versões de arquivos CDR?
GroupDocs.Viewer for .NET oferece suporte à renderização de arquivos CDR criados por diferentes versões do CorelDRAW.
### Posso personalizar a saída dos arquivos renderizados?
Sim, o GroupDocs.Viewer for .NET oferece várias opções para personalizar a saída, como ajustar a qualidade da imagem, definir marca d'água, etc.
### O GroupDocs.Viewer for .NET requer alguma dependência externa?
Não, o GroupDocs.Viewer for .NET é uma biblioteca independente e não requer nenhuma dependência externa para renderizar documentos.
### Existe uma versão de teste disponível para GroupDocs.Viewer for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita do GroupDocs.Viewer for .NET em[aqui](https://releases.groupdocs.com/).
### Onde posso obter suporte para GroupDocs.Viewer for .NET?
 Você pode obter suporte no fórum da comunidade GroupDocs.Viewer[aqui](https://forum.groupdocs.com/c/viewer/9).