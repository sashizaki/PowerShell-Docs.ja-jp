---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: 51bb791e0633cf172252f5b0dca22373bb065fcc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601421"
---
# <span data-ttu-id="4a7f7-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="4a7f7-102">Set-LogProperties</span></span>

## <span data-ttu-id="4a7f7-103">概要</span><span class="sxs-lookup"><span data-stu-id="4a7f7-103">SYNOPSIS</span></span>
<span data-ttu-id="4a7f7-104">Windows イベントログのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="4a7f7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a7f7-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="4a7f7-106">Description</span><span class="sxs-lookup"><span data-stu-id="4a7f7-106">DESCRIPTION</span></span>

<span data-ttu-id="4a7f7-107">このコマンドレットは、Windows イベントログの構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="4a7f7-108">このコマンドレットは、コマンドレットとコマンドレットによって使用され `Enable-PSTrace` `Disable-PSTrace` ます。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="4a7f7-109">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4a7f7-110">例</span><span class="sxs-lookup"><span data-stu-id="4a7f7-110">EXAMPLES</span></span>

### <span data-ttu-id="4a7f7-111">例 1: Windows PowerShell イベントログの保有期間の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="4a7f7-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

```powershell
$logDetails = Get-LogProperties 'Windows PowerShell'
$logDetails.Retention = $True
Set-LogProperties -LogDetails $logDetails
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : True
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="4a7f7-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a7f7-112">PARAMETERS</span></span>

### <span data-ttu-id="4a7f7-113">-Force</span><span class="sxs-lookup"><span data-stu-id="4a7f7-113">-Force</span></span>

<span data-ttu-id="4a7f7-114">プロンプトを表示せずに変更を強制するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="4a7f7-115">-LogDetails</span><span class="sxs-lookup"><span data-stu-id="4a7f7-115">-LogDetails</span></span>

<span data-ttu-id="4a7f7-116">イベントログに割り当てられる更新された構成設定。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-116">The updated configuration settings to be assigned to the event log.</span></span>

```yaml
Type: Microsoft.PowerShell.Diagnostics.LogDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4a7f7-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a7f7-117">CommonParameters</span></span>

<span data-ttu-id="4a7f7-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a7f7-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a7f7-120">入力</span><span class="sxs-lookup"><span data-stu-id="4a7f7-120">INPUTS</span></span>

### <span data-ttu-id="4a7f7-121">Microsoft. 診断. LogDetails</span><span class="sxs-lookup"><span data-stu-id="4a7f7-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="4a7f7-122">完全に構成された **Logdetails** オブジェクトをコマンドレットに渡す必要があり `Set-LogProperties` ます。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="4a7f7-123">したがって、1つの設定を変更するには、を使用して現在の構成を取得する必要があり `Get-LogProperties` ます。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="4a7f7-124">出力</span><span class="sxs-lookup"><span data-stu-id="4a7f7-124">OUTPUTS</span></span>

### <span data-ttu-id="4a7f7-125">なし</span><span class="sxs-lookup"><span data-stu-id="4a7f7-125">None</span></span>

## <span data-ttu-id="4a7f7-126">注</span><span class="sxs-lookup"><span data-stu-id="4a7f7-126">NOTES</span></span>

<span data-ttu-id="4a7f7-127">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a7f7-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4a7f7-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4a7f7-128">RELATED LINKS</span></span>

[<span data-ttu-id="4a7f7-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="4a7f7-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="4a7f7-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="4a7f7-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="4a7f7-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="4a7f7-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

