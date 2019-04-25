---
title: PSModulePath インストール パスの変更 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082211"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="9e09b-102">PSModulePath インストール パスを変更する</span><span class="sxs-lookup"><span data-stu-id="9e09b-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="9e09b-103">`PSModulePath`環境変数には、ディスクにインストールされているモジュールの場所へのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="9e09b-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="9e09b-104">Windows PowerShell では、この変数を使用して、ユーザーは、モジュールへの完全パスを指定しない場合に、モジュールを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9e09b-104">Windows PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="9e09b-105">この変数のパスが表示される順序で検索されます。</span><span class="sxs-lookup"><span data-stu-id="9e09b-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="9e09b-106">Windows PowerShell の起動時、`PSModulePath`で既定値は、次のシステム環境変数として作成されます:`$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`します。</span><span class="sxs-lookup"><span data-stu-id="9e09b-106">When Windows PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="9e09b-107">PSModulePath 変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="9e09b-107">To view the PSModulePath variable</span></span>

<span data-ttu-id="9e09b-108">指定されているパスを表示する、`PSModulePath`変数、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="9e09b-108">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="9e09b-109">PSModulePath 変数に場所を追加</span><span class="sxs-lookup"><span data-stu-id="9e09b-109">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="9e09b-110">パスをこの変数を追加するには、次のメソッドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e09b-110">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="9e09b-111">現在のセッションでのみ使用できる一時的な値を追加するには、コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e09b-111">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- <span data-ttu-id="9e09b-112">セッションが開かれるたびに使用できる永続的な値を追加するには、Windows PowerShell プロファイルに、次のコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e09b-112">To add a persistent value that is available whenever a session is opened, add the following command to a Windows PowerShell profile:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  <span data-ttu-id="9e09b-113">プロファイルの詳細については、次を参照してください。 [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) 、Microsoft TechNet ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="9e09b-113">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) in the Microsoft TechNet library.</span></span>

- <span data-ttu-id="9e09b-114">レジストリに永続的な変数を追加するには、という新しいユーザーの環境変数を作成`PSModulePath`で環境変数エディターを使用して、**システム プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9e09b-114">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="9e09b-115">スクリプトを使用して永続的な変数を追加するには、使用、 **SetEnvironmentVariable**環境クラスのメソッド。</span><span class="sxs-lookup"><span data-stu-id="9e09b-115">To add a persistent variable by using a script, use the **SetEnvironmentVariable** method on the Environment class.</span></span> <span data-ttu-id="9e09b-116">たとえば、次のスクリプト パスに追加します"C:\Program Files\Fabrikam\Module コンピューターの PSModulePath 環境変数の値にします。</span><span class="sxs-lookup"><span data-stu-id="9e09b-116">For example, the following script adds the "C:\Program Files\Fabrikam\Module path to the value of the PSModulePath environment variable for the computer.</span></span> <span data-ttu-id="9e09b-117">ユーザーの PSModulePath 環境変数には、パスを追加するには、「ユーザー」、ターゲットを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e09b-117">To add the path to the user PSModulePath environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="9e09b-118">PSModulePath の場所を削除するには</span><span class="sxs-lookup"><span data-stu-id="9e09b-118">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="9e09b-119">同様のメソッドを使用して、変数からのパスを削除することができます。 たとえば、`$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"`が削除されます、 **c:\ModulePath** 、現在のセッションからのパス。</span><span class="sxs-lookup"><span data-stu-id="9e09b-119">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e09b-120">参照</span><span class="sxs-lookup"><span data-stu-id="9e09b-120">See Also</span></span>

[<span data-ttu-id="9e09b-121">Windows PowerShell モジュールの記述</span><span class="sxs-lookup"><span data-stu-id="9e09b-121">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
