---
title: GetProcessSample04 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa2aa4c4-3457-4601-806a-801afe3dcc80
caps.latest.revision: 6
ms.openlocfilehash: 095bebf868efd00f8eeaec979a5606f140714cb1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365711"
---
# <a name="getprocesssample04-sample"></a><span data-ttu-id="554fd-102">GetProcessSample04 サンプル</span><span class="sxs-lookup"><span data-stu-id="554fd-102">GetProcessSample04 Sample</span></span>

<span data-ttu-id="554fd-103">このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="554fd-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="554fd-104">プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="554fd-104">It generates a nonterminating error if an error occurs while retrieving a process.</span></span> <span data-ttu-id="554fd-105">このコマンドレットは、Windows PowerShell 2.0 によって提供される `Get-Process` コマンドレットの簡略化されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="554fd-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="554fd-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="554fd-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="554fd-107">Windows PowerShell 2.0 SDK がインストールされている状態で、GetProcessSample04 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="554fd-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample04 folder.</span></span> <span data-ttu-id="554fd-108">既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04. です。</span><span class="sxs-lookup"><span data-stu-id="554fd-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span></span>

2. <span data-ttu-id="554fd-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="554fd-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="554fd-110">これにより、Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="554fd-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="554fd-111">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="554fd-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="554fd-112">サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。</span><span class="sxs-lookup"><span data-stu-id="554fd-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="554fd-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="554fd-113">How to run the sample</span></span>

1. <span data-ttu-id="554fd-114">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="554fd-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. <span data-ttu-id="554fd-115">サンプルアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="554fd-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="554fd-116">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="554fd-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="554fd-117">次のコマンドを実行して、Windows PowerShell にアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="554fd-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample04`

5. <span data-ttu-id="554fd-118">次のコマンドを実行して、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="554fd-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="554fd-119">要件</span><span class="sxs-lookup"><span data-stu-id="554fd-119">Requirements</span></span>

<span data-ttu-id="554fd-120">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="554fd-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="554fd-121">使用例</span><span class="sxs-lookup"><span data-stu-id="554fd-121">Demonstrates</span></span>

<span data-ttu-id="554fd-122">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="554fd-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="554fd-123">コマンドレットの属性を使用して、コマンドレットクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="554fd-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="554fd-124">Parameter 属性を使用してコマンドレットパラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="554fd-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="554fd-125">パラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="554fd-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="554fd-126">パラメーターがパイプラインからの入力を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="554fd-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="554fd-127">入力は、オブジェクトまたはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値から取得できます。</span><span class="sxs-lookup"><span data-stu-id="554fd-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="554fd-128">パラメーター入力の検証属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="554fd-128">Declaring a validation attribute for the parameter input.</span></span>

- <span data-ttu-id="554fd-129">終了しないエラーをトラップし、エラーメッセージをエラーストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="554fd-129">Trapping a nonterminating error and writing an error message to the error stream.</span></span>

## <a name="example"></a><span data-ttu-id="554fd-130">例</span><span class="sxs-lookup"><span data-stu-id="554fd-130">Example</span></span>

<span data-ttu-id="554fd-131">このサンプルでは、終了しないエラーを処理し、エラーメッセージをエラーストリームに書き込むコマンドレットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="554fd-131">This sample shows how to create a cmdlet that handles nonterminating errors and writes error messages to the error stream.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
    using System;
    using System.Diagnostics;
    using System.Management.Automation;      // Windows PowerShell namespace.
   #region GetProcCommand

   /// <summary>
   /// This class implements the get-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Parameters

       /// <summary>
       /// The names of the processes to act on.
       /// </summary>
       private string[] processNames;

      /// <summary>
      /// Gets or sets the list of process names on
      /// which the Get-Proc cmdlet will work.
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
          // If no process names are passed to cmdlet, get all
          // processes.
          if (this.processNames == null)
          {
              WriteObject(Process.GetProcesses(), true);
          }
          else
          {
              // If process names are passed to the cmdlet, get and write
              // the associated processes.
              // If a nonterminating error occurs while retrieving processes,
              // call the WriteError method to send an error record to the
              // error stream.
              foreach (string name in this.processNames)
              {
                  Process[] processes;

                  try
                  {
                      processes = Process.GetProcessesByName(name);
                  }
                  catch (InvalidOperationException ex)
                  {
                      WriteError(new ErrorRecord(
                         ex,
                         "UnableToAccessProcessByName",
                         ErrorCategory.InvalidOperation,
                         name));
                      continue;
                  }

                  WriteObject(processes, true);
              } // foreach (string name...
          } // else
      } // ProcessRecord

      #endregion Overrides
    } // End GetProcCommand class.

   #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="554fd-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="554fd-132">See Also</span></span>

[<span data-ttu-id="554fd-133">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="554fd-133">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
