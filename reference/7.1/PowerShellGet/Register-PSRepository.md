---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 300d3388c39a86cb732d50404ad7d8c28bd3034e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892193"
---
# <span data-ttu-id="da266-103">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="da266-103">Register-PSRepository</span></span>

## <span data-ttu-id="da266-104">概要</span><span class="sxs-lookup"><span data-stu-id="da266-104">SYNOPSIS</span></span>
<span data-ttu-id="da266-105">PowerShell リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="da266-105">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="da266-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da266-106">SYNTAX</span></span>

### <span data-ttu-id="da266-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="da266-107">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="da266-108">PSGalleryParameterSet</span><span class="sxs-lookup"><span data-stu-id="da266-108">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="da266-109">Description</span><span class="sxs-lookup"><span data-stu-id="da266-109">DESCRIPTION</span></span>

<span data-ttu-id="da266-110">`Register-PSRepository`コマンドレットは、PowerShell モジュールの既定のリポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="da266-110">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="da266-111">リポジトリが登録されると、 `Find-Module` 、 `Install-Module` 、およびコマンドレットから参照でき `Publish-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="da266-111">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="da266-112">登録されたリポジトリは、およびの既定のリポジトリになり `Find-Module` `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="da266-112">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="da266-113">登録されているリポジトリはユーザー固有です。</span><span class="sxs-lookup"><span data-stu-id="da266-113">Registered repositories are user-specific.</span></span> <span data-ttu-id="da266-114">システム全体のコンテキストには登録されません。</span><span class="sxs-lookup"><span data-stu-id="da266-114">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="da266-115">登録されている各リポジトリは、 **PackageManagementProvider** パラメーターで指定される oneget パッケージプロバイダーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="da266-115">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="da266-116">各 OneGet プロバイダーは、特定の種類のリポジトリと対話するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="da266-116">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="da266-117">たとえば、nuget プロバイダーは NuGet ベースのリポジトリと対話するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="da266-117">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="da266-118">登録時に OneGet プロバイダーが指定されていない場合、PowerShellGet は、指定されたソースの場所を処理できる OneGet プロバイダーの検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="da266-118">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="da266-119">例</span><span class="sxs-lookup"><span data-stu-id="da266-119">EXAMPLES</span></span>

### <span data-ttu-id="da266-120">例 1: リポジトリを登録する</span><span class="sxs-lookup"><span data-stu-id="da266-120">Example 1: Register a repository</span></span>

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

<span data-ttu-id="da266-121">最初のコマンドは、 `https://www.myget.org/F/powershellgetdemo/` 現在のユーザーのリポジトリとして登録します。</span><span class="sxs-lookup"><span data-stu-id="da266-121">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="da266-122">MyNuGetSource を登録すると、モジュールの検索、インストール、および発行時に明示的に参照できます。</span><span class="sxs-lookup"><span data-stu-id="da266-122">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="da266-123">**PackageManagementProvider** パラメーターが指定されていないため、リポジトリが oneget パッケージプロバイダーに明示的に関連付けられていないため、PowerShellGet は使用可能なパッケージプロバイダーをポーリングし、NuGet プロバイダーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="da266-123">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="da266-124">2番目のコマンドは、登録されているリポジトリを取得し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="da266-124">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="da266-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da266-125">PARAMETERS</span></span>

### <span data-ttu-id="da266-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="da266-126">-Credential</span></span>

<span data-ttu-id="da266-127">リポジトリを登録する権限を持つアカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-127">Specifies credentials of an account that has rights to register a repository.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da266-128">-Default</span><span class="sxs-lookup"><span data-stu-id="da266-128">-Default</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-129">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="da266-129">-InstallationPolicy</span></span>

<span data-ttu-id="da266-130">インストールポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-130">Specifies the installation policy.</span></span> <span data-ttu-id="da266-131">有効な値は、信頼されている、信頼されていないです。</span><span class="sxs-lookup"><span data-stu-id="da266-131">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="da266-132">既定値は信頼されていません。</span><span class="sxs-lookup"><span data-stu-id="da266-132">The default value is UnTrusted.</span></span>

