---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: ネットワーク関連タスクの実行
ms.openlocfilehash: e0aa3b8ef3d911ab0fe851f6621d70e1265c5bd4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737204"
---
# <a name="performing-networking-tasks"></a><span data-ttu-id="4c165-103">ネットワーク関連タスクの実行</span><span class="sxs-lookup"><span data-stu-id="4c165-103">Performing Networking Tasks</span></span>

<span data-ttu-id="4c165-104">TCP/IP は最も一般的に使用されるネットワーク プロトコルです。そのため、TCP/IP に関連したタスクは、最も低レベルのネットワーク プロトコル管理タスクと言えます。</span><span class="sxs-lookup"><span data-stu-id="4c165-104">Because TCP/IP is the most commonly used network protocol, most low-level network protocol administration tasks involve TCP/IP.</span></span> <span data-ttu-id="4c165-105">このセクションでは、PowerShell および WMI を使用して、これらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c165-105">In this section, we use PowerShell and WMI to do these tasks.</span></span>

## <a name="listing-ip-addresses-for-a-computer"></a><span data-ttu-id="4c165-106">コンピューターの IP アドレスの一覧表示</span><span class="sxs-lookup"><span data-stu-id="4c165-106">Listing IP Addresses for a Computer</span></span>

<span data-ttu-id="4c165-107">ローカル コンピューターで使用されているすべての IP アドレスを取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-107">To get all IP addresses in use on the local computer, use the following command:</span></span>

```powershell
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Select-Object -ExpandProperty IPAddress
```

<span data-ttu-id="4c165-108">このコマンドの出力結果を見ると、値が中かっこで囲まれており、他の多くのプロパティの一覧表示結果とは異なることがわかります。</span><span class="sxs-lookup"><span data-stu-id="4c165-108">The output of this command differs from most property lists, because values are enclosed in braces:</span></span>

```Output
10.0.0.1
fe80::60ea:29a7:a233:7cb7
2601:600:a27f:a470:f532:6451:5630:ec8b
2601:600:a27f:a470:e167:477d:6c5c:342d
2601:600:a27f:a470:b021:7f0d:eab9:6299
2601:600:a27f:a470:a40e:ebce:1a8c:a2f3
2601:600:a27f:a470:613c:12a2:e0e0:bd89
2601:600:a27f:a470:444f:17ec:b463:7edd
2601:600:a27f:a470:10fd:7063:28e9:c9f3
2601:600:a27f:a470:60ea:29a7:a233:7cb7
2601:600:a27f:a470::2ec1
```

<span data-ttu-id="4c165-109">中かっこで囲まれている理由を理解するには、`Get-Member` コマンドレットを使用して **IPAddress** プロパティを調べます。</span><span class="sxs-lookup"><span data-stu-id="4c165-109">To understand why the braces appear, use the `Get-Member` cmdlet to examine the **IPAddress** property:</span></span>

```powershell
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Get-Member -Name IPAddress
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_NetworkAdapterConfiguration
Name      MemberType Definition
----      ---------- ----------
IPAddress Property   string[] IPAddress {get;}
```

<span data-ttu-id="4c165-110">各ネットワーク アダプターの IPAddress プロパティは、実際には配列です。</span><span class="sxs-lookup"><span data-stu-id="4c165-110">The IPAddress property for each network adapter is actually an array.</span></span> <span data-ttu-id="4c165-111">Definition 列に示されている中かっこは、**IPAddress** が **System.String** 値ではなく、**System.String** 値の配列であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="4c165-111">The braces in the definition indicate that **IPAddress** is not a **System.String** value, but an array of **System.String** values.</span></span>

## <a name="listing-ip-configuration-data"></a><span data-ttu-id="4c165-112">IP 構成データの一覧表示</span><span class="sxs-lookup"><span data-stu-id="4c165-112">Listing IP Configuration Data</span></span>

