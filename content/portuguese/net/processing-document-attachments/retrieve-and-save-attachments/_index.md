---
"description": "Gerencie anexos de documentos com eficiência em aplicativos .NET usando o GroupDocs.Viewer. Recupere e salve anexos sem complicações."
"linktitle": "Recuperar e salvar anexos de documentos"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Recuperar e salvar anexos de documentos"
"url": "/pt/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# Recuperar e salvar anexos de documentos

## Introdução
Na era digital, o gerenciamento eficiente de documentos é crucial para empresas e indivíduos. Seja para gerenciar e-mails, visualizar contratos ou acessar relatórios, ter uma ferramenta confiável para visualização de documentos é essencial. O GroupDocs.Viewer para .NET surge como uma solução robusta, permitindo que os usuários visualizem e interajam facilmente com diversos formatos de documentos diretamente em seus aplicativos .NET.

![Recuperar e salvar anexos de documentos com GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Pré-requisitos
Antes de começar a utilizar o GroupDocs.Viewer para .NET para recuperar e salvar anexos de documentos, certifique-se de ter os seguintes pré-requisitos:
1. Ambiente operacional: Um ambiente de trabalho configurado com o .NET Framework.
2. Instalação: Biblioteca GroupDocs.Viewer para .NET baixada e instalada. Você pode acessar a biblioteca a partir do [link para download](https://releases.groupdocs.com/viewer/net/).
3. Noções básicas: Familiaridade com a linguagem de programação C#.
4. Fonte do documento: acesso a um documento de exemplo com anexos para fins de demonstração.

## Importar namespaces
Para começar a utilizar o GroupDocs.Viewer for .NET para recuperar e salvar anexos de documentos, importe os namespaces necessários:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Etapa 1: definir diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Defina o diretório onde você deseja salvar os anexos recuperados do documento.
## Etapa 2: Instanciar objeto do visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instancie o objeto Viewer com o caminho para o documento que contém anexos.
## Etapa 3: recuperar anexos
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Recuperar uma lista de anexos presentes no documento.
## Etapa 4: Salvar anexos
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Percorra cada anexo, defina o caminho do arquivo e salve o anexo no diretório especificado.
## Etapa 5: Exibir mensagem de sucesso
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Exibe uma mensagem de sucesso indicando que os anexos foram salvos com sucesso, juntamente com o caminho do diretório.

## Conclusão
A incorporação do GroupDocs.Viewer para .NET aos seus fluxos de trabalho de gerenciamento de documentos simplifica o processo de gerenciamento de anexos, oferecendo eficiência e conveniência. Seguindo o guia passo a passo descrito acima, os usuários podem recuperar e salvar anexos de documentos facilmente em seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer para .NET pode manipular vários formatos de documentos?
Sim, o GroupDocs.Viewer suporta uma ampla variedade de formatos de documentos, incluindo PDF, documentos do Microsoft Office, imagens e muito mais.
### Existe uma avaliação gratuita disponível para o GroupDocs.Viewer para .NET?
Sim, você pode acessar o teste gratuito em [aqui](https://releases.groupdocs.com/).
### Como posso obter licenças temporárias para o GroupDocs.Viewer para .NET?
As licenças temporárias podem ser adquiridas em [este link](https://purchase.groupdocs.com/temporary-license/).
### Onde posso encontrar documentação do GroupDocs.Viewer para .NET?
Documentação abrangente disponível [aqui](https://tutorials.groupdocs.com/viewer/net/).
### Quais opções de suporte estão disponíveis para o GroupDocs.Viewer para .NET?
Você pode buscar ajuda no fórum da comunidade [aqui](https://forum.groupdocs.com/c/viewer/9).