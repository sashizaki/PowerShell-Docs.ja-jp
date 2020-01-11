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
ms.openlocfilehash: 5761ed2168a46d6ed9a2e50554d459f5b93223ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359661"
---
# <a name="creating-a-workflow-activity-from-a-windows-powershell-cmdlet"></a>Windows PowerShell コマンドレットからワークフロー アクティビティを作成する

任意の Windows PowerShell モジュールまたはコマンドレットをワークフローアクティビティとしてパッケージ化するに[は、そのクラスの](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator)メソッドを使用します。 アクティビティを C# 表すコードを生成するには、Generatefromname クラスの[*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromName)メソッドを使用して、microsoft. Powershell. [activityfromcommandinfo](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromModuleInfo)* メソッドと、[microsoft. powershell. activity. activitygenerator. activity. activity. activity](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromCommandInfo), activity. [activitygenerator](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) クラスのメソッドを使用します。 その後、結果C#のコードをコンパイルして、プロジェクトにアクティビティとして追加できるアセンブリにすることができます。

その後、次の形式C#のコマンドラインを使用して、アクティビティとしてプロジェクトに追加できるアセンブリに、結果のコードをコンパイルできます。

**csc/nologo/out: AssemblyName/target: library/reference: codefile.cs/reference: Microsoft. PowerShell. 活動**

## <a name="example"></a>例

次の例は、Windows PowerShell C#モジュールからアクティビティのコードを生成する方法を示しています。

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

次の例は、Windows PowerShell C#コマンドレットからアクティビティのコードを生成する方法を示しています。

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