<span data-ttu-id="4c165-113">各ネットワーク アダプターの詳しい IP 構成データを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-113">To display detailed IP configuration data for each network adapter, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true
```

<span data-ttu-id="4c165-114">ネットワーク アダプター構成オブジェクトに対して既定で表示される情報は、確認できる情報のごく一部のみです。</span><span class="sxs-lookup"><span data-stu-id="4c165-114">The default display for the network adapter configuration object is a very reduced set of the available information.</span></span> <span data-ttu-id="4c165-115">詳細な調査とトラブルシューティングを行う場合は、`Select-Object` または書式設定用コマンドレット (`Format-List` など) を使用して、表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c165-115">For in-depth inspection and troubleshooting, use `Select-Object` or a formatting cmdlet, such as `Format-List`, to specify the properties to be displayed.</span></span>

<span data-ttu-id="4c165-116">最新の TCP/IP ネットワークでは、IPX や WINS のプロパティには関心がないことが考えられます。</span><span class="sxs-lookup"><span data-stu-id="4c165-116">In modern TCP/IP networks you are probably not interested in IPX or WINS properties.</span></span> <span data-ttu-id="4c165-117">`Select-Object` の **ExcludeProperty** パラメーターを使用して、名前が "WINS" または "IPX" で始まるプロパティを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c165-117">You can use the **ExcludeProperty** parameter of `Select-Object` to hide properties with names that begin with "WINS" or "IPX".</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Select-Object -ExcludeProperty IPX*,WINS*
```

<span data-ttu-id="4c165-118">このコマンドは、DHCP、DNS、ルーティングなど、IP に関連した従属的な構成プロパティについて詳しい情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4c165-118">This command returns detailed information about DHCP, DNS, routing, and other minor IP configuration properties.</span></span>

## <a name="pinging-computers"></a><span data-ttu-id="4c165-119">コンピューターへの ping の送信</span><span class="sxs-lookup"><span data-stu-id="4c165-119">Pinging Computers</span></span>

<span data-ttu-id="4c165-120">**Win32_PingStatus** を使用すると、コンピューターに対して簡単に ping を送信できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-120">You can perform a simple ping against a computer using by **Win32_PingStatus**.</span></span> <span data-ttu-id="4c165-121">次のコマンドは ping を実行しますが、長い出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="4c165-121">The following command performs the ping, but returns lengthy output:</span></span>

```powershell
Get-CimInstance -Class Win32_PingStatus -Filter "Address='127.0.0.1'"
```

<span data-ttu-id="4c165-122">次のコマンドでは、概要を把握しやすくするため、Address、ResponseTime、StatusCode の各プロパティだけを表示しています。</span><span class="sxs-lookup"><span data-stu-id="4c165-122">A more useful form for summary information a display of the Address, ResponseTime, and StatusCode properties, as generated by the following command.</span></span> <span data-ttu-id="4c165-123">`Format-Table` の **Autosize** パラメーターを使用すると、PowerShell で適切に表示されるように表の列のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="4c165-123">The **Autosize** parameter of `Format-Table` resizes the table columns so that they display properly in PowerShell.</span></span>

```powershell
Get-CimInstance -Class Win32_PingStatus -Filter "Address='127.0.0.1'" |
  Format-Table -Property Address,ResponseTime,StatusCode -Autosize
```

```Output
Address   ResponseTime StatusCode
-------   ------------ ----------
127.0.0.1            0          0
```

<span data-ttu-id="4c165-124">StatusCode が 0 の場合、ping が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="4c165-124">A StatusCode of 0 indicates a successful ping.</span></span>

<span data-ttu-id="4c165-125">配列を使用すると、1 つのコマンドで複数のコンピューターに ping を送信できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-125">You can use an array to ping multiple computers with a single command.</span></span> <span data-ttu-id="4c165-126">複数のアドレスが存在するため、`ForEach-Object` を使用して、各アドレスに対して個別に ping を送信します。</span><span class="sxs-lookup"><span data-stu-id="4c165-126">Because there is more than one address, use the `ForEach-Object` to ping each address separately:</span></span>

```powershell
'127.0.0.1','localhost','research.microsoft.com' |
  ForEach-Object -Process {
    Get-CimInstance -Class Win32_PingStatus -Filter ("Address='$_'") |
      Select-Object -Property Address,ResponseTime,StatusCode
  }
```

<span data-ttu-id="4c165-127">同じコマンド形式を使用して、サブネット上のすべてのコンピューターに ping を送信できます。たとえば、ネットワーク番号が 192.168.1.0 で、標準的なクラス C のサブネット マスク (255.255.255.0) を使用しているプライベート ネットワークを調べる場合、実際に調べる必要があるローカル アドレスは 192.168.1.1 ～ 192.168.1.254 の範囲のアドレスだけです (0 および 255 は、それぞれネットワーク番号およびサブネットのブロードキャスト アドレスとして常に予約されています)。</span><span class="sxs-lookup"><span data-stu-id="4c165-127">You can use the same command format to ping all of the computers on a subnet, such as a private network that uses network number 192.168.1.0 and a standard Class C subnet mask (255.255.255.0)., Only addresses in the range of 192.168.1.1 through 192.168.1.254 are legitimate local addresses (0 is always reserved for the network number and 255 is a subnet broadcast address).</span></span>

