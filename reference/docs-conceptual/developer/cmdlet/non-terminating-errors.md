---
title: 終了しないエラー |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d74c248e6ef54151400b8060d76524e89d87352c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786562"
---
# <a name="non-terminating-errors"></a>終了しないエラー

このトピックでは、終了しないエラーの報告に使用する方法について説明します。 また、コマンドレット内からメソッドを呼び出す方法についても説明します。

終了しないエラーが発生した場合、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出してこのエラーを報告する必要があります。 コマンドレットが終了しないエラーを報告した場合、コマンドレットはこの入力オブジェクトおよびさらに受信パイプラインオブジェクトに対して引き続き操作できます。 コマンドレットで[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出すと、コマンドレットは、終了しないエラーの原因となった状態を説明するエラーレコードを書き込むことができます。 エラーレコードの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。

コマンドレットは、入力処理メソッド内から必要に応じて[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができます。 ただし、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができます。このために[は、コマンド](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)[レットを呼び出し](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)たスレッド[、または system.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) ................................... コマンドレットを実行します。 別のスレッドから[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出さないでください。 代わりに、エラーをメインスレッドに送り返します。

## <a name="see-also"></a>参照

[WriteError (システム管理)](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[システムの管理... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[システムの管理....................](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[システムの管理... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Windows PowerShell エラー レコード](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
