---
title: Virar e girar páginas
linktitle: Virar e girar páginas
second_title: API GroupDocs.Viewer .NET
description: Aprenda como integrar o Groupdocs.Viewer for .NET em seus aplicativos para renderização, inversão e rotação contínua de documentos.
weight: 12
url: /pt/net/rendering-options/flip-rotate-pages/
---

# Virar e girar páginas

## Introdução
Neste tutorial, nos aprofundaremos nas funcionalidades do Groupdocs.Viewer for .NET, focando especificamente na inversão e rotação de páginas. Groupdocs.Viewer for .NET é uma ferramenta poderosa projetada para renderizar documentos em vários formatos em aplicativos .NET. Esteja você desenvolvendo um sistema de gerenciamento de documentos ou precise integrar recursos de visualização de documentos em seu software, o Groupdocs.Viewer for .NET oferece uma solução eficiente.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos configurados:
### Instalando Groupdocs.Viewer para .NET
 Para usar o Groupdocs.Viewer for .NET, você precisa instalar o pacote por meio do NuGet Package Manager. Você pode encontrar instruções detalhadas de instalação no[documentação](https://tutorials.groupdocs.com/viewer/net/).

## Importar namespaces
Certifique-se de ter os namespaces necessários importados em seu projeto para utilizar o Groupdocs.Viewer for .NET de maneira eficaz.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Vamos dividir o processo de virar e girar páginas usando Groupdocs.Viewer for .NET em etapas simples:
## Etapa 1: definir o diretório de saída e o caminho do arquivo
Defina o diretório onde deseja que o arquivo de saída seja salvo e especifique o caminho do arquivo de saída.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Etapa 2: inicializar o objeto visualizador
Crie uma instância da classe Viewer passando o caminho do documento que deseja visualizar.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Etapa 3: configurar opções de visualização
Configure as opções de visualização, como especificar o formato do arquivo de saída e quaisquer configurações adicionais, como rotação de página.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Etapa 4: renderizar documento
Invoque o método View do objeto Viewer e passe as opções de visualização.
```csharp
viewer.View(viewOptions);
```
## Etapa 5: exibir mensagem de sucesso
Informe ao usuário que o documento foi renderizado com sucesso e especifique o diretório de saída para verificação.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Concluindo, Groupdocs.Viewer for .NET oferece recursos poderosos para renderizar documentos, incluindo virar e girar páginas. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente esses recursos aos seus aplicativos .NET, aprimorando as experiências de visualização de documentos para seus usuários.
## Perguntas frequentes
### O Groupdocs.Viewer for .NET é compatível com todos os formatos de documentos?
Sim, o Groupdocs.Viewer for .NET oferece suporte a uma ampla variedade de formatos de documentos, incluindo DOCX, PDF, PPTX e muito mais.
### Posso personalizar as opções de visualização além de virar e girar as páginas?
Com certeza, Groupdocs.Viewer for .NET oferece várias opções de personalização para visualização de documentos, permitindo adaptar a experiência de acordo com suas necessidades.
### Existe uma avaliação gratuita disponível para Groupdocs.Viewer for .NET?
 Sim, você pode aproveitar uma avaliação gratuita do Groupdocs.Viewer for .NET visitando o[local na rede Internet](https://releases.groupdocs.com/).
### Como posso obter suporte para Groupdocs.Viewer for .NET?
 Você pode buscar assistência e interagir com a comunidade por meio do[Fórum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Onde posso obter uma licença temporária do Groupdocs.Viewer for .NET?
 Licenças temporárias para Groupdocs.Viewer for .NET podem ser obtidas no site[página de compra](https://purchase.groupdocs.com/temporary-license/).