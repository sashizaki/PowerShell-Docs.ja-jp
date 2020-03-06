---
title: PSModulePath のインストールパスを変更する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: b176d8439025ac132962859f79e72ae6f9703e82
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78405049"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="3301c-102">PSModulePath インストール パスを変更する</span><span class="sxs-lookup"><span data-stu-id="3301c-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="3301c-103">`PSModulePath` 環境変数には、ディスクにインストールされているモジュールの場所へのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3301c-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="3301c-104">PowerShell では、モジュールへの完全パスをユーザーが指定しない場合、この変数を使用してモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="3301c-104">PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="3301c-105">この変数のパスは、表示されている順序で検索されます。</span><span class="sxs-lookup"><span data-stu-id="3301c-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="3301c-106">PowerShell を起動すると、`PSModulePath` がシステム環境変数として作成されます。既定値は、Windows の場合は `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules`、Linux または Mac の場合は `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules`、Windows PowerShell の場合は `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="3301c-106">When PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` on Windows and `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` on Linux or Mac, and `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` for Windows PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="3301c-107">ユーザー固有の**CurrentUser**の場所は、ユーザープロファイル内の**ドキュメント**の場所にある `WindowsPowerShell\Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3301c-107">The user-specific **CurrentUser** location is the `WindowsPowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="3301c-108">その場所の特定のパスは、Windows のバージョンと、フォルダーリダイレクトを使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3301c-108">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="3301c-109">既定では、Windows 10 の場合、その場所は `$HOME\Documents\WindowsPowerShell\Modules`です。</span><span class="sxs-lookup"><span data-stu-id="3301c-109">By default, on Windows 10, that location is `$HOME\Documents\WindowsPowerShell\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="3301c-110">PSModulePath 変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="3301c-110">To view the PSModulePath variable</span></span>

<span data-ttu-id="3301c-111">`PSModulePath` 変数に指定されているパスを表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3301c-111">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="3301c-112">PSModulePath 変数に場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="3301c-112">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="3301c-113">この変数にパスを追加するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3301c-113">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="3301c-114">現在のセッションでのみ使用できる一時的な値を追加するには、コマンドラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3301c-114">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- <span data-ttu-id="3301c-115">セッションが開かれるたびに使用できる永続的な値を追加するには、上記のコマンドを PowerShell プロファイルファイル (`$PROFILE`) に追加し ></span><span class="sxs-lookup"><span data-stu-id="3301c-115">To add a persistent value that is available whenever a session is opened, add the above command to a PowerShell profile file (`$PROFILE`)></span></span>

  <span data-ttu-id="3301c-116">プロファイルの詳細については、「[about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3301c-116">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

- <span data-ttu-id="3301c-117">永続変数をレジストリに追加するには、**システムのプロパティ** ダイアログボックスの 環境変数エディター を使用して、`PSModulePath` という名前の新しいユーザー環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="3301c-117">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="3301c-118">スクリプトを使用して永続変数を追加する[には、](https://docs.microsoft.com/dotnet/api/system.environment) [SetEnvironmentVariable](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable)クラスの .net メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3301c-118">To add a persistent variable by using a script, use the .Net method [SetEnvironmentVariable](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable) on the [System.Environment](https://docs.microsoft.com/dotnet/api/system.environment) class.</span></span> <span data-ttu-id="3301c-119">たとえば、次のスクリプトは、コンピューターの `PSModulePath` 環境変数の値に `C:\Program Files\Fabrikam\Module` パスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3301c-119">For example, the following script adds the `C:\Program Files\Fabrikam\Module` path to the value of the `PSModulePath` environment variable for the computer.</span></span> <span data-ttu-id="3301c-120">ユーザー `PSModulePath` 環境変数にパスを追加するには、ターゲットを "User" に設定します。</span><span class="sxs-lookup"><span data-stu-id="3301c-120">To add the path to the user `PSModulePath` environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="3301c-121">PSModulePath から場所を削除するには</span><span class="sxs-lookup"><span data-stu-id="3301c-121">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="3301c-122">同様のメソッドを使用して、変数からパスを削除できます。たとえば、`$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` によって、現在のセッションから**C:\ モジュールパス**パスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3301c-122">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="3301c-123">参照</span><span class="sxs-lookup"><span data-stu-id="3301c-123">See Also</span></span>

[<span data-ttu-id="3301c-124">Windows PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="3301c-124">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="3301c-125">about_Modules</span><span class="sxs-lookup"><span data-stu-id="3301c-125">about_Modules</span></span>](/powershell/module/microsoft.powershell.core/about/about_modules)
