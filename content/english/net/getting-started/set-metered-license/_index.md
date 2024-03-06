---
title: Set Metered License
linktitle: Set Metered License
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/getting-started/set-metered-license/
---

## Complete Source Code
```csharp
using System;

namespace GroupDocs.Viewer.Examples.CSharp.QuickStart
{
    /// <summary>
    /// This example demonstrates how to set Metered license.
    /// Learn more about Metered license at https://purchase.groupdocs.com/faqs/licensing/metered.
    /// </summary>
    class SetMeteredLicense
    {
        public static void Run()
        {
            string publicKey = "";
            string privateKey = "";

            if (string.IsNullOrEmpty(publicKey))
            {
                Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Lear more at https://purchase.groupdocs.com/faqs/licensing/metered.");
                return;
            } 

            Metered metered = new Metered();
            metered.SetMeteredKey(publicKey, privateKey);

            Console.WriteLine("License set successfully.");
        }
    }
}

```