<span data-ttu-id="da266-133">リポジトリのインストールポリシーでは、そのリポジトリからのインストール時に PowerShell の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-133">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="da266-134">信頼されていないリポジトリからモジュールをインストールする場合は、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da266-134">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="da266-135">**Installationpolicy** は、コマンドレットを使用して設定でき `Set-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="da266-135">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

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

### <span data-ttu-id="da266-136">-Name</span><span class="sxs-lookup"><span data-stu-id="da266-136">-Name</span></span>

<span data-ttu-id="da266-137">登録するリポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-137">Specifies the name of the repository to register.</span></span> <span data-ttu-id="da266-138">この名前を使用して、やなどのコマンドレットでリポジトリを指定することができ `Find-Module` `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="da266-138">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-139">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="da266-139">-PackageManagementProvider</span></span>

<span data-ttu-id="da266-140">OneGet パッケージプロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-140">Specifies a OneGet package provider.</span></span> <span data-ttu-id="da266-141">このパラメーターの値を指定しない場合、PowerShellGet は使用可能なパッケージプロバイダーをポーリングし、リポジトリを処理できることを示す最初のパッケージプロバイダーにこのリポジトリを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="da266-141">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-142">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="da266-142">-Proxy</span></span>

<span data-ttu-id="da266-143">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="da266-144">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="da266-144">-ProxyCredential</span></span>

<span data-ttu-id="da266-145">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="da266-146">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="da266-146">-PublishLocation</span></span>

<span data-ttu-id="da266-147">発行場所の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-147">Specifies the URI of the publish location.</span></span> <span data-ttu-id="da266-148">たとえば、NuGet ベースのリポジトリの場合、発行場所はに似てい `https://someNuGetUrl.com/api/v2/Packages` ます。</span><span class="sxs-lookup"><span data-stu-id="da266-148">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-149">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="da266-149">-ScriptPublishLocation</span></span>

<span data-ttu-id="da266-150">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-150">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-151">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="da266-151">-ScriptSourceLocation</span></span>

<span data-ttu-id="da266-152">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-152">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-153">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="da266-153">-SourceLocation</span></span>

<span data-ttu-id="da266-154">このリポジトリからモジュールを検出してインストールするための URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="da266-154">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="da266-155">URI には、NuGet サーバーフィード (最も一般的な状況)、HTTP、HTTPS、FTP、またはファイルの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="da266-155">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="da266-156">たとえば、NuGet ベースのリポジトリの場合、ソースの場所はに似てい `https://someNuGetUrl.com/api/v2` ます。</span><span class="sxs-lookup"><span data-stu-id="da266-156">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da266-157">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="da266-157">CommonParameters</span></span>

<span data-ttu-id="da266-158">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="da266-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da266-159">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da266-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da266-160">入力</span><span class="sxs-lookup"><span data-stu-id="da266-160">INPUTS</span></span>

### <span data-ttu-id="da266-161">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="da266-161">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="da266-162">System.Uri</span><span class="sxs-lookup"><span data-stu-id="da266-162">System.Uri</span></span>

## <span data-ttu-id="da266-163">出力</span><span class="sxs-lookup"><span data-stu-id="da266-163">OUTPUTS</span></span>

### <span data-ttu-id="da266-164">System.Object</span><span class="sxs-lookup"><span data-stu-id="da266-164">System.Object</span></span>

## <span data-ttu-id="da266-165">注</span><span class="sxs-lookup"><span data-stu-id="da266-165">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da266-166">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da266-166">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="da266-167">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="da266-167">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="da266-168">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da266-168">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="da266-169">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da266-169">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="da266-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="da266-170">RELATED LINKS</span></span>

[<span data-ttu-id="da266-171">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="da266-171">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="da266-172">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="da266-172">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="da266-173">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="da266-173">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
