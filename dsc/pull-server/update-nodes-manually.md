---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーからのノードを更新する
ms.openlocfilehash: 4333a5bf82ef45f22a062942ebe93409433623f5
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402150"
---
# <a name="update-nodes-from-a-pull-server"></a>プル サーバーからのノードを更新する

以下のセクションでは、プル サーバーを既に設定したことを前提としています。 プル サーバーを設定していない場合は、次のガイドを使用できます。

- [DSC SMB プル サーバーを設定する](pullServerSmb.md)
- [DSC HTTP プル サーバーを設定する](pullServer.md)

各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。 この記事では、ダウンロード、およびリソースを自動的にダウンロードするクライアントの構成に利用できるように、リソースをアップロードする方法を示します。 ノードがを通じて割り当てられた構成を受信すると**プル**または**プッシュ**(v5) では、自動的にダウンロードし、LCM で指定された場所からの構成に必要なすべてのリソース。

## <a name="using-the-update-dscconfiguration-cmdlet"></a>Update-dscconfiguration コマンドレットを使用してください。

PowerShell 5.0 以降、 [Update-dscconfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration)コマンドレット、LCM の構成をプル サーバーからその構成を更新するノードを強制的にします。

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a>呼び出す CIMMethod を使用します。

PowerShell 4.0 では、プル クライアントを使用してその構成を更新する手動で強制できます[Invoke-cimmethod](/powershell/module/cimcmdlets/invoke-cimmethod)します。 次の例では、指定した資格情報で CIM セッションを作成するが適切な CIM メソッドを呼び出すおよびセッションを削除します。

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a>参照

[PerformRequiredConfigurationChecks](/powershell/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)
