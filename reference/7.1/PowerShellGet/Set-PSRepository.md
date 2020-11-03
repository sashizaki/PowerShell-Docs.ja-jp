---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 5b9addd42ca655436ad12d624afd39fa6747dadf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212624"
---
# <span data-ttu-id="a2555-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a2555-103">Set-PSRepository</span></span>

## <span data-ttu-id="a2555-104">概要</span><span class="sxs-lookup"><span data-stu-id="a2555-104">SYNOPSIS</span></span>
<span data-ttu-id="a2555-105">登録されているリポジトリの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="a2555-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2555-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="a2555-107">Description</span><span class="sxs-lookup"><span data-stu-id="a2555-107">DESCRIPTION</span></span>

<span data-ttu-id="a2555-108">コマンドレットでは、 `Set-PSRepository` 登録されているモジュールリポジトリの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="a2555-109">設定は、現在のユーザーに対して永続的であり、そのユーザーに対してインストールされているすべてのバージョンの PowerShell に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2555-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="a2555-110">例</span><span class="sxs-lookup"><span data-stu-id="a2555-110">EXAMPLES</span></span>

### <span data-ttu-id="a2555-111">例 1: リポジトリのインストールポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a2555-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="a2555-112">このコマンドは、 **Myinternalsource** リポジトリのインストールポリシーを **信頼済み** に設定し、そのソースからモジュールをインストールする前に確認メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="a2555-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted** , so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="a2555-113">例 2: リポジトリのソースと発行場所を設定する</span><span class="sxs-lookup"><span data-stu-id="a2555-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="a2555-114">このコマンドは、 **Myinternalsource** のソースの場所と発行場所を、指定された uri に設定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="a2555-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2555-115">PARAMETERS</span></span>

### <span data-ttu-id="a2555-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="a2555-116">-Credential</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-117">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="a2555-117">-InstallationPolicy</span></span>

<span data-ttu-id="a2555-118">インストールポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-118">Specifies the installation policy.</span></span> <span data-ttu-id="a2555-119">有効な値は、 **信頼さ** れている、信頼されてい **ない** です。</span><span class="sxs-lookup"><span data-stu-id="a2555-119">Valid values are: **Trusted** , **Untrusted** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-120">-Name</span><span class="sxs-lookup"><span data-stu-id="a2555-120">-Name</span></span>

<span data-ttu-id="a2555-121">リポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-121">Specifies the name of the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-122">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="a2555-122">-PackageManagementProvider</span></span>

<span data-ttu-id="a2555-123">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-123">Specifies the package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-124">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="a2555-124">-Proxy</span></span>

<span data-ttu-id="a2555-125">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-126">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="a2555-126">-ProxyCredential</span></span>

<span data-ttu-id="a2555-127">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-128">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="a2555-128">-PublishLocation</span></span>

<span data-ttu-id="a2555-129">発行場所の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="a2555-130">たとえば、NuGet ベースのリポジトリの場合、発行場所はに似てい `https://someNuGetUrl.com/api/v2/Packages` ます。</span><span class="sxs-lookup"><span data-stu-id="a2555-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-131">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="a2555-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="a2555-132">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-132">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-133">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="a2555-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="a2555-134">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-134">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-135">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="a2555-135">-SourceLocation</span></span>

<span data-ttu-id="a2555-136">このリポジトリからモジュールを検出してインストールするための URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2555-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="a2555-137">たとえば、NuGet ベースのリポジトリの場合、ソースの場所はに似てい `https://someNuGetUrl.com/api/v2` ます。</span><span class="sxs-lookup"><span data-stu-id="a2555-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2555-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2555-138">CommonParameters</span></span>

<span data-ttu-id="a2555-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a2555-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2555-140">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2555-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2555-141">入力</span><span class="sxs-lookup"><span data-stu-id="a2555-141">INPUTS</span></span>

### <span data-ttu-id="a2555-142">System.String</span><span class="sxs-lookup"><span data-stu-id="a2555-142">System.String</span></span>

### <span data-ttu-id="a2555-143">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="a2555-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="a2555-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="a2555-144">System.Uri</span></span>

## <span data-ttu-id="a2555-145">出力</span><span class="sxs-lookup"><span data-stu-id="a2555-145">OUTPUTS</span></span>

### <span data-ttu-id="a2555-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="a2555-146">System.Object</span></span>

## <span data-ttu-id="a2555-147">注</span><span class="sxs-lookup"><span data-stu-id="a2555-147">NOTES</span></span>

## <span data-ttu-id="a2555-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a2555-148">RELATED LINKS</span></span>

[<span data-ttu-id="a2555-149">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a2555-149">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="a2555-150">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a2555-150">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="a2555-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a2555-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

