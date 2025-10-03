---
"description": "Aprimore seus aplicativos .NET com o GroupDocs.Viewer para uma visualização perfeita de documentos. Siga nosso guia passo a passo e integre recursos avançados de visualização de documentos sem esforço."
"linktitle": "Definir licença do fluxo"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Definir licença do fluxo"
"url": "/pt/net/getting-started/set-license-from-stream/"
"weight": 11
type: docs
---
# Definir licença do fluxo

## Introdução
Deseja potencializar seus aplicativos .NET com recursos avançados de visualização de documentos? O GroupDocs.Viewer para .NET oferece uma solução completa para integrar perfeitamente funcionalidades de visualização de documentos aos seus projetos. Neste tutorial, vamos nos aprofundar no processo de utilização do GroupDocs.Viewer para .NET para enriquecer seus aplicativos com poderosos recursos de visualização de documentos. 

![Definir licença do fluxo com GroupDocs.Viewer para .NET](/viewer/getting-started/set-license-from-stream.png)

## Pré-requisitos
Antes de começarmos o processo de integração, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Conhecimento básico de desenvolvimento .NET: familiaridade com C# e .NET Framework é essencial para acompanhar este tutorial.
   
2. Pacote GroupDocs.Viewer para .NET: Certifique-se de ter baixado e instalado o pacote GroupDocs.Viewer para .NET. Você pode obtê-lo em [link para download](https://releases.groupdocs.com/viewer/net/).
3. Acesso à documentação do GroupDocs: Mantenha o [documentação](https://tutorials.groupdocs.com/viewer/net/) útil para tutoriais durante o processo de integração.

## Importar namespaces
Para começar, importe os namespaces necessários para o seu aplicativo .NET. Siga estes passos:
### Etapa 1: Abra seu projeto .NET.
Certifique-se de ter seu projeto .NET aberto no seu ambiente de desenvolvimento preferido.
### Etapa 2: adicione o namespace GroupDocs.Viewer.
No seu arquivo de código, adicione o seguinte namespace para acessar as funcionalidades do GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Definir licença do fluxo
O próximo passo envolve definir a licença a partir de um fluxo. Siga estes passos detalhados:
### Etapa 1: definir o diretório de saída.
Defina o diretório onde seus documentos serão armazenados definindo o diretório de saída:
```csharp
string outputDirectory = "Your Document Directory";
```
### Etapa 2: verificar a existência do arquivo de licença.
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
### Etapa 4: lidar com a ausência de licença.
Se o arquivo de licença não for encontrado, forneça instruções para obter uma licença:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Conclusão
Parabéns! Você aprendeu com sucesso a integrar o GroupDocs.Viewer para .NET aos seus aplicativos. Com esta poderosa ferramenta, agora você pode visualizar facilmente vários formatos de documentos em seus projetos .NET, aprimorando a experiência do usuário e a produtividade.
## Perguntas frequentes
### Preciso de uma licença para usar o GroupDocs.Viewer para .NET?
Sim, você precisa de uma licença para usar o GroupDocs.Viewer para .NET. Você pode obter uma licença temporária ou permanente no site do GroupDocs.
### Posso integrar o GroupDocs.Viewer ao meu aplicativo ASP.NET?
Com certeza! O GroupDocs.Viewer para .NET integra-se perfeitamente a aplicativos desktop e web, incluindo ASP.NET.
### Quais formatos de documento são suportados pelo GroupDocs.Viewer?
O GroupDocs.Viewer suporta uma ampla variedade de formatos de documentos, incluindo PDF, Microsoft Office (Word, Excel, PowerPoint), imagens e muito mais.
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, o GroupDocs.Viewer para .NET é compatível com o .NET Framework e o .NET Core.
### Posso personalizar a interface do visualizador de acordo com o tema do meu aplicativo?
Sim, o GroupDocs.Viewer oferece amplas opções de personalização, permitindo que você adapte a interface do visualizador para corresponder perfeitamente ao tema do seu aplicativo.