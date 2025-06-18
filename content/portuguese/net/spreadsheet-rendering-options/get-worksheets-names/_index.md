---
"description": "Explore a magia do GroupDocs.Viewer para .NET – integre perfeitamente a visualização de documentos aos seus aplicativos. Experimente o teste gratuito agora mesmo!"
"linktitle": "Obter nomes de planilhas"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Obter nomes de planilhas"
"url": "/pt/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Obter nomes de planilhas

## Introdução
Bem-vindo ao fascinante mundo do GroupDocs.Viewer para .NET! Se você é um desenvolvedor ou entusiasta interessado em explorar recursos poderosos de visualização de documentos em seus aplicativos .NET, você terá uma surpresa. Neste guia completo, vamos nos aprofundar nas complexidades da recuperação de nomes de planilhas usando o GroupDocs.Viewer. Então, aperte o cinto e vamos embarcar nessa jornada emocionante!
## Pré-requisitos
Antes de mergulharmos na mágica da codificação, vamos garantir que você tenha tudo configurado:
1. Instalar GroupDocs.Viewer para .NET: Vá para o [link para download](https://releases.groupdocs.com/viewer/net/) para obter a versão mais recente do GroupDocs.Viewer para .NET. Siga as instruções de instalação para integrá-lo perfeitamente ao seu ambiente de desenvolvimento.
2. Prepare seu documento: certifique-se de ter um documento de destino, digamos, um arquivo do Excel chamado "file.xlsx", no diretório de documentos designado.
## Importar namespaces
Agora que você já tem os pré-requisitos definidos, vamos começar importando os namespaces necessários. Isso garante que seu aplicativo reconheça e possa utilizar as funcionalidades fornecidas pelo GroupDocs.Viewer para .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Configurando o Diretório de Documentos
```csharp
string outputDirectory = "Your Document Directory";
```
Substitua "Seu diretório de documentos" pelo caminho para o diretório onde seu documento de destino está localizado.
## 2. Inicializando o Visualizador
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Nesta etapa, criamos uma instância da classe Viewer, fornecendo o caminho para seu arquivo Excel.
## 3. Configurando opções de informações de exibição
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Aqui, configuramos o ViewInfoOptions para gerar visualizações HTML e definimos opções adicionais para renderização de planilhas.
## 4. Recuperando informações de exibição
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilize a instância do Viewer para recuperar informações de exibição com base nas opções configuradas.
## 5. Exibindo nomes de planilhas
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Percorra as páginas recuperadas e imprima o nome de cada planilha no console.
## Conclusão
Parabéns! Você concluiu com sucesso o processo de busca de nomes de planilhas usando o GroupDocs.Viewer para .NET. Isso abre uma infinidade de possibilidades para aprimorar as funcionalidades de visualização de documentos em seus aplicativos.
## Perguntas frequentes
### Posso usar o GroupDocs.Viewer para .NET com outros formatos de documento?
Com certeza! O GroupDocs.Viewer suporta uma ampla variedade de formatos de documentos, incluindo PDF, Microsoft Office e muito mais.
### Existe um teste gratuito disponível?
Sim, você pode explorar o GroupDocs.Viewer para .NET com nosso [teste gratuito](https://releases.groupdocs.com/).
### Onde posso encontrar suporte adicional?
Vá para o [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para apoio e discussões da comunidade.
### Posso obter uma licença temporária?
Certamente! Visite [este link](https://purchase.groupdocs.com/temporary-license/) para obter sua licença temporária.
### Há recursos de documentação detalhados disponíveis?
Com certeza! Confira o [documentação oficial](https://tutorials.groupdocs.com/viewer/net/) para obter informações e guias detalhados.