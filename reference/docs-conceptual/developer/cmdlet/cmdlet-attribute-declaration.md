---
title: コマンドレットの属性宣言 |Microsoft Docs
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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363541"
---
# <a name="cmdlet-attribute-declaration"></a>コマンドレット属性の宣言

コマンドレット属性は、コマンドレットとして Microsoft .NET Framework クラスを識別し、コマンドレットを呼び出すために使用される動詞と名詞を指定します。

## <a name="syntax"></a>構文

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a>パラメーター

`VerbName` ([system.string](/dotnet/api/System.String)) が必要です。 コマンドレットの動詞を指定します。 この動詞は、コマンドレットによって実行されるアクションを指定します。 承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」および「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。

`NounName` ([system.string](/dotnet/api/System.String)) が必要です。 コマンドレットの名詞を指定します。 この名詞は、コマンドレットが処理するリソースを指定します。 コマンドレットの名詞の詳細については、「[コマンドレットの宣言](./cmdlet-class-declaration.md)」を[参照してください。](./strongly-encouraged-development-guidelines.md)

`SupportsShouldProcess` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。 `True` は、コマンドレット[が、システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を変更する操作を実行する前にユーザーにプロンプトを表示する方法を提供する、コマンドレットの呼び出しをサポートしていることを示します。 既定値である `False`は、このコマンドレットが、 [system.object メソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しをサポートしていないことを示します。 確認要求の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。

`ConfirmImpact` ([System. Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) 省略可能な名前付きパラメーター。 コマンドレットのアクションを、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しによって確認するかどうかを指定します。 コマンドレットの ConfirmImpact 値 (既定では、Medium) が `$ConfirmPreference` 変数の値以上である場合にのみ、指定[された](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)値が呼び出されます。 このパラメーターは、`SupportsShouldProcess` パラメーターが指定されている場合にのみ指定する必要があります。

`DefaultParameterSetName` ([system.string](/dotnet/api/System.String)) 省略可能な名前付きパラメーター。 使用するパラメーターセットを判別できない場合に、Windows PowerShell ランタイムが使用を試みる既定のパラメーターセットを指定します。 各パラメーターの unique パラメーターに必須パラメーターを設定することで、この状況を解消できることに注意してください。

既定のパラメーターセット名が指定されている場合でも、Windows PowerShell で既定のパラメーターセットを使用できないケースが1つあります。 Windows PowerShell ランタイムでは、オブジェクトの種類のみを基にしたパラメーターセットを区別できません。 たとえば、ファイルパスとして文字列を受け取る1つのパラメーターセットと、 **FileInfo**オブジェクトを直接受け取る別のセットがある場合、Windows PowerShell は、コマンドレットに渡された値に基づいて、使用するパラメーターセットを決定できません。また、既定のパラメーターセットを使用しません。 この場合、既定のパラメーターセット名を指定しても、Windows PowerShell はあいまいなパラメーターセットのエラーメッセージをスローします。

`SupportsTransactions` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。 `True` は、コマンドレットをトランザクション内で使用できることを示します。 `True` が指定されている場合、Windows PowerShell ランタイムは、コマンドレットのパラメーターリストに `UseTransaction` パラメーターを追加します。 既定値の `False`は、コマンドレットをトランザクション内で使用できないことを示します。

## <a name="remarks"></a>コメント

- 動詞と名詞を一緒に使用して、登録されているコマンドレットを識別し、スクリプト内でコマンドレットを呼び出します。

- コマンドレットが Windows PowerShell コンソールから呼び出されると、コマンドは次のようになります。

**VerbName-NounName**

- コマンドレット属性が宣言されている場合は、Windows PowerShell の外部でリソースを変更するすべてのコマンドレットに `SupportsShouldProcess` キーワードを含める必要があります。これにより、コマンドレットは、コマンドレットがアクションを実行する前[に、このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出すことができます。 この呼び出し[によって `false`](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)が返された場合、アクションを実行する必要はありません。 [コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しによって生成される確認要求の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。

`Confirm` および `WhatIf` のコマンドレットパラメーターは、の呼び出しをサポートするコマンドレットでのみ使用[できます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

## <a name="example"></a>例

次のクラス定義では、コマンドレット属性を使用して、ローカルコンピューター上で実行されているプロセスに関する情報を取得する**Get Proc**コマンドレットの .NET Framework クラスを識別します。

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

**Get proc**コマンドレットの詳細については、「 [getproc チュートリアル](./getproc-tutorial.md)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
