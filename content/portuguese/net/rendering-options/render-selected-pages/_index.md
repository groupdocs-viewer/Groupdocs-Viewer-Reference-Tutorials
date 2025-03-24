---
title: Renderizar páginas selecionadas
linktitle: Renderizar páginas selecionadas
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar páginas selecionadas de documentos usando Groupdocs.Viewer for .NET. Tutorial passo a passo com exemplos de código incluídos.
weight: 17
url: /pt/net/rendering-options/render-selected-pages/
---

# Renderizar páginas selecionadas

## Introdução

Neste tutorial, nos aprofundaremos em como utilizar Groupdocs.Viewer for .NET para renderizar páginas selecionadas de um documento. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia passo a passo o guiará pelo processo com facilidade.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

### 1. Instalação

 Certifique-se de ter o Groupdocs.Viewer for .NET instalado em seu ambiente de desenvolvimento. Caso contrário, você pode baixá-lo no[Link para Download](https://releases.groupdocs.com/viewer/net/).

## Importando Namespaces

Em seu arquivo de código C#, importe os namespaces necessários para acessar as classes e métodos necessários. Você pode fazer isso usando o`using` diretiva:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora vamos dividir o código de exemplo fornecido em várias etapas:

## Etapa 1: definir o diretório de saída

 Defina o diretório onde deseja que as páginas renderizadas sejam salvas. Substituir`"Your Document Directory"` com o caminho do diretório desejado.

```csharp
string outputDirectory = "Your Document Directory";
```

## Etapa 2: definir o formato do caminho do arquivo de página

Especifique o formato dos caminhos de arquivo das páginas renderizadas. Isso será usado para salvar cada página como um arquivo HTML no diretório de saída.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Etapa 3: instanciar o objeto visualizador

Crie uma instância da classe Viewer, passando como argumento o caminho do documento que deseja renderizar.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Etapa 4: configurar opções de visualização HTML

Configure as opções de visualização HTML para renderização. Neste exemplo, estamos configurando opções para incorporar recursos na saída HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Etapa 5: renderizar as páginas selecionadas

Especifique os números das páginas que você deseja renderizar. Nesse caso, estamos renderizando as páginas 1 a 3. Em seguida, chame o método View no objeto Viewer, passando as opções e os números das páginas como argumentos.

```csharp
viewer.View(options, 1, 3);
```

## Etapa 6: resultado de saída

Por fim, exiba uma mensagem indicando a renderização bem-sucedida do documento e o local onde os arquivos de saída foram salvos.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão

Parabéns! Você aprendeu com sucesso como renderizar páginas selecionadas de um documento usando Groupdocs.Viewer for .NET. Com esse conhecimento, agora você pode integrar recursos de renderização de documentos em seus aplicativos .NET com facilidade.

## Perguntas frequentes

### P: Posso renderizar páginas de diferentes tipos de documentos, como PDFs ou imagens?

R: Sim, o Groupdocs.Viewer for .NET oferece suporte à renderização de páginas de vários formatos de documentos, incluindo PDFs, documentos do Microsoft Office e arquivos de imagem.

### P: Existe uma versão de avaliação disponível para teste antes da compra?

 R: Sim, você pode acessar uma versão de avaliação gratuita do Groupdocs.Viewer for .NET no site[local na rede Internet](https://releases.groupdocs.com/).

### P: Posso personalizar o formato de saída diferente de HTML?

R: Com certeza, o Groupdocs.Viewer for .NET oferece opções para renderizar páginas como imagens, PDFs e muito mais, além de HTML.

### P: Como posso obter licenças temporárias para fins de teste?

R: Licenças temporárias podem ser adquiridas no[página de licença temporária](https://purchase.groupdocs.com/temporary-license/) no site Groupdocs.

### P: Onde posso procurar assistência ou obter ajuda para quaisquer problemas que encontrar?

 R: Você pode visitar o[Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para suporte e orientação da comunidade e dos desenvolvedores.