<span data-ttu-id="4c165-128">PowerShell で 1 から 254 の数値の配列を表現するには、**1..254** というステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-128">To represent an array of the numbers from 1 through 254 in PowerShell, use the statement **1..254.**</span></span>
<span data-ttu-id="4c165-129">まず、この配列を生成した後、それぞれの値を、ping ステートメントのアドレスの一部として使用すると、サブネット全体に対して ping を送信できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-129">A complete subnet ping can be performed by generating the array and then adding the values onto a partial address in the ping statement:</span></span>

```powershell
1..254| ForEach-Object -Process {
  Get-CimInstance -Class Win32_PingStatus -Filter ("Address='192.168.1.$_ '") } |
    Select-Object -Property Address,ResponseTime,StatusCode
```

<span data-ttu-id="4c165-130">このテクニックは、一定範囲のアドレスを生成する場合だけでなく、さまざまな状況で応用できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-130">Note that this technique for generating a range of addresses can be used elsewhere as well.</span></span> <span data-ttu-id="4c165-131">アドレスの完全なセットを生成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4c165-131">You can generate a complete set of addresses in this way:</span></span>

```powershell
$ips = 1..254 | ForEach-Object -Process {'192.168.1.' + $_}
```

## <a name="retrieving-network-adapter-properties"></a><span data-ttu-id="4c165-132">ネットワーク アダプターのプロパティの取得</span><span class="sxs-lookup"><span data-stu-id="4c165-132">Retrieving Network Adapter Properties</span></span>

<span data-ttu-id="4c165-133">前に、**Win32_NetworkAdapterConfiguration** クラスを使用して一般的な構成プロパティを取得できることを説明しました。</span><span class="sxs-lookup"><span data-stu-id="4c165-133">Earlier, we mentioned that you could retrieve general configuration properties using the **Win32_NetworkAdapterConfiguration** class.</span></span> <span data-ttu-id="4c165-134">厳密には TCP/IP 情報とは言えませんが、MAC アドレスやアダプター タイプなどのネットワーク アダプター情報は、コンピューターでどのようなことが起こっているかを把握する上で有益な手段です。</span><span class="sxs-lookup"><span data-stu-id="4c165-134">Although not strictly TCP/IP information, network adapter information such as MAC addresses and adapter types can be useful for understanding what is going on with a computer.</span></span> <span data-ttu-id="4c165-135">この情報の要約を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-135">To get a summary of this information, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapter -ComputerName .
```

## <a name="assigning-the-dns-domain-for-a-network-adapter"></a><span data-ttu-id="4c165-136">ネットワーク アダプターの DNS ドメインの割り当て</span><span class="sxs-lookup"><span data-stu-id="4c165-136">Assigning the DNS Domain for a Network Adapter</span></span>

<span data-ttu-id="4c165-137">自動名前解決のために DNS ドメインを割り当てるには、**Win32_NetworkAdapterConfiguration** の **SetDNSDomain** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-137">To assign the DNS domain for automatic name resolution, use the **SetDNSDomain** method of the **Win32_NetworkAdapterConfiguration**.</span></span> <span data-ttu-id="4c165-138">DNS ドメインは、各ネットワーク アダプター構成に対して別々に割り当てることになります。したがって、`ForEach-Object` ステートメントを使用して、各アダプターにドメインを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c165-138">Because you assign the DNS domain for each network adapter configuration independently, you need to use a `ForEach-Object` statement to assign the domain to each adapter:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  ForEach-Object -Process { $_.SetDNSDomain('fabrikam.com') }
```

<span data-ttu-id="4c165-139">ここでは、フィルター処理ステートメントとして、`IPEnabled=$true` が必要です。その理由は、TCP/IP だけを使用したネットワークでも、コンピューター上のネットワーク アダプター構成のいくつかが、実際には TCP/IP アダプターではないためです。これらは、すべてのアダプターについて RAS、PPTP、QoS などのサービスをサポートする汎用的なソフトウェア要素であるため、自己のアドレスを持ちません。</span><span class="sxs-lookup"><span data-stu-id="4c165-139">The filtering statement `IPEnabled=$true` is necessary, because even on a network that uses only TCP/IP, several of the network adapter configurations on a computer are not true TCP/IP adapters; they are general software elements supporting RAS, PPTP, QoS, and other services for all adapters and thus do not have an address of their own.</span></span>

