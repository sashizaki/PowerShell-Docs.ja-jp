---
ms.date: 09/13/2016
ms.topic: reference
title: GetProcessSample01 サンプル
description: GetProcessSample01 サンプル
ms.openlocfilehash: 159c277d17a8551d2b5c52377a230babacafc9ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652770"
---
# <a name="getprocesssample01-sample"></a><span data-ttu-id="f1bf7-103">GetProcessSample01 サンプル</span><span class="sxs-lookup"><span data-stu-id="f1bf7-103">GetProcessSample01 Sample</span></span>

<span data-ttu-id="f1bf7-104">このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-104">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="f1bf7-105">このコマンドレットは、 `Get-Process` Windows PowerShell 2.0 によって提供されるコマンドレットの簡略化されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-105">This cmdlet is a simplified version of the `Get-Process` cmdlet that is provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="f1bf7-106">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-106">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="f1bf7-107">Windows PowerShell 2.0 SDK がインストールされている状態で、GetProcessSample01 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample01 folder.</span></span> <span data-ttu-id="f1bf7-108">既定の場所は C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01. です。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span></span>

2. <span data-ttu-id="f1bf7-109">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="f1bf7-110">これにより、Microsoft Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-110">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="f1bf7-111">**[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-111">In the **Build** menu, select **Build Solution**.</span></span>

  <span data-ttu-id="f1bf7-112">サンプルのライブラリは、既定の \bin フォルダーまたは \bin\debug フォルダーに構築されます。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="f1bf7-113">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f1bf7-113">How to run the sample</span></span>

1. <span data-ttu-id="f1bf7-114">コマンド プロンプト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-114">Open a Command Prompt window.</span></span>

2. <span data-ttu-id="f1bf7-115">サンプル .dll ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-115">Navigate to the directory containing the sample .dll file.</span></span>

3. <span data-ttu-id="f1bf7-116">Installutil.exe "GetProcessSample01.dll" を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-116">Run installutil "GetProcessSample01.dll".</span></span>

4. <span data-ttu-id="f1bf7-117">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-117">Start Windows PowerShell.</span></span>

5. <span data-ttu-id="f1bf7-118">次のコマンドを実行して、スナップインをシェルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-118">Run the following command to add the snap-in to the shell.</span></span>

   `Add-PSSnapin GetProcPSSnapIn01`

6. <span data-ttu-id="f1bf7-119">次のコマンドを入力して、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-119">Enter the following command to run the cmdlet.</span></span> `get-proc`

   `get-proc`

   <span data-ttu-id="f1bf7-120">これは、次の手順を実行した結果として得られるサンプル出力です。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-120">This is a sample output that results from following these steps.</span></span>

   ```output
   Id              Name            State      HasMoreData     Location             Command
   --              ----            -----      -----------     --------             -------
   1               26932870-d3b... NotStarted False                                 Write-Host "A f...

   ```

   ```powershell
   Set-Content $env:temp\test.txt "This is a test file"
   ```

   ```output
   A file was created in the TEMP directory
   ```

## <a name="requirements"></a><span data-ttu-id="f1bf7-121">要件</span><span class="sxs-lookup"><span data-stu-id="f1bf7-121">Requirements</span></span>

<span data-ttu-id="f1bf7-122">このサンプルには、Windows PowerShell 1.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-122">This sample requires Windows PowerShell 1.0 or later.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f1bf7-123">対象</span><span class="sxs-lookup"><span data-stu-id="f1bf7-123">Demonstrates</span></span>

<span data-ttu-id="f1bf7-124">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-124">This sample demonstrates the following.</span></span>

- <span data-ttu-id="f1bf7-125">基本的なサンプルコマンドレットを作成しています。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-125">Creating a basic sample cmdlet.</span></span>

- <span data-ttu-id="f1bf7-126">コマンドレットの属性を使用して、コマンドレットクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-126">Defining a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="f1bf7-127">Windows PowerShell 1.0 と Windows PowerShell 2.0 の両方で動作するスナップインを作成する。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-127">Creating a snap-in that works with both Windows PowerShell 1.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="f1bf7-128">後続のサンプルでは、Windows PowerShell 2.0 を必要とするために、スナップインではなくモジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-128">Subsequent samples use modules instead of snap-ins so they require Windows PowerShell 2.0.</span></span>

## <a name="example"></a><span data-ttu-id="f1bf7-129">例</span><span class="sxs-lookup"><span data-stu-id="f1bf7-129">Example</span></span>

<span data-ttu-id="f1bf7-130">このサンプルでは、簡単なコマンドレットとそのスナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1bf7-130">This sample shows how to create a simple cmdlet and its snap-in.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{

   #region GetProcCommand

   /// <summary>
   /// This class implements the Get-Proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes of the local computer.
      /// Then, the WriteObject method writes the associated processes
      /// to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
         // Retrieve the current processes.
         Process[] processes = Process.GetProcesses();

         // Write the processes to the pipeline to make them available
         // to the next cmdlet. The second argument (true) tells Windows
         // PowerShell to enumerate the array and to send one process
         // object at a time to the pipeline.
         WriteObject(processes, true);
      }

      #endregion Overrides

   } //GetProcCommand

   #endregion GetProcCommand

   #region PowerShell snap-in

   /// <summary>
   /// Create this sample as an PowerShell snap-in
   /// </summary>
   [RunInstaller(true)]
   public class GetProcPSSnapIn01 : PSSnapIn
   {
       /// <summary>
       /// Create an instance of the GetProcPSSnapIn01
       /// </summary>
       public GetProcPSSnapIn01()
           : base()
       {
       }

       /// <summary>
       /// Get a name for this PowerShell snap-in. This name will be used in registering
       /// this PowerShell snap-in.
       /// </summary>
       public override string Name
       {
           get
           {
               return "GetProcPSSnapIn01";
           }
       }

       /// <summary>
       /// Vendor information for this PowerShell snap-in.
       /// </summary>
       public override string Vendor
       {
           get
           {
               return "Microsoft";
           }
       }

       /// <summary>
       /// Gets resource information for vendor. This is a string of format:
       /// resourceBaseName,resourceName.
       /// </summary>
       public override string VendorResource
       {
           get
           {
               return "GetProcPSSnapIn01,Microsoft";
           }
       }

       /// <summary>
       /// Description of this PowerShell snap-in.
       /// </summary>
       public override string Description
       {
           get
           {
               return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
           }
       }
   }

   #endregion PowerShell snap-in
}
```

## <a name="see-also"></a><span data-ttu-id="f1bf7-131">参照</span><span class="sxs-lookup"><span data-stu-id="f1bf7-131">See Also</span></span>

[<span data-ttu-id="f1bf7-132">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="f1bf7-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
