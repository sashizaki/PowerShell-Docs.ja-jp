---
title: GetProcessSample03 サンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 09df93792ab611e167279bc35755d8d6c28e7cf3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784216"
---
# <a name="getprocesssample03-sample"></a><span data-ttu-id="e9802-102">GetProcessSample03 サンプル</span><span class="sxs-lookup"><span data-stu-id="e9802-102">GetProcessSample03 Sample</span></span>

<span data-ttu-id="e9802-103">このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e9802-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="e9802-104">このメソッドは、 `Name` パイプラインからのオブジェクト、またはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値を受け取ることができるパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9802-104">It provides a `Name` parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span> <span data-ttu-id="e9802-105">このコマンドレットは、 `Get-Process` Windows PowerShell 2.0 によって提供されるコマンドレットの簡略化されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e9802-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="e9802-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="e9802-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="e9802-107">Windows PowerShell 2.0 SDK がインストールされている状態で、GetProcessSample03 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e9802-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample03 folder.</span></span> <span data-ttu-id="e9802-108">既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03. です。</span><span class="sxs-lookup"><span data-stu-id="e9802-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.</span></span>

2. <span data-ttu-id="e9802-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9802-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="e9802-110">これにより、Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="e9802-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="e9802-111">**[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9802-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="e9802-112">サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。</span><span class="sxs-lookup"><span data-stu-id="e9802-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="e9802-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="e9802-113">How to run the sample</span></span>

1. <span data-ttu-id="e9802-114">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9802-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. <span data-ttu-id="e9802-115">サンプルアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9802-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="e9802-116">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="e9802-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="e9802-117">次のコマンドを実行して、Windows PowerShell にアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e9802-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample03`

5. <span data-ttu-id="e9802-118">次のコマンドを実行して、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9802-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="e9802-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9802-119">Requirements</span></span>

<span data-ttu-id="e9802-120">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9802-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e9802-121">対象</span><span class="sxs-lookup"><span data-stu-id="e9802-121">Demonstrates</span></span>

<span data-ttu-id="e9802-122">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="e9802-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="e9802-123">コマンドレットの属性を使用して、コマンドレットクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9802-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="e9802-124">Parameter 属性を使用してコマンドレットパラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="e9802-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="e9802-125">パラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9802-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="e9802-126">パラメーターがパイプラインからの入力を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9802-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="e9802-127">入力は、オブジェクトまたはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値から取得できます。</span><span class="sxs-lookup"><span data-stu-id="e9802-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="e9802-128">パラメーター入力の検証属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="e9802-128">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="e9802-129">例</span><span class="sxs-lookup"><span data-stu-id="e9802-129">Example</span></span>

<span data-ttu-id="e9802-130">このサンプルでは、パイプラインからの入力を受け入れるパラメーターを含む、Get Proc コマンドレットの実装を示し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="e9802-130">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter that accepts input from the pipeline.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;           // Windows PowerShell namespace
  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the names of the
    /// process that the cmdlet will retrieve.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return this.processNames; }
      set { this.processNames = value; }
    }

    #endregion Parameters

    #region Cmdlet Overrides

    /// <summary>
    /// The ProcessRecord method calls the Process.GetProcesses
    /// method to retrieve the processes specified by the Name
    /// parameter. Then, the WriteObject method writes the
    /// associated processes to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to the cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames ...)
    } // End ProcessRecord.

    #endregion Overrides
  } // End GetProcCommand.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="e9802-131">参照</span><span class="sxs-lookup"><span data-stu-id="e9802-131">See Also</span></span>

[<span data-ttu-id="e9802-132">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="e9802-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
