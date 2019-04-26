---
title: 入力処理メソッドをオーバーライドする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1ad921-5816-4937-acf1-ed4760fae740
caps.latest.revision: 8
ms.openlocfilehash: cfee55576518cf9ce38501192872ce94054f5213
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067945"
---
# <a name="how-to-override-input-processing-methods"></a>入力処理メソッドをオーバーライドする方法

これらの例では、入力の処理をコマンドレット内のメソッドを上書きする方法を示します。 これらのメソッドは、次の操作を実行に使用されます。

- [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)コマンドレットによって処理されたすべてのオブジェクトに対して有効では 1 回限りのスタートアップ操作を実行するメソッドを使用します。 Windows PowerShell ランタイムでは、このメソッドを 1 回だけ呼び出します。

- [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットに渡されるオブジェクトを処理するメソッドを使用します。 Windows PowerShell ランタイムでは、コマンドレットに渡される各オブジェクトに対してこのメソッドを呼び出します。

- [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)投稿を 1 回限りの処理操作を実行するメソッドを使用します。 Windows PowerShell ランタイムでは、このメソッドを 1 回だけ呼び出します。

## <a name="to-override-the-beginprocessing-method"></a>BeginProcessing メソッドをオーバーライドするには

- 保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。

次のクラスは、サンプル メッセージを出力します。 このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a>ProcessRecord メソッドをオーバーライドするには

- 保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。

次のクラスは、サンプル メッセージを出力します。 このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a>EndProcessing メソッドをオーバーライドするには

- 保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。

次のクラスは、サンプルを印刷します。 このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
