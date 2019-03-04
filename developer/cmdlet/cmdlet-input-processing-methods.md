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
ms.openlocfilehash: dfaaa19fd3d4eb65a3fd335fb984a69874688f27
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861488"
---
# <a name="cmdlet-input-processing-methods"></a>コマンドレットの入力処理メソッド

コマンドレットは、1 つ以上の入力処理メソッドが作業を実行するには、このトピックで説明をオーバーライドする必要があります。 これらのメソッドは、処理前の操作、入力処理操作、および処理後の操作を実行するコマンドレットを使用できます。 これらのメソッドでは、コマンドレットの処理を停止することもできます。

## <a name="pre-processing-tasks"></a>処理前のタスク

コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)コマンドレットによって後で処理されるすべてのレコードの有効な前処理の操作を追加します。 Windows PowerShell コマンドのパイプラインを処理するとき Windows PowerShell はこのメソッド 1 回パイプラインでのコマンドレットの各インスタンスについて、 Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。

次のコードの実装を示します、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)メソッド。

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the BeginProcessing template."
  WriteObject("This is a test of the BeginProcessing template.");
}
```

使用する方法の詳細な例については、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)メソッドを参照してください[SelectStr チュートリアル](./selectstr-tutorial.md)します。 このチュートリアルで、**選択 Str**コマンドレットを使用して、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)検索入力レコードの処理に使用される正規表現を生成します。

## <a name="input-processing-tasks"></a>処理タスクを入力します。

コマンドレットをオーバーライドできます、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)コマンドレットに送信される入力を処理するメソッド。 Windows PowerShell コマンドのパイプラインを処理するとき、Windows PowerShell は、コマンドレットによって処理される各入力レコードのこのメソッドを呼び出します。 Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。
コマンドレットをオーバーライドできます、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)コマンドレットに送信される入力を処理するメソッド。 Windows PowerShell コマンドのパイプラインを処理するとき、Windows PowerShell は、コマンドレットによって処理される各入力レコードのこのメソッドを呼び出します。 Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。

次のコードの実装を示します、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッド。

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the ProcessRecord template."
  WriteObject("This is a test of the ProcessRecord template.");
}
```

使用する方法の詳細な例については、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッドを参照してください[SelectStr チュートリアル](./selectstr-tutorial.md)します。

## <a name="post-processing-tasks"></a>処理後のタスク

コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)コマンドレットによって処理されたすべてのレコードの有効な任意の後処理操作を追加するメソッド。 コマンドレットが完了したら、オブジェクト変数をクリーンアップする必要がありますなどを処理します。

Windows PowerShell コマンドのパイプラインを処理するとき Windows PowerShell はこのメソッド 1 回パイプラインでのコマンドレットの各インスタンスについて、 ただし、それは、Windows PowerShell ランタイムを呼び出さないことに注意してください、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)メソッドの場合、コマンドレットは、その入力の処理によって途中キャンセルまたは終端コマンドレットのすべての部分で、エラーが発生します。 このため、オブジェクトのクリーンアップが必要なコマンドレットの完全な実装する必要があります[System.Idisposable](/dotnet/api/System.IDisposable)パターン、ファイナライザーをなど、ランタイムは、両方を呼び出すことができます、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)と[System.Idisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。 Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。
Windows PowerShell コマンドのパイプラインを処理するとき Windows PowerShell はこのメソッド 1 回パイプラインでのコマンドレットの各インスタンスについて、 ただし、それは、Windows PowerShell ランタイムを呼び出さないことに注意してください、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)メソッドの場合、コマンドレットは、その入力の処理によって途中キャンセルまたは終端コマンドレットのすべての部分で、エラーが発生します。 このため、オブジェクトのクリーンアップが必要なコマンドレットの完全な実装する必要があります[System.Idisposable](/dotnet/api/System.IDisposable)パターン、ファイナライザーをなど、ランタイムは、両方を呼び出すことができます、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)と[System.Idisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。 Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。

次のコードの実装を示します、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッド。

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the EndProcessing template."
  WriteObject("This is a test of the EndProcessing template.");
}
```

使用する方法の詳細な例については、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッドを参照してください[SelectStr チュートリアル](./selectstr-tutorial.md)します。

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)

[System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)

[System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)

[System.Idisposable](/dotnet/api/System.IDisposable)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
