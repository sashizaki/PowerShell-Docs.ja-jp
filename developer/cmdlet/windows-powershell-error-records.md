---
title: Windows PowerShell のエラーを記録 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error category [PowerShell SDK]
- error identifier [PowerShell SDK]
- error records [PowerShell SDK]
- error category string [PowerShell SDK]
ms.assetid: bdd66fea-eb63-4bb6-9cbe-9a799e5e0db5
caps.latest.revision: 9
ms.openlocfilehash: bbe04a8fb556f0f6807bc0eae6634e3cf505759e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861978"
---
# <a name="windows-powershell-error-records"></a>Windows PowerShell エラー レコード

コマンドレットに渡す必要があります、 [System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)を終了し、未終了エラーをエラー状態を識別するオブジェクト。

[System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトには、次の情報が含まれています。

- エラーを説明する例外。 多くの場合、これは、コマンドレットがキャッチされ、エラー レコードに変換する例外です。 すべてのエラー レコードには、例外を含める必要があります。

コマンドレットでは、例外をキャッチしなかった場合は新しい例外を作成する必要があり、エラー条件に最も近い例外クラスを選択します。 ただしを使用してアクセスできるため、例外がスローする必要はありません、 [System.Management.Automation.Errorrecord.Exception*](/dotnet/api/System.Management.Automation.ErrorRecord.Exception)のプロパティ、 [System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。

- 特定のエラー ハンドラーを使用して特定のエラー条件を処理する Windows PowerShell スクリプト、診断のために使用できる対象となる指定子を提供するエラーの識別子です。 すべてのエラー レコードは、エラーの識別子を含める必要があります (エラーの識別子を参照してください)。

- 診断のために使用できる一般的な指定子を提供するエラー カテゴリ。 すべてのエラー レコードは、エラー カテゴリを指定する必要があります (エラーのカテゴリを参照してください)。

- 省略可能な交換のエラー メッセージと推奨される操作 (交換のエラー メッセージを参照してください)。

- 省略可能な呼び出しをエラーをスローしたコマンドレットについて説明します。 Windows PowerShell でこの情報が指定された (呼び出しメッセージを参照してください)。

- エラーが発生したときに処理されていたターゲット オブジェクト。 入力のオブジェクトがあります。 または別のオブジェクト、コマンドレットを処理している場合があります。 たとえば、コマンドは、`remove-item -recurse c:\somedirectory`エラー"c:\somedirectory\lockedfile"の FileInfo オブジェクトのインスタンスである可能性があります。 ターゲット オブジェクトの情報は省略可能です。

## <a name="error-identifier"></a>エラー識別子

エラー レコードを作成するときに、コマンドレット内のエラー条件を指定する識別子を指定します。 Windows PowerShell は、エラーの完全修飾識別子を作成するコマンドレットの名前と、対象となる識別子を結合します。 エラーの完全修飾識別子をを介してアクセスできる、 [System.Management.Automation.Errorrecord.Fullyqualifiederrorid*](/dotnet/api/System.Management.Automation.ErrorRecord.FullyQualifiedErrorId)のプロパティ、 [System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。 単独では、エラーの識別子を使用できません。 入手可能になったエラーの完全修飾識別子の一部としてのみです。

エラー レコードを作成するときに、エラーの識別子を生成するのにには、次のガイドラインを使用します。

- エラー条件に固有のエラー識別子を作成します。 診断のために、特定のエラー ハンドラーを使用して特定のエラー条件を処理するスクリプトのエラー識別子を対象します。 ユーザーは、エラーの識別子を使用して、エラーとそのソースを識別するためにできる必要があります。 エラー識別子では、新しい例外のサブクラスが必要でないように、既存の例外からの特定のエラー条件のレポートも有効にします。

- 一般に、異なるコード パスを別のエラーの識別子を割り当てます。 エンドユーザーは、特定の識別子からメリットがあります。 多くの場合、各コードのパスを呼び出す[System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)または[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)が独自の識別子。 原則として、エラー メッセージ、およびその逆の新しいテンプレート文字列を定義するときに、新しい識別子を定義します。 識別子としてエラー メッセージを使わないでください。

- 特定のエラー識別子を使用してコードを発行するときに、完全な製品の識別子を持つエラーのセマンティクスのサポート ライフ サイクルを確立します。 再利用しないことは、元のコンテキストから意味の異なるコンテキストでします。 このエラーのセマンティクスを変更する場合は、作成し、新しい識別子を使用します。

- 特定の CLR 型の例外に対してのみ、特定のエラー識別子を使用する必要があります一般にします。 例外の種類またはターゲット オブジェクトの型が変更された場合は、作成し、新しい識別子を使用します。

- 簡潔に報告するエラーに対応するユーザーのエラー識別子のテキストを選択します。 標準の .NET Framework の名前付けおよび大文字と小文字の規則を使用します。 空白や句読点を使用しないでください。 エラー識別子はローカライズしないでください。

- 動的に生成しませんエラー識別子再現できない方法で。 たとえば、プロセス ID などのエラー情報を組み込んでいません。 エラー識別子は、同じエラー条件が発生している他のユーザーに表示されるエラーの識別子に対応する場合にのみ役立ちます。

## <a name="error-category"></a>エラー カテゴリ

エラー レコードを作成する場合は、によって定義された定数のいずれかを使用してエラーのカテゴリを指定、 [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)列挙体。 Windows PowerShell ユーザー設定するときに、エラー情報を表示するエラー カテゴリを使用して、`$ErrorView`変数を`"CategoryView"`します。

使用しないでください、 [System.Management.Automation.Errorcategory.Notspecified](/dotnet/api/System.Management.Automation.ErrorCategory.NotSpecified)定数。 エラーの原因となった操作、またはエラーに関する情報があれば、カテゴリが完全に一致する場合でも、エラーまたは操作に最も近いカテゴリを選択します。

Windows PowerShell によって表示される情報はカテゴリの表示文字列として参照されておりのプロパティから構築された、 [System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)クラス。 (このクラスは、エラー [System.Management.Automation.Errorrecord.Categoryinfo*](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo)プロパティです)。

```
{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}
```

次の一覧には、表示される情報について説明します。

- カテゴリ:Windows PowerShell による[System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)定数。

- TargetName:既定では、オブジェクトの名前、コマンドレットが処理エラーが発生したときにします。 または、別のコマンドレットで定義された文字列。

- TargetType:既定では、ターゲット オブジェクトの種類。 または、別のコマンドレットで定義された文字列。

- アクティビティ:既定ではエラー レコードを作成したコマンドレットの名前。 または、他のコマンドレットで定義されている文字列。

- 理由:既定では、例外の種類。 または、別のコマンドレットで定義された文字列。

## <a name="replacement-error-message"></a>エラー メッセージの交換

エラーの既定のエラー メッセージに由来の既定のメッセージ テキスト、コマンドレットのエラー レコードを開発する際に、 [System.Exception.Message](/dotnet/api/System.Exception.Message)プロパティ。 これは、プロパティは読み取り専用プロパティ (.NET Framework ガイドライン) によるデバッグのためだけのメッセージ テキストが対象としています。 置き換えるか、既定のメッセージ テキストを補強するエラー メッセージを作成することをお勧めします。 メッセージをユーザーにわかりやすいより限定コマンドレットに加えます。

交換のメッセージがによって提供される、 [System.Management.Automation.Errordetails](/dotnet/api/System.Management.Automation.ErrorDetails)オブジェクト。 Windows PowerShell で使用できる追加のローカリゼーション情報を提供するために、このオブジェクトの次のコンス トラクターのいずれかを使用します。

- [ErrorDetails.ErrorDetails (コマンドレット、文字列、文字列、オブジェクト\[System.Management.Automation.Errordetails.%23Ctor%28System.Management.Automation.Cmdlet%2Csystem.String%2Csystem.String%2Csystem.Object%5B%5D%29 でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.ErrorDetails.%23ctor%28System.Management.Automation.Cmdlet%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29):このコンス トラクターを使用して、テンプレート文字列が、コマンドレットが実装される、同じアセンブリ内のリソース文字列の場合、またはの上書きすることによって、テンプレート文字列をロードする場合、 [System.Management.Automation.Cmdlet.Getresourcestring*](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString)メソッド。

- [ErrorDetails.ErrorDetails (アセンブリ、文字列、文字列、オブジェクト\[System.Management.Automation.Errordetails.%23Ctor%28System.Reflection.Assembly%2Csystem.String%2Csystem.String%2Csystem.Object%5B%5D%29 でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.ErrorDetails.%23ctor%28System.Reflection.Assembly%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29):このコンス トラクターを使用して、テンプレート文字列が別のアセンブリでのオーバーライドによって読み込みは[System.Management.Automation.Cmdlet.Getresourcestring*](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString)します。

交換のメッセージは、わずかな違いで例外メッセージを書き込むための .NET Framework デザイン ガイドラインに従う必要があります。 開発者の例外メッセージを書き込む必要があるガイドラインの状態。 コマンドレットのユーザーに対して、これらの交換のメッセージが書き込まれます。

前に、交換のエラー メッセージを追加する必要があります、 [System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)または[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドが呼び出されます. 交換のメッセージを追加するには、設定、 [System.Management.Automation.Errorrecord.Errordetails*](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails)エラー レコードのプロパティ。 このプロパティを設定すると、Windows PowerShell が表示されます、 [System.Management.Automation.Errordetails.Message*](/dotnet/api/System.Management.Automation.ErrorDetails.Message)既定のメッセージ テキストではなくプロパティ。

## <a name="recommended-action-information"></a>アクションの情報をお勧めします。

[System.Management.Automation.Errordetails](/dotnet/api/System.Management.Automation.ErrorDetails)オブジェクトは、どのようなアクションは、エラーが発生した場合に推奨されるに関する情報を提供もできます。

## <a name="invocation-information"></a>呼び出し情報

コマンドレットを使用する場合[System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)または[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)エラー レコード、Windows PowerShell を報告するにはエラーが発生したときに呼び出されたコマンドを説明する情報を自動的に追加します。 この情報によって提供されます、 [System.Management.Automation.Invocationinfo](/dotnet/api/System.Management.Automation.InvocationInfo)コマンド、コマンド自体には、によって呼び出されたコマンドレットの名前を格納しているオブジェクトと、パイプラインまたはスクリプトに関する情報。 このプロパティは読み取り専用です。

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)

[System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)

[System.Management.Automation.Errordetails](/dotnet/api/System.Management.Automation.ErrorDetails)

[System.Management.Automation.Invocationinfo](/dotnet/api/System.Management.Automation.InvocationInfo)

[Windows PowerShell のエラー報告](./error-reporting-concepts.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
