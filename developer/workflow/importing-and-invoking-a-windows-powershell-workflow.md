---
title: インポートして、Windows PowerShell ワークフローを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50e6f9b1-2678-4f53-9250-7c48843a9549
caps.latest.revision: 5
ms.openlocfilehash: 1113c0d1cd68bb97d2f96b529f755b62137d1f40
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854588"
---
# <a name="importing-and-invoking-a-windows-powershell-workflow"></a>Windows PowerShell ワークフローをインポートして呼び出す

Windows PowerShell の 3 を使用すると、インポートして、Windows PowerShell モジュールとしてパッケージ化されているワークフローを呼び出すことができます。 Windows PowerShell モジュールに関する情報は、[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)を参照してください。

[System.Management.Automation.Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)クラスは、サーバー上のワークフロー オブジェクトのクライアント側のプロキシとして使用されます。 次の手順を使用する方法を説明する、 [System.Management.Automation.Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)にワークフローを呼び出すオブジェクト。

### <a name="creating-a-psjobproxy-object-to-execute-workflow-commands-on-a-remote-server"></a>リモート サーバーでワークフロー コマンドを実行する PSJobProxy オブジェクトを作成します。

1. 作成、 [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)リモート実行空間への接続を作成するオブジェクト。

2. 設定、 [System.Management.Automation.Runspaces.Wsmanconnectioninfo.Shelluri*](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ShellUri)のプロパティ、 [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトを`Microsoft.PowerShell.Workflow`にWindows PowerShell エンドポイントを指定します。

3. 前の手順を実行して作成した接続を使用する実行空間を作成します。

4. 作成、 [System.Management.Automation.Powershell](/dotnet/api/System.Management.Automation.PowerShell)オブジェクトし、設定その[System.Management.Automation.Powershell.Runspace*](/dotnet/api/System.Management.Automation.PowerShell.Runspace)プロパティを前の手順で作成された実行空間を指定します。

5. ワークフロー モジュールとそのコマンドをインポート、 [System.Management.Automation.Powershell](/dotnet/api/System.Management.Automation.PowerShell)します。

6. 作成、 [System.Management.Automation.Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)オブジェクトし、リモート サーバーでワークフロー コマンドの実行に使用します。

## <a name="example"></a>例

次のコード例では、Windows PowerShell を使用してワークフローを呼び出す方法を示します。

この例では、Windows PowerShell 3 が必要です。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;
using System.Management.Automation.Runspaces;

namespace WorkflowHostTest
{

class Program
    {
        static void Main(string[] args)
        {
            if (args.Length == 0)
            {
                Console.WriteLine("Specify path to Workflow module");
                return;
            }

            string moduleFile = args[0];

            Console.Write("Creating Remote runspace connection...");
            WSManConnectionInfo connectionInfo = new WSManConnectionInfo();

            //Set the shellURI to workflow endpoint Microsoft.PowerShell.Workflow
            connectionInfo.ShellUri = "Microsoft.PowerShell.Workflow";

            //Create and open a runspace.
            Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo);
            runspace.Open();
            Console.WriteLine("done");

            PowerShell powershell = PowerShell.Create();
            powershell.Runspace = runspace;
            Console.Write("Setting $VerbosePreference=\"Continue\"...");
            powershell.AddScript("$VerbosePreference=\"Continue\"");
            powershell.Invoke();
            Console.WriteLine("done");

            Console.Write("Importing Workflow module...");
            powershell.Commands.Clear();

            //Import the module in to the PowerShell runspace. A XAML file could also be imported directly by using Import-Module.
            powershell.AddCommand("Import-Module").AddArgument(moduleFile);
            powershell.Invoke();
            Console.WriteLine("done");

            Console.Write("Creating job proxy...");
            powershell.Commands.Clear();
            powershell.AddCommand("Get-Proc").AddArgument("*");
            PSJobProxy job = powershell.AsJobProxy();
            Console.WriteLine("done");

                Console.WriteLine();
                Console.WriteLine("Using job proxy and performing operations...");
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());
                Console.WriteLine("Starting job...");
                job.StartJob();
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());

                // use blocking enumerator to wait for objects until job finishes
                job.Output.BlockingEnumerator = true;
                foreach (PSObject o in job.Output)
                {
                    Console.WriteLine(o.Properties["ProcessName"].Value.ToString());
                }

                // wait for a random time before attempting to stop job
                Random random = new Random();
                int time = random.Next(1, 10);
                Console.Write("Sleeping for {0} seconds when job is running on another thread...", time);
                System.Threading.Thread.Sleep(time * 1000);
                Console.WriteLine("done");
                Console.WriteLine("Stopping job...");
                job.StopJob();
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());
                Console.WriteLine();
                job.Finished.WaitOne();
                Console.WriteLine("Output from job");
                Console.WriteLine("---------------");

                foreach (PSObject o in job.Output)
                {
                    Console.WriteLine(o.Properties["ProcessName"].Value.ToString());
                }

                Console.WriteLine();
                Console.WriteLine("Verbose messages from job");
                Console.WriteLine("-------------------------");
                foreach (VerboseRecord v in job.Verbose)
                {
                    Console.WriteLine(v.Message);
                }

            runspace.Close();
        }
    }
}

```