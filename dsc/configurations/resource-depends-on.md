---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DependsOn を使用したリソースの依存関係
ms.openlocfilehash: 0d060f7d99bd261b0766028b245d4d32a5e1c349
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402493"
---
# <a name="resource-dependencies-using-dependson"></a><span data-ttu-id="fcd40-103">DependsOn を使用したリソースの依存関係</span><span class="sxs-lookup"><span data-stu-id="fcd40-103">Resource dependencies using DependsOn</span></span>

<span data-ttu-id="fcd40-104">記述するとき[構成](configurations.md)、追加する[リソース ブロック](../resources/resources.md)ターゲット ノードの機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="fcd40-104">When you write [Configurations](configurations.md), you add [Resource blocks](../resources/resources.md) to configure aspects of a target Node.</span></span> <span data-ttu-id="fcd40-105">リソース ブロックの追加を続行すると、構成は非常に大規模な管理する煩雑に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-105">As you continue to add Resource blocks, your Configurations can grow quite large and cumbersome to manage.</span></span> <span data-ttu-id="fcd40-106">このような課題の 1 つは、リソース、ブロックの適用順序です。</span><span class="sxs-lookup"><span data-stu-id="fcd40-106">One such challenge is the applied order of your resource blocks.</span></span> <span data-ttu-id="fcd40-107">通常のリソースは、構成内で定義されている順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-107">Typically resources are applied in the order they are defined within the Configuration.</span></span> <span data-ttu-id="fcd40-108">使用することができます、構成大きく拡大し複雑、`DependsOn`キーを指定することで、リソースが別のリソースに依存するリソースの適用順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="fcd40-108">As your Configuration grows larger and more complex, you can use the `DependsOn` key to change the applied order of your resources by specifying that a resource depends on another resource.</span></span>

<span data-ttu-id="fcd40-109">`DependsOn`キーは、任意のリソース ブロックで使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-109">The `DependsOn` key can be used in any Resource block.</span></span> <span data-ttu-id="fcd40-110">これは、他のリソース キーと同じキー/値機構で定義されます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-110">It is defined with the same key/value mechanism as other Resource keys.</span></span> <span data-ttu-id="fcd40-111">`DependsOn`キーが次の構文で文字列の配列が必要です。</span><span class="sxs-lookup"><span data-stu-id="fcd40-111">The `DependsOn` key expects an array of strings with the following syntax.</span></span>

```
DependsOn = '[<Resource Type>]<Resoure Name>', '[<Resource Type>]<Resource Name'
```

<span data-ttu-id="fcd40-112">次の例を有効にすると、パブリック プロファイルを構成するファイアウォール規則を構成します。</span><span class="sxs-lookup"><span data-stu-id="fcd40-112">The following example configures a firewall rule after enabling and configuring the public profile.</span></span>

```powershell
# Install the NetworkingDSC module to configure firewall rules and profiles.
Install-Module -Name NetworkingDSC

Configuration ConfigureFirewall
{
    Import-DSCResource -Name Firewall, FirewallProfile
    Node localhost
    {
        Firewall Firewall
        {
            Name                  = 'IIS-WebServerRole-HTTP-In-TCP'
            Ensure                = 'Present'
            Enabled               = 'True'
            DependsOn             = '[FirewallProfile]FirewallProfilePublic'
        }

        FirewallProfile FirewallProfilePublic
        {
            Name = 'Public'
            Enabled = 'True'
            DefaultInboundAction = 'Block'
            DefaultOutboundAction = 'Allow'
            AllowInboundRules = 'True'
            AllowLocalFirewallRules = 'False'
            AllowLocalIPsecRules = 'False'
            NotifyOnListen = 'True'
            LogFileName = '%systemroot%\system32\LogFiles\Firewall\pfirewall.log'
            LogMaxSizeKilobytes = 16384
            LogAllowed = 'False'
            LogBlocked = 'True'
            LogIgnored = 'NotConfigured'
        }
    }
}

ConfigureFirewall -OutputPath C:\Temp\
```

