---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 179e672a099cfb92275795a0dc6129581a0e0299
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603030"
---
# <span data-ttu-id="52b22-102">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="52b22-102">Register-PSRepository</span></span>

## <span data-ttu-id="52b22-103">概要</span><span class="sxs-lookup"><span data-stu-id="52b22-103">SYNOPSIS</span></span>
<span data-ttu-id="52b22-104">PowerShell リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="52b22-104">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="52b22-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52b22-105">SYNTAX</span></span>

### <span data-ttu-id="52b22-106">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="52b22-106">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="52b22-107">PSGalleryParameterSet</span><span class="sxs-lookup"><span data-stu-id="52b22-107">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="52b22-108">Description</span><span class="sxs-lookup"><span data-stu-id="52b22-108">DESCRIPTION</span></span>

<span data-ttu-id="52b22-109">`Register-PSRepository`コマンドレットは、PowerShell モジュールの既定のリポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="52b22-109">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="52b22-110">リポジトリが登録されると、 `Find-Module` 、 `Install-Module` 、およびコマンドレットから参照でき `Publish-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="52b22-110">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="52b22-111">登録されたリポジトリは、およびの既定のリポジトリになり `Find-Module` `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="52b22-111">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="52b22-112">登録されているリポジトリはユーザー固有です。</span><span class="sxs-lookup"><span data-stu-id="52b22-112">Registered repositories are user-specific.</span></span> <span data-ttu-id="52b22-113">システム全体のコンテキストには登録されません。</span><span class="sxs-lookup"><span data-stu-id="52b22-113">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="52b22-114">登録されている各リポジトリは、 **PackageManagementProvider** パラメーターで指定される oneget パッケージプロバイダーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="52b22-114">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="52b22-115">各 OneGet プロバイダーは、特定の種類のリポジトリと対話するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="52b22-115">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="52b22-116">たとえば、nuget プロバイダーは NuGet ベースのリポジトリと対話するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="52b22-116">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="52b22-117">登録時に OneGet プロバイダーが指定されていない場合、PowerShellGet は、指定されたソースの場所を処理できる OneGet プロバイダーの検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="52b22-117">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="52b22-118">例</span><span class="sxs-lookup"><span data-stu-id="52b22-118">EXAMPLES</span></span>

### <span data-ttu-id="52b22-119">例 1: リポジトリを登録する</span><span class="sxs-lookup"><span data-stu-id="52b22-119">Example 1: Register a repository</span></span>

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

<span data-ttu-id="52b22-120">最初のコマンドは、 `https://www.myget.org/F/powershellgetdemo/` 現在のユーザーのリポジトリとして登録します。</span><span class="sxs-lookup"><span data-stu-id="52b22-120">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="52b22-121">MyNuGetSource を登録すると、モジュールの検索、インストール、および発行時に明示的に参照できます。</span><span class="sxs-lookup"><span data-stu-id="52b22-121">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="52b22-122">**PackageManagementProvider** パラメーターが指定されていないため、リポジトリが oneget パッケージプロバイダーに明示的に関連付けられていないため、PowerShellGet は使用可能なパッケージプロバイダーをポーリングし、NuGet プロバイダーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="52b22-122">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="52b22-123">2番目のコマンドは、登録されているリポジトリを取得し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="52b22-123">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="52b22-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52b22-124">PARAMETERS</span></span>

### <span data-ttu-id="52b22-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="52b22-125">-Credential</span></span>

<span data-ttu-id="52b22-126">リポジトリを登録する権限を持つアカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-126">Specifies credentials of an account that has rights to register a repository.</span></span>

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

### <span data-ttu-id="52b22-127">-Default</span><span class="sxs-lookup"><span data-stu-id="52b22-127">-Default</span></span>

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

### <span data-ttu-id="52b22-128">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="52b22-128">-InstallationPolicy</span></span>

<span data-ttu-id="52b22-129">インストールポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-129">Specifies the installation policy.</span></span> <span data-ttu-id="52b22-130">有効な値は、信頼されている、信頼されていないです。</span><span class="sxs-lookup"><span data-stu-id="52b22-130">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="52b22-131">既定値は信頼されていません。</span><span class="sxs-lookup"><span data-stu-id="52b22-131">The default value is UnTrusted.</span></span>

