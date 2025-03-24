---
title: Obtenha informações de visualização para arquivos de dados do Outlook (PST, OST)
linktitle: Obtenha informações de visualização para arquivos de dados do Outlook (PST, OST)
second_title: API GroupDocs.Viewer .NET
description: Explore como extrair informações de visualização de arquivos de dados do Outlook (PST, OST) usando GroupDocs.Viewer for .NET. Aprimore seus recursos de gerenciamento de documentos sem esforço.
weight: 10
url: /pt/net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---
## Introdução
No domínio do gerenciamento e visualização de documentos, GroupDocs.Viewer for .NET se destaca como uma ferramenta poderosa, especialmente quando se trata de lidar com arquivos de dados do Outlook (PST, OST). Neste tutorial, nos aprofundaremos no processo de extração de informações de visualização para esses arquivos passo a passo.
## Pré-requisitos
Antes de embarcarmos neste tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
### 1. Instalação do GroupDocs.Viewer para .NET
 Primeiramente, você precisa ter o GroupDocs.Viewer for .NET instalado em seu ambiente de desenvolvimento. Você pode baixar o pacote necessário no[Site GroupDocs.Viewer para .NET](https://releases.groupdocs.com/viewer/net/).
### 2. Familiaridade com a linguagem de programação C#
O conhecimento básico da linguagem de programação C# é essencial para compreender e implementar os exemplos de código fornecidos.
### 3. Arquivos de dados do Outlook (PST, OST)
Certifique-se de ter arquivos de dados do Outlook (PST, OST) disponíveis para fins de teste. Você pode obter arquivos de amostra de diversas fontes ou usar seus próprios arquivos de dados.

## Importar namespaces
Antes de mergulhar no código, vamos importar os namespaces necessários:
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Agora, vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: instanciar o objeto visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Aqui, estamos inicializando um objeto Viewer com o caminho para o arquivo de dados do Outlook (OST) especificado como argumento.
## Etapa 2: configurar opções de visualização de informações
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
Estamos configurando as opções para recuperar informações de visualização. Neste caso, optamos pela visualização HTML.
## Etapa 3: recuperar informações de visualização do Outlook
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
Esta linha busca as informações de visualização do arquivo de dados do Outlook.
## Etapa 4: exibir tipo de arquivo e contagem de páginas
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
Estamos imprimindo o tipo de arquivo e a contagem de páginas no arquivo de dados do Outlook.
## Etapa 5: iterar pelas pastas
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
Esse loop percorre as pastas contidas no arquivo de dados do Outlook e imprime seus nomes.
## Etapa 6: finalizar a recuperação
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
Uma mensagem indicando a recuperação bem-sucedida das informações de visualização é exibida.

## Conclusão
GroupDocs.Viewer for .NET fornece uma solução perfeita para extrair informações de visualização de arquivos de dados do Outlook (PST, OST). Seguindo as etapas descritas neste tutorial, você pode obter facilmente informações valiosas sobre esses arquivos para aprimorar o gerenciamento de documentos.
## Perguntas frequentes
### GroupDocs.Viewer for .NET é compatível com diferentes versões de arquivos de dados do Outlook?
Sim, o GroupDocs.Viewer for .NET oferece suporte a várias versões de arquivos de dados do Outlook, garantindo compatibilidade em diferentes ambientes.
### Posso personalizar as opções de visualização dos arquivos de dados do Outlook usando GroupDocs.Viewer for .NET?
Absolutamente! GroupDocs.Viewer for .NET oferece amplas opções de personalização, permitindo personalizar a experiência de visualização de acordo com suas necessidades.
### O GroupDocs.Viewer for .NET oferece suporte a outros formatos de arquivo além dos arquivos de dados do Outlook?
Sim, o GroupDocs.Viewer for .NET oferece suporte a uma ampla variedade de formatos de arquivo, incluindo, entre outros, PDF, DOCX, XLSX e muito mais.
### Existe uma avaliação gratuita disponível para GroupDocs.Viewer for .NET?
 Sim, você pode acessar uma avaliação gratuita do GroupDocs.Viewer for .NET no site:[Teste grátis](https://releases.groupdocs.com/).
### Onde posso encontrar suporte ou assistência adicional para GroupDocs.Viewer for .NET?
 Para qualquer dúvida ou assistência, você pode visitar o fórum de suporte do GroupDocs.Viewer for .NET:[Apoiar](https://forum.groupdocs.com/c/viewer/9).