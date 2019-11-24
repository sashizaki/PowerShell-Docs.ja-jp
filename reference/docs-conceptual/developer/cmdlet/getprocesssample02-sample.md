---
title: GetProcessSample02 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 481f557d-3344-4d33-b2da-4736a0165181
caps.latest.revision: 7
ms.openlocfilehash: fa4cd8a724793e71b615c84a5c5a833aa92c93fc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364571"
---
# <a name="getprocesssample02-sample"></a><span data-ttu-id="37b07-102">GetProcessSample02 サンプル</span><span class="sxs-lookup"><span data-stu-id="37b07-102">GetProcessSample02 Sample</span></span>

<span data-ttu-id="37b07-103">このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37b07-103">This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="37b07-104">これには、取得するプロセスを指定するために使用できる `Name` パラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="37b07-104">It provides a `Name` parameter that can be used to specify the processes to be retrieved.</span></span> <span data-ttu-id="37b07-105">このコマンドレットは、Windows PowerShell 2.0 によって提供される `Get-Process` コマンドレットの簡略化されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="37b07-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="37b07-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="37b07-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="37b07-107">Windows PowerShell 2.0 SDK がインストールされている状態で、GetProcessSample02 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="37b07-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample02 folder.</span></span> <span data-ttu-id="37b07-108">既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02. です。</span><span class="sxs-lookup"><span data-stu-id="37b07-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span></span>

2. <span data-ttu-id="37b07-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="37b07-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="37b07-110">これにより、Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="37b07-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="37b07-111">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37b07-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="37b07-112">サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。</span><span class="sxs-lookup"><span data-stu-id="37b07-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="37b07-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="37b07-113">How to run the sample</span></span>

1. <span data-ttu-id="37b07-114">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="37b07-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. <span data-ttu-id="37b07-115">サンプルアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="37b07-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="37b07-116">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="37b07-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="37b07-117">次のコマンドを実行して、Windows PowerShell にアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="37b07-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module getprossessample02`

5. <span data-ttu-id="37b07-118">次のコマンドを実行して、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="37b07-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="37b07-119">要件</span><span class="sxs-lookup"><span data-stu-id="37b07-119">Requirements</span></span>

<span data-ttu-id="37b07-120">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="37b07-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="37b07-121">使用例</span><span class="sxs-lookup"><span data-stu-id="37b07-121">Demonstrates</span></span>

<span data-ttu-id="37b07-122">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="37b07-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="37b07-123">コマンドレットの属性を使用して、コマンドレットクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="37b07-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="37b07-124">Parameter 属性を使用してコマンドレットパラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="37b07-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="37b07-125">パラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="37b07-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="37b07-126">パラメーター入力の検証属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="37b07-126">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="37b07-127">例</span><span class="sxs-lookup"><span data-stu-id="37b07-127">Example</span></span>

<span data-ttu-id="37b07-128">このサンプルでは、`Name` パラメーターを含む Get Proc コマンドレットの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="37b07-128">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;     // Windows PowerShell namespace

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
    /// Gets or sets the list of process names on which
    /// the Get-Proc cmdlet will work.
    /// </summary>
    [Parameter(Position = 0)]
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
    /// associated process objects to the pipeline.
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
        // If process names are passed to cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames...).
    } // End ProcessRecord.
    #endregion Cmdlet Overrides
  } // End GetProcCommand class.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="37b07-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="37b07-129">See Also</span></span>

[<span data-ttu-id="37b07-130">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="37b07-130">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
