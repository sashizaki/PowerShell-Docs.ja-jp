---
title: 終了エラー |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 272e6cdd9a1da3cfd2e4f730f6aeb27577948278
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786392"
---
# <a name="terminating-errors"></a>終了するエラー

このトピックでは、終了エラーを報告するために使用する方法について説明します。 また、コマンドレット内からメソッドを呼び出す方法についても説明し、メソッドが呼び出されたときに Windows PowerShell ランタイムによって返される可能性がある例外について説明します。

終了エラーが発生した場合、コマンドレットは[Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドを呼び出してエラーを報告する必要があります。 このメソッドを使用すると、コマンドレットは、終了エラーの原因となった状態を説明するエラーレコードを送信できます。 エラーレコードの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。

[Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドが呼び出されると、Windows PowerShell ランタイムによって、パイプラインの実行が完全に停止され、 [Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外がスローされてしまいます。 その後、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)、またはその他のいくつかの api を呼び出そうとすると、これらの呼び出しによって[Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外がスローされることになります。

また、 [Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外は、パイプラインの別のコマンドレットが終了エラーを報告した場合、ユーザーがパイプラインの停止を要求した場合、または何らかの理由で完了前にパイプラインが停止した場合にも発生することがあります。 このコマンドレットは、開いているリソースまたはその内部状態をクリーンアップする必要がない限り、 [Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)例外をキャッチする必要はありません。

コマンドレットは、終了エラーを報告する前に、任意の数の出力オブジェクトまたは終了しないエラーを書き込むことができます。 ただし、終了エラーによってパイプラインが完全に停止されます。これ以降の出力、終了エラー、または終了しないエラーは報告されません。

コマンドレットで[Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)を呼び出すことができるのは、[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の呼び出しを実行したスレッド、また[は、また](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)[はシステムを](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)使用して、..................................... コマンド処理メソッド 別のスレッドから[Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)または[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことはできませんが、このような処理は行われません。 代わりに、エラーをメインスレッドに送り返す必要があります。

コマンドレット[が、](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の実装で例外をスローする可能性があります。...................................................... コマンド[レット。](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) これらのメソッドからスローされた例外 (Windows PowerShell ホストを停止するいくつかの重大なエラー状態を除く) は、Windows PowerShell 全体ではなく、パイプラインを停止する終了エラーとして解釈されます。 (これは、メインコマンドレットスレッドにのみ適用されます。 一般に、コマンドレットによって生成されるスレッドでキャッチされない例外は、Windows PowerShell ホストを停止します)。エラーレコードには、エンドユーザーに役立つエラー状態に関する追加情報が記載されているので、例外をスローするのではなく、 [Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)を使用することをお勧めします。 コマンドレットは、すべての例外のキャッチと処理 () に対してマネージコードのガイドラインに従う必要があり `catch (Exception e)` ます。 既知の型と予期される型の例外のみをエラーレコードに変換します。

## <a name="see-also"></a>参照

[システムの管理... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[システムの管理... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[システムの管理....................](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[Pipelinestoppedexception (システム管理)](/dotnet/api/System.Management.Automation.PipelineStoppedException)

[Throwterminatingerror * のようになります。](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[WriteError (システム管理)](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell エラー レコード](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
