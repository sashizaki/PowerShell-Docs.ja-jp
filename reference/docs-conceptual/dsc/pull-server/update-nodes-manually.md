---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーからのノードを更新する
ms.openlocfilehash: fa59a2f6574db2dbc96621be4326f1d5a55e5de9
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500675"
---
# <a name="update-nodes-from-a-pull-server"></a>プル サーバーからのノードを更新する

以下のセクションでは、プル サーバーを既にセットアップしてあるものとします。 プル サーバーをセットアップしていない場合は、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。 この記事では、ダウンロードできるようにリソースをアップロードする方法、およびリソースを自動的にダウンロードするようにクライアントを構成する方法を示します。 ノードは、割り当てられた構成を**プル**または**プッシュ** (v5) によって受け取ると、構成で必要なすべてのリソースを LCM で指定された場所から自動的にダウンロードします。

## <a name="using-the-update-dscconfiguration-cmdlet"></a>Update-DSCConfiguration コマンドレットの使用

PowerShell 5.0 以降では、[Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) コマンドレットによって、LCM で構成されているプル サーバーからノードの構成が強制的に更新されます。

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a>Invoke-CIMMethod の使用

PowerShell 4.0 ではまだ、[Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod) を使用して手動で強制的にプル クライアントの構成を更新できます。 次の例では、指定した資格情報で CIM セッションを作成し、適切な CIM メソッドを呼び出して、セッションを削除します。

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a>参照

[PerformRequiredConfigurationChecks](../reference/mof-classes/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)
