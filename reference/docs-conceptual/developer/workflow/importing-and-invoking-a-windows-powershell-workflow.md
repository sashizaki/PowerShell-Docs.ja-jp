---
title: Windows PowerShell ワークフローのインポートと呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50e6f9b1-2678-4f53-9250-7c48843a9549
caps.latest.revision: 5
ms.openlocfilehash: 1113c0d1cd68bb97d2f96b529f755b62137d1f40
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366041"
---
# <a name="importing-and-invoking-a-windows-powershell-workflow"></a>Windows PowerShell ワークフローをインポートして呼び出す

Windows PowerShell 3 では、Windows PowerShell モジュールとしてパッケージ化されたワークフローをインポートして呼び出すことができます。 Windows PowerShell モジュールの詳細については、「 [Windows Powershell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。

[Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)クラスは、サーバー上のワークフローオブジェクトのクライアント側プロキシとして使用されます。 次の手順では、 [Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)オブジェクトを使用してワークフローを呼び出す方法について説明します。

### <a name="creating-a-psjobproxy-object-to-execute-workflow-commands-on-a-remote-server"></a>リモートサーバーでワークフローコマンドを実行するための PSJobProxy オブジェクトの作成。

1. [Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトを作成して、リモートの実行空間への接続を作成します。

2. Wsmanconnectioninfo オブジェクトの[Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトの[*](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ShellUri)プロパティを `Microsoft.PowerShell.Workflow` に設定して、Windows PowerShell エンドポイントを指定するように指定していますが、

3. 前の手順を完了することによって作成された接続を使用する実行空間を作成します。

4. 前の手順で作成した実行空間[に、system.servicemodel オブジェクトを](/dotnet/api/System.Management.Automation.PowerShell)作成し、その[system. powershell.](/dotnet/api/System.Management.Automation.PowerShell.Runspace)実行空間を設定します。

5. ワークフローモジュールとそのコマンドを、 [System. Automation. Powershell](/dotnet/api/System.Management.Automation.PowerShell)にインポートします。

6. [Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)オブジェクトを作成し、それを使用してリモートサーバー上でワークフローコマンドを実行します。

## <a name="example"></a>例

次のコード例は、Windows PowerShell を使用してワークフローを呼び出す方法を示しています。

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