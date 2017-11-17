---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: "NuGet プロバイダーと EXE をブートストラップする"
ms.openlocfilehash: 0036972eb9a0c20469da1aadafe223e6ec80f16a
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="bootstrap-both-nuget-provider-and-nugetexe-or-bootstrap-only-nuget-provider"></a><span data-ttu-id="40bcd-103">NuGet プロバイダーと NuGet.exe の両方をブートストラップまたは NuGet プロバイダーのみをブートストラップする</span><span class="sxs-lookup"><span data-stu-id="40bcd-103">Bootstrap both NuGet provider and NuGet.exe or bootstrap only NuGet provider</span></span>

<span data-ttu-id="40bcd-104">NuGet.exe は最新の NuGet プロバイダーには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="40bcd-104">NuGet.exe is not included in the latest NuGet provider.</span></span>
<span data-ttu-id="40bcd-105">モジュールまたはスクリプトのいずれかの公開操作には、バイナリ実行可能ファイルの NuGet.exe が PowerShellGet で必要です。</span><span class="sxs-lookup"><span data-stu-id="40bcd-105">For publish operations of either a module or script, PowerShellGet requires the binary executable NuGet.exe.</span></span>
<span data-ttu-id="40bcd-106">それ以外のすべての操作 (*検索*、*インストール*、*保存*、*アンインストール*など) では、NuGet プロバイダーのみを必要とします。</span><span class="sxs-lookup"><span data-stu-id="40bcd-106">Only the NuGet provider is required for all other operations, including *find*, *install*, *save*, and *uninstall*.</span></span>
<span data-ttu-id="40bcd-107">PowerShellGet には、NuGet プロバイダーと NuGet.exe の結合ブートストラップ、または NuGet プロバイダーのみのブートストラップのいずれかを処理するロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="40bcd-107">PowerShellGet includes logic to handle either a combined bootstrap of the NuGet provider and NuGet.exe, or bootstrap of only the NuGet provider.</span></span>
<span data-ttu-id="40bcd-108">どちらの場合も、プロンプト メッセージは 1 つしか表示されません。</span><span class="sxs-lookup"><span data-stu-id="40bcd-108">In either case, only a single prompt message should occur.</span></span>
<span data-ttu-id="40bcd-109">マシンがインターネットに接続されていない場合、ユーザーまたは管理者は、切断されたマシンに NuGet プロバイダーまたは NuGet.exe ファイルの信頼されたインスタンスをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40bcd-109">If the machine is not connected to the Internet, the user or an administrator must copy a trusted instance of the NuGet provider and/or the NuGet.exe file to the disconnected machine.</span></span>

