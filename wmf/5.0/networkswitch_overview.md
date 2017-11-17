---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 80852bf750700d549de24e150ffd89ac55b7bf88
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="network-switch-management-with-powershell"></a><span data-ttu-id="fe334-102">PowerShell を使用したネットワーク スイッチの管理</span><span class="sxs-lookup"><span data-stu-id="fe334-102">Network Switch Management with PowerShell</span></span>

<span data-ttu-id="fe334-103">**Get-NetworkSwitchEthernetPort** コマンドレットはインスタンスで次の追加情報を返します。</span><span class="sxs-lookup"><span data-stu-id="fe334-103">The **Get-NetworkSwitchEthernetPort** cmdlet now returns the following additional information with instances:</span></span>

- <span data-ttu-id="fe334-104">IPAddress: ポートに関連付けられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="fe334-104">IPAddress – the IP address associated with the port</span></span>
- <span data-ttu-id="fe334-105">PortMode: ポートのモード: アクセス、ルート、またはトランク</span><span class="sxs-lookup"><span data-stu-id="fe334-105">PortMode – the port mode: access, route, or trunk</span></span>
- <span data-ttu-id="fe334-106">AccessVLAN: アクセス モードでこのポートに関連付けられた VLAN の ID</span><span class="sxs-lookup"><span data-stu-id="fe334-106">AccessVLAN – the ID of the VLAN associated with this port in access mode</span></span>
- <span data-ttu-id="fe334-107">TrunkedVLANList: トランク モードでこのポートに関連付けられた VLAN の ID 一覧</span><span class="sxs-lookup"><span data-stu-id="fe334-107">TrunkedVLANList – a list of IDs of VLANs associated with this port in trunk mode</span></span>

## <a name="fundamental-network-switch-management-with-windows-powershell"></a><span data-ttu-id="fe334-108">Windows PowerShell を使用した基本的なネットワーク スイッチの管理</span><span class="sxs-lookup"><span data-stu-id="fe334-108">Fundamental network switch management with Windows PowerShell</span></span>

<span data-ttu-id="fe334-109">WMF 5.0 で導入されたネットワーク スイッチのコマンドレットを使用すると、Windows Server 2012 R2 ロゴ認定を受けたネットワーク スイッチに、スイッチ、仮想 LAN (VLAN)、および基本的なレイヤー 2 ネットワーク スイッチ ポートの構成を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="fe334-109">The Network Switch cmdlets, introduced in WMF 5.0, enable you to apply switch, virtual LAN (VLAN), and basic Layer 2 network switch port configuration to Windows Server 2012 R2 logo-certified network switches.</span></span> <span data-ttu-id="fe334-110">Microsoft では、[データセンター アブストラクション](http://technet.microsoft.com/en-us/cloud/dal.aspx) レイヤー (DAL) のビジョンをサポートし、この領域において顧客とパートナーにもたらされる価値を示すことに努めています。</span><span class="sxs-lookup"><span data-stu-id="fe334-110">Microsoft remains committed to supporting the [Datacenter Abstraction](http://technet.microsoft.com/en-us/cloud/dal.aspx) Layer (DAL) vision, and to show value for our customers and partners in this space.</span></span> <span data-ttu-id="fe334-111">これらのコマンドレットを使用して、次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe334-111">Using these cmdlets you can perform:</span></span>

- <span data-ttu-id="fe334-112">次のようなグローバル スイッチ構成:</span><span class="sxs-lookup"><span data-stu-id="fe334-112">Global switch configuration, such as:</span></span>
    - <span data-ttu-id="fe334-113">ホスト名の設定</span><span class="sxs-lookup"><span data-stu-id="fe334-113">Set host name</span></span>
    - <span data-ttu-id="fe334-114">スイッチ バナーの設定</span><span class="sxs-lookup"><span data-stu-id="fe334-114">Set switch banner</span></span>
    - <span data-ttu-id="fe334-115">構成の保持</span><span class="sxs-lookup"><span data-stu-id="fe334-115">Persist configuration</span></span>
    - <span data-ttu-id="fe334-116">機能の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="fe334-116">Enable or disable feature</span></span>

- <span data-ttu-id="fe334-117">VLAN 構成:</span><span class="sxs-lookup"><span data-stu-id="fe334-117">VLAN configuration:</span></span>
    - <span data-ttu-id="fe334-118">VLAN の作成または削除</span><span class="sxs-lookup"><span data-stu-id="fe334-118">Create or remove VLAN</span></span>
    - <span data-ttu-id="fe334-119">VLAN の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="fe334-119">Enable or disable VLAN</span></span>
    - <span data-ttu-id="fe334-120">VLAN の列挙</span><span class="sxs-lookup"><span data-stu-id="fe334-120">Enumerate VLAN</span></span>
    - <span data-ttu-id="fe334-121">VLAN にわかりやすい名前を設定する</span><span class="sxs-lookup"><span data-stu-id="fe334-121">Set friendly name to a VLAN</span></span>

- <span data-ttu-id="fe334-122">レイヤー 2 ポート構成:</span><span class="sxs-lookup"><span data-stu-id="fe334-122">Layer 2 port configuration:</span></span>
    - <span data-ttu-id="fe334-123">ポートの列挙</span><span class="sxs-lookup"><span data-stu-id="fe334-123">Enumerate ports</span></span>
    - <span data-ttu-id="fe334-124">ポートの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="fe334-124">Enable or disable ports</span></span>
    - <span data-ttu-id="fe334-125">ポートのモードおよびプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="fe334-125">Set port modes and properties</span></span>
    - <span data-ttu-id="fe334-126">ポートのトランクまたはアクセスに VLAN を追加または関連付ける</span><span class="sxs-lookup"><span data-stu-id="fe334-126">Add or associate VLAN to Trunk or Access on the port</span></span>

<span data-ttu-id="fe334-127">すべての NetworkSwitch コマンドレットを探すことで調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="fe334-127">Start exploring by looking for all of the NetworkSwitch cmdlets!</span></span>

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

<span data-ttu-id="fe334-128">詳細については、Jeffrey Snover の WMF 5.0 Preview について通知するブログ投稿 (<http://blogs.technet.com/b/windowsserver/archive/2014/04/03/windows-management-framework-v5-preview.aspx>) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe334-128">More information is available in Jeffrey Snover’s WMF 5.0 Preview announcement blog post: <http://blogs.technet.com/b/windowsserver/archive/2014/04/03/windows-management-framework-v5-preview.aspx></span></span>

