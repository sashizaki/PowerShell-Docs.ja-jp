---
title: Windows PowerShell01 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f607a5ad-5372-4392-b2dc-ef3532fabd0f
caps.latest.revision: 9
ms.openlocfilehash: 7fafbc6bc19082abb8f37b68c031e0995bf879f6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367351"
---
# <a name="windows-powershell01-sample"></a><span data-ttu-id="bf6d4-102">Windows PowerShell01 サンプル</span><span class="sxs-lookup"><span data-stu-id="bf6d4-102">Windows PowerShell01 Sample</span></span>

<span data-ttu-id="bf6d4-103">このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用して、実行空間の機能を制限する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-103">This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="bf6d4-104">このサンプルの出力では、実行空間の言語モードを制限する方法、コマンドレットをプライベートとしてマークする方法、コマンドレットとプロバイダーを追加および削除する方法、プロキシコマンドを追加する方法などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-104">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span> <span data-ttu-id="bf6d4-105">このサンプルでは、実行空間をプログラムで制限する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-105">This sample concentrates on how to restrict the runspace programmatically.</span></span> <span data-ttu-id="bf6d4-106">実行空間を制限するためのスクリプトの代替手段としては $ExecutionContext、SessionState. LanguageMode コマンドと Register-pssessionconfiguration コマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-106">Scripting alternatives to restricting the runspace include the $ExecutionContext.SessionState.LanguageMode and PSSessionConfiguration commands.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf6d4-107">要件</span><span class="sxs-lookup"><span data-stu-id="bf6d4-107">Requirements</span></span>

<span data-ttu-id="bf6d4-108">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="bf6d4-109">サンプル</span><span class="sxs-lookup"><span data-stu-id="bf6d4-109">Demonstrates</span></span>

<span data-ttu-id="bf6d4-110">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-110">This sample demonstrates the following:</span></span>

- <span data-ttu-id="bf6d4-111">[Languagemode](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.LanguageMode)プロパティを設定して、言語を制限しています。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-111">Restricting the language by setting the [System.Management.Automation.Runspaces.Initialsessionstate.Languagemode](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.LanguageMode) property.</span></span>

- <span data-ttu-id="bf6d4-112">Sessionstatealiasentry を使用して、最初のセッション状態にエイリアスを追加する[Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateAliasEntry)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-112">Adding aliases to the initial session state by using a [System.Management.Automation.Runspaces.Sessionstatealiasentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateAliasEntry) object.</span></span>

- <span data-ttu-id="bf6d4-113">コマンドをプライベートとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-113">Marking commands as private.</span></span>

- <span data-ttu-id="bf6d4-114">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Providers)プロパティを使用して、最初のセッション状態からプロバイダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-114">Removing providers from the initial session state by using the [System.Management.Automation.Runspaces.Initialsessionstate.Providers](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Providers) property.</span></span>

- <span data-ttu-id="bf6d4-115">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Commands)プロパティを使用して、最初のセッション状態からコマンドを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-115">Removing commands from the initial session state by using the [System.Management.Automation.Runspaces.Initialsessionstate.Commands](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Commands) property.</span></span>

