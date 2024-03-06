---
title: Render with Custom Fonts
linktitle: Render with Custom Fonts
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 18
url: /net/rendering-options/render-custom-fonts/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.CommonRenderingOptions
{
    /// <summary>
    /// This example demonstrates how to add custom fonts to use when rendering documents.
    /// </summary>
    class RenderWithCustomFonts
    {
        public static void Run()
        {            
            FontSettings.SetFontSources(
                new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));                       
            
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
