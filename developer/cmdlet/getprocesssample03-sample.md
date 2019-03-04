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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856478"
---
# <a name="getprocesssample03-sample"></a><span data-ttu-id="ed58c-102">GetProcessSample03 サンプル</span><span class="sxs-lookup"><span data-stu-id="ed58c-102">GetProcessSample03 Sample</span></span>

<span data-ttu-id="ed58c-103">このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="ed58c-104">提供、`Name`パラメーター パイプラインからオブジェクトまたはプロパティの名前は、パラメーター名と同じオブジェクトのプロパティの値を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="ed58c-104">It provides a `Name` parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span> <span data-ttu-id="ed58c-105">このコマンドレットは、簡略化されたバージョンの`Get-Process`コマンドレットの Windows PowerShell 2.0 で提供されます。</span><span class="sxs-lookup"><span data-stu-id="ed58c-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="ed58c-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="ed58c-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="ed58c-107">インストールされている Windows PowerShell 2.0 sdk では、GetProcessSample03 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample03 folder.</span></span> <span data-ttu-id="ed58c-108">既定の場所は、C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03 します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.</span></span>

2. <span data-ttu-id="ed58c-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed58c-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="ed58c-110">これは、Visual Studio でサンプル プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed58c-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="ed58c-111">**ビルド**メニューの **ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="ed58c-112">サンプルのライブラリは、既定の \bin または \bin\debug フォルダーにビルドされます。</span><span class="sxs-lookup"><span data-stu-id="ed58c-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="ed58c-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="ed58c-113">How to run the sample</span></span>

1. <span data-ttu-id="ed58c-114">次のモジュール フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. <span data-ttu-id="ed58c-115">モジュール フォルダーにサンプル アセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ed58c-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="ed58c-116">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="ed58c-117">Windows PowerShell にアセンブリを読み込むには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample03`

5. <span data-ttu-id="ed58c-118">コマンドレットを実行する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="ed58c-119">要件</span><span class="sxs-lookup"><span data-stu-id="ed58c-119">Requirements</span></span>

<span data-ttu-id="ed58c-120">このサンプルでは、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ed58c-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ed58c-121">使用例</span><span class="sxs-lookup"><span data-stu-id="ed58c-121">Demonstrates</span></span>

<span data-ttu-id="ed58c-122">このサンプルは、次を示します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="ed58c-123">コマンドレットの属性を使用して、コマンドレット クラスを宣言することです。</span><span class="sxs-lookup"><span data-stu-id="ed58c-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="ed58c-124">パラメーター属性を使用して、コマンドレット パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="ed58c-125">パラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="ed58c-126">パラメーターはパイプラインから入力されるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="ed58c-127">入力は、オブジェクトまたはプロパティの名前は、パラメーター名と同じオブジェクトのプロパティの値から取得できます。</span><span class="sxs-lookup"><span data-stu-id="ed58c-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="ed58c-128">入力パラメーターの検証属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ed58c-128">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="ed58c-129">例</span><span class="sxs-lookup"><span data-stu-id="ed58c-129">Example</span></span>

<span data-ttu-id="ed58c-130">このサンプルを含む Get-proc コマンドレットの実装を示しています、`Name`をパイプラインから入力を受け取るパラメーター。</span><span class="sxs-lookup"><span data-stu-id="ed58c-130">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter that accepts input from the pipeline.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ed58c-131">参照</span><span class="sxs-lookup"><span data-stu-id="ed58c-131">See Also</span></span>

[<span data-ttu-id="ed58c-132">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ed58c-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
