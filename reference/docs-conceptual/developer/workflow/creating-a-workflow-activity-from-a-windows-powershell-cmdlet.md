---
title: Windows PowerShell コマンドレットからワークフローアクティビティを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4174e84f-d516-4aca-b418-273047dcfb07
caps.latest.revision: 7
ms.openlocfilehash: f45b5e985fa38ca4ff41707f1842ddb8b930e2b1
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557501"
---
# <a name="creating-a-workflow-activity-from-a-windows-powershell-cmdlet"></a>Windows PowerShell コマンドレットからワークフロー アクティビティを作成する

任意の Windows PowerShell モジュールまたはコマンドレットをワークフローアクティビティとしてパッケージ化するに[は、そのクラスの](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator)メソッドを使用します。 アクティビティを表す C# コードを生成するには、Generatefromname クラスの[*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromName)メソッドを使用して、microsoft [. Powershell.](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) [activityfrommoduleinfo](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromModuleInfo) [* メソッド](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromCommandInfo)と、microsoft. powershell. activity. activitygenerator. activity. activity. activity. activity. activity. activity. activity. activity. activity. を使用します。 その後、結果の C# コードをコンパイルして、プロジェクトにアクティビティとして追加できるアセンブリにすることができます。

その後、生成された C# コードを、次の形式のコマンドラインを使用して、アクティビティとしてプロジェクトに追加できるアセンブリにコンパイルできます。

**csc/nologo/out: AssemblyName/target: library/reference: codefile.cs/reference: Microsoft. PowerShell. 活動**

## <a name="example"></a>例

次の例は、Windows PowerShell モジュールからアクティビティの C# コードを生成する方法を示しています。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Management.Automation;
using System.Collections.ObjectModel;
using Microsoft.PowerShell.Activities;

namespace MakeActivity
{
    class Program
    {
        static void Main(string[] args)

        {
            StreamWriter CodeFile = new StreamWriter("c:\\\\testmodule\\codefile.cs");
            Collection<PSModuleInfo> ModuleInfos = new Collection<PSModuleInfo> { };
            PSModuleInfo ModuleInfo;
            string ActivityCode = "";
            string ModulePath = "";
            Console.Write("Type the full path and filename of the module to process:");
            ModulePath = Console.ReadLine();

            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Import-Module").AddArgument(ModulePath);
            ps.AddParameter("PassThru");
            ModuleInfos = ps.Invoke<PSModuleInfo>();

            ModuleInfo = (PSModuleInfo)ModuleInfos[0];

            ActivityCode = ActivityGenerator.GenerateFromModuleInfo(ModuleInfo, "MyNamespace").First<String>();

           CodeFile.Write(ActivityCode);
            Console.ReadLine();

        }
    }
}

```

## <a name="example"></a>例

次の例は、Windows PowerShell コマンドレットからアクティビティの C# コードを生成する方法を示しています。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Management.Automation;
using System.Collections.ObjectModel;
using Microsoft.PowerShell.Activities;

namespace MakeActivity
{
    class Program
    {
        static void Main(string[] args)

        {
            StreamWriter CodeFile = new StreamWriter("c:\\\\testmodule\\codefile.cs");
            Collection<PSModuleInfo> ModuleInfos = new Collection<PSModuleInfo> { };
            PSModuleInfo ModuleInfo;
            Collection<CommandInfo> CommandInfos = new Collection<CommandInfo> { };
            CommandInfo MyCommand;
            string ActivityCode = "";
            string ModulePath = "";
            Console.Write("Type the full path and filename of the module to process:");
            ModulePath = Console.ReadLine();

            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Import-Module").AddArgument(ModulePath);
            ps.AddParameter("PassThru");
            ModuleInfos = ps.Invoke<PSModuleInfo>();

            ModuleInfo = (PSModuleInfo)ModuleInfos[0];

            ps.AddCommand("Get-Command").AddArgument(ModuleInfo);
            CommandInfos = ps.Invoke<CommandInfo>();

            MyCommand = CommandInfos[0];

            ActivityCode = ActivityGenerator.GenerateFromCommandInfo(MyCommand, "MyNamespace");

           CodeFile.Write(ActivityCode);
            Console.ReadLine();

        }
    }
}

```
