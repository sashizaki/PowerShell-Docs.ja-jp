---
title: コマンドレットの入力処理メソッド |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual methods (PowerShell SDK]
ms.assetid: b0bb8172-c9fa-454b-9f1b-57c3fe60671b
caps.latest.revision: 12
ms.openlocfilehash: a28c8d3df19bc72bf338d6abc4e02768c5097209
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068489"
---
# <a name="cmdlet-input-processing-methods"></a>コマンドレットの入力処理メソッド

コマンドレットは、1 つ以上の入力処理メソッドが作業を実行するには、このトピックで説明をオーバーライドする必要があります。
これらのメソッドは、事前処理、入力の処理、および処理後の操作を実行するコマンドレットを使用できます。
これらのメソッドでは、コマンドレットの処理を停止することもできます。
これらのメソッドを使用する方法の詳細な例を参照してください。 [SelectStr チュートリアル](selectstr-tutorial.md)します。

## <a name="pre-processing-operations"></a>処理前の操作

コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)コマンドレットによって後で処理されるすべてのレコードの有効な前処理の操作を追加します。
PowerShell コマンドのパイプラインを処理するとき PowerShell メソッドを呼び出しますこの 1 回パイプラインでのコマンドレットの各インスタンスについて。
PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](/previous-versions/ms714429(v=vs.85))します。

次のコードでは、BeginProcessing メソッドの実装を示します。

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>処理操作の入力

コマンドレットをオーバーライドできます、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットに送信される入力を処理するメソッド。
PowerShell コマンドのパイプラインを処理するとき、PowerShell は、コマンドレットによって処理される各入力レコードのこのメソッドを呼び出します。
PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](/previous-versions/ms714429(v=vs.85))します。

次のコードでは、ProcessRecord メソッドの実装を示します。

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>処理後の操作

コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)コマンドレットによって処理されたすべてのレコードの有効な任意の後処理操作を追加するメソッド。
コマンドレットが完了したら、オブジェクト変数をクリーンアップする必要がありますなどを処理します。

PowerShell コマンドのパイプラインを処理するとき PowerShell メソッドを呼び出しますこの 1 回パイプラインでのコマンドレットの各インスタンスについて。
ただしは、PowerShell 実行時は呼び出さないこと、EndProcessing メソッド、コマンドレットがその入力の処理によって途中取り消された場合、または、コマンドレットのすべての部分では終了エラーが発生した場合に注意してください。
このため、オブジェクトのクリーンアップが必要なコマンドレットの完全な実装する必要があります[System.IDisposable](/dotnet/api/System.IDisposable)パターン、ファイナライザーをなど、ランタイムは両方、EndProcessing を呼び出すことができますと[System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。
PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](/previous-versions/ms714429(v=vs.85))します。

次のコードでは、EndProcessing メソッドの実装を示します。

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[SelectStr チュートリアル](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
