---
title: Obtenha nomes de planilhas
linktitle: Obtenha nomes de planilhas
second_title: API GroupDocs.Viewer .NET
description: Explore a magia do GroupDocs.Viewer for .NET – integre perfeitamente a visualização de documentos aos seus aplicativos. Experimente o teste gratuito agora!
weight: 11
url: /pt/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Introdução
Bem-vindo ao fascinante mundo do GroupDocs.Viewer for .NET! Se você é um desenvolvedor ou entusiasta interessado em explorar recursos poderosos de visualização de documentos em seus aplicativos .NET, você terá uma surpresa. Neste guia abrangente, nos aprofundaremos nas complexidades da recuperação de nomes de planilhas usando GroupDocs.Viewer. Então, aperte o cinto e vamos embarcar nessa emocionante jornada!
## Pré-requisitos
Antes de mergulharmos na magia da codificação, vamos garantir que você tenha tudo configurado:
1.  Instale GroupDocs.Viewer for .NET: Vá para o[Link para Download](https://releases.groupdocs.com/viewer/net/)para obter a versão mais recente do GroupDocs.Viewer for .NET. Siga as instruções de instalação para integrá-lo perfeitamente ao seu ambiente de desenvolvimento.
2. Prepare seu documento: certifique-se de ter um documento de destino, digamos um arquivo Excel chamado “file.xlsx”, no diretório de documentos designado.
## Importar namespaces
Agora que você tem os pré-requisitos definidos, vamos começar importando os namespaces necessários. Isso garante que seu aplicativo reconheça e possa utilizar as funcionalidades fornecidas pelo GroupDocs.Viewer for .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Configurando o diretório de documentos
```csharp
string outputDirectory = "Your Document Directory";
```
Substitua “Seu diretório de documentos” pelo caminho para o diretório onde seu documento de destino está localizado.
## 2. Inicializando o Visualizador
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Nesta etapa, criamos uma instância da classe Viewer, fornecendo o caminho para o seu arquivo Excel.
## 3. Configurando opções de informações de visualização
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Aqui, configuramos ViewInfoOptions para gerar visualizações HTML e definir opções adicionais para renderização de planilhas.
## 4. Recuperando informações de visualização
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilize a instância do Viewer para recuperar informações de visualização com base nas opções configuradas.
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
Parabéns! Você navegou com sucesso pelo processo de busca de nomes de planilhas usando GroupDocs.Viewer for .NET. Isso abre uma infinidade de possibilidades para aprimorar as funcionalidades de visualização de documentos em seus aplicativos.
## Perguntas frequentes
### Posso usar o GroupDocs.Viewer for .NET com outros formatos de documentos?
Absolutamente! GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, Microsoft Office e muito mais.
### Existe um teste gratuito disponível?
 Sim, você pode explorar o GroupDocs.Viewer for .NET com nosso[teste grátis](https://releases.groupdocs.com/).
### Onde posso encontrar suporte adicional?
 Vá para o[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para apoio e discussões da comunidade.
### Posso obter uma licença temporária?
 Certamente! Visita[esse link](https://purchase.groupdocs.com/temporary-license/) para obter sua licença temporária.
### Existem recursos de documentação detalhada disponíveis?
 Absolutamente! Confira a[documentação oficial](https://tutorials.groupdocs.com/viewer/net/) para obter informações e guias detalhados.