---
title: Carregar documentos do stream
linktitle: Carregar documentos do stream
second_title: API GroupDocs.Viewer .NET
description: Aprenda como carregar documentos de fluxos de maneira transparente usando GroupDocs.Viewer for .NET. Aprimore seus aplicativos .NET com poderosos recursos de visualização de documentos.
weight: 12
url: /pt/net/loading-documents/loading-document-stream/
---

# Carregar documentos do stream

## Introdução
No domínio do desenvolvimento .NET, gerenciar e visualizar documentos com eficiência é fundamental. Com o advento de ferramentas e bibliotecas avançadas, tarefas que antes pareciam assustadoras agora são simplificadas. Dentre essas ferramentas, GroupDocs.Viewer for .NET se destaca como uma solução versátil para lidar perfeitamente com diversos formatos de documentos. Neste guia abrangente, nos aprofundamos nas complexidades do uso do GroupDocs.Viewer for .NET para carregar documentos de um fluxo. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este tutorial irá equipá-lo com o conhecimento para aproveitar o poder do GroupDocs.Viewer de forma eficaz.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Compreensão básica de C# e .NET Framework: A familiaridade com a linguagem de programação C# e o .NET Framework ajudará na compreensão dos conceitos discutidos.
   
2.  Instalação do GroupDocs.Viewer for .NET: Baixe e instale o GroupDocs.Viewer for .NET a partir do[local na rede Internet](https://releases.groupdocs.com/viewer/net/).
3. IDE: tenha um ambiente de desenvolvimento integrado (IDE) como o Visual Studio instalado para codificação e teste.
4. Fluxo de documentos: prepare um fluxo de documentos para carregamento. Pode ser um fluxo de arquivo ou qualquer outra fonte de fluxo compatível.

## Importar namespaces
Antes de implementar o código para carregar documentos de um fluxo, importe os namespaces necessários:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Defina o caminho do diretório onde o documento renderizado será salvo.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Defina o formato do caminho do arquivo de cada página. Aqui, "{0}" será substituído pelo número da página.
## Etapa 3: obter fluxo de documentos
```csharp
Stream stream = GetFileStream();
```
Obtenha o fluxo de documentos da fonte desejada. Pode ser um fluxo de arquivo, fluxo de memória ou qualquer outro fluxo compatível.
## Etapa 4: carregar o documento usando o visualizador
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Inicialize uma nova instância da classe Viewer com o fluxo de documentos. Em seguida, configure as opções de visualização HTML e renderize o documento.
## Etapa 5: Exibir diretório de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informe o usuário sobre a renderização bem-sucedida do documento e forneça o local onde a saída foi salva.

## Conclusão
Concluindo, GroupDocs.Viewer for .NET oferece uma solução robusta para carregar e visualizar documentos de fluxos sem esforço. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente recursos de visualização de documentos em seus aplicativos .NET, melhorando a experiência do usuário e a produtividade.
## Perguntas frequentes
### O GroupDocs.Viewer for .NET pode lidar com diferentes formatos de documentos?
Sim, GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, DOCX, XLSX, PPTX e muito mais.
### O GroupDocs.Viewer for .NET é adequado para aplicativos da Web e de desktop?
Absolutamente! O GroupDocs.Viewer pode ser perfeitamente integrado a aplicativos da web e de desktop desenvolvidos em .NET.
### O GroupDocs.Viewer oferece opções de personalização para renderização de documentos?
Sim, você pode personalizar vários aspectos da renderização do documento, como marca d'água, rotação de página e nível de zoom, de acordo com suas necessidades.
### Posso usar o GroupDocs.Viewer for .NET em projetos comerciais?
Sim, o GroupDocs.Viewer oferece opções de licenciamento adequadas para projetos comerciais. Você pode comprar licenças do site oficial[local na rede Internet](https://purchase.groupdocs.com/temporary-license/).
### O suporte técnico está disponível para GroupDocs.Viewer for .NET?
 Sim, você pode buscar assistência técnica e orientação no fórum de suporte dedicado fornecido por[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).