---
title: GetProcessSample03 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc9d80ee-6ebd-48cd-a7ea-53cb2b442a22
caps.latest.revision: 6
ms.openlocfilehash: ec5a8c284dd3fa772261099281aba1fb68c49118
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369711"
---
# <a name="getprocesssample03-sample"></a><span data-ttu-id="a2417-102">GetProcessSample03 サンプル</span><span class="sxs-lookup"><span data-stu-id="a2417-102">GetProcessSample03 Sample</span></span>

<span data-ttu-id="a2417-103">このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a2417-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="a2417-104">パイプラインからオブジェクトを受け取ることができる @no__t 0 のパラメーター、およびプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2417-104">It provides a `Name` parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span> <span data-ttu-id="a2417-105">このコマンドレットは、Windows PowerShell 2.0 によって提供される @no__t 0 コマンドレットの簡略化されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="a2417-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="a2417-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="a2417-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="a2417-107">Windows PowerShell 2.0 SDK がインストールされている状態で、GetProcessSample03 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a2417-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample03 folder.</span></span> <span data-ttu-id="a2417-108">既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03. です。</span><span class="sxs-lookup"><span data-stu-id="a2417-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.</span></span>

2. <span data-ttu-id="a2417-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2417-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="a2417-110">これにより、Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="a2417-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="a2417-111">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2417-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="a2417-112">サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。</span><span class="sxs-lookup"><span data-stu-id="a2417-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="a2417-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="a2417-113">How to run the sample</span></span>

1. <span data-ttu-id="a2417-114">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2417-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. <span data-ttu-id="a2417-115">サンプルアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a2417-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="a2417-116">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="a2417-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="a2417-117">次のコマンドを実行して、Windows PowerShell にアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a2417-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample03`

5. <span data-ttu-id="a2417-118">次のコマンドを実行して、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2417-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="a2417-119">要件</span><span class="sxs-lookup"><span data-stu-id="a2417-119">Requirements</span></span>

<span data-ttu-id="a2417-120">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2417-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a2417-121">サンプル</span><span class="sxs-lookup"><span data-stu-id="a2417-121">Demonstrates</span></span>

<span data-ttu-id="a2417-122">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="a2417-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="a2417-123">コマンドレットの属性を使用して、コマンドレットクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a2417-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="a2417-124">Parameter 属性を使用してコマンドレットパラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="a2417-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="a2417-125">パラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2417-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="a2417-126">パラメーターがパイプラインからの入力を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2417-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="a2417-127">入力は、オブジェクトまたはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値から取得できます。</span><span class="sxs-lookup"><span data-stu-id="a2417-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="a2417-128">パラメーター入力の検証属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="a2417-128">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="a2417-129">例</span><span class="sxs-lookup"><span data-stu-id="a2417-129">Example</span></span>

<span data-ttu-id="a2417-130">このサンプルでは、パイプラインからの入力を受け入れる @no__t 0 パラメーターを含む、Get Proc コマンドレットの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="a2417-130">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter that accepts input from the pipeline.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a2417-131">参照</span><span class="sxs-lookup"><span data-stu-id="a2417-131">See Also</span></span>

[<span data-ttu-id="a2417-132">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="a2417-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
