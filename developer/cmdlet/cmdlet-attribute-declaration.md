---
title: コマンドレットの属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlet attribute, described
- attributes, Cmdlet
- Cmdlet attribute
ms.assetid: 1d323332-f773-4c0e-8a69-2aada765afb2
caps.latest.revision: 12
ms.openlocfilehash: 6887467ad5ccafe6edf8f03f531b4750133aa9e9
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058030"
---
# <a name="cmdlet-attribute-declaration"></a>コマンドレット属性の宣言

コマンドレット属性は、コマンドレットとして Microsoft .NET Framework クラスを識別し、コマンドレットを呼び出すために使用する名詞と動詞を指定します。

## <a name="syntax"></a>構文

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a>パラメーター

`VerbName` ([System.String](/dotnet/api/System.String)) が必要です。 コマンドレットの動詞を指定します。 この動詞は、コマンドレットによって実行されるアクションを指定します。 承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)と[開発ガイドラインのために必要な](./required-development-guidelines.md)します。

`NounName` ([System.String](/dotnet/api/System.String)) が必要です。 コマンドレットの名詞を指定します。 この名詞では、コマンドレットが実行されるリソースを指定します。 コマンドレットの名詞の詳細については、次を参照してください。[コマンドレット宣言](./cmdlet-class-declaration.md)と[推奨される開発ガイドライン強く](./strongly-encouraged-development-guidelines.md)します。

`SupportsShouldProcess` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 `True` このコマンドレットへの呼び出しをサポートしていることを示します、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)コマンドレットをシステムを変更する操作を実行する前にユーザーに確認する方法を提供するメソッド。 `False`、既定値は、コマンドレットでは、への呼び出しはサポートされていないことを示します、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。 確認要求の詳細については、次を参照してください。[確認を要求する](./requesting-confirmation-from-cmdlets.md)します。

`ConfirmImpact` ([System.Management.Automation.Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) という名前のパラメーター (省略可能)。 呼び出しによって、コマンドレットのアクションを確認する場合を指定します、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) (既定では Medium)、コマンドレットの ConfirmImpact 値が等しくまたはの値よりも大きい場合にのみ呼び出される、`$ConfirmPreference`変数。 このパラメーターを指定する必要がある場合にのみ、`SupportsShouldProcess`パラメーターを指定します。

`DefaultParameterSetName` ([System.String](/dotnet/api/System.String)) という名前のパラメーター (省略可能)。 Windows PowerShell ランタイムが使用するパラメーターの設定を判断できないときに使用しようとする既定のパラメーターの設定を指定します。 このような状況は、必須のパラメーターを設定する各パラメーターの一意のパラメーターを削除できることを確認します。

Windows PowerShell が設定の既定のパラメーター セット名が指定した場合でも、既定のパラメーターを使用できない場合は。 Windows PowerShell ランタイムは、オブジェクトの種類のみに基づくパラメーター セットを区別できません。 たとえばがある場合、ファイル パスと別のセットとして文字列を受け取る 1 つのパラメーター セットは、 **FileInfo**オブジェクトを直接の Windows PowerShell に渡される値に基づいてパラメーターを使用する設定を確認することはできません、コマンドレットでは、既定のパラメーター セットが使用されることもできません。 この場合、既定のパラメーター セット名を指定した場合でも、Windows PowerShell はあいまいなパラメーター セット エラー メッセージをスローします。

`SupportsTransactions` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 `True` トランザクション内でコマンドレットを使用できることを示します。 ときに`True`を指定すると、Windows PowerShell ランタイムを追加、`UseTransaction`コマンドレットのパラメーター リストのパラメーター。 `False`で、既定値は、トランザクション内でコマンドレットを使用できないことを示します。

## <a name="remarks"></a>コメント

- 同時に、動詞と名詞は、スクリプト内でコマンドレットを呼び出すと、登録されているコマンドレットを識別するために使用されます。

- コマンドレットは、Windows PowerShell コンソールから起動されるのコマンドは、次のコマンドと似ています。

**VerbName-NounName**

- Windows PowerShell の外部のリソースを変更するすべてのコマンドレットを含める必要があります、 `SupportsShouldProcess` 、コマンドレットを呼び出すことができるキーワード コマンドレット属性が宣言されている場合、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドの前に、そのアクションを実行します。 場合、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)返しますを呼び出す`false`、この操作を実行しない必要があります。 によって生成される確認要求の詳細については、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しを参照してください[確認を要求する](./requesting-confirmation-from-cmdlets.md)します。

`Confirm`と`WhatIf`コマンドレットのパラメーターはサポートするコマンドレットでのみ使用できます[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出し。

## <a name="example"></a>例

次のクラス定義の .NET Framework クラスを識別するためにコマンドレットの属性を使用して、 **Get-proc**ローカル コンピューターで実行されているプロセスに関する情報を取得するコマンドレットです。

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

詳細については、 **Get-proc**コマンドレットを参照してください[GetProc チュートリアル](./getproc-tutorial.md)します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
