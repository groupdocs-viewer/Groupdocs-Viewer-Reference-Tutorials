---
title: Ajustar tamanho e qualidade da imagem (JPG)
linktitle: Ajustar tamanho e qualidade da imagem (JPG)
second_title: API GroupDocs.Viewer .NET
description: Aprenda como otimizar o tamanho e a qualidade da imagem no formato JPEG usando Groupdocs.Viewer for .NET. Aprimore sua experiência de visualização de documentos.
type: docs
weight: 11
url: /pt/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Introdução
Groupdocs.Viewer for .NET é uma biblioteca poderosa que permite aos desenvolvedores integrar perfeitamente a funcionalidade de visualização de documentos em seus aplicativos .NET. Um requisito comum em aplicativos de visualização de documentos é a capacidade de ajustar o tamanho e a qualidade das imagens, principalmente ao lidar com imagens JPEG (JPG). Neste tutorial, orientaremos você no processo de ajuste do tamanho e da qualidade da imagem usando Groupdocs.Viewer for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Compreensão básica da linguagem de programação C#.
2. Visual Studio instalado em seu sistema.
3.  Biblioteca Groupdocs.Viewer para .NET instalada. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para o seu código C#. Esses namespaces fornecem acesso às classes e métodos necessários para trabalhar com Groupdocs.Viewer.
## Etapa 1: importar namespaces
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos dividir o código de exemplo fornecido em várias etapas para um melhor entendimento.
## Etapa 2: definir o diretório de saída e o formato do caminho do arquivo de página
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Nesta etapa, especificamos o diretório de saída onde as imagens renderizadas serão salvas e definimos o formato do caminho do arquivo de cada imagem da página.
## Etapa 3: inicializar o visualizador e configurar as opções de visualização JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Aqui inicializamos o objeto Viewer com o caminho do documento a ser visualizado. Em seguida, criamos uma instância de JpgViewOptions e definimos a largura e altura desejadas para as imagens JPEG.
## Etapa 4: renderizar o documento de origem
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Por fim, imprimimos uma mensagem indicando a renderização bem-sucedida do documento de origem e o local onde as imagens de saída foram salvas.

## Conclusão
Neste tutorial, aprendemos como ajustar o tamanho e a qualidade das imagens JPEG usando Groupdocs.Viewer for .NET. Seguindo as etapas descritas acima, você pode incorporar facilmente essa funcionalidade em seus aplicativos .NET, proporcionando aos usuários uma experiência otimizada de visualização de imagens.
## Perguntas frequentes
### Posso ajustar a qualidade da imagem também?
Sim, você pode ajustar a qualidade da imagem definindo a propriedade Quality em JpgViewOptions.
### Quais formatos de documento são suportados pelo Groupdocs.Viewer for .NET?
Groupdocs.Viewer for .NET oferece suporte a uma ampla variedade de formatos de documentos, incluindo DOCX, PDF, PPTX, XLSX e muito mais.
### O Groupdocs.Viewer para .NET é compatível com o .NET Core?
Sim, o Groupdocs.Viewer for .NET é compatível com o .NET Core junto com o .NET Framework tradicional.
### Posso personalizar o formato de nomenclatura do arquivo de saída?
Sim, você pode personalizar o formato de nomenclatura do arquivo de saída modificando a variável pageFilePathFormat no código.
### O Groupdocs.Viewer for .NET oferece suporte a anotações de documentos?
Sim, o Groupdocs.Viewer for .NET fornece suporte abrangente para anotações de documentos, incluindo destaque, sublinhado e comentários de texto.