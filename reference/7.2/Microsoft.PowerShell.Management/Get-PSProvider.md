---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 20820d2d194f41d43048c9617b63b9acb3fbb4f8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602771"
---
# <span data-ttu-id="dfa51-102">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="dfa51-102">Get-PSProvider</span></span>

## <span data-ttu-id="dfa51-103">概要</span><span class="sxs-lookup"><span data-stu-id="dfa51-103">SYNOPSIS</span></span>
<span data-ttu-id="dfa51-104">指定された PowerShell プロバイダーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-104">Gets information about the specified PowerShell provider.</span></span>

## <span data-ttu-id="dfa51-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dfa51-105">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="dfa51-106">Description</span><span class="sxs-lookup"><span data-stu-id="dfa51-106">DESCRIPTION</span></span>

<span data-ttu-id="dfa51-107">`Get-PSProvider`コマンドレットは、現在のセッションの PowerShell プロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-107">The `Get-PSProvider` cmdlet gets the PowerShell providers in the current session.</span></span>
<span data-ttu-id="dfa51-108">セッション内の特定のドライブを取得することも、すべてのドライブを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfa51-108">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="dfa51-109">PowerShell プロバイダーを使用すると、ファイルシステムドライブのようにさまざまなデータストアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dfa51-109">PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="dfa51-110">PowerShell プロバイダーの詳細については、「 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa51-110">For information about PowerShell providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="dfa51-111">例</span><span class="sxs-lookup"><span data-stu-id="dfa51-111">EXAMPLES</span></span>

### <span data-ttu-id="dfa51-112">例 1: 使用可能なすべてのプロバイダーの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="dfa51-112">Example 1: Display a list of all available providers</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="dfa51-113">このコマンドは、使用可能なすべての PowerShell プロバイダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-113">This command displays a list of all available PowerShell providers.</span></span>

### <span data-ttu-id="dfa51-114">例 2: 指定した文字で始まるすべての PowerShell プロバイダーの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="dfa51-114">Example 2: Display a list of all PowerShell providers that begin with specified letters</span></span>

```powershell
Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="dfa51-115">このコマンドは、名前が f または r で始まるすべての PowerShell プロバイダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-115">This command displays a list of all PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="dfa51-116">例 3: プロバイダーをセッションに追加したスナップインまたはモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dfa51-116">Example 3: Find snap-ins or module that added providers to your session</span></span>

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
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
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="dfa51-117">これらのコマンドは、セッションにプロバイダーを追加した PowerShell スナップインまたはモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-117">These commands find the PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="dfa51-118">プロバイダーを含むすべての PowerShell 要素は、スナップインまたはモジュール内で発生します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-118">All PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="dfa51-119">これらのコマンドは、を返す **Providerinfo** オブジェクトの Add-pssnapin および Module プロパティを使用し `Get-PSProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="dfa51-119">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that `Get-PSProvider` returns.</span></span>
<span data-ttu-id="dfa51-120">これらのプロパティの値には、プロバイダーを追加するスナップインまたはモジュールの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfa51-120">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="dfa51-121">最初のコマンドは、セッションのすべてのプロバイダーを取得し、Name、Module、および PSSnapin プロパティの値を含め、表形式に書式設定します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-121">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="dfa51-122">2番目のコマンドは、コマンドレットを使用して、 `Where-Object` **Microsoft. PowerShell** スナップインから取得されたプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-122">The second command uses the `Where-Object` cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="dfa51-123">例 4: ファイルシステムプロバイダーの Home プロパティのパスを解決する</span><span class="sxs-lookup"><span data-stu-id="dfa51-123">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

<span data-ttu-id="dfa51-124">この例では、チルダ記号 (~) が FileSystem プロバイダーの **Home** プロパティの値を表していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dfa51-124">This example shows that the tilde symbol (~) represents the value of the **Home** property of the FileSystem provider.</span></span>
<span data-ttu-id="dfa51-125">**Home** プロパティの値は省略可能ですが、 **FileSystem** プロバイダーでは、またはとして定義されてい `$env:homedrive\$env:homepath` `$home` ます。</span><span class="sxs-lookup"><span data-stu-id="dfa51-125">The **Home** property value is optional, but for the **FileSystem** provider, it is defined as `$env:homedrive\$env:homepath` or `$home`.</span></span>

## <span data-ttu-id="dfa51-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dfa51-126">PARAMETERS</span></span>

### <span data-ttu-id="dfa51-127">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="dfa51-127">-PSProvider</span></span>

<span data-ttu-id="dfa51-128">このコマンドレットによって情報が取得される PowerShell プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-128">Specifies the name or names of the PowerShell providers about which this cmdlet gets information.</span></span>

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

### <span data-ttu-id="dfa51-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dfa51-129">CommonParameters</span></span>

<span data-ttu-id="dfa51-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dfa51-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dfa51-131">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa51-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dfa51-132">入力</span><span class="sxs-lookup"><span data-stu-id="dfa51-132">INPUTS</span></span>

### <span data-ttu-id="dfa51-133">String[]</span><span class="sxs-lookup"><span data-stu-id="dfa51-133">String[]</span></span>

<span data-ttu-id="dfa51-134">パイプを使用して、1つまたは複数のプロバイダー名文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-134">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="dfa51-135">出力</span><span class="sxs-lookup"><span data-stu-id="dfa51-135">OUTPUTS</span></span>

### <span data-ttu-id="dfa51-136">システムの管理. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="dfa51-136">System.Management.Automation.ProviderInfo</span></span>

<span data-ttu-id="dfa51-137">このコマンドレットは、セッション内の PowerShell プロバイダーを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dfa51-137">This cmdlet returns objects that represent the PowerShell providers in the session.</span></span>

## <span data-ttu-id="dfa51-138">注</span><span class="sxs-lookup"><span data-stu-id="dfa51-138">NOTES</span></span>

## <span data-ttu-id="dfa51-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dfa51-139">RELATED LINKS</span></span>

