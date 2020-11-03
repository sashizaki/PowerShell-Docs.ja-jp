---
external help file: Get-DSCLocalConfigurationManager.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscLocalConfigurationManager
ms.openlocfilehash: 162770d8eb3a8953dcfaeb31f30742a46353b33b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215315"
---
# <span data-ttu-id="737b3-103">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="737b3-103">Get-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="737b3-104">概要</span><span class="sxs-lookup"><span data-stu-id="737b3-104">SYNOPSIS</span></span>

<span data-ttu-id="737b3-105">ノードのローカル Configuration Manager (LCM) 設定と状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="737b3-105">Gets Local Configuration Manager (LCM) settings and states for the node.</span></span>

## <span data-ttu-id="737b3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="737b3-106">SYNTAX</span></span>

```
Get-DscLocalConfigurationManager [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="737b3-107">Description</span><span class="sxs-lookup"><span data-stu-id="737b3-107">DESCRIPTION</span></span>

<span data-ttu-id="737b3-108">この `Get-DscLocalConfigurationManager` コマンドレットは、lcm 設定、またはメタ構成、およびノードの lcm の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="737b3-108">The `Get-DscLocalConfigurationManager` cmdlet gets LCM settings, or meta-configuration, and the states of LCM for the node.</span></span> <span data-ttu-id="737b3-109">Common Information Model (CIM) セッションを使用してコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="737b3-109">Specify computers by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="737b3-110">ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターから構成設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="737b3-110">If you do not specify a target computer, the cmdlet gets the configuration settings from the local computer.</span></span>

## <span data-ttu-id="737b3-111">例</span><span class="sxs-lookup"><span data-stu-id="737b3-111">EXAMPLES</span></span>

### <span data-ttu-id="737b3-112">例 1: ローカルコンピューターの LCM 設定を取得する</span><span class="sxs-lookup"><span data-stu-id="737b3-112">Example 1: Get LCM settings for the local computer</span></span>

```powershell
Get-DscLocalConfigurationManager
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 47edd8c9-2798-4827-839a-b35cc87e69fb
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName
```

<span data-ttu-id="737b3-113">このコマンドは、ローカルコンピューターの LCM 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="737b3-113">This command gets LCM settings for the local computer.</span></span>

<span data-ttu-id="737b3-114">出力の個々の属性の詳細については、 [ローカル Configuration Manager の構成](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="737b3-114">For more information on the individual attributes of the output, see the [Configuring the Local Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) documentation.</span></span>

### <span data-ttu-id="737b3-115">例 2: 指定したコンピューターの LCM 設定を取得する</span><span class="sxs-lookup"><span data-stu-id="737b3-115">Example 2: Get LCM settings for a specified computer</span></span>

```powershell
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Get-DscLocalConfigurationManager -CimSession $Session
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 169dfa57-a7f9-43be-a7a5-9dd06587e052
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName                 : Server01
PSComputerName                 : Server01
```

<span data-ttu-id="737b3-116">この例では、CIM セッションによって指定されたコンピューターの LCM 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="737b3-116">This example gets LCM settings for a computer specified by a CIM session.</span></span>
<span data-ttu-id="737b3-117">例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="737b3-117">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="737b3-118">または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。</span><span class="sxs-lookup"><span data-stu-id="737b3-118">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="737b3-119">最初のコマンドは、コマンドレットを使用して CIM セッションを作成し、 `New-CimSession` その **CimSession** オブジェクトを $Session 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="737b3-119">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span> <span data-ttu-id="737b3-120">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="737b3-120">The command prompts you for a password.</span></span> <span data-ttu-id="737b3-121">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="737b3-121">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="737b3-122">2番目のコマンドは、$Session 変数に格納されている **CimSession** オブジェクトによって識別されるコンピューターのローカル Configuration Manager 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="737b3-122">The second command gets Local Configuration Manager settings for the computers identified by the **CimSession** objects stored in the $Session variable.</span></span> <span data-ttu-id="737b3-123">この場合、Server01 という名前のコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="737b3-123">In this case, the computer named Server01.</span></span>

## <span data-ttu-id="737b3-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="737b3-124">PARAMETERS</span></span>

### <span data-ttu-id="737b3-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="737b3-125">-AsJob</span></span>

<span data-ttu-id="737b3-126">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="737b3-126">Indicates that this cmdlet runs the command as a background job.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="737b3-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="737b3-127">-CimSession</span></span>

<span data-ttu-id="737b3-128">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="737b3-128">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="737b3-129">またはコマンドレットの出力など、コンピューター名またはセッションオブジェクトを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="737b3-129">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="737b3-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="737b3-130">-ThrottleLimit</span></span>

<span data-ttu-id="737b3-131">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="737b3-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="737b3-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="737b3-132">CommonParameters</span></span>

<span data-ttu-id="737b3-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="737b3-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="737b3-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="737b3-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="737b3-135">入力</span><span class="sxs-lookup"><span data-stu-id="737b3-135">INPUTS</span></span>

## <span data-ttu-id="737b3-136">出力</span><span class="sxs-lookup"><span data-stu-id="737b3-136">OUTPUTS</span></span>

## <span data-ttu-id="737b3-137">注</span><span class="sxs-lookup"><span data-stu-id="737b3-137">NOTES</span></span>

## <span data-ttu-id="737b3-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="737b3-138">RELATED LINKS</span></span>

[<span data-ttu-id="737b3-139">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="737b3-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="737b3-140">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="737b3-140">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)
