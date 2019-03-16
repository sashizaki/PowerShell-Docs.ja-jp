---
title: コマンドレットのエラーの報告 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error records [PowerShell], terminating
- non-terminating errors [PowerShell]
- error records [PowerShell]
- terminating errors [PowerShell]
- error records [PowerShell], non-terminating
ms.assetid: 0b014035-52ea-44cb-ab38-bbe463c5465a
caps.latest.revision: 8
ms.openlocfilehash: 45f5934314a2871ceb921c7a66b9dfb658d0bd99
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057945"
---
# <a name="cmdlet-error-reporting"></a>コマンドレット エラー レポート

コマンドレットには、エラーがエラーを終了しているかどうかに応じて異なる方法でエラーまたは終了しないエラーを報告する必要があります。 終了するエラーは、すぐに終了するパイプラインが発生したエラーまたは処理を続行する理由がない場合に発生するエラーです。 終了しないエラーは、現在のエラー条件を報告するこれらのエラーは、コマンドレットは、入力オブジェクトの処理を継続できます。 終了しないエラーは、通常、ユーザーは、問題の通知がコマンドレットは、[次へ] の入力オブジェクトの処理を続行します。

## <a name="terminating-and-nonterminating-errors"></a>終了しないエラー エラー

エラー状態が終了エラーまたは終了しないエラーを確認するのには、次のガイドラインを使用できます。

- エラー状態は、さらに入力オブジェクトはすべてを正常に処理されないコマンドレットをできなくなりますか。 場合は、終了エラーになります。

- 特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連するエラー状態ですか。 そうである場合は、終了しないエラーです。

- コマンドレットは別の入力オブジェクトの処理が成功しないことなど、複数の入力オブジェクトをそのまま使用しますか。 そうである場合は、終了しないエラーです。

- 間で何が終了して、終了しないエラーは、特定の状況が入力オブジェクトが 1 つのみに適用される場合にも複数の入力オブジェクトを受け入れ可能なコマンドレット決定します。

- コマンドレットは、任意の数の入力オブジェクトを受信し、終了例外をスローする前に任意の数のオブジェクトの成功またはエラーを送信できます。 受信した入力オブジェクトの数と送信オブジェクトの成功とエラーの数の間の関係はありません。

- 0 ~ 1 のオブジェクトを入力して生成が 0 ~ 1 に受け入れ可能なコマンドレットの出力オブジェクトのエラーを終了するエラーとして扱うし、終端の例外を生成する必要があります。

## <a name="reporting-nonterminating-errors"></a>終了しないエラーの報告

終了しないエラーの報告する必要がありますを行うまでのコマンドレットの実装内で、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド、または[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。 この種のエラーが呼び出すことによって報告された、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)さらに、エラー ストリームにエラー レコードを送信するメソッド。

## <a name="reporting-terminating-errors"></a>終了するエラーを報告

例外がスローされても呼び出すことによって、終了するエラーが報告された、 [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッド。 ただし、Windows PowerShell ランタイムはそれらをキャッチも例外を再びスローする必要はありません、コマンドレットのキャッチし再 OutOfMemory などの例外をスローできますもことに注意します。

状況に固有の問題に対して、独自の例外を定義または、そのエラー レコードを使用して既存の例外に情報を追加できます。

## <a name="error-records"></a>エラー レコード

Windows PowerShell を使用すると、終了しないエラー状態の説明[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。 各[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトは、エラー カテゴリの情報、省略可能なターゲット オブジェクト、およびエラーの状態に関する詳細情報を提供します。

### <a name="error-identifiers"></a>エラー識別子

エラー識別子は、コマンドレット内のエラー条件を識別する単純な文字列です。 Windows PowerShell は、特定のエラーに応答する場合は、エラー ストリームまたはエラーのログ記録をフィルター処理する場合は、後で使用できるエラーの完全修飾識別子を作成するコマンドレットの識別子を使用またはその他のユーザー固有のアクティビティでは、この識別子を組み合わせたものです。

エラーの識別子を指定するときに、次のガイドラインに従ってください。

- 異なるコード パスを別の高い特定のエラーの識別子を割り当てます。 呼び出すコード パスの各[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)または[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)独自のエラー識別子があります。

- エラー識別子は終了し、終了しないエラーの例外型を CLR に一意である必要があります。

- コマンドレットまたは Windows PowerShell プロバイダーのバージョン間でのエラー識別子のセマンティクスは変更されません。 エラー識別子のセマンティクスが確立されるは、コマンドレットのライフ サイクル全体で一定維持する必要があります。

- 終了するエラーを特定の CLR 例外型の一意のエラー識別子を使用します。 例外の種類が変更された場合は、新しいエラー識別子を使用します。

- 終了しないエラーの場合は、特定の入力オブジェクトの特定のエラー識別子を使用します。

- 答えました報告されるエラーに対応する識別子のテキストを選択します。 空白や句読点を使用しないでください。

- 再現可能でないエラー識別子を生成することはありません。 たとえば、プロセス識別子が含まれる識別子を生成しません。 エラー識別子は、同じ問題が発生している他のユーザーに表示される識別子に対応する場合にのみ役立ちます。

### <a name="error-categories"></a>エラー カテゴリ

エラー カテゴリは、エンドユーザーのエラーをグループ化に使用されます。 Windows PowerShell は、これらのカテゴリを定義し、エラー レコードを生成するときにそれらの間のコマンドレットと Windows PowerShell プロバイダーを選択する必要があります。

使用可能なエラー カテゴリの説明は、次を参照してください。、 [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)列挙体。 一般に、NoError、UndefinedError、および GenericError 可能な限り使用を避ける必要があります。

ユーザーが設定されている場合は、カテゴリに基づいてエラーを表示できます"`$ErrorView`""CategoryView"にします。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレット](./cmdlet-overview.md)

[コマンドレットの出力](./types-of-cmdlet-output.md)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
