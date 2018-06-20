---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 の既知の問題
ms.openlocfilehash: d53031bea978087c68fcb22989c7cd2e2cf2d9fa
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219455"
---
# <a name="known-issues-in-wmf-51"></a>WMF 5.1 の既知の問題 #

> 注意: この情報は変更されることがあります。

## <a name="starting-powershell-shortcut-as-administrator"></a>PowerShell ショートカットを管理者として起動する
WMF がインストールされている場合に、管理者としてショートカットから PowerShell を起動しようとすると、"未定義のエラー" メッセージが表示されることがあります。
管理者以外でショートカットを開き直すと、その後は管理者としても動作します。

## <a name="pester"></a>Pester
このリリースでは、Nano Server で Pester を利用するとき、2 つの問題に注意する必要があります。

* Pester 自体にテストを実行すると、FULL CLR と CORE CLR の違いに起因し、エラーが発生します。 具体的には、Validate メソッドが XmlDocument 型で利用できません。 NUnit 出力ログのスキーマの検証を試行するテストが 6 つありますが、これでエラーが発生することが確認されています。
* 現在、コード カバレッジの 1 つでエラーが発生します。*WindowsFeature* DSC リソースが Nano Server にないためです。 しかしながら、以上のエラーは一般的に無害であり、無視しても問題ありません。

## <a name="operation-validation"></a>操作検証

* Microsoft.PowerShell.Operation.Validation モジュールの場合、ヘルプ URI が動作しないため、Update-Help は失敗する

## <a name="dsc-after-uninstall-wmf"></a>WMF をアンインストールした後の DSC
* WMF をアンインストールしても、構成フォルダーから DSC の MOF ドキュメントは削除されません。 MOF ドキュメントに、以前のシステムで使用できない新しいプロパティが含まれている場合、DSC は正しく機能しません。 この場合は、管理者特権の PowerShell コンソールから次のスクリプトを実行して、DSC の状態をクリーンアップします。
 ```powershell
    $PreviousDSCStates = @("$env:windir\system32\configuration\*.mof",
            "$env:windir\system32\configuration\*.mof.checksum",
            "$env:windir\system32\configuration\PartialConfiguration\*.mof",
            "$env:windir\system32\configuration\PartialConfiguration\*.mof.checksum"
           )

    $PreviousDSCStates | Remove-Item -ErrorAction SilentlyContinue -Verbose
 ```

## <a name="jea-virtual-accounts"></a>JEA 仮想アカウント
WMF 5.0 で仮想アカウントを使用するように構成された JEA エンドポイントおよびセッション構成は、WMF 5.1 へのアップグレード後に仮想アカウントを使用するように構成されません。
これは、JEA セッションで実行されるコマンドは一時管理者アカウントではなく接続しているユーザーの ID で実行されるため、昇格された特権を必要とするコマンドをユーザーが実行できない可能性があることを意味します。
仮想アカウントを復元するには、仮想アカウントを使用するすべてのセッション構成を登録解除し、再登録する必要があります。

```powershell
# Find the JEA endpoint by its name
$jea = Get-PSSessionConfiguration -Name MyJeaEndpoint

# Copy the cached PSSC file so it can be re-registered
$pssc = Copy-Item $jea.ConfigFilePath $env:temp -PassThru

# Unregister the current PSSC
Unregister-PSSessionConfiguration -Name $jea.Name

# Re-register the PSSC
Register-PSSessionConfiguration -Name $jea.Name -Path $pssc.FullName -Force

# Ensure the access policies remain the same
Set-PSSessionConfiguration -Name $newjea.Name -SecurityDescriptorSddl $jea.SecurityDescriptorSddl
```