- <span data-ttu-id="bf6d4-116">コマンドとプロバイダーを[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトに追加しますが、</span><span class="sxs-lookup"><span data-stu-id="bf6d4-116">Adding commands and providers to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

## <a name="example"></a><span data-ttu-id="bf6d4-117">例</span><span class="sxs-lookup"><span data-stu-id="bf6d4-117">Example</span></span>

<span data-ttu-id="bf6d4-118">このサンプルでは、実行空間の機能を制限するいくつかの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bf6d4-118">This sample shows several ways to limit the functionality of a runspace.</span></span>

```csharp
namespace Sample
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class PowerShell01
  {
    /// <summary>
    /// The runspace used to run commands.
    /// </summary>
    private Runspace runspace;

    /// <summary>
    /// Return the first index of the entry in <paramref name="entries"/>
    /// with the name <paramref name="name"/>. Return -1 if it is not found.
    /// </summary>
    /// <typeparam name="T">Type of ConstrainedSessionStateEntry</typeparam>
    /// <param name="entries">Collection of entries to search for <paramref name="name"/> in.</param>
    /// <param name="name">Named of the entry we are looking for</param>
    /// <returns>
    /// The first index of the entry in <paramref name="entries"/> with the
    /// name <paramref name="name"/>, or return -1 if it is not found.
    /// </returns>
    private static int GetIndexOfEntry<T>(
            InitialSessionStateEntryCollection<T> entries,
            string name) where T : ConstrainedSessionStateEntry
    {
      int foundIndex = 0;
      foreach (T entry in entries)
      {
        if (entry.Name.Equals(name, StringComparison.OrdinalIgnoreCase))
        {
          return foundIndex;
        }

        foundIndex++;
      }

      return -1;
    }

    /// <summary>
    /// Run commands to demonstrate the ways to constrain the runspace.
    /// </summary>
    /// <param name="args">This parameter is unused.</param>
    private static void Main(string[] args)
    {
      new PowerShell01().RunCommands();
    }

    /// <summary>
    /// Run a script to display the results and errors.
    /// </summary>
    /// <param name="script">Script to be run.</param>
    /// <param name="scriptComment">Comment to be printed about
    /// the script.</param>
    private void RunScript(string script, string scriptComment)
    {
      Console.WriteLine("Running '{0}'\n{1}.\n\nPowerShell Output:", script, scriptComment);

      // Using a PowerShell object, create a pipeline, add the script to the
      //  pipeline, and specify the runspace where the pipeline is invoked.
      PowerShell powerShellCommand = PowerShell.Create();
      powerShellCommand.AddScript(script);
      powerShellCommand.Runspace = this.runspace;

      try
      {
        Collection<PSObject> results = powerShellCommand.Invoke();

        // Display the results.
        foreach (PSObject result in results)
        {
          Console.WriteLine(result);
        }

        // Display any non-terminating errors.
        foreach (ErrorRecord error in powerShellCommand.Streams.Error)
        {
          Console.WriteLine("PowerShell Error: {0}", error);
        }
      }
      catch (RuntimeException ex)
      {
        Console.WriteLine("PowerShell Error: {0}", ex.Message);
        Console.WriteLine();
      }

      Console.WriteLine("\n-----------------------------\n");
    }

    /// <summary>
    /// Run some commands to demonstrate the script capabilities.
    /// </summary>
    private void RunCommands()
    {
      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.Open();
      this.RunScript("$a=0;$a", "Assigning to a variable will work for a default InitialSessionState");
      this.runspace.Close();

      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.InitialSessionState.LanguageMode = PSLanguageMode.RestrictedLanguage;
      this.runspace.Open();
      this.RunScript("$a=0;$a", "Assigning to a variable will not work in RestrictedLanguage LanguageMode");
      this.runspace.Close();

      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.InitialSessionState.LanguageMode = PSLanguageMode.NoLanguage;
      this.runspace.Open();
      this.RunScript("10/2", "A script will not work in NoLanguage LanguageMode.");
      this.runspace.Close();

      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.Open();
      string scriptComment = "get-childitem with a default InitialSessionState will work since the standard \n" +
           "PowerShell cmdlets are included in the default InitialSessionState";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      InitialSessionState defaultSessionState = InitialSessionState.CreateDefault();
      defaultSessionState.Commands.Add(new SessionStateAliasEntry("dir2", "get-childitem"));
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      this.RunScript("dir2", "An alias, like dir2, can be added to InitialSessionState");
      this.runspace.Close();

      defaultSessionState = InitialSessionState.CreateDefault();
      int commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
      defaultSessionState.Commands.RemoveItem(commandIndex);
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      scriptComment = "get-childitem was removed from the list of commands so it\nwill no longer be found";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      defaultSessionState = InitialSessionState.CreateDefault();
      defaultSessionState.Providers.Clear();
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      this.RunScript("get-childitem", "There are no providers so get-childitem will not work");
      this.runspace.Close();

      // Marks a command as private, and then defines a proxy command
      // that uses the private command.  One reason to define a proxy for
      // a command is to remove a parameter of the original command.
      // For a more complete sample of a proxy command, see the Runspace11
      // sample.
      defaultSessionState = InitialSessionState.CreateDefault();
      commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
      defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;
      CommandMetadata getChildItemMetadata = new CommandMetadata(
           typeof(Microsoft.PowerShell.Commands.GetChildItemCommand));
      getChildItemMetadata.Parameters.Remove("Recurse");
      string getChildItemBody = ProxyCommand.Create(getChildItemMetadata);
      defaultSessionState.Commands.Add(new SessionStateFunctionEntry("get-childitem2", getChildItemBody));
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      this.RunScript("get-childitem", "get-childitem is private so it will not be available");
      scriptComment = "get-childitem2 is a proxy to get-childitem. \n" +
                    "It works even when get-childitem is private.";
      this.RunScript("get-childitem2", scriptComment);
      scriptComment = "This will fail. Unlike get-childitem, get-childitem2 does not have -Recurse";
      this.RunScript("get-childitem2 -Recurse", scriptComment);

      InitialSessionState cleanSessionState = InitialSessionState.Create();
      this.runspace = RunspaceFactory.CreateRunspace(cleanSessionState);
      this.runspace.Open();
      scriptComment = "A script will not work because \n" +
                   "InitialSessionState.Create() will have the default LanguageMode of NoLanguage";
      this.RunScript("10/2", scriptComment);
      this.runspace.Close();

      cleanSessionState = InitialSessionState.Create();
      cleanSessionState.LanguageMode = PSLanguageMode.FullLanguage;
      this.runspace = RunspaceFactory.CreateRunspace(cleanSessionState);
      this.runspace.Open();
      scriptComment = "get-childitem, standard cmdlets and providers are not present \n" +
                   "in an InitialSessionState returned from InitialSessionState.Create()";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      cleanSessionState = InitialSessionState.Create();
      cleanSessionState.Commands.Add(
                new SessionStateCmdletEntry(
                    "Get-ChildItem",
                    typeof(Microsoft.PowerShell.Commands.GetChildItemCommand),
                    null));
      cleanSessionState.Providers.Add(
                new SessionStateProviderEntry(
                    "FileSystem",
                    typeof(Microsoft.PowerShell.Commands.FileSystemProvider),
                    null));
      cleanSessionState.LanguageMode = PSLanguageMode.FullLanguage;
      this.runspace = RunspaceFactory.CreateRunspace(cleanSessionState);
      this.runspace.Open();
      scriptComment = "get-childitem and the FileSystem provider were explicitly added\n" +
                "so get-childitem will work";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      Console.Write("Done...");
      Console.ReadLine();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="bf6d4-119">参照</span><span class="sxs-lookup"><span data-stu-id="bf6d4-119">See Also</span></span>

[<span data-ttu-id="bf6d4-120">Windows PowerShell ホストアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="bf6d4-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)