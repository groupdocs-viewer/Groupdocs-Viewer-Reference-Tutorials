---
"description": "Aprenda a renderizar páginas selecionadas de documentos usando o Groupdocs.Viewer para .NET. Tutorial passo a passo com exemplos de código incluídos."
"linktitle": "Renderizar páginas selecionadas"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar páginas selecionadas"
"url": "/pt/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Renderizar páginas selecionadas

## Introdução

Neste tutorial, vamos nos aprofundar em como utilizar o Groupdocs.Viewer para .NET para renderizar páginas selecionadas de um documento. Seja você um desenvolvedor experiente ou iniciante, este guia passo a passo o guiará pelo processo com facilidade.

## Pré-requisitos

Antes de começar, certifique-se de que você tenha os seguintes pré-requisitos:

### 1. Instalação

Certifique-se de ter o Groupdocs.Viewer para .NET instalado em seu ambiente de desenvolvimento. Caso contrário, você pode baixá-lo do site [Link para download](https://releases.groupdocs.com/viewer/net/).

## Importando namespaces

No seu arquivo de código C#, importe os namespaces necessários para acessar as classes e métodos necessários. Você pode fazer isso usando o `using` diretiva:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora vamos dividir o código de exemplo fornecido em várias etapas:

## Etapa 1: definir diretório de saída

Defina o diretório onde deseja que as páginas renderizadas sejam salvas. Substituir `"Your Document Directory"` com o caminho do diretório desejado.

```csharp
string outputDirectory = "Your Document Directory";
```

## Etapa 2: Definir o formato do caminho do arquivo de página

Especifique o formato para os caminhos de arquivo das páginas renderizadas. Isso será usado para salvar cada página como um arquivo HTML no diretório de saída.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Etapa 3: Instanciar objeto do visualizador

Crie uma instância da classe Viewer, passando o caminho do documento que você deseja renderizar como argumento.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Etapa 4: Configurar opções de visualização HTML

Configure as opções de visualização HTML para renderização. Neste exemplo, estamos configurando opções para incorporar recursos na saída HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Etapa 5: renderizar páginas selecionadas

Especifique os números de página que deseja renderizar. Neste caso, estamos renderizando as páginas 1 a 3. Em seguida, chame o método View no objeto Viewer, passando as opções e os números de página como argumentos.

```csharp
viewer.View(options, 1, 3);
```

## Etapa 6: Resultado de saída

Por fim, exiba uma mensagem indicando a renderização bem-sucedida do documento e o local onde os arquivos de saída foram salvos.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão

Parabéns! Você aprendeu com sucesso a renderizar páginas selecionadas de um documento usando o Groupdocs.Viewer para .NET. Com esse conhecimento, agora você pode integrar recursos de renderização de documentos aos seus aplicativos .NET com facilidade.

## Perguntas frequentes

### P: Posso renderizar páginas de diferentes tipos de documentos, como PDFs ou imagens?

R: Sim, o Groupdocs.Viewer para .NET suporta a renderização de páginas de vários formatos de documentos, incluindo PDFs, documentos do Microsoft Office e arquivos de imagem.

### P: Existe uma versão de teste disponível para testes antes da compra?

R: Sim, você pode acessar uma versão de teste gratuita do Groupdocs.Viewer para .NET no [site](https://releases.groupdocs.com/).

### P: Posso personalizar o formato de saída além de HTML?

R: Com certeza, o Groupdocs.Viewer para .NET oferece opções para renderizar páginas como imagens, PDFs e muito mais, além de HTML.

### P: Como posso obter licenças temporárias para fins de testes?

A: As licenças temporárias podem ser adquiridas na [página de licença temporária](https://purchase.groupdocs.com/temporary-license/) no site Groupdocs.

### P: Onde posso buscar assistência ou obter ajuda com quaisquer problemas que eu encontrar?

A: Você pode visitar o [Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para obter suporte e orientação da comunidade e dos desenvolvedores.