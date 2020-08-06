---
title: StopProcessSample01 サンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6d4737d0526a7d142b4a986986974bcbdc12ec7e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786460"
---
# <a name="stopprocesssample01-sample"></a><span data-ttu-id="f7da6-102">StopProcessSample01 サンプル</span><span class="sxs-lookup"><span data-stu-id="f7da6-102">StopProcessSample01 Sample</span></span>

<span data-ttu-id="f7da6-103">このサンプルでは、プロセスを停止する前にユーザーからのフィードバックを要求するコマンドレットを記述する方法と、 `PassThru` ユーザーがコマンドレットにオブジェクトを返すことを示すパラメーターを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-103">This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter indicating that the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="f7da6-104">このコマンドレットは、 `Stop-Process` Windows PowerShell 2.0 によって提供されるコマンドレットに似ています。</span><span class="sxs-lookup"><span data-stu-id="f7da6-104">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="f7da6-105">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="f7da6-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="f7da6-106">Windows PowerShell 2.0 SDK がインストールされている状態で、StopProcessSample01 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-106">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample01 folder.</span></span> <span data-ttu-id="f7da6-107">既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01. です。</span><span class="sxs-lookup"><span data-stu-id="f7da6-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span></span>

2. <span data-ttu-id="f7da6-108">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7da6-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="f7da6-109">これにより、Microsoft Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f7da6-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="f7da6-110">**[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-110">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="f7da6-111">サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。</span><span class="sxs-lookup"><span data-stu-id="f7da6-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="f7da6-112">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f7da6-112">How to run the sample</span></span>

1. <span data-ttu-id="f7da6-113">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-113">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample01`

2. <span data-ttu-id="f7da6-114">サンプルアセンブリをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7da6-114">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="f7da6-115">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-115">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="f7da6-116">次のコマンドを実行して、Windows PowerShell にアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f7da6-116">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample01`

5. <span data-ttu-id="f7da6-117">次のコマンドを実行して、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-117">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="f7da6-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7da6-118">Requirements</span></span>

<span data-ttu-id="f7da6-119">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="f7da6-119">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f7da6-120">対象</span><span class="sxs-lookup"><span data-stu-id="f7da6-120">Demonstrates</span></span>

<span data-ttu-id="f7da6-121">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-121">This sample demonstrates the following.</span></span>

- <span data-ttu-id="f7da6-122">コマンドレット属性を使用してコマンドレットクラスを宣言する。</span><span class="sxs-lookup"><span data-stu-id="f7da6-122">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="f7da6-123">パラメーター属性を使用してコマンドレットパラメーターを宣言する。</span><span class="sxs-lookup"><span data-stu-id="f7da6-123">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="f7da6-124">確認を要求するために、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-124">Calling the ShouldProcess method to request confirmation.</span></span>

- <span data-ttu-id="f7da6-125">`PassThru`コマンドレットがオブジェクトを返すかどうかを示すパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="f7da6-125">Implementing a `PassThru` parameter that indicates if the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="f7da6-126">既定では、このコマンドレットはパイプラインにオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="f7da6-126">By default, this cmdlet does not return an object to the pipeline.</span></span>

## <a name="example"></a><span data-ttu-id="f7da6-127">例</span><span class="sxs-lookup"><span data-stu-id="f7da6-127">Example</span></span>

<span data-ttu-id="f7da6-128">このサンプルでは、 `PassThru` ユーザーがオブジェクトを返すことを示すパラメーターの実装方法、およびメソッドとメソッドの呼び出しによってユーザーフィードバックを要求する方法を示し `ShouldProcess` `ShouldContinue` ます。</span><span class="sxs-lookup"><span data-stu-id="f7da6-128">This sample shows how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object, and how to request user feedback by calls to the `ShouldProcess` and `ShouldContinue` methods.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using Win32Exception = System.ComponentModel.Win32Exception;
using System.Management.Automation;    // Windows PowerShell namespace
using System.Globalization;

namespace Microsoft.Samples.PowerShell.Commands
{
   #region StopProcCommand

    /// <summary>
   /// This class implements the stop-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsLifecycle.Stop, "Proc",
       SupportsShouldProcess = true)]
   public class StopProcCommand : Cmdlet
   {
       #region Parameters

      /// <summary>
      /// This parameter provides the list of process names on
      /// which the Stop-Proc cmdlet will work.
      /// </summary>
       [Parameter(
          Position = 0,
          Mandatory = true,
          ValueFromPipeline = true,
          ValueFromPipelineByPropertyName = true
       )]
       public string[] Name
       {
           get { return processNames; }
           set { processNames = value; }
       }
       private string[] processNames;

       /// <summary>
       /// This parameter overrides the ShouldContinue call to force
       /// the cmdlet to stop its operation. This parameter should always
       /// be used with caution.
       /// </summary>
       [Parameter]
       public SwitchParameter Force
       {
           get { return force; }
           set { force = value; }
       }
       private bool force;

       /// <summary>
       /// This parameter indicates that the cmdlet should return
       /// an object to the pipeline after the processing has been
       /// completed.
       /// </summary>
       [Parameter]
       public SwitchParameter PassThru
       {
           get { return passThru; }
           set { passThru = value; }
       }
       private bool passThru;

       #endregion Parameters

       #region Cmdlet Overrides

       /// <summary>
       /// The ProcessRecord method does the following for each of the
       /// requested process names:
       /// 1) Check that the process is not a critical process.
       /// 2) Attempt to stop that process.
       /// If no process is requested then nothing occurs.
       /// </summary>
       protected override void ProcessRecord()
       {
           foreach (string name in processNames)
           {
               // For every process name passed to the cmdlet, get the associated
               // processes.
               // Write a nonterminating error for failure to retrieve
               // a process.
               Process[] processes;

               try
               {
                   processes = Process.GetProcessesByName(name);
               }
               catch (InvalidOperationException ioe)
               {
                   WriteError(new ErrorRecord(ioe,"UnableToAccessProcessByName",
                       ErrorCategory.InvalidOperation, name));

                   continue;
               }

               // Try to stop the processes that have been retrieved.
               foreach (Process process in processes)
               {
                   string processName;

                   try
                   {
                       processName = process.ProcessName;
                   }
                   catch (Win32Exception e)
                   {
                      WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                                           ErrorCategory.ReadError, process));
                      continue;
                   }

                   // Confirm the operation with the user first.
                   // This is always false if the WhatIf parameter is set.
                   if (!ShouldProcess(string.Format(CultureInfo.CurrentCulture,"{0} ({1})", processName,
                               process.Id)))
                   {
                       continue;
                   }

                   // Make sure that the user really wants to stop a critical
                   // process that could possibly stop the computer.
                   bool criticalProcess =
                       criticalProcessNames.Contains(processName.ToLower(CultureInfo.CurrentCulture));

                   if (criticalProcess &&!force)
                   {
                       string message = String.Format
                           (CultureInfo.CurrentCulture,
                                "The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                                    processName);

                       // It is possible that the ProcessRecord method is called
                       // multiple times when objects are received as inputs from
                       // the pipeline. So to retain YesToAll and NoToAll input that
                       // the user may enter across multiple calls to this function,
                       // they are stored as private members of the cmdlet.
                       if (!ShouldContinue(message, "Warning!",
                                               ref yesToAll, ref noToAll))
                       {
                           continue;
                       }
                   } // if (criticalProcess...

                   // Stop the named process.
                   try
                   {
                       process.Kill();
                   }
                   catch (Exception e)
                   {
                       if ((e is Win32Exception) || (e is SystemException) ||
                          (e is InvalidOperationException))
                       {
                           // This process could not be stopped so write
                           // a nonterminating error.
                           WriteError(new ErrorRecord(e, "CouldNotStopProcess",
                                           ErrorCategory.CloseError, process));
                           continue;
                       } // if ((e is...
                       else throw;
                   } // catch

                   // If the PassThru parameter is
                   // specified, return the terminated process.
                   if (passThru)
                   {
                       WriteObject(process);
                   }
               } // foreach (Process...
           } // foreach (string...
       } // ProcessRecord

       #endregion Cmdlet Overrides

       #region Private Data

       private bool yesToAll, noToAll;

       /// <summary>
       /// Partial list of critical processes that should not be
       /// stopped.  Lower case is used for case insensitive matching.
       /// </summary>
       private ArrayList criticalProcessNames = new ArrayList(
          new string[] { "system", "winlogon", "spoolsv" }
       );

       #endregion Private Data

   } // StopProcCommand

   #endregion StopProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="f7da6-129">参照</span><span class="sxs-lookup"><span data-stu-id="f7da6-129">See Also</span></span>

[<span data-ttu-id="f7da6-130">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="f7da6-130">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
