---
title: ErrorRecord オブジェクトの解釈 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a65b964-5bc6-4ade-a66b-b6afa7351ce7
caps.latest.revision: 9
ms.openlocfilehash: 32ebf2531237bfd1042310ccc4155193a58401fd
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058778"
---
# <a name="interpreting-errorrecord-objects"></a>ErrorRecord オブジェクトを解釈する

ほとんどの場合、 [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトは、コマンドまたはスクリプトによって生成された未終了エラーを表します。 エラーを終了できますも追加で情報を指定を使用して、ErrorRecord、 [System.Management.Automation.Icontainserrorrecord](/dotnet/api/System.Management.Automation.IContainsErrorRecord)インターフェイス。

スクリプトまたはホストを解釈する必要がありますが、コマンドまたはスクリプトの実行中に発生する特定のエラー処理でエラー ハンドラーを記述する場合、 [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)を決定するオブジェクトかどうか、処理するエラーのクラスを表します。

コマンドレットが検出した場合、終了または未終了エラー、エラー状態を説明するエラー レコードを作成する必要があります。 ホスト アプリケーションは、これらのエラー レコードを調査し、任意のアクションは、エラーを軽減するために実行する必要があります。 ホスト アプリケーションでは、レコードの処理に失敗しましたが、操作を続行することが終了しないエラーのエラー レコードを調べる必要がありますも、パイプラインが停止の原因となった終了するエラーのエラー レコードを調査する必要があります。

> [!NOTE]
> コマンドレットの呼び出しを終了するエラー、 [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッド。 コマンドレットを呼び出して、未終了エラーを[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド。

## <a name="error-record-design"></a>エラー レコードのデザイン

エラー レコードは、各エラー レコードの結合された情報が一意であることを確認中に例外に記載されていない追加のエラー情報を提供する設計されています。 この一意性は、ホスト アプリケーションがエラー状態を特定することし、ホストのアクションが実行する必要がありますようにエラー レコードのさまざまな部分を検査することができます。

## <a name="interpreting-error-records"></a>エラー レコードの解釈

エラーを識別するために、エラー レコードの複数の部分を確認することができます。 これらの部分を以下に示します。

- エラー カテゴリ

- エラーの例外

- エラーの完全修飾識別子 (FQID)

- その他の情報

### <a name="the-error-category"></a>エラー カテゴリ

エラー レコードのエラー カテゴリは、によって提供される定義済み定数のいずれか、 [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)列挙体。 この情報を利用、 [System.Management.Automation.ErrorRecord.CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo)のプロパティ、 [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。

このコマンドレットは、CloseError、OpenError、InvalidType、ReadError、および WriteError カテゴリ、およびその他のエラー カテゴリを指定できます。 ホスト アプリケーションは、エラー カテゴリを使用して、エラーのグループをキャプチャできます。

### <a name="the-exception"></a>例外

エラー レコードに含まれる例外は、コマンドレットによって提供され、を介してアクセスできる、 [System.Management.Automation.ErrorRecord.Exception*](/dotnet/api/System.Management.Automation.ErrorRecord.Exception)のプロパティ、 [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。

ホスト アプリケーションの使用、`is`の特定のクラスまたは派生クラスの例外がいることを識別するキーワード。 勧め例外の種類で branch に次の例に示すようにします。

`if (MyNonTerminatingError.Exception is AccessDeniedException)`

これにより、派生クラスをキャッチします。 ただし、問題は場合は、例外が逆シリアル化です。

### <a name="the-fqid"></a>FQID

FQID は、最も詳細な情報、エラーを識別するために使用することができます。 それは、コマンドレット定義の識別子、コマンドレット クラスでは、およびエラーを報告したソースの名前を含む文字列です。 一般に、エラー レコードは、Windows イベント ログのイベント レコードに似ています。 FQID は次の組は、イベント レコードのクラスを識別するに似ています。 (*ログ名*、*ソース*、*イベント ID*)。

1 つの文字列を検査するのには、FQID は設計されています。 ただし、エラーの識別子が、ホスト アプリケーションによって解析するように設計ケースが存在します。 次の例は、適切な形式の完全修飾エラー識別子です。

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand.`

前の例では、最初のトークンは、コマンドレット クラスの名前が続くエラー識別子です。 エラーの識別子は、1 つのトークンを指定できますか、識別子の検査で分岐できるドットで区切られた識別子であることができます。 エラー識別子で空白や句読点を使用することはできません。 コンマを使用しないように、特に重要ですがコンマは、コマンドレット クラスの名前、識別子を区切るために Windows PowerShell によって使用されます。

### <a name="other-information"></a>その他の情報

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトは、エラーが発生した環境を説明する情報も提供可能性があります。 この情報には、エラーの詳細、呼び出し情報、エラーが発生したときに処理されていたターゲット オブジェクトなどのアイテムが含まれます。 この情報は、ホスト アプリケーションに立つ可能性のある、これは通常使用されませんエラーを識別します。 この情報は、次のプロパティを使用します。

[System.Management.Automation.ErrorRecord.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails)

[System.Management.Automation.ErrorRecord.InvocationInfo](/dotnet/api/System.Management.Automation.ErrorRecord.InvocationInfo)

[System.Management.Automation.ErrorRecord.TargetObject](/dotnet/api/System.Management.Automation.ErrorRecord.TargetObject)

## <a name="see-also"></a>参照

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)

[System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)

[System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[未終了エラー レポート、コマンドレットに追加します。](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Windows PowerShell のエラー報告](./error-reporting-concepts.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