<span data-ttu-id="4c165-140">`Get-CimInstance` フィルターを使う代わりに、`Where-Object` コマンドレットを使用して、コマンドをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c165-140">You can filter the command by using the `Where-Object` cmdlet, instead of using the `Get-CimInstance` filter.</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration |
  Where-Object {$_.IPEnabled} |
    ForEach-Object -Process {$_.SetDNSDomain('fabrikam.com')}
```

## <a name="performing-dhcp-configuration-tasks"></a><span data-ttu-id="4c165-141">DHCP の構成タスクの実行</span><span class="sxs-lookup"><span data-stu-id="4c165-141">Performing DHCP Configuration Tasks</span></span>

<span data-ttu-id="4c165-142">DNS の構成と同様、DHCP 情報の変更には、一連のネットワーク アダプターに対する操作が伴います。</span><span class="sxs-lookup"><span data-stu-id="4c165-142">Modifying DHCP details involves working with a set of network adapters, just as the DNS configuration does.</span></span> <span data-ttu-id="4c165-143">WMI で実行できる操作はさまざまですが、ここでは、その中でも一般的なものをいくつか選んで説明します。</span><span class="sxs-lookup"><span data-stu-id="4c165-143">There are several distinct actions you can perform by using WMI, and we will step through a few of the common ones.</span></span>

### <a name="determining-dhcp-enabled-adapters"></a><span data-ttu-id="4c165-144">DHCP 対応アダプターの特定</span><span class="sxs-lookup"><span data-stu-id="4c165-144">Determining DHCP-Enabled Adapters</span></span>

<span data-ttu-id="4c165-145">コンピューター上の DHCP 対応アダプターを検索するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-145">To find the DHCP-enabled adapters on a computer, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=$true"
```

<span data-ttu-id="4c165-146">IP 構成の問題があるアダプターを除外するために、IP 対応アダプターだけを検索できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-146">To exclude adapters with IP configuration problems, you can retrieve only IP-enabled adapters:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true"
```

### <a name="retrieving-dhcp-properties"></a><span data-ttu-id="4c165-147">DHCP のプロパティの取得</span><span class="sxs-lookup"><span data-stu-id="4c165-147">Retrieving DHCP Properties</span></span>

<span data-ttu-id="4c165-148">通常、アダプターの DHCP 関連のプロパティは先頭に `DHCP` が付くため、`Format-Table` の Property パラメーターを使用することで、それらのプロパティだけを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-148">Because DHCP-related properties for an adapter generally begin with `DHCP`, you can use the Property parameter of `Format-Table` to display only those properties:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=$true" |
  Format-Table -Property DHCP*
```

### <a name="enabling-dhcp-on-each-adapter"></a><span data-ttu-id="4c165-149">各アダプターの DHCP の有効化</span><span class="sxs-lookup"><span data-stu-id="4c165-149">Enabling DHCP on Each Adapter</span></span>

<span data-ttu-id="4c165-150">すべてのアダプターで DHCP を有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-150">To enable DHCP on all adapters, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  ForEach-Object -Process {$_.EnableDHCP()}
```

<span data-ttu-id="4c165-151">既に有効化されている DHCP は除外するために、**Filter** ステートメントとして `IPEnabled=$true and DHCPEnabled=$false` を使用できます。ただし、この手順を省略しても、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="4c165-151">You can use the **Filter** statement `IPEnabled=$true and DHCPEnabled=$false` to avoid enabling DHCP where it is already enabled, but omitting this step will not cause errors.</span></span>

### <a name="releasing-and-renewing-dhcp-leases-on-specific-adapters"></a><span data-ttu-id="4c165-152">特定のアダプターの DHCP リースの解放および更新</span><span class="sxs-lookup"><span data-stu-id="4c165-152">Releasing and Renewing DHCP Leases on Specific Adapters</span></span>

<span data-ttu-id="4c165-153">**Win32_NetworkAdapterConfiguration** クラスには **ReleaseDHCPLease** メソッドと **RenewDHCPLease** メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="4c165-153">The **Win32_NetworkAdapterConfiguration** class has **ReleaseDHCPLease** and **RenewDHCPLease** methods.</span></span> <span data-ttu-id="4c165-154">使用方法はどちらも同じです。</span><span class="sxs-lookup"><span data-stu-id="4c165-154">Both are used in the same way.</span></span> <span data-ttu-id="4c165-155">通常、これらのメソッドを使用するのは、特定のサブネット上に存在するアダプターのアドレスを解放または更新する必要がある場合だけです。</span><span class="sxs-lookup"><span data-stu-id="4c165-155">In general, use these methods if you only need to release or renew addresses for an adapter on a specific subnet.</span></span> <span data-ttu-id="4c165-156">サブネット上のアダプターをフィルター処理する最も簡単な方法は、対応するサブネットのゲートウェイを使用したアダプター構成だけを選ぶことです。</span><span class="sxs-lookup"><span data-stu-id="4c165-156">The easiest way to filter adapters on a subnet is to choose only the adapter configurations that use the gateway for that subnet.</span></span> <span data-ttu-id="4c165-157">たとえば、次のコマンドでは、DHCP リースを 192.168.1.254 から取得しているローカル コンピューターについて、アダプターの DHCP リースがすべて解放されます。</span><span class="sxs-lookup"><span data-stu-id="4c165-157">For example, the following command releases all DHCP leases on adapters on the local computer that are obtaining DHCP leases from 192.168.1.254:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true" |
  Where-Object {$_.DHCPServer -contains '192.168.1.254'} |
    ForEach-Object -Process {$_.ReleaseDHCPLease()}
```

<span data-ttu-id="4c165-158">DHCP リースを更新する場合は、**ReleaseDHCPLease** メソッドの代わりに **RenewDHCPLease** メソッドを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="4c165-158">The only change for renewing a DHCP lease is to use the **RenewDHCPLease** method instead of the **ReleaseDHCPLease** method:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true" |
  Where-Object {$_.DHCPServer -contains '192.168.1.254'} |
    ForEach-Object -Process {$_.ReleaseDHCPLease()}
```

> [!NOTE]
> <span data-ttu-id="4c165-159">これらのメソッドをリモート コンピューターに対して使用する場合は、接続に使用されているアダプターのリースが解放または更新されると、リモート システムへのアクセスが失われる可能性があることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4c165-159">When using these methods on a remote computer, be aware that you can lose access to the remote system if you are connected to it through the adapter with the released or renewed lease.</span></span>

### <a name="releasing-and-renewing-dhcp-leases-on-all-adapters"></a><span data-ttu-id="4c165-160">すべてのアダプターの DHCP リースの解放および更新</span><span class="sxs-lookup"><span data-stu-id="4c165-160">Releasing and Renewing DHCP Leases on All Adapters</span></span>

<span data-ttu-id="4c165-161">**Win32_NetworkAdapterConfiguration** の **ReleaseDHCPLeaseAll** メソッドと **RenewDHCPLeaseAll** メソッドを使用すれば、すべてのアダプターを対象に DHCP アドレスをグローバルに解放または更新できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-161">You can perform global DHCP address releases or renewals on all adapters by using the **Win32_NetworkAdapterConfiguration** methods, **ReleaseDHCPLeaseAll** and **RenewDHCPLeaseAll**.</span></span>
<span data-ttu-id="4c165-162">ただし、リースの解放と更新をグローバルに実行する場合、実行の対象は、特定のアダプターではなく、WMI クラスになります。したがって、コマンドは特定のアダプターに適用するのではなく、WMI クラスに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c165-162">However, the command must apply to the WMI class, rather than a particular adapter, because releasing and renewing leases globally is performed on the class, not on a specific adapter.</span></span>

<span data-ttu-id="4c165-163">すべての WMI クラスを一覧表示して、目的のクラスだけを名前で選べば、特定の WMI クラスの参照 (クラスのインスタンスではない) を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4c165-163">You can get a reference to a WMI class, instead of class instances, by listing all WMI classes and then selecting only the desired class by name.</span></span> <span data-ttu-id="4c165-164">たとえば、**Win32_NetworkAdapterConfiguration** クラスを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c165-164">For example, the following command returns the **Win32_NetworkAdapterConfiguration** class:</span></span>

```powershell
Get-CimInstance -List | Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}
```

<span data-ttu-id="4c165-165">コマンド全体をクラスとして扱い、その **ReleaseDHCPAdapterLease** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4c165-165">You can treat the entire command as the class and then invoke the **ReleaseDHCPAdapterLease** method on it.</span></span> <span data-ttu-id="4c165-166">次のコマンドでは、パイプライン要素 `Get-CimInstance` および `Where-Object` を丸かっこで囲むことにより、それらを最初に評価するように PowerShell に指示しています。</span><span class="sxs-lookup"><span data-stu-id="4c165-166">In the following command, the parentheses surrounding the `Get-CimInstance` and `Where-Object` pipeline elements direct PowerShell to evaluate them first:</span></span>

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}).ReleaseDHCPLeaseAll()
```

<span data-ttu-id="4c165-167">**RenewDHCPLeaseAll** メソッドも、同じコマンド形式で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4c165-167">You can use the same command format to invoke the **RenewDHCPLeaseAll** method:</span></span>

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}).RenewDHCPLeaseAll()
```

## <a name="creating-a-network-share"></a><span data-ttu-id="4c165-168">ネットワーク共有の作成</span><span class="sxs-lookup"><span data-stu-id="4c165-168">Creating a Network Share</span></span>

<span data-ttu-id="4c165-169">ネットワーク共有を作成するには、**Win32_Share** の **Create** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-169">To create a network share, use the **Create** method of **Win32_Share**:</span></span>

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_Share'}).Create(
    'C:\temp','TempShare',0,25,'test share of the temp folder'
  )
```

<span data-ttu-id="4c165-170">Windows では PowerShell の `net share` を使用して、共有を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c165-170">You can also create the share by using `net share` in PowerShell on Windows:</span></span>

```powershell
net share tempshare=c:\temp /users:25 /remark:"test share of the temp folder"
```

## <a name="removing-a-network-share"></a><span data-ttu-id="4c165-171">ネットワーク共有の削除</span><span class="sxs-lookup"><span data-stu-id="4c165-171">Removing a Network Share</span></span>

<span data-ttu-id="4c165-172">ネットワーク共有を削除する場合も **Win32_Share** を使用できます。ただし、そのプロセスは共有を作成する場合と若干異なります。共有を作成する場合は、フィルターで **Win32_Share** クラスを取得していました。これに対し、共有を削除する場合は、削除対象となる特定の共有を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c165-172">You can remove a network share with **Win32_Share**, but the process is slightly different from creating a share, because you need to retrieve the specific share to be removed, rather than the **Win32_Share** class.</span></span> <span data-ttu-id="4c165-173">次のステートメントでは、**TempShare** という共有を削除します。</span><span class="sxs-lookup"><span data-stu-id="4c165-173">The following statement deletes the share **TempShare**:</span></span>

```powershell
(Get-CimInstance -Class Win32_Share -Filter "Name='TempShare'").Delete()
```

<span data-ttu-id="4c165-174">Windows では、`net share` も同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="4c165-174">In Windows, `net share` works as well:</span></span>

```powershell
net share tempshare /delete
```

```Output
tempshare was deleted successfully.
```

## <a name="connecting-a-windows-accessible-network-drive"></a><span data-ttu-id="4c165-175">Windows でアクセス可能なネットワーク ドライブの接続</span><span class="sxs-lookup"><span data-stu-id="4c165-175">Connecting a Windows Accessible Network Drive</span></span>

<span data-ttu-id="4c165-176">`New-PSDrive` コマンドレットを使用すると、PowerShell ドライブを作成できます。しかし、この方法で作成されたドライブは、PowerShell でしかアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4c165-176">The `New-PSDrive` cmdlets creates a PowerShell drive, but drives created this way are available only to PowerShell.</span></span> <span data-ttu-id="4c165-177">新しいネットワーク ドライブを作成するには、**WScript.Network** という COM オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c165-177">To create a new networked drive, you can use the **WScript.Network** COM object.</span></span> <span data-ttu-id="4c165-178">次のコマンドは、共有 `\\FPS01\users` をローカルの `B:` ドライブにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="4c165-178">The following command maps the share `\\FPS01\users` to local drive `B:`,</span></span>

```powershell
(New-Object -ComObject WScript.Network).MapNetworkDrive('B:', '\\FPS01\users')
```

<span data-ttu-id="4c165-179">Windows では、`net use` コマンドでも同じことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c165-179">On Windows, the `net use` command works as well:</span></span>

```powershell
net use B: \\FPS01\users
```

<span data-ttu-id="4c165-180">**WScript.Network** または `net use` でマッピングされたドライブは、PowerShell から直ちにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4c165-180">Drives mapped with either **WScript.Network** or `net use` are immediately available to PowerShell.</span></span>
