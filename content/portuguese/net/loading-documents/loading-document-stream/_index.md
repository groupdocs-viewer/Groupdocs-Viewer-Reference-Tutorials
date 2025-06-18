---
"description": "Aprenda a carregar documentos de fluxos com facilidade usando o GroupDocs.Viewer para .NET. Aprimore seus aplicativos .NET com poderosos recursos de visualização de documentos."
"linktitle": "Carregar documentos do fluxo"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Carregar documentos do fluxo"
"url": "/pt/net/loading-documents/loading-document-stream/"
"weight": 12
---

# Carregar documentos do fluxo

## Introdução
No âmbito do desenvolvimento .NET, gerenciar e visualizar documentos com eficiência é fundamental. Com o advento de ferramentas e bibliotecas avançadas, tarefas que antes pareciam assustadoras agora são simplificadas. Entre essas ferramentas, o GroupDocs.Viewer para .NET se destaca como uma solução versátil para lidar perfeitamente com diversos formatos de documentos. Neste guia abrangente, exploramos as complexidades do uso do GroupDocs.Viewer para .NET para carregar documentos de um fluxo. Seja você um desenvolvedor experiente ou iniciante, este tutorial o equipará com o conhecimento necessário para aproveitar o poder do GroupDocs.Viewer de forma eficaz.

![Carregar documentos do fluxo com GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-stream.png)

## Pré-requisitos
Antes de começar o tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Noções básicas de C# e .NET Framework: A familiaridade com a linguagem de programação C# e o .NET Framework ajudará na compreensão dos conceitos discutidos.
   
2. Instalação do GroupDocs.Viewer para .NET: Baixe e instale o GroupDocs.Viewer para .NET do [site](https://releases.groupdocs.com/viewer/net/).
3. IDE: tenha um Ambiente de Desenvolvimento Integrado (IDE), como o Visual Studio, instalado para codificação e testes.
4. Fluxo de Documentos: Prepare um fluxo de documentos para carregamento. Pode ser um fluxo de arquivos ou qualquer outra fonte de fluxo compatível.

## Importar namespaces
Antes de implementar o código para carregar documentos de um fluxo, certifique-se de importar os namespaces necessários:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: definir diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Defina o caminho do diretório onde o documento renderizado será salvo.
## Etapa 2: Definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Defina o formato do caminho do arquivo de cada página. Aqui, "{0}" será substituído pelo número da página.
## Etapa 3: Obtenha o Document Stream
```csharp
Stream stream = GetFileStream();
```
Obtenha o fluxo de documentos da fonte desejada. Pode ser um fluxo de arquivo, um fluxo de memória ou qualquer outro fluxo compatível.
## Etapa 4: Carregar documento usando o visualizador
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
Concluindo, o GroupDocs.Viewer para .NET oferece uma solução robusta para carregar e visualizar documentos de fluxos sem esforço. Seguindo os passos descritos neste tutorial, você pode integrar perfeitamente os recursos de visualização de documentos aos seus aplicativos .NET, aprimorando a experiência do usuário e a produtividade.
## Perguntas frequentes
### O GroupDocs.Viewer para .NET pode manipular diferentes formatos de documentos?
Sim, o GroupDocs.Viewer suporta uma ampla variedade de formatos de documentos, incluindo PDF, DOCX, XLSX, PPTX e muito mais.
### O GroupDocs.Viewer para .NET é adequado para aplicativos web e desktop?
Com certeza! O GroupDocs.Viewer pode ser perfeitamente integrado a aplicativos web e desktop desenvolvidos com .NET.
### O GroupDocs.Viewer oferece opções de personalização para renderização de documentos?
Sim, você pode personalizar vários aspectos da renderização de documentos, como marca d'água, rotação de página e nível de zoom, de acordo com suas necessidades.
### Posso usar o GroupDocs.Viewer para .NET em projetos comerciais?
Sim, o GroupDocs.Viewer oferece opções de licenciamento adequadas para projetos comerciais. Você pode adquirir licenças no site oficial [site](https://purchase.groupdocs.com/temporary-license/).
### Há suporte técnico disponível para o GroupDocs.Viewer para .NET?
Sim, você pode buscar assistência técnica e orientação no fórum de suporte dedicado fornecido por [GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).