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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068047"
---
# <a name="getprocesssample03-sample"></a>GetProcessSample03 サンプル

このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットを実装する方法を示します。 提供、`Name`パラメーター パイプラインからオブジェクトまたはプロパティの名前は、パラメーター名と同じオブジェクトのプロパティの値を受け入れることができます。 このコマンドレットは、簡略化されたバージョンの`Get-Process`コマンドレットの Windows PowerShell 2.0 で提供されます。

## <a name="how-to-build-the-sample-using-visual-studio"></a>Visual Studio を使用してサンプルをビルドする方法。

1. インストールされている Windows PowerShell 2.0 sdk では、GetProcessSample03 フォルダーに移動します。 既定の場所は、C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03 します。

2. ソリューション (.sln) ファイルのアイコンをダブルクリックします。 これは、Visual Studio でサンプル プロジェクトを開きます。

3. **ビルド**メニューの **ソリューションのビルド**します。

    サンプルのライブラリは、既定の \bin または \bin\debug フォルダーにビルドされます。

### <a name="how-to-run-the-sample"></a>サンプルを実行する方法

1. 次のモジュール フォルダーを作成します。

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. モジュール フォルダーにサンプル アセンブリをコピーします。

3. Windows PowerShell を起動します。

4. Windows PowerShell にアセンブリを読み込むには、次のコマンドを実行します。

    `Import-module getprossessample03`

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

## <a name="example"></a>例

このサンプルを含む Get-proc コマンドレットの実装を示しています、`Name`をパイプラインから入力を受け取るパラメーター。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
