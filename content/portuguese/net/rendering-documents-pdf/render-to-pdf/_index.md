---
title: Renderizar documento para PDF
linktitle: Renderizar documento para PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar documentos em PDF usando GroupDocs.Viewer for .NET. Guia passo a passo com pré-requisitos e perguntas frequentes incluídas.
type: docs
weight: 10
url: /pt/net/rendering-documents-pdf/render-to-pdf/
---
## Introdução
GroupDocs.Viewer for .NET é uma ferramenta poderosa para renderizar vários formatos de documentos em PDF. Neste tutorial, guiaremos você pelo processo passo a passo.
## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:
1.  Biblioteca GroupDocs.Viewer for .NET: você pode baixar a biblioteca em[aqui](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: certifique-se de ter a versão apropriada do .NET Framework instalada em sua máquina.
3. Arquivos de documentos: prepare os arquivos de documentos que deseja renderizar. Os formatos suportados incluem DOCX, PDF, PPTX, XLSX e muito mais.

## Importando Namespaces:
Antes de mergulhar no código, certifique-se de importar os namespaces necessários:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos dividir o processo de renderização em várias etapas:
## Etapa 1: definir o diretório de saída e o caminho do arquivo
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
 Certifique-se de substituir`"Your Document Directory"` com o diretório onde você deseja salvar o arquivo PDF renderizado.
## Etapa 2: instanciar o objeto visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Seu código aqui
}
```
 Substituir`TestFiles.SAMPLE_DOCX` com o caminho para o arquivo do seu documento.
## Passo 3: Definir opções de visualização de PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Etapa 4: renderizar documento em PDF
```csharp
viewer.View(options);
```
## Etapa 5: exibir mensagem de sucesso
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Depois de seguir essas etapas, você terá renderizado com êxito seu documento em PDF usando GroupDocs.Viewer for .NET.

## Conclusão
Renderizar documentos em PDF é um requisito comum em vários aplicativos. Com o GroupDocs.Viewer for .NET, esse processo se torna contínuo e eficiente, permitindo lidar com uma ampla variedade de formatos de documentos com facilidade.
## Perguntas frequentes
### Posso renderizar documentos diferentes de DOCX para PDF?
Sim, GroupDocs.Viewer for .NET oferece suporte a vários formatos, como PDF, PPTX, XLSX e muito mais.
### Existe uma versão de teste disponível?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.groupdocs.com/).
### Como posso obter suporte se encontrar algum problema?
 Você pode visitar o fórum GroupDocs.Viewer[aqui](https://forum.groupdocs.com/c/viewer/9) para assistência.
### Preciso de uma licença temporária para fins de teste?
 Sim, você pode obter uma licença temporária de[aqui](https://purchase.groupdocs.com/temporary-license/).
### Onde posso comprar uma licença completa?
 Você pode comprar uma licença de[aqui](https://purchase.groupdocs.com/buy).