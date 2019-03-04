---
title: エラーの終了 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b804e738-aefa-41bb-9649-f9ed897fd96c
caps.latest.revision: 8
ms.openlocfilehash: c593da1f7bdb6ddf09ba8d5de92af730687dbc8a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859238"
---
# <a name="terminating-errors"></a>終了するエラー

このトピックでは、エラーの終了レポートに使用する方法について説明します。 コマンドレットは、内からメソッドを呼び出す方法についても説明し、メソッドが呼び出されたときに、Windows PowerShell ランタイムによって返される例外について説明します。

終了中にエラーが発生した、コマンドレットは呼び出すことによって、エラーを報告する必要があります、 [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッド。 このメソッドは、終了エラーの原因となった状態を説明するエラー レコードを送信するためのコマンドレットを使用します。 エラー レコードの詳細については、次を参照してください。 [Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)します。

ときに、 [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドが呼び出されると、Windows PowerShell ランタイムは完全に、パイプラインの実行を停止し、スロー、 [System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外。 呼び出すしようとした後続[System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)、 [System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)、またはその他のいくつかの Api によりこれらの呼び出しをスローする、[System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外。

[System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外は、場合は、ユーザーが、パイプラインを停止するように求められます、パイプライン内の別のコマンドレットは、終了エラーを報告する場合、またはパイプラインが停止した場合にも発生することができます何らかの理由で完了前にします。 コマンドレットは、キャッチする必要はありません、 [System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外しない限り、リソースまたは内部の状態、クリーンアップを開く必要があります。

コマンドレットは、終了エラーを報告する前に、任意の数の出力オブジェクトまたは未終了エラーを記述できます。 ただし、終了エラーは、パイプラインと、エラーを終了しながら、さらに出力なしに完全に停止または未終了エラーを報告することができます。

コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)を呼び出したスレッドからのみ、 [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、 [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、または[System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)処理方法を入力します。 呼び出すしないで[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)または[System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)別のスレッドから。 代わりに、エラーは、メイン スレッドに伝達する必要があります。

実装で例外をスローすることができます、コマンドレット、 [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、 [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、または[System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。 (Windows PowerShell ホストを停止するいくつかの重大なエラー条件) を除くこれらのメソッドからスローされた例外は、パイプラインが全体として Windows PowerShell ではなくを停止する終了エラーとして解釈されます。 (これは、コマンドレットのメイン スレッドにのみ適用されます。 キャッチされない例外、コマンドレットによって生成されたスレッドで一般に、停止、Windows PowerShell ホストします。)使用することをお勧めします[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)エラー レコードがエラー状態に関する追加情報を提供するために例外がスローされるのではなくするのに便利です。エンドユーザー。 コマンドレットをキャッチして、すべての例外の処理に対してマネージ コードのガイドラインを受け入れる必要がある (`catch (Exception e)`)。 エラー レコードには、既知および必要な型の例外のみを変換します。

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
