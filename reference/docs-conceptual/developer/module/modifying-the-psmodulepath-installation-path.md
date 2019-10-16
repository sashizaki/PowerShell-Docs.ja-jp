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
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360671"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="ea465-102">PSModulePath インストール パスを変更する</span><span class="sxs-lookup"><span data-stu-id="ea465-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="ea465-103">@No__t 0 環境変数は、ディスクにインストールされているモジュールの場所へのパスを格納します。</span><span class="sxs-lookup"><span data-stu-id="ea465-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="ea465-104">ユーザーがモジュールへの完全パスを指定していない場合、Windows PowerShell はこの変数を使用してモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="ea465-104">Windows PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="ea465-105">この変数のパスは、表示されている順序で検索されます。</span><span class="sxs-lookup"><span data-stu-id="ea465-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="ea465-106">Windows PowerShell が起動すると、`PSModulePath` は、次の既定値を持つシステム環境変数として作成されます: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`。</span><span class="sxs-lookup"><span data-stu-id="ea465-106">When Windows PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="ea465-107">PSModulePath 変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="ea465-107">To view the PSModulePath variable</span></span>

<span data-ttu-id="ea465-108">@No__t 0 変数に指定されているパスを表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea465-108">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="ea465-109">PSModulePath 変数に場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="ea465-109">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="ea465-110">この変数にパスを追加するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea465-110">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="ea465-111">現在のセッションでのみ使用できる一時的な値を追加するには、コマンドラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea465-111">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- <span data-ttu-id="ea465-112">セッションが開かれるたびに使用できる永続的な値を追加するには、次のコマンドを Windows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea465-112">To add a persistent value that is available whenever a session is opened, add the following command to a Windows PowerShell profile:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  <span data-ttu-id="ea465-113">プロファイルの詳細については、Microsoft TechNet ライブラリの「 [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea465-113">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) in the Microsoft TechNet library.</span></span>

- <span data-ttu-id="ea465-114">永続変数をレジストリに追加するには、**システムのプロパティ** ダイアログボックスの 環境変数エディター を使用して、`PSModulePath` という名前の新しいユーザー環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="ea465-114">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="ea465-115">スクリプトを使用して永続変数を追加するには、環境クラスで**SetEnvironmentVariable**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea465-115">To add a persistent variable by using a script, use the **SetEnvironmentVariable** method on the Environment class.</span></span> <span data-ttu-id="ea465-116">たとえば、次のスクリプトは、"C:\Program Files\Fabrikam\Module path をコンピューターの PSModulePath 環境変数の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="ea465-116">For example, the following script adds the "C:\Program Files\Fabrikam\Module path to the value of the PSModulePath environment variable for the computer.</span></span> <span data-ttu-id="ea465-117">このパスを user PSModulePath 環境変数に追加するには、ターゲットを "User" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea465-117">To add the path to the user PSModulePath environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="ea465-118">PSModulePath から場所を削除するには</span><span class="sxs-lookup"><span data-stu-id="ea465-118">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="ea465-119">同様の方法を使用して、変数からパスを削除できます。たとえば、`$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` は、現在のセッションから**C:\ モジュールパス**パスを削除します。</span><span class="sxs-lookup"><span data-stu-id="ea465-119">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea465-120">参照</span><span class="sxs-lookup"><span data-stu-id="ea465-120">See Also</span></span>

[<span data-ttu-id="ea465-121">Windows PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="ea465-121">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
