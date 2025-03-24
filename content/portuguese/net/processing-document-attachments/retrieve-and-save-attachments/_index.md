---
title: Recuperar e salvar anexos de documentos
linktitle: Recuperar e salvar anexos de documentos
second_title: API GroupDocs.Viewer .NET
description: Gerencie com eficiência anexos de documentos em aplicativos .NET usando GroupDocs.Viewer. Recupere e salve anexos sem complicações.
weight: 12
url: /pt/net/processing-document-attachments/retrieve-and-save-attachments/
---

# Recuperar e salvar anexos de documentos

## Introdução
Na era digital, o tratamento eficiente de documentos é crucial tanto para empresas como para indivíduos. Seja gerenciando e-mails, visualizando contratos ou acessando relatórios, contar com uma ferramenta confiável para visualização de documentos é essencial. GroupDocs.Viewer for .NET surge como uma solução robusta, capacitando os usuários a visualizar e interagir sem esforço com vários formatos de documentos diretamente em seus aplicativos .NET.
## Pré-requisitos
Antes de começar a utilizar o GroupDocs.Viewer for .NET para recuperar e salvar anexos de documentos, certifique-se de ter os seguintes pré-requisitos:
1. Ambiente Operacional: Um ambiente de trabalho configurado com o .NET framework.
2.  Instalação: biblioteca GroupDocs.Viewer para .NET baixada e instalada. Você pode acessar a biblioteca a partir do[Link para Download](https://releases.groupdocs.com/viewer/net/).
3. Compreensão Básica: Familiaridade com a linguagem de programação C#.
4. Fonte do Documento: Acesso a um documento modelo com anexos para fins de demonstração.

## Importar namespaces
Para começar a utilizar o GroupDocs.Viewer for .NET para recuperar e salvar anexos de documentos, importe os namespaces necessários:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Defina o diretório onde deseja salvar os anexos recuperados do documento.
## Etapa 2: instanciar o objeto visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instancie o objeto Viewer com o caminho para o documento que contém os anexos.
## Etapa 3: recuperar anexos
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Recuperar uma lista de anexos presentes no documento.
## Etapa 4: salvar anexos
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Itere cada anexo, defina o caminho do arquivo e salve o anexo no diretório especificado.
## Etapa 5: exibir mensagem de sucesso
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Exiba uma mensagem de sucesso indicando o salvamento bem-sucedido dos anexos junto com o caminho do diretório.

## Conclusão
Incorporar o GroupDocs.Viewer for .NET em seus fluxos de trabalho de manuseio de documentos agiliza o processo de gerenciamento de anexos, oferecendo eficiência e conveniência. Seguindo o guia passo a passo descrito acima, os usuários podem recuperar e salvar facilmente anexos de documentos em seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer for .NET pode lidar com vários formatos de documentos?
Sim, o GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, documentos do Microsoft Office, imagens e muito mais.
### Existe uma avaliação gratuita disponível para GroupDocs.Viewer for .NET?
 Sim, você pode acessar o teste gratuito em[aqui](https://releases.groupdocs.com/).
### Como posso obter licenças temporárias para GroupDocs.Viewer for .NET?
 Licenças temporárias podem ser adquiridas em[esse link](https://purchase.groupdocs.com/temporary-license/).
### Onde posso encontrar a documentação do GroupDocs.Viewer for .NET?
 Documentação abrangente está disponível[aqui](https://tutorials.groupdocs.com/viewer/net/).
### Quais opções de suporte estão disponíveis para GroupDocs.Viewer for .NET?
 Você pode procurar ajuda no fórum da comunidade[aqui](https://forum.groupdocs.com/c/viewer/9).