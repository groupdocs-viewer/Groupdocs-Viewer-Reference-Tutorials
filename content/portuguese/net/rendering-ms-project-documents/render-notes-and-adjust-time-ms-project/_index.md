---
title: Renderizar notas e ajustar unidades de tempo (MS Project)
linktitle: Renderizar notas e ajustar unidades de tempo (MS Project)
second_title: API GroupDocs.Viewer .NET
description: Domine a renderização de documentos do MS Project com GroupDocs.Viewer para .NET. Renderize notas, ajuste unidades de tempo e explore vários formatos de saída sem esforço.
type: docs
weight: 11
url: /pt/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Introdução
GroupDocs.Viewer for .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores visualizar e manipular vários formatos de documentos em seus aplicativos .NET. Neste tutorial, focaremos na renderização de notas e no ajuste de unidades de tempo especificamente para documentos do MS Project.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. GroupDocs.Viewer for .NET: certifique-se de ter baixado e instalado a biblioteca GroupDocs.Viewer for .NET. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: Configure seu ambiente de desenvolvimento preferido com suporte .NET.
3. Documento do MS Project: Tenha um exemplo de documento do MS Project pronto para teste.
## Importar namespaces
Primeiro, vamos importar os namespaces necessários para começar a renderizar documentos do MS Project:
## Etapa 1: importar namespaces
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Agora que importamos os namespaces necessários, vamos dividir cada exemplo em várias etapas para uma compreensão abrangente.
## Renderizando documento do MS Project para HTML
Para renderizar um documento MS Project em formato HTML com notas incluídas, siga estas etapas:
### Etapa 2: definir o diretório de saída e o formato do arquivo
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Etapa 3: inicializar o objeto visualizador e definir opções
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Etapa 4: renderizar documento em HTML
```csharp
viewer.View(options);
```
## Renderizando documento do MS Project em formatos de imagem
Você também pode renderizar documentos do MS Project em formatos de imagem como JPG e PNG. Veja como:
### Etapa 5: definir o diretório de saída e o formato de arquivo para JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Etapa 6: inicializar o objeto visualizador e definir opções de JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Etapa 7: renderizar documento para JPG
```csharp
viewer.View(options);
```
Repita etapas semelhantes para renderizar em PNG e outros formatos de imagem.
## Renderizando documento do MS Project em PDF
Para renderizar um documento MS Project em formato PDF, proceda da seguinte forma:
### Etapa 8: Definir diretório de saída e formato de arquivo para PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Etapa 9: inicializar o objeto do visualizador e definir as opções do PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Etapa 10: renderizar documento em PDF
```csharp
viewer.View(options);
```

## Conclusão
Parabéns! Você aprendeu com sucesso como renderizar documentos do MS Project e ajustar unidades de tempo usando GroupDocs.Viewer for .NET. Incorpore esse conhecimento em seus projetos para aprimorar os recursos de visualização de documentos.
## Perguntas frequentes
### Posso renderizar documentos do MS Project para outros formatos além de HTML, imagens e PDF?
Sim, o GroupDocs.Viewer for .NET oferece suporte à renderização em vários formatos, como DOCX, XLSX, PPTX e muito mais.
### Existe uma versão de teste disponível para GroupDocs.Viewer for .NET?
 Sim, você pode obter um teste gratuito em[aqui](https://releases.groupdocs.com/).
### Como posso obter licenciamento temporário para GroupDocs.Viewer for .NET?
 Visita[esse link](https://purchase.groupdocs.com/temporary-license/) para obter uma licença temporária.
### Onde posso encontrar a documentação do GroupDocs.Viewer for .NET?
 Consulte a documentação[aqui](https://reference.groupdocs.com/viewer/net/).
### Onde posso procurar suporte ou fazer perguntas relacionadas ao GroupDocs.Viewer for .NET?
 Você pode visitar o fórum de suporte[aqui](https://forum.groupdocs.com/c/viewer/9).