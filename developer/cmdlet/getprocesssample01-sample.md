---
title: GetProcessSample01 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b48bf80-cbf0-4cb1-8d5b-3b8d06196598
caps.latest.revision: 10
ms.openlocfilehash: 00190c7350cb0f1cfc5c389b56e48e9397480446
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068064"
---
# <a name="getprocesssample01-sample"></a>GetProcessSample01 サンプル

このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。 このコマンドレットは、簡略化されたバージョンの`Get-Process`コマンドレットは Windows PowerShell 2.0 によって提供されます。

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>Visual Studio を使用してサンプルをビルドする方法。

1. インストールされている Windows PowerShell 2.0 sdk では、GetProcessSample01 フォルダーに移動します。 既定の場所は、C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01 します。

2. ソリューション (.sln) ファイルのアイコンをダブルクリックします。 これは、Microsoft Visual Studio でサンプル プロジェクトを開きます。

3. **ビルド**メニューの **ソリューションのビルド**します。

  サンプルのライブラリは、既定の \bin または \bin\debug フォルダーにビルドされます。

### <a name="how-to-run-the-sample"></a>サンプルを実行する方法

1. コマンド プロンプト ウィンドウを開きます。

2. サンプルの .dll ファイルを含むディレクトリに移動します。

3. Installutil"GetProcessSample01.dll"を実行します。

4. Windows PowerShell を起動します。

5. シェルにスナップインを追加するには、次のコマンドを実行します。

   `Add-PSSnapin GetProcPSSnapIn01`

6. コマンドレットを実行する次のコマンドを入力します。 `get-proc`

   `get-proc`

   これは、以下の手順によって生成される出力の例です。

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

## <a name="requirements"></a>要件

このサンプルでは、Windows PowerShell 1.0 以降が必要です。

## <a name="demonstrates"></a>使用例

このサンプルは、次を示します。

- 基本的なサンプルのコマンドレットを作成します。

- コマンドレットの属性を使用して、コマンドレット クラスを定義します。

- Windows PowerShell 1.0 と Windows PowerShell 2.0 の両方で動作するスナップインを作成します。 以降のサンプルは、Windows PowerShell 2.0 が必要なために、スナップインではなくモジュールを使用します。

## <a name="example"></a>例

このサンプルでは、単純なコマンドレットとそのスナップインで作成する方法を示します。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)