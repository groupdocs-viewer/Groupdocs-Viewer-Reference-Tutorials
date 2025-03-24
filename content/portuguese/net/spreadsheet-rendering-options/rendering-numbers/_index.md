---
title: Renderizando Números
linktitle: Renderizando Números
second_title: API GroupDocs.Viewer .NET
description: Explore o poder do Groupdocs.Viewer for .NET na renderização perfeita de arquivos do Numbers. Converta para HTML, JPG, PNG e PDF sem esforço.
weight: 15
url: /pt/net/spreadsheet-rendering-options/rendering-numbers/
---

# Renderizando Números

## Introdução
Bem-vindo a este tutorial passo a passo sobre renderização de arquivos do Numbers usando Groupdocs.Viewer para .NET. Quer você seja um desenvolvedor experiente ou iniciante, este guia irá orientá-lo no processo de conversão de documentos do Numbers em vários formatos. Groupdocs.Viewer for .NET é uma ferramenta poderosa que permite integrar perfeitamente recursos de visualização de documentos em seus aplicativos .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de desenvolvimento em C# e .NET.
-  Biblioteca Groupdocs.Viewer para .NET instalada. Você pode baixá-lo[aqui](https://releases.groupdocs.com/viewer/net/).
- O caminho do diretório do documento onde os arquivos de saída serão salvos.
## Importar namespaces
Em seu projeto C#, certifique-se de importar os namespaces necessários para usar a biblioteca Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: configurar o diretório de saída
Antes de iniciar a renderização, defina o diretório de saída onde os arquivos convertidos serão salvos. Substitua "Seu diretório de documentos" pelo caminho real:
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: renderizar em HTML de várias páginas
Use o código a seguir para converter o arquivo do Numbers em HTML de várias páginas:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Etapa 3: renderizar para JPG
Converta o arquivo Numbers para o formato JPG com o seguinte código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Etapa 4: renderizar para PNG
Transforme o arquivo Numbers em formato PNG usando o seguinte código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Etapa 5: renderizar em PDF
Por último, converta o arquivo Numbers para o formato PDF usando o seguinte código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Parabéns! Você renderizou com sucesso arquivos do Numbers em vários formatos usando Groupdocs.Viewer for .NET.
## Conclusão
Neste tutorial, cobrimos os fundamentos da renderização de arquivos do Numbers usando Groupdocs.Viewer para .NET. Esta poderosa biblioteca oferece integração perfeita para visualização e conversão de documentos em seus aplicativos .NET.
## Perguntas frequentes
### Posso usar o Groupdocs.Viewer for .NET com outros tipos de documentos?
Sim, o Groupdocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo Word, Excel, PDF e muito mais.
### Existe uma licença temporária disponível para fins de teste?
 Sim, você pode obter uma licença temporária[aqui](https://purchase.groupdocs.com/temporary-license/) para teste.
### Onde posso encontrar suporte para Groupdocs.Viewer for .NET?
 Visite a[Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para assistência e discussões.
### Como posso adquirir a versão completa do Groupdocs.Viewer for .NET?
 Você pode comprar a versão completa[aqui](https://purchase.groupdocs.com/buy).
### Existe uma versão de teste gratuita disponível?
 Sim, você pode explorar a versão de avaliação gratuita[aqui](https://releases.groupdocs.com/).