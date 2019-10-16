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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366041"
---
# <a name="importing-and-invoking-a-windows-powershell-workflow"></a><span data-ttu-id="ec879-102">Windows PowerShell ワークフローをインポートして呼び出す</span><span class="sxs-lookup"><span data-stu-id="ec879-102">Importing and Invoking a Windows PowerShell Workflow</span></span>

<span data-ttu-id="ec879-103">Windows PowerShell 3 では、Windows PowerShell モジュールとしてパッケージ化されたワークフローをインポートして呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ec879-103">Windows PowerShell 3, allows you to import and invoke a workflow that is packaged as a Windows PowerShell module.</span></span> <span data-ttu-id="ec879-104">Windows PowerShell モジュールの詳細については、「 [Windows Powershell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec879-104">For information about Windows PowerShell modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

<span data-ttu-id="ec879-105">[Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)クラスは、サーバー上のワークフローオブジェクトのクライアント側プロキシとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec879-105">The [System.Management.Automation.Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)class is used as a client side proxy for workflow objects on the server.</span></span> <span data-ttu-id="ec879-106">次の手順では、 [Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)オブジェクトを使用してワークフローを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec879-106">The following procedure explains how to use a [System.Management.Automation.Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)object to invoke a workflow.</span></span>

### <a name="creating-a-psjobproxy-object-to-execute-workflow-commands-on-a-remote-server"></a><span data-ttu-id="ec879-107">リモートサーバーでワークフローコマンドを実行するための PSJobProxy オブジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="ec879-107">Creating a PSJobProxy object to execute workflow commands on a remote server.</span></span>

1. <span data-ttu-id="ec879-108">[Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトを作成して、リモートの実行空間への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ec879-108">Create an [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)object to create a connection to a remote runspace.</span></span>

2. <span data-ttu-id="ec879-109">[Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトの[Wsmanconnectioninfo \*](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ShellUri)プロパティを、`Microsoft.PowerShell.Workflow` に設定して、Windows PowerShell エンドポイントを指定します。この設定は、Windows PowerShell エンドポイントを指定するために行います。</span><span class="sxs-lookup"><span data-stu-id="ec879-109">Set the [System.Management.Automation.Runspaces.Wsmanconnectioninfo.Shelluri\*](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ShellUri) property of the [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)object to `Microsoft.PowerShell.Workflow` to specify a Windows PowerShell endpoint.</span></span>

3. <span data-ttu-id="ec879-110">前の手順を完了することによって作成された接続を使用する実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="ec879-110">Create a runspace that uses the connection created by completing the previous steps.</span></span>

4. <span data-ttu-id="ec879-111">前の手順で作成した実行空間[に、system.servicemodel オブジェクトを](/dotnet/api/System.Management.Automation.PowerShell)作成し、その[system. powershell.](/dotnet/api/System.Management.Automation.PowerShell.Runspace)実行空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="ec879-111">Create a [System.Management.Automation.Powershell](/dotnet/api/System.Management.Automation.PowerShell)object and set its [System.Management.Automation.Powershell.Runspace\*](/dotnet/api/System.Management.Automation.PowerShell.Runspace) property to the runspace created in the previous step.</span></span>

5. <span data-ttu-id="ec879-112">ワークフローモジュールとそのコマンドを、 [System. Automation. Powershell](/dotnet/api/System.Management.Automation.PowerShell)にインポートします。</span><span class="sxs-lookup"><span data-stu-id="ec879-112">Import the workflow module and its commands into the [System.Management.Automation.Powershell](/dotnet/api/System.Management.Automation.PowerShell).</span></span>

6. <span data-ttu-id="ec879-113">[Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)オブジェクトを作成し、それを使用してリモートサーバー上でワークフローコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec879-113">Create a [System.Management.Automation.Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy) object and use it to execute workflow commands on the remote server.</span></span>

## <a name="example"></a><span data-ttu-id="ec879-114">例</span><span class="sxs-lookup"><span data-stu-id="ec879-114">Example</span></span>

<span data-ttu-id="ec879-115">次のコード例は、Windows PowerShell を使用してワークフローを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ec879-115">The following code example demonstrates how to invoke a workflow by using Windows PowerShell.</span></span>

<span data-ttu-id="ec879-116">この例では、Windows PowerShell 3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec879-116">This example requires Windows PowerShell 3.</span></span>

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