<span data-ttu-id="52b22-132">リポジトリのインストールポリシーでは、そのリポジトリからのインストール時に PowerShell の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-132">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="52b22-133">信頼されていないリポジトリからモジュールをインストールする場合は、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52b22-133">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="52b22-134">**Installationpolicy** は、コマンドレットを使用して設定でき `Set-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="52b22-134">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

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

### <span data-ttu-id="52b22-135">-Name</span><span class="sxs-lookup"><span data-stu-id="52b22-135">-Name</span></span>

<span data-ttu-id="52b22-136">登録するリポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-136">Specifies the name of the repository to register.</span></span> <span data-ttu-id="52b22-137">この名前を使用して、やなどのコマンドレットでリポジトリを指定することができ `Find-Module` `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="52b22-137">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

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

### <span data-ttu-id="52b22-138">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="52b22-138">-PackageManagementProvider</span></span>

<span data-ttu-id="52b22-139">OneGet パッケージプロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-139">Specifies a OneGet package provider.</span></span> <span data-ttu-id="52b22-140">このパラメーターの値を指定しない場合、PowerShellGet は使用可能なパッケージプロバイダーをポーリングし、リポジトリを処理できることを示す最初のパッケージプロバイダーにこのリポジトリを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="52b22-140">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

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

### <span data-ttu-id="52b22-141">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="52b22-141">-Proxy</span></span>

<span data-ttu-id="52b22-142">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-142">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="52b22-143">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="52b22-143">-ProxyCredential</span></span>

<span data-ttu-id="52b22-144">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-144">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="52b22-145">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="52b22-145">-PublishLocation</span></span>

<span data-ttu-id="52b22-146">発行場所の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-146">Specifies the URI of the publish location.</span></span> <span data-ttu-id="52b22-147">たとえば、NuGet ベースのリポジトリの場合、発行場所はに似てい `https://someNuGetUrl.com/api/v2/Packages` ます。</span><span class="sxs-lookup"><span data-stu-id="52b22-147">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="52b22-148">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="52b22-148">-ScriptPublishLocation</span></span>

<span data-ttu-id="52b22-149">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-149">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="52b22-150">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="52b22-150">-ScriptSourceLocation</span></span>

<span data-ttu-id="52b22-151">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-151">Specifies the script source location.</span></span>

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

### <span data-ttu-id="52b22-152">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="52b22-152">-SourceLocation</span></span>

<span data-ttu-id="52b22-153">このリポジトリからモジュールを検出してインストールするための URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="52b22-153">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="52b22-154">URI には、NuGet サーバーフィード (最も一般的な状況)、HTTP、HTTPS、FTP、またはファイルの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="52b22-154">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="52b22-155">たとえば、NuGet ベースのリポジトリの場合、ソースの場所はに似てい `https://someNuGetUrl.com/api/v2` ます。</span><span class="sxs-lookup"><span data-stu-id="52b22-155">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="52b22-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="52b22-156">CommonParameters</span></span>

<span data-ttu-id="52b22-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="52b22-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="52b22-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52b22-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="52b22-159">入力</span><span class="sxs-lookup"><span data-stu-id="52b22-159">INPUTS</span></span>

### <span data-ttu-id="52b22-160">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="52b22-160">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="52b22-161">System.Uri</span><span class="sxs-lookup"><span data-stu-id="52b22-161">System.Uri</span></span>

## <span data-ttu-id="52b22-162">出力</span><span class="sxs-lookup"><span data-stu-id="52b22-162">OUTPUTS</span></span>

### <span data-ttu-id="52b22-163">System.Object</span><span class="sxs-lookup"><span data-stu-id="52b22-163">System.Object</span></span>

## <span data-ttu-id="52b22-164">注</span><span class="sxs-lookup"><span data-stu-id="52b22-164">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52b22-165">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="52b22-165">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="52b22-166">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="52b22-166">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="52b22-167">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="52b22-167">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="52b22-168">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52b22-168">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="52b22-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="52b22-169">RELATED LINKS</span></span>

[<span data-ttu-id="52b22-170">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="52b22-170">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="52b22-171">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="52b22-171">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="52b22-172">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="52b22-172">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
