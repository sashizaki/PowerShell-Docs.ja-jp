---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215400"
---
# <span data-ttu-id="a2865-103">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a2865-103">Get-PSProvider</span></span>

## <span data-ttu-id="a2865-104">概要</span><span class="sxs-lookup"><span data-stu-id="a2865-104">SYNOPSIS</span></span>
<span data-ttu-id="a2865-105">指定した Windows PowerShell プロバイダーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a2865-105">Gets information about the specified Windows PowerShell provider.</span></span>

## <span data-ttu-id="a2865-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2865-106">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a2865-107">Description</span><span class="sxs-lookup"><span data-stu-id="a2865-107">DESCRIPTION</span></span>
<span data-ttu-id="a2865-108">**Get PSProvider** コマンドレットは、現在のセッションの Windows PowerShell プロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a2865-108">The **Get-PSProvider** cmdlet gets the Windows PowerShell providers in the current session.</span></span>
<span data-ttu-id="a2865-109">セッション内の特定のドライブを取得することも、すべてのドライブを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2865-109">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="a2865-110">Windows PowerShell プロバイダーを使用すると、さまざまなデータ ストアにファイル システム ドライブと同様にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a2865-110">Windows PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="a2865-111">Windows PowerShell プロバイダーの詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2865-111">For information about Windows PowerShell providers, see about_Providers.</span></span>

## <span data-ttu-id="a2865-112">例</span><span class="sxs-lookup"><span data-stu-id="a2865-112">EXAMPLES</span></span>

### <span data-ttu-id="a2865-113">例 1: 使用可能なすべてのプロバイダーの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="a2865-113">Example 1: Display a list of all available providers</span></span>

```
PS C:\> Get-PSProvider
```

<span data-ttu-id="a2865-114">このコマンドを実行すると、利用可能なすべての Windows PowerShell プロバイダーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2865-114">This command displays a list of all available Windows PowerShell providers.</span></span>

### <span data-ttu-id="a2865-115">例 2: 指定した文字で始まるすべての Windows PowerShell プロバイダーの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="a2865-115">Example 2: Display a list of all Windows PowerShell providers that begin with specified letters</span></span>

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="a2865-116">このコマンドは、名前が f または r で始まるすべての Windows PowerShell プロバイダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2865-116">This command displays a list of all Windows PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="a2865-117">例 3: プロバイダーをセッションに追加したスナップインまたはモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="a2865-117">Example 3: Find snap-ins or module that added providers to your session</span></span>

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="a2865-118">これらのコマンドは、セッションにプロバイダーを追加した Windows PowerShell スナップインまたはモジュールを見つけます。</span><span class="sxs-lookup"><span data-stu-id="a2865-118">These commands find the Windows PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="a2865-119">プロバイダーを含むすべての Windows PowerShell 要素は、スナップインまたはモジュールから取得されます。</span><span class="sxs-lookup"><span data-stu-id="a2865-119">All Windows PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="a2865-120">これらのコマンドは、Add-pssnapin **プロバイダー** が返す **providerinfo** オブジェクトのプロパティとモジュールのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2865-120">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that **Get-PSProvider** returns.</span></span>
<span data-ttu-id="a2865-121">これらのプロパティの値には、プロバイダーを追加するスナップインまたはモジュールの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2865-121">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="a2865-122">最初のコマンドは、セッションのすべてのプロバイダーを取得し、Name、Module、および PSSnapin プロパティの値を含め、表形式に書式設定します。</span><span class="sxs-lookup"><span data-stu-id="a2865-122">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="a2865-123">2番目のコマンドは、Where-Object コマンドレットを使用して、 **Microsoft. PowerShell** スナップインから取得されたプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a2865-123">The second command uses the Where-Object cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="a2865-124">例 4: ファイルシステムプロバイダーの Home プロパティのパスを解決する</span><span class="sxs-lookup"><span data-stu-id="a2865-124">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

<span data-ttu-id="a2865-125">この例では、チルダ記号 (~) が FileSystem プロバイダーの Home プロパティの値を表すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a2865-125">This example shows that the tilde symbol (~) represents the value of the Home property of the FileSystem provider.</span></span>
<span data-ttu-id="a2865-126">Home プロパティの値は省略可能ですが、FileSystem プロバイダーの場合は $env: homedrive \$ env: ホームパスまたは $home として定義されます。</span><span class="sxs-lookup"><span data-stu-id="a2865-126">The Home property value is optional, but for the FileSystem provider, it is defined as $env:homedrive\$env:homepath or $home.</span></span>

## <span data-ttu-id="a2865-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2865-127">PARAMETERS</span></span>

### <span data-ttu-id="a2865-128">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a2865-128">-PSProvider</span></span>
<span data-ttu-id="a2865-129">このコマンドレットが情報を取得する Windows PowerShell プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2865-129">Specifies the name or names of the Windows PowerShell providers about which this cmdlet gets information.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2865-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2865-130">CommonParameters</span></span>
<span data-ttu-id="a2865-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a2865-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2865-132">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2865-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2865-133">入力</span><span class="sxs-lookup"><span data-stu-id="a2865-133">INPUTS</span></span>

### <span data-ttu-id="a2865-134">String[]</span><span class="sxs-lookup"><span data-stu-id="a2865-134">String[]</span></span>

<span data-ttu-id="a2865-135">パイプを使用して、1つまたは複数のプロバイダー名文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="a2865-135">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="a2865-136">出力</span><span class="sxs-lookup"><span data-stu-id="a2865-136">OUTPUTS</span></span>

### <span data-ttu-id="a2865-137">システムの管理. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="a2865-137">System.Management.Automation.ProviderInfo</span></span>
<span data-ttu-id="a2865-138">このコマンドレットは、セッション内の Windows PowerShell プロバイダーを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a2865-138">This cmdlet returns objects that represent the Windows PowerShell providers in the session.</span></span>

## <span data-ttu-id="a2865-139">注</span><span class="sxs-lookup"><span data-stu-id="a2865-139">NOTES</span></span>

## <span data-ttu-id="a2865-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a2865-140">RELATED LINKS</span></span>

## <span data-ttu-id="a2865-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a2865-141">RELATED LINKS</span></span>
