---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 2b6b81d250c3d745f3ab21ebadb9a657583638b0
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="network-switch-management-with-powershell"></a>PowerShell を使用したネットワーク スイッチの管理

**Get-NetworkSwitchEthernetPort** コマンドレットはインスタンスで次の追加情報を返します。

- IPAddress: ポートに関連付けられた IP アドレス
- PortMode: ポートのモード: アクセス、ルート、またはトランク
- AccessVLAN: アクセス モードでこのポートに関連付けられた VLAN の ID
- TrunkedVLANList: トランク モードでこのポートに関連付けられた VLAN の ID 一覧

## <a name="fundamental-network-switch-management-with-windows-powershell"></a>Windows PowerShell を使用した基本的なネットワーク スイッチの管理

WMF 5.0 で導入されたネットワーク スイッチのコマンドレットを使用すると、Windows Server 2012 R2 ロゴ認定を受けたネットワーク スイッチに、スイッチ、仮想 LAN (VLAN)、および基本的なレイヤー 2 ネットワーク スイッチ ポートの構成を適用することができます。 Microsoft では、[データセンター アブストラクション](http://technet.microsoft.com/cloud/dal.aspx) レイヤー (DAL) のビジョンをサポートし、この領域において顧客とパートナーにもたらされる価値を示すことに努めています。 これらのコマンドレットを使用して、次のことを実行できます。

- 次のようなグローバル スイッチ構成:
    - ホスト名の設定
    - スイッチ バナーの設定
    - 構成の保持
    - 機能の有効化または無効化

- VLAN 構成:
    - VLAN の作成または削除
    - VLAN の有効化または無効化
    - VLAN の列挙
    - VLAN にわかりやすい名前を設定する

- レイヤー 2 ポート構成:
    - ポートの列挙
    - ポートの有効化または無効化
    - ポートのモードおよびプロパティの設定
    - ポートのトランクまたはアクセスに VLAN を追加または関連付ける

すべての NetworkSwitch コマンドレットを探すことで調査を開始します。

```powershell
PS> Get-Command *-NetworkSwitch*

| CommandType | Name                                      | Source        |
|-------------|-------------------------------------------|---------------|
|             |                                           |               |
| Function    | Disable-NetworkSwitchEthernetPort         | NetworkSwitch |
| Function    | Disable-NetworkSwitchFeature              | NetworkSwitch |
| Function    | Disable-NetworkSwitchVlan                 | NetworkSwitch |
| Function    | Enable-NetworkSwitchEthernetPort          | NetworkSwitch |
| Function    | Enable-NetworkSwitchFeature               | NetworkSwitch |
| Function    | Enable-NetworkSwitchVlan                  | NetworkSwitch |
| Function    | Get-NetworkSwitchEthernetPort             | NetworkSwitch |
| Function    | Get-NetworkSwitchFeature                  | NetworkSwitch |
| Function    | Get-NetworkSwitchGlobalData               | NetworkSwitch |
| Function    | Get-NetworkSwitchVlan                     | NetworkSwitch |
| Function    | New-NetworkSwitchVlan                     | NetworkSwitch |
| Function    | Remove-NetworkSwitchEthernetPortIPAddress | NetworkSwitch |
| Function    | Remove-NetworkSwitchVlan                  | NetworkSwitch |
| Function    | Restore-NetworkSwitchConfiguration        | NetworkSwitch |
| Function    | Save-NetworkSwitchConfiguration           | NetworkSwitch |
| Function    | Set-NetworkSwitchEthernetPortIPAddress    | NetworkSwitch |
| Function    | Set-NetworkSwitchPortMode                 | NetworkSwitch |
| Function    | Set-NetworkSwitchPortProperty             | NetworkSwitch |
| Function    | Set-NetworkSwitchVlanProperty             | NetworkSwitch |
```

詳細については、Jeffrey Snover の WMF 5.0 Preview に関するお知らせのブログ投稿 (<http://blogs.technet.com/b/windowsserver/archive/2014/04/03/windows-management-framework-v5-preview.aspx>) を参照してください。