---
title: Ajustar o tamanho da imagem de saída para desenhos CAD
linktitle: Ajustar o tamanho da imagem de saída para desenhos CAD
second_title: API GroupDocs.Viewer .NET
description: Aprenda como ajustar o tamanho da imagem de saída para desenhos CAD usando GroupDocs.Viewer for .NET. Melhore a visibilidade e a usabilidade sem esforço.
weight: 15
url: /pt/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## Introdução
Os desenhos CAD geralmente exigem ajustes específicos para visualização e apresentação ideais. GroupDocs.Viewer for .NET fornece um conjunto de ferramentas poderoso para gerenciar e personalizar a saída de desenhos CAD. Neste tutorial, iremos guiá-lo passo a passo pelo processo de ajuste do tamanho da imagem de saída para desenhos CAD.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1.  GroupDocs.Viewer for .NET: Baixe e instale o GroupDocs.Viewer for .NET em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Diretório de Documentos: Prepare o diretório onde seu documento está localizado.
3. Compreensão Básica: Familiarize-se com os conceitos básicos de programação .NET.

## Importar namespaces
Primeiro, certifique-se de importar os namespaces necessários para acessar as funcionalidades do GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: definir o diretório de saída
Defina o diretório onde deseja armazenar as imagens de saída dos desenhos CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: definir o formato do caminho do arquivo de página
Defina o formato dos caminhos dos arquivos de paginação. Este formato será usado para nomear e salvar páginas individuais como arquivos HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 3: ajustar o tamanho da imagem
Dentro de um bloco using para o objeto Viewer, ajuste o tamanho da imagem para desenhos CAD definindo as opções apropriadas:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Etapa 4: Exibir diretório de saída
Após renderizar o documento, exiba uma mensagem indicando a renderização bem-sucedida e forneça a localização do diretório de saída:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Ajustar o tamanho da imagem de saída para desenhos CAD é crucial para melhorar sua visibilidade e usabilidade. Com GroupDocs.Viewer for .NET, esse processo se torna simplificado e eficiente, permitindo personalizar a saída de acordo com seus requisitos específicos.
## Perguntas frequentes
### Posso ajustar o tamanho da imagem de saída para outros tipos de documentos além de desenhos CAD?
Sim, o GroupDocs.Viewer for .NET oferece suporte a vários tipos de documentos e você pode ajustar o tamanho da imagem de saída para a maioria dos formatos de documentos.
### O GroupDocs.Viewer for .NET é compatível com diferentes versões do .NET framework?
Sim, o GroupDocs.Viewer for .NET é compatível com diversas versões do .NET framework, garantindo flexibilidade e usabilidade em diferentes ambientes.
### Há alguma opção de licenciamento disponível para GroupDocs.Viewer for .NET?
Sim, você pode explorar diferentes opções de licenciamento, incluindo licenças temporárias e licenças comerciais, para atender às suas necessidades.
### Posso personalizar o formato de saída dos documentos renderizados?
Com certeza, GroupDocs.Viewer for .NET oferece várias opções de personalização, permitindo personalizar o formato de saída de acordo com suas preferências.
### Onde posso encontrar suporte ou assistência adicional com GroupDocs.Viewer for .NET?
 Você pode visitar o fórum GroupDocs.Viewer[aqui](https://forum.groupdocs.com/c/viewer/9) para obter suporte, fazer perguntas e interagir com a comunidade.