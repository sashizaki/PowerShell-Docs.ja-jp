---
ms.date: 09/13/2016
ms.topic: reference
title: PSModulePath インストール パスを変更する
description: PSModulePath インストール パスを変更する
ms.openlocfilehash: b802492bf9b49e8165e296817e3f80b9ae8265a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92661954"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="6c68e-103">PSModulePath インストール パスを変更する</span><span class="sxs-lookup"><span data-stu-id="6c68e-103">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="6c68e-104">環境変数には、 `PSModulePath` ディスクにインストールされているモジュールの場所へのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c68e-104">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="6c68e-105">PowerShell では、モジュールへの完全パスをユーザーが指定しない場合、この変数を使用してモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-105">PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="6c68e-106">この変数のパスは、表示されている順序で検索されます。</span><span class="sxs-lookup"><span data-stu-id="6c68e-106">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="6c68e-107">PowerShell を起動すると、 `PSModulePath` はシステム環境変数として作成されます。既定値は、windows の場合 `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` は、 `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` Linux または Mac の場合は、 `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` windows powershell の場合はです。</span><span class="sxs-lookup"><span data-stu-id="6c68e-107">When PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` on Windows and `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` on Linux or Mac, and `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` for Windows PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="6c68e-108">ユーザー固有の **CurrentUser** の場所は、 `WindowsPowerShell\Modules` ユーザープロファイル内の **ドキュメント** の場所にあるフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6c68e-108">The user-specific **CurrentUser** location is the `WindowsPowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="6c68e-109">その場所の特定のパスは、Windows のバージョンと、フォルダーリダイレクトを使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6c68e-109">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="6c68e-110">既定では、Windows 10 の場合、その場所は `$HOME\Documents\WindowsPowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="6c68e-110">By default, on Windows 10, that location is `$HOME\Documents\WindowsPowerShell\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="6c68e-111">PSModulePath 変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="6c68e-111">To view the PSModulePath variable</span></span>

<span data-ttu-id="6c68e-112">変数に指定されているパスを表示するには、 `PSModulePath` 次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-112">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="6c68e-113">PSModulePath 変数に場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="6c68e-113">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="6c68e-114">この変数にパスを追加するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-114">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="6c68e-115">現在のセッションでのみ使用できる一時的な値を追加するには、コマンドラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-115">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- <span data-ttu-id="6c68e-116">セッションが開かれるたびに使用できる永続的な値を追加するには、上記のコマンドを PowerShell プロファイルファイル () に追加し `$PROFILE` ></span><span class="sxs-lookup"><span data-stu-id="6c68e-116">To add a persistent value that is available whenever a session is opened, add the above command to a PowerShell profile file (`$PROFILE`)></span></span>

  <span data-ttu-id="6c68e-117">プロファイルの詳細については、「[about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c68e-117">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

- <span data-ttu-id="6c68e-118">永続変数をレジストリに追加するには、 `PSModulePath` [ **システムのプロパティ** ] ダイアログボックスの [環境変数エディター] を使用して、という名前の新しいユーザー環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-118">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="6c68e-119">スクリプトを使用して永続変数を追加する[には、](/dotnet/api/system.environment) [SetEnvironmentVariable](/dotnet/api/system.environment.setenvironmentvariable)クラスの .net メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-119">To add a persistent variable by using a script, use the .Net method [SetEnvironmentVariable](/dotnet/api/system.environment.setenvironmentvariable) on the [System.Environment](/dotnet/api/system.environment) class.</span></span> <span data-ttu-id="6c68e-120">たとえば、次のスクリプトは、 `C:\Program Files\Fabrikam\Module` コンピューターの環境変数の値にパスを追加し `PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="6c68e-120">For example, the following script adds the `C:\Program Files\Fabrikam\Module` path to the value of the `PSModulePath` environment variable for the computer.</span></span> <span data-ttu-id="6c68e-121">ユーザー環境変数にパスを追加するには、 `PSModulePath` ターゲットを "user" に設定します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-121">To add the path to the user `PSModulePath` environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="6c68e-122">PSModulePath から場所を削除するには</span><span class="sxs-lookup"><span data-stu-id="6c68e-122">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="6c68e-123">同様のメソッドを使用して、変数からパスを削除できます。たとえば、 `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` は、現在のセッションから **C:\ モジュールパス** パスを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c68e-123">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c68e-124">参照</span><span class="sxs-lookup"><span data-stu-id="6c68e-124">See Also</span></span>

[<span data-ttu-id="6c68e-125">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="6c68e-125">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="6c68e-126">about_Modules</span><span class="sxs-lookup"><span data-stu-id="6c68e-126">about_Modules</span></span>](/powershell/module/microsoft.powershell.core/about/about_modules)