><span data-ttu-id="40bcd-110">**注**: バージョン 6 以降では、NuGet プロバイダーは PowerShell のインストールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="40bcd-110">**Note**: Starting with version 6, the NuGet provider is included in the installation of PowerShell.</span></span> [<span data-ttu-id="40bcd-111">http://github.com/powershell/powershell</span><span class="sxs-lookup"><span data-stu-id="40bcd-111">http://github.com/powershell/powershell</span></span>](http://github.com/powershell/powershell)

## <a name="resolving-error-when-the-nuget-provider-has-not-been-installed-on-a-machine-that-is-internet-connected"></a><span data-ttu-id="40bcd-112">インターネット接続されているマシンに NuGet プロバイダーがインストールされていない場合のエラーを解決する</span><span class="sxs-lookup"><span data-stu-id="40bcd-112">Resolving error when the NuGet provider has not been installed on a machine that is Internet connected</span></span>

```powershell
PS C:\> Find-Module -Repository PSGallery -Verbose -Name Contoso

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\manikb\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the NuGet provider
now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): n
Find-Module : NuGet provider is required to interact with NuGet-based repositories. Please ensure that '2.8.5.201' or newer version of NuGet provider is installed.
At line:1 char:1
+ Find-Module -Repository PSGallery -Verbose -Name Contoso
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Find-Module], InvalidOperationException
   + FullyQualifiedErrorId : CouldNotInstallNuGetProvider,Find-Module

PS C:\> Find-Module -Repository PSGallery -Verbose -Name Contoso

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\manikb\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the NuGet provider
now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: Installing NuGet provider.

Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Contoso                             Module     PSGallery        Contoso module
```
## <a name="resolving-error-when-the-nuget-provider-is-available-and-nugetexe-is-not-available-during-the-publish-operation-on-a-machine-that-is-internet-connected"></a><span data-ttu-id="40bcd-113">インターネットに接続されているマシンで公開操作を行うときに NuGet プロバイダーは使用できるが NuGet.exe は使用できない場合のエラーを解決する</span><span class="sxs-lookup"><span data-stu-id="40bcd-113">Resolving error when the NuGet provider is available and NuGet.exe is not available during the publish operation on a machine that is Internet connected</span></span>

```powershell
PS C:\> Publish-Module -Name Contoso -Repository PSGallery -Verbose

NuGet.exe is required to continue
PowerShellGet requires NuGet.exe to publish an item to the NuGet-based repositories. NuGet.exe must be available under one of the paths specified in PATH environment variable value. Do you want PowerShellGet to install NuGet.exe now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): N
Publish-Module : NuGet.exe is required to interact with NuGet-based repositories. Please ensure that NuGet.exe is available under one of the paths specified in PATH environment variable value.
At line:1 char:1
+ Publish-Module -Name Contoso -Repository PSGallery -Verbose
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Publish-Module], InvalidOperationException
    + FullyQualifiedErrorId : CouldNotInstallNuGetExe,Publish-Module

PS C:\> Publish-Module -Name Contoso -Repository PSGallery -Verbose

NuGet.exe is required to continue
PowerShellGet requires NuGet.exe to publish an item to the NuGet-based repositories. NuGet.exe must be available under one of the paths specified in PATH environment variable value. Do you want PowerShellGet to install NuGet.exe now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: Installing NuGet.exe.
VERBOSE: Successfully published module 'Contoso' to the module publish location 'https://www.powershellgallery.com/api/v2/'. Please allow few minutes for 'Contoso' to show up in the search results.
```

## <a name="resolving-error-when-both-nuget-provider-and-nugetexe-are-not-available-during-the-publish-operation-on-a-machine-that-is-internet-connected"></a><span data-ttu-id="40bcd-114">インターネットに接続されているマシンで公開操作を行うときに NuGet プロバイダーと NuGet.exe のどちらも使用できない場合のエラーを解決する</span><span class="sxs-lookup"><span data-stu-id="40bcd-114">Resolving error when both NuGet provider and NuGet.exe are not available during the publish operation on a machine that is Internet connected</span></span>

```powershell
PS C:\> Publish-Module -Name Contoso -Repository PSGallery -Verbose

NuGet.exe and NuGet provider are required to continue
PowerShellGet requires NuGet.exe and NuGet provider version '2.8.5.201' or newer to interact with the NuGet-based repositories. Do you want PowerShellGet to install both NuGet.exe and NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): N
Publish-Module : PowerShellGet requires NuGet.exe and NuGet provider version '2.8.5.201' or newer to interact with the NuGet-based repositories. Please ensure that '2.8.5.201' or newer version of NuGet provider is installed and NuGet.exe is available under 
one of the paths specified in PATH environment variable value.
At line:1 char:1
+ Publish-Module -Name Contoso -Repository PSGallery -Verbose
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Publish-Module], InvalidOperationException
    + FullyQualifiedErrorId : CouldNotInstallNuGetBinaries,Publish-Module

PS C:\> Publish-Module -Name Contoso -Repository PSGallery -Verbose

NuGet.exe and NuGet provider are required to continue
PowerShellGet requires NuGet.exe and NuGet provider version '2.8.5.201' or newer to interact with the NuGet-based repositories. Do you want PowerShellGet to install both NuGet.exe and NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: Installing NuGet provider.
VERBOSE: Installing NuGet.exe.
VERBOSE: Successfully published module 'Contoso' to the module publish location 'https://www.powershellgallery.com/api/v2/'. Please allow few minutes for 'Contoso' to show up in the search results.
```

## <a name="manually-bootstrapping-the-nuget-provider-on-a-machine-that-is-not-connected-to-the-internet"></a><span data-ttu-id="40bcd-115">インターネットに接続されていないマシンで NuGet プロバイダーを手動でブートストラップする</span><span class="sxs-lookup"><span data-stu-id="40bcd-115">Manually bootstrapping the NuGet provider on a machine that is not connected to the Internet</span></span>

<span data-ttu-id="40bcd-116">上記のプロセスは、マシンがインターネットに接続されていて、共有の場所にあるファイルをダウンロードできることが前提となっています。</span><span class="sxs-lookup"><span data-stu-id="40bcd-116">The processes demonstrated above assume the machine is connected to the Internet and can download files from a public location.</span></span>
<span data-ttu-id="40bcd-117">この前提条件を満たせない場合は、唯一の方法として、上記のプロセスに従ってマシンをブートストラップしてから、オフラインの信頼されたプロセスを使用して、分離されたノードにプロバイダーを手動でコピーします。</span><span class="sxs-lookup"><span data-stu-id="40bcd-117">If that is not possible, the only option is to bootstrap a machine using the processes given above, and manually copy the provider to the isolated node through an offline trusted process.</span></span>
<span data-ttu-id="40bcd-118">このシナリオで最も一般的なユース ケースは、分離された環境のサポートでプライベート ギャラリーが使用可能な場合です。</span><span class="sxs-lookup"><span data-stu-id="40bcd-118">The most common use case for this scenario is when a private gallery is available to support an isolated environment.</span></span>

<span data-ttu-id="40bcd-119">上記のプロセスに従ってインターネットに接続されたマシンをブートストラップすると、次の場所にプロバイダー ファイルが保存されます。</span><span class="sxs-lookup"><span data-stu-id="40bcd-119">After following the process above to bootstrap an Internet connected machine, you will find provider files in the location:</span></span>
```
C:\Program Files\PackageManagement\ProviderAssemblies\
```

<span data-ttu-id="40bcd-120">NuGet プロバイダーのフォルダーまたはファイルの構造は、次のようになります (バージョン番号は異なる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="40bcd-120">The folder/file structure of the NuGet provider will be (possibly with a different version number):</span></span>

<span data-ttu-id="40bcd-121">NuGet</span><span class="sxs-lookup"><span data-stu-id="40bcd-121">NuGet</span></span><br>
<span data-ttu-id="40bcd-122">--2.8.5.208</span><span class="sxs-lookup"><span data-stu-id="40bcd-122">--2.8.5.208</span></span><br>
<span data-ttu-id="40bcd-123">---Microsoft.PackageManagement.NuGetProvider.dll</span><span class="sxs-lookup"><span data-stu-id="40bcd-123">----Microsoft.PackageManagement.NuGetProvider.dll</span></span>

<span data-ttu-id="40bcd-124">信頼されたプロセスを使用して、これらのフォルダーとファイルをオフラインのマシンにコピーします。</span><span class="sxs-lookup"><span data-stu-id="40bcd-124">Copy these folders and file using a trusted process to the offline machines.</span></span>

## <a name="manually-bootstrapping-nugetexe-to-support-publish-operations-on-a-machine-that-is-not-connected-to-the-internet"></a><span data-ttu-id="40bcd-125">手動で NuGet.exe をブートストラップしてインターネットに接続していないマシンでの公開操作をサポートする</span><span class="sxs-lookup"><span data-stu-id="40bcd-125">Manually bootstrapping NuGet.exe to support publish operations on a machine that is not connected to the Internet</span></span>

<span data-ttu-id="40bcd-126">NuGet.exe プロバイダーを手動でブートストラップするプロセスの他に、マシンで *Publish-Module* または *Publish-Script* コマンドレットを使用してプライベート ギャラリーにモジュールまたはスクリプトを公開する場合に、NuGet.exe のバイナリ実行可能ファイルが必要になります。</span><span class="sxs-lookup"><span data-stu-id="40bcd-126">In addition to the process to manually bootstrap the NuGet provider, if the machine will be used to publish modules or scripts to a private gallery using the *Publish-Module* or *Publish-Script* cmdlets, the NuGet.exe binary executable file will be required.</span></span>
<span data-ttu-id="40bcd-127">このシナリオで最も一般的なユース ケースは、分離された環境のサポートでプライベート ギャラリーが使用可能な場合です。</span><span class="sxs-lookup"><span data-stu-id="40bcd-127">The most common use case for this scenario is when a private gallery is available to support an isolated environment.</span></span>
<span data-ttu-id="40bcd-128">NuGet.exe ファイルを取得する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="40bcd-128">There are two options to obtain the NuGet.exe file.</span></span>

<span data-ttu-id="40bcd-129">1 つは、インターネット接続されているマシンをブートストラップしてから、信頼されたプロセスを使用してオンラインのマシンにファイルをコピーする方法です。</span><span class="sxs-lookup"><span data-stu-id="40bcd-129">One option is to bootstrap a machine that is Internet connected and copy the files to the offline machines using a trusted process.</span></span>
<span data-ttu-id="40bcd-130">インターネット接続されているマシンをブートストラップすると、次の 2 つのフォルダーのいずれかに NuGet.exe バイナリが配置されます。</span><span class="sxs-lookup"><span data-stu-id="40bcd-130">After bootstrapping the Internet connected machine, the NuGet.exe binary will be located in one of two folders:</span></span>

<span data-ttu-id="40bcd-131">*Publish-Module* または *Publish-Script* コマンドレットが、管理者特権のアクセス許可で (管理者によって) 実行された場合:</span><span class="sxs-lookup"><span data-stu-id="40bcd-131">If the *Publish-Module* or *Publish-Script* cmdlets were executed with elevated permissions (As an Administrator):</span></span>
```
$env:ProgramData\Microsoft\Windows\PowerShell\PowerShellGet
```

<span data-ttu-id="40bcd-132">管理者特権のアクセス許可を持たないユーザーによってコマンドレットが実行された場合:</span><span class="sxs-lookup"><span data-stu-id="40bcd-132">If the cmdlets were executed as a user without elevated permissions:</span></span>
```
$env:userprofile\AppData\Local\Microsoft\Windows\PowerShell\PowerShellGet\
```

<span data-ttu-id="40bcd-133">2 つ目は、NuGet.Org の Web サイト ([https://dist.nuget.org/index.html](https://dist.nuget.org/index.html)) から NuGet.exe をダウンロードする方法です。</span><span class="sxs-lookup"><span data-stu-id="40bcd-133">A second option is to download NuGet.exe from the NuGet.Org website: [https://dist.nuget.org/index.html](https://dist.nuget.org/index.html)</span></span><br>
<span data-ttu-id="40bcd-134">運用環境のマシンで使用する NugGet のバージョンを選択するときに、2.8.5.208 よりも新しく、"推奨" の表記があるバージョンであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="40bcd-134">When selecting a NugGet version for production machines, make sure it is later than 2.8.5.208, and identify the version that has been labeled "recommended".</span></span>
<span data-ttu-id="40bcd-135">ブラウザーを使用してダウンロードした場合、ファイルのブロックを解除することを忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="40bcd-135">Remember to unblock the file if it was downloaded using a browser.</span></span>
<span data-ttu-id="40bcd-136">この操作は *Unblock-File* コマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="40bcd-136">This can be performed by using the *Unblock-File* cmdlet.</span></span>

<span data-ttu-id="40bcd-137">どちらの場合も、NuGet.exe ファイルを *$env:path* の任意の場所にコピーできますが、通常は次の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="40bcd-137">In either case, the NuGet.exe file can be copied to any location in *$env:path*, but the standard locations are:</span></span>

<span data-ttu-id="40bcd-138">すべてのユーザーが *Publish-Module* と *Publish-Script* コマンドレットを使用できるように、実行可能ファイルを使用可能にする場合:</span><span class="sxs-lookup"><span data-stu-id="40bcd-138">To make the executable available so that all users can use *Publish-Module* and *Publish-Script* cmdlets:</span></span>
```
$env:ProgramData\Microsoft\Windows\PowerShell\PowerShellGet
```

<span data-ttu-id="40bcd-139">特定のユーザーだけが実行可能ファイルを使用できるようにするには、対象ユーザーのプロファイル内の場所にのみコピーします。</span><span class="sxs-lookup"><span data-stu-id="40bcd-139">To make the executable available to only a specific user, copy to the location within only that user's profile:</span></span>
```
$env:userprofile\AppData\Local\Microsoft\Windows\PowerShell\PowerShellGet\
```

