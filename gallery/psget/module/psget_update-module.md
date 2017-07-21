---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Update-Module
ms.openlocfilehash: 343c296dad2a3df35f13393b3796a1d484f5f535
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="update-module"></a><span data-ttu-id="3b365-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="3b365-103">Update-Module</span></span>

<span data-ttu-id="3b365-104">指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b365-104">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <a name="description"></a><span data-ttu-id="3b365-105">説明</span><span class="sxs-lookup"><span data-stu-id="3b365-105">Description</span></span>

<span data-ttu-id="3b365-106">Update-Module コマンドレットは、Install-Module を実行してオンライン ギャラリーからインストールした Windows PowerShell モジュールの最新バージョンをローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b365-106">The Update-Module cmdlet installs a newer version of a Windows PowerShell module that was installed from the online gallery by running Install-Module on the local computer.</span></span>

<span data-ttu-id="3b365-107">既定では、必要なバージョンを指定しない限り、オンライン ギャラリーで入手可能な指定のモジュールの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3b365-107">By default, the newest version of the specified module available in online gallery is installed, unless you specify a required version.</span></span> <span data-ttu-id="3b365-108">モジュール名を指定して、既存のインストール済みのモジュールを更新できます。更新が必要なモジュールについては、Update-Module が $env:PSModulePath を検索します。</span><span class="sxs-lookup"><span data-stu-id="3b365-108">You can update an existing, installed module by specifying the name of the module; Update-Module searches $env:PSModulePath for the module that you want to update.</span></span>

<span data-ttu-id="3b365-109">Name パラメーターを指定せずに Update-Module を実行すると、ローカル コンピューターで更新が可能なすべてのモジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3b365-109">Running Update-Module without the Name parameter updates all modules that can be updated on the local computer.</span></span>

### <a name="notes"></a><span data-ttu-id="3b365-110">メモ</span><span class="sxs-lookup"><span data-stu-id="3b365-110">Notes</span></span>

- <span data-ttu-id="3b365-111">このコマンドレットは、Windows 7 または Windows 2008 R2 および今後のリリースの Windows での、Windows PowerShell 3.0 または今後のリリースの Windows PowerShell で機能します。</span><span class="sxs-lookup"><span data-stu-id="3b365-111">This cmdlet runs on Windows PowerShell 3.0 or later releases of Windows PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>
- <span data-ttu-id="3b365-112">Name パラメーターで指定したモジュールが、Install-Module によってインストールされていない場合はエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3b365-112">If the module that you specify with the Name parameter was not installed by using Install-Module, an error occurs.</span></span> <span data-ttu-id="3b365-113">Update-Module は、Install-Module を使用してオンライン ギャラリーからインストールしたモジュールについてのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b365-113">You can only run Update-Module on modules that you installed from the online gallery by running Install-Module.</span></span>
- <span data-ttu-id="3b365-114">Update-Module が使用中のバイナリを更新しようとすると、問題が発生したプロセスを特定し、プロセスを停止してから Update-Module を再試行するように求めるエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="3b365-114">If Update-Module attempts to update binaries that are in use, Update-Module returns an error that identifies the problem processes, and informs the user to retry Update-Module after stopping the processes.</span></span>
- <span data-ttu-id="3b365-115">PowerShell 5.0 以降のバージョンでは、Update-Module がモジュールを更新するときに、モジュールの最新 (または指定した) バージョンが追加されるため、古いバージョンと新しいバージョンが同じディレクトリに並んで存在することになります。</span><span class="sxs-lookup"><span data-stu-id="3b365-115">On PowerShell 5.0 or newer versions, when Update-Module updates a module, it adds the latest (or specified) version of the module, so the older and newer versions are now side-by-side in the same directory.</span></span> <span data-ttu-id="3b365-116">これについては、理解しやすいようコマンドの出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="3b365-116">It would be useful to say so and to show an example of the output from these commands.</span></span>


## <a name="cmdlet-syntax"></a><span data-ttu-id="3b365-117">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="3b365-117">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Update-Module -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="3b365-118">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="3b365-118">Cmdlet online help reference</span></span>

[<span data-ttu-id="3b365-119">Update-Module</span><span class="sxs-lookup"><span data-stu-id="3b365-119">Update-Module</span></span>](http://go.microsoft.com/fwlink/?LinkID=398576)


## <a name="example-commands"></a><span data-ttu-id="3b365-120">コマンド例</span><span class="sxs-lookup"><span data-stu-id="3b365-120">Example commands</span></span>

```powershell
PS C:\\windows\\system32> Update-Module -Name ContosoServer -RequiredVersion 1.5
PS C:\\windows\\system32> Get-Module -ListAvailable -Name ContosoServer | Format-List Name,Version,ModuleBase
Name : ContosoServer
Version : 2.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\2.0
Name : ContosoServer
Version : 1.5
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.5
Name : ContosoServer
Version : 1.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.0
PS C:\\windows\\system32> Get-InstalledModule
Version Name Repository Description
------- ---- ---------- -----------
1.0 ContosoServer MSPSGallery ContosoServer module
1.5 ContosoServer MSPSGallery ContosoServer module
2.0 ContosoServer MSPSGallery ContosoServer module
PS C:\\windows\\system32> Update-Module -Name ContosoServer
PS C:\\windows\\system32> Get-Module -ListAvailable -Name ContosoServer | Format-List Name,Version,ModuleBase
Name : ContosoServer
Version : 2.8.1
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\2.8.1
Name : ContosoServer
Version : 2.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\2.0
Name : ContosoServer
Version : 1.5
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.5
Name : ContosoServer
Version : 1.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.0
PS C:\\windows\\system32> Get-InstalledModule
Version Name Repository Description
------- ---- ---------- -----------
1.0 ContosoServer MSPSGallery ContosoServer module
1.5 ContosoServer MSPSGallery ContosoServer module
2.0 ContosoServer MSPSGallery ContosoServer module
2.8.1 ContosoServer MSPSGallery ContosoServer module
```


###  <a name="update-the-testdepwithnestedrequiredmodules1-module-with-dependencies"></a><span data-ttu-id="3b365-121">依存関係を持つ TestDepWithNestedRequiredModules1 モジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="3b365-121">Update the TestDepWithNestedRequiredModules1 module with dependencies.</span></span>
```powershell
Find-Module -Name TestDepWithNestedRequiredModules1 -Repository LocalRepo -AllVersions

Version    Name                                Repository  Description
-------    ----                                ----------  -----------
1.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module
2.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module

Update-Module -Name TestDepWithNestedRequiredModules1 -RequiredVersion 2.0
Get-InstalledModule

Version    Name                                Repository  Description
-------    ----                                ----------  -----------
1.0        NestedRequiredModule1               LocalRepo   NestedRequiredModule1 module
2.5        NestedRequiredModule2               LocalRepo   NestedRequiredModule2 module
2.0        NestedRequiredModule3               LocalRepo   NestedRequiredModule3 module
2.5        NestedRequiredModule3               LocalRepo   NestedRequiredModule3 module
1.0        RequiredModule1                     LocalRepo   RequiredModule1 module
2.5        RequiredModule2                     LocalRepo   RequiredModule2 module
2.0        RequiredModule3                     LocalRepo   RequiredModule3 module
2.5        RequiredModule3                     LocalRepo   RequiredModule3 module
1.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module
2.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module
```

