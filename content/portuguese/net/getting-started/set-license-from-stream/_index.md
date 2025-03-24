---
title: Definir licença do Stream
linktitle: Definir licença do Stream
second_title: API GroupDocs.Viewer .NET
description: Aprimore seus aplicativos .NET com GroupDocs.Viewer para visualização perfeita de documentos. Siga nosso guia passo a passo e integre recursos poderosos de visualização de documentos sem esforço.
weight: 11
url: /pt/net/getting-started/set-license-from-stream/
---

# Definir licença do Stream

## Introdução
Você deseja capacitar seus aplicativos .NET com recursos avançados de visualização de documentos? GroupDocs.Viewer for .NET oferece uma solução abrangente para integrar perfeitamente funcionalidades de visualização de documentos em seus projetos. Neste tutorial, nos aprofundaremos no processo de aproveitamento do GroupDocs.Viewer for .NET para enriquecer seus aplicativos com poderosos recursos de visualização de documentos. 
## Pré-requisitos
Antes de mergulharmos no processo de integração, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Conhecimento básico de desenvolvimento .NET: Familiaridade com C# e estrutura .NET é essencial para acompanhar este tutorial.
   
2.  Pacote GroupDocs.Viewer for .NET: certifique-se de ter baixado e instalado o pacote GroupDocs.Viewer for .NET. Você pode obtê-lo no[Link para Download](https://releases.groupdocs.com/viewer/net/).
3.  Acesso à documentação do GroupDocs: Mantenha o[documentação](https://tutorials.groupdocs.com/viewer/net/) útil para referência durante o processo de integração.

## Importar namespaces
Para começar, importe os namespaces necessários para seu aplicativo .NET. Siga esses passos:
### Passo 1: Abra seu projeto .NET.
Certifique-se de ter seu projeto .NET aberto em seu ambiente de desenvolvimento preferido.
### Etapa 2: adicione o namespace GroupDocs.Viewer.
Em seu arquivo de código, adicione o seguinte namespace para acessar as funcionalidades do GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Definir licença do Stream
A próxima etapa envolve definir a licença de um stream. Siga estas etapas detalhadas:
### Etapa 1: Definir o diretório de saída.
Defina o diretório onde seus documentos serão armazenados definindo o diretório de saída:
```csharp
string outputDirectory = "Your Document Directory";
```
### Etapa 2: Verifique a existência do arquivo de licença.
Verifique se o arquivo de licença existe no diretório do seu projeto:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Etapa 3: definir licença.
Se o arquivo de licença existir, defina a licença usando o fluxo fornecido:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Etapa 4: Lidar com a ausência de licença.
Se o arquivo de licença não for encontrado, forneça instruções para obter uma licença:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license.");
}
```

## Conclusão
Parabéns! Você aprendeu com sucesso como integrar o GroupDocs.Viewer for .NET aos seus aplicativos. Com esta ferramenta poderosa, agora você pode visualizar facilmente vários formatos de documentos em seus projetos .NET, melhorando a experiência do usuário e a produtividade.
## Perguntas frequentes
### Preciso de uma licença para usar o GroupDocs.Viewer for .NET?
Sim, você precisa de uma licença para usar o GroupDocs.Viewer for .NET. Você pode obter uma licença temporária ou permanente no site GroupDocs.
### Posso integrar o GroupDocs.Viewer ao meu aplicativo ASP.NET?
Absolutamente! GroupDocs.Viewer for .NET integra-se perfeitamente em aplicativos de desktop e web, incluindo ASP.NET.
### Quais formatos de documento são suportados pelo GroupDocs.Viewer?
GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, Microsoft Office (Word, Excel, PowerPoint), imagens e muito mais.
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, GroupDocs.Viewer for .NET é compatível com .NET Framework e .NET Core.
### Posso personalizar a interface do visualizador de acordo com o tema da minha aplicação?
Sim, o GroupDocs.Viewer oferece amplas opções de personalização, permitindo que você adapte a interface do visualizador para combinar perfeitamente com o tema do seu aplicativo.