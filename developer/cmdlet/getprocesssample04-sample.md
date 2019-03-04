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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861878"
---
# <a name="getprocesssample04-sample"></a>GetProcessSample04 サンプル

このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。 プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。 このコマンドレットは、簡略化されたバージョンの`Get-Process`コマンドレットの Windows PowerShell 2.0 で提供されます。

## <a name="how-to-build-the-sample-using-visual-studio"></a>Visual Studio を使用してサンプルをビルドする方法。

1. インストールされている Windows PowerShell 2.0 sdk では、GetProcessSample04 フォルダーに移動します。 既定の場所は、C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04 します。

2. ソリューション (.sln) ファイルのアイコンをダブルクリックします。 これは、Visual Studio でサンプル プロジェクトを開きます。

3. **ビルド**メニューの **ソリューションのビルド**します。

    サンプルのライブラリは、既定の \bin または \bin\debug フォルダーにビルドされます。

### <a name="how-to-run-the-sample"></a>サンプルを実行する方法

1. 次のモジュール フォルダーを作成します。

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. モジュール フォルダーにサンプル アセンブリをコピーします。

3. Windows PowerShell を起動します。

4. Windows PowerShell にアセンブリを読み込むには、次のコマンドを実行します。

    `Import-module getprossessample04`

5. コマンドレットを実行する次のコマンドを実行します。

    `get-proc`

## <a name="requirements"></a>要件

このサンプルでは、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>使用例

このサンプルは、次を示します。

- コマンドレットの属性を使用して、コマンドレット クラスを宣言することです。

- パラメーター属性を使用して、コマンドレット パラメーターを宣言します。

- パラメーターの位置を指定します。

- パラメーターはパイプラインから入力されるかを指定します。 入力は、オブジェクトまたはプロパティの名前は、パラメーター名と同じオブジェクトのプロパティの値から取得できます。

- 入力パラメーターの検証属性を宣言します。

- 終了しないエラーをトラップして、エラー メッセージをエラー ストリームに書き込みます。

## <a name="example"></a>例

このサンプルでは、終了しないエラーを処理し、エラー メッセージをエラー ストリームに書き込みますコマンドレットを作成する方法を示します。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
