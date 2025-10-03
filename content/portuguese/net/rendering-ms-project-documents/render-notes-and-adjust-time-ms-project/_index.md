---
"description": "Domine a renderização de documentos do MS Project com o GroupDocs.Viewer para .NET. Renderize notas, ajuste unidades de tempo e explore diversos formatos de saída sem esforço."
"linktitle": "Renderizar notas e ajustar unidades de tempo (MS Project)"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar notas e ajustar unidades de tempo (MS Project)"
"url": "/pt/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Renderizar notas e ajustar unidades de tempo (MS Project)

## Introdução
O GroupDocs.Viewer para .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores visualizar e manipular diversos formatos de documentos em seus aplicativos .NET. Neste tutorial, vamos nos concentrar na renderização de notas e no ajuste de unidades de tempo especificamente para documentos do MS Project.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1. GroupDocs.Viewer para .NET: Certifique-se de ter baixado e instalado a biblioteca GroupDocs.Viewer para .NET. Você pode baixá-la em [aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento preferido com suporte ao .NET.
3. Documento do MS Project: tenha um documento de amostra do MS Project pronto para teste.
## Importar namespaces
Primeiro, vamos importar os namespaces necessários para começar a renderizar documentos do MS Project:
## Etapa 1: Importar namespaces
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Agora que importamos os namespaces necessários, vamos dividir cada exemplo em várias etapas para uma compreensão abrangente.
## Renderizando documento do MS Project para HTML
Para renderizar um documento do MS Project para o formato HTML com notas incluídas, siga estas etapas:
### Etapa 2: definir diretório de saída e formato de arquivo
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Etapa 3: Inicializar o objeto do visualizador e definir as opções
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Etapa 4: Renderizar documento para HTML
```csharp
viewer.View(options);
```
## Renderizando documentos do MS Project em formatos de imagem
Você também pode renderizar documentos do MS Project para formatos de imagem como JPG e PNG. Veja como:
### Etapa 5: definir diretório de saída e formato de arquivo para JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Etapa 6: Inicializar o objeto do visualizador e definir as opções JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Etapa 7: Renderizar documento para JPG
```csharp
viewer.View(options);
```
Repita etapas semelhantes para renderizar para PNG e outros formatos de imagem.
## Renderizando documento do MS Project para PDF
Para renderizar um documento do MS Project para o formato PDF, proceda da seguinte forma:
### Etapa 8: definir diretório de saída e formato de arquivo para PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Etapa 9: Inicializar o objeto do visualizador e definir as opções do PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Etapa 10: Renderizar documento para PDF
```csharp
viewer.View(options);
```

## Conclusão
Parabéns! Você aprendeu com sucesso a renderizar documentos do MS Project e ajustar unidades de tempo usando o GroupDocs.Viewer para .NET. Incorpore esse conhecimento aos seus projetos para aprimorar os recursos de visualização de documentos.
## Perguntas frequentes
### Posso renderizar documentos do MS Project em outros formatos além de HTML, imagens e PDF?
Sim, o GroupDocs.Viewer para .NET suporta renderização em vários formatos, como DOCX, XLSX, PPTX e mais.
### Existe uma versão de teste disponível para o GroupDocs.Viewer para .NET?
Sim, você pode obter um teste gratuito em [aqui](https://releases.groupdocs.com/).
### Como posso obter uma licença temporária para o GroupDocs.Viewer para .NET?
Visita [este link](https://purchase.groupdocs.com/temporary-license/) para obter uma licença temporária.
### Onde posso encontrar documentação do GroupDocs.Viewer para .NET?
Consulte a documentação [aqui](https://tutorials.groupdocs.com/viewer/net/).
### Onde posso buscar suporte ou tirar dúvidas relacionadas ao GroupDocs.Viewer para .NET?
Você pode visitar o fórum de suporte [aqui](https://forum.groupdocs.com/c/viewer/9).