<span data-ttu-id="fcd40-113">構成を適用するときに、順序に関係なく最初に、リソース要素が定義されて、ファイアウォール プロファイル常に構成するされます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-113">When you apply the Configuration, the firewall profile will always be configured first regardless of which order the Resource blocks are defined.</span></span> <span data-ttu-id="fcd40-114">構成を適用すると、必ず既存の構成が必要な場合に戻すことができますので、ターゲット ノードに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcd40-114">If you apply the Configuration, be sure to note your target Nodes existing Configuration so you can revert if desired.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -Path C:\Temp\ -ComputerName localhost

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid S-1-5-21-181338-0189125723-1543119021-1282804.
VERBOSE: [SERVER01]: LCM:  [ Start  Set      ]
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module C:\Program Files\WindowsPowerShell\Modules\NetworkingDsc\6.1.0.0\DscResources\MSFT_Firewall\MSFT_Firewall.psm1 in force mode.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module C:\Program Files\WindowsPowerShell\Modules\NetworkingDsc\6.1.0.0\DscResources\MSFT_FirewallProfile\MSFT_FirewallProfile.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Importing the module MSFT_FirewallProfile in force mode.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Testing Firewall Public Profile.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "AllowInboundRules" is "NotConfigured" but should be "True". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "AllowLocalFirewallRules" is "NotConfigured" but should be "False". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "AllowLocalIPsecRules" is "NotConfigured" but should be "False". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "DefaultOutboundAction" is "NotConfigured" but should be "Allow". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "LogBlocked" is "False" but should be "True". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "LogMaxSizeKilobytes" is "4096" but should be "16384". Change required.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[FirewallProfile]FirewallProfilePublic]  in 1.6890 seconds.
VERBOSE: [SERVER01]: LCM:  [ Start  Set      ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Importing the module MSFT_FirewallProfile in force mode.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter AllowInboundRules to "AllowInboundRules".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter AllowLocalFirewallRules to "AllowLocalFirewallRules".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter AllowLocalIPsecRules to "AllowLocalIPsecRules".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter DefaultOutboundAction to "DefaultOutboundAction".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter LogBlocked to "LogBlocked".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter LogMaxSizeKilobytes to "LogMaxSizeKilobytes".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile updated.
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]  [[FirewallProfile]FirewallProfilePublic]  in 10.0360 seconds.
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Importing the module MSFT_Firewall in force mode.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Checking settings for firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Find firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Get-FirewallRule: No Firewall Rule found with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' does not exist.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Check Firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' returning False.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Firewall]Firewall]  in 1.1780 seconds.
VERBOSE: [SERVER01]: LCM:  [ Start  Set      ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Importing the module MSFT_Firewall in force mode.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: Applying settings for firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: Find firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Get-FirewallRule: No Firewall Rule found with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: We want the firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' to exist since Ensure is set to Present.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: We want the firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' to exist, but it does not.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] New-NetFirewallRule DisplayName: IIS-WebServerRole-HTTP-In-TCP
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]  [[Firewall]Firewall]  in 1.0850 seconds.
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]    in  15.2880 seconds.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 15.385 seconds
```

<span data-ttu-id="fcd40-115">これもにより、その場合、 **FirewallProfile**何らかの理由で失敗したリソース、**ファイアウォール**が最初に定義された場合でも、ブロックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fcd40-115">This also ensures that if the **FirewallProfile** resource fails for any reason, the **Firewall** block will not execute even though it was defined first.</span></span> <span data-ttu-id="fcd40-116">`DependsOn`キーによりより柔軟にリソース ブロックをグループ化し、リソースの実行前に依存関係が解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcd40-116">The `DependsOn` key allows more flexibility in grouping resource blocks and ensuring that dependencies are resolved before a Resource executes.</span></span>

<span data-ttu-id="fcd40-117">高度な構成で使用することも[ノードの依存関係をクロス](crossNodeDependencies.md)(たとえば、クライアントをドメインに参加させる前に、ドメイン コント ローラーが構成されていることを確認) をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-117">In more advanced Configurations, you can also use [Cross Node Dependency](crossNodeDependencies.md) to allow even more granular control (For example, ensuring a domain controller is configured before joining a client to the domain).</span></span>

## <a name="cleaning-up"></a><span data-ttu-id="fcd40-118">クリーンアップ</span><span class="sxs-lookup"><span data-stu-id="fcd40-118">Cleaning Up</span></span>

<span data-ttu-id="fcd40-119">上記の構成を適用した場合は、すべての変更を元に戻すキーを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="fcd40-119">If you applied the Configuration above, you can reverse keys to undo any changes.</span></span> <span data-ttu-id="fcd40-120">上記の例では、設定、**有効**ファイアウォール規則とプロファイルを false にキーが無効になります。</span><span class="sxs-lookup"><span data-stu-id="fcd40-120">In the above example, setting the **Enabled** key to false will disable the firewall rule and profile.</span></span> <span data-ttu-id="fcd40-121">ターゲット ノードの前の構成済みの状態に一致するように、必要に応じて、例を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd40-121">You should modify the example as needed to match your target Node's previous configured state.</span></span>

```powershell
        Firewall Firewall
        {
            Name                  = 'IIS-WebServerRole-HTTP-In-TCP'
            Enabled               = 'False'
            DependsOn             = '[FirewallProfile]FirewallProfilePublic'
        }

        FirewallProfile FirewallProfilePublic
        {
            Name = 'Public'
            Enabled = 'False'
        }
```

## <a name="see-also"></a><span data-ttu-id="fcd40-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcd40-122">See also</span></span>

- [<span data-ttu-id="fcd40-123">ノードの相互依存関係を使用して、</span><span class="sxs-lookup"><span data-stu-id="fcd40-123">Use Cross Node Dependencies</span></span>](./crossNodeDependencies.md)
