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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859858"
---
# <a name="getprocesssample02-sample"></a>GetProcessSample02 サンプル

このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 提供、`Name`パラメーターを取得するプロセスを指定するために使用できます。 このコマンドレットは、簡略化されたバージョンの`Get-Process`コマンドレットの Windows PowerShell 2.0 で提供されます。

## <a name="how-to-build-the-sample-using-visual-studio"></a>Visual Studio を使用してサンプルをビルドする方法。

1. インストールされている Windows PowerShell 2.0 sdk では、GetProcessSample02 フォルダーに移動します。 既定の場所は、C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02 します。

2. ソリューション (.sln) ファイルのアイコンをダブルクリックします。 これは、Visual Studio でサンプル プロジェクトを開きます。

3. **ビルド**メニューの **ソリューションのビルド**します。

    サンプルのライブラリは、既定の \bin または \bin\debug フォルダーにビルドされます。

### <a name="how-to-run-the-sample"></a>サンプルを実行する方法

1. 次のモジュール フォルダーを作成します。

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. モジュール フォルダーにサンプル アセンブリをコピーします。

3. Windows PowerShell を起動します。

4. Windows PowerShell にアセンブリを読み込むには、次のコマンドを実行します。

    `import-module getprossessample02`

5. コマンドレットを実行する次のコマンドを実行します。

    `get-proc`

## <a name="requirements"></a>要件

このサンプルでは、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>使用例

このサンプルは、次を示します。

- コマンドレットの属性を使用して、コマンドレット クラスを宣言することです。

- パラメーター属性を使用して、コマンドレット パラメーターを宣言します。

- パラメーターの位置を指定します。

- 入力パラメーターの検証属性を宣言します。

## <a name="example"></a>例

このサンプルを含む Get-proc コマンドレットの実装を示しています、`Name`パラメーター。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
