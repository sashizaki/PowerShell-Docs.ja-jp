---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 の既知の問題
ms.openlocfilehash: e59ea1b9a5282eb5727a37ce605c71724a219827
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084965"
---
# <a name="known-issues-in-wmf-51"></a><span data-ttu-id="e9926-103">WMF 5.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="e9926-103">Known Issues in WMF 5.1</span></span>

> [!Note]
> <span data-ttu-id="e9926-104">この情報は変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e9926-104">This information is subject to change.</span></span>

## <a name="starting-powershell-shortcut-as-administrator"></a><span data-ttu-id="e9926-105">PowerShell ショートカットを管理者として起動する</span><span class="sxs-lookup"><span data-stu-id="e9926-105">Starting PowerShell shortcut as Administrator</span></span>

<span data-ttu-id="e9926-106">WMF がインストールされている場合に、管理者としてショートカットから PowerShell を起動しようとすると、"未定義のエラー" メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e9926-106">Upon installing WMF, if you try to start PowerShell as administrator from the shortcut, you may get an "Unspecified error" message.</span></span>
<span data-ttu-id="e9926-107">管理者以外でショートカットを開き直すと、その後は管理者としても動作します。</span><span class="sxs-lookup"><span data-stu-id="e9926-107">Reopen the shortcut as non-administrator and the shortcut now works even as administrator.</span></span>

## <a name="pester"></a><span data-ttu-id="e9926-108">Pester</span><span class="sxs-lookup"><span data-stu-id="e9926-108">Pester</span></span>

<span data-ttu-id="e9926-109">このリリースでは、Nano Server で Pester を利用するとき、2 つの問題に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9926-109">In this release, there are two issues you should be aware of when using Pester on Nano Server:</span></span>

- <span data-ttu-id="e9926-110">Pester 自体にテストを実行すると、FULL CLR と CORE CLR の違いに起因し、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e9926-110">Running tests against Pester itself can result in some failures because of differences between FULL CLR and CORE CLR.</span></span> <span data-ttu-id="e9926-111">具体的には、Validate メソッドが XmlDocument 型で利用できません。</span><span class="sxs-lookup"><span data-stu-id="e9926-111">In particular, the Validate method is not available on the XmlDocument type.</span></span> <span data-ttu-id="e9926-112">NUnit 出力ログのスキーマの検証を試行するテストが 6 つありますが、これでエラーが発生することが確認されています。</span><span class="sxs-lookup"><span data-stu-id="e9926-112">Six tests which attempt to validate the schema of the NUnit output logs are known to fail.</span></span>
- <span data-ttu-id="e9926-113">現在、コード カバレッジの 1 つでエラーが発生します。*WindowsFeature* DSC リソースが Nano Server にないためです。</span><span class="sxs-lookup"><span data-stu-id="e9926-113">One Code Coverage test fails currently because the *WindowsFeature* DSC Resource does not exist in Nano Server.</span></span> <span data-ttu-id="e9926-114">しかしながら、以上のエラーは一般的に無害であり、無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="e9926-114">However, these failures are generally benign and can safely be ignored.</span></span>

## <a name="operation-validation"></a><span data-ttu-id="e9926-115">操作検証</span><span class="sxs-lookup"><span data-stu-id="e9926-115">Operation Validation</span></span>

- <span data-ttu-id="e9926-116">Microsoft.PowerShell.Operation.Validation モジュールの場合、ヘルプ URI が動作しないため、`Update-Help` は失敗する</span><span class="sxs-lookup"><span data-stu-id="e9926-116">`Update-Help` fails for Microsoft.PowerShell.Operation.Validation module due to non-working help URI</span></span>

## <a name="dsc-after-uninstall-wmf"></a><span data-ttu-id="e9926-117">WMF をアンインストールした後の DSC</span><span class="sxs-lookup"><span data-stu-id="e9926-117">DSC after uninstall WMF</span></span>

- <span data-ttu-id="e9926-118">WMF をアンインストールしても、構成フォルダーから DSC の MOF ドキュメントは削除されません。</span><span class="sxs-lookup"><span data-stu-id="e9926-118">Uninstalling WMF does not delete DSC MOF documents from the configuration folder.</span></span> <span data-ttu-id="e9926-119">MOF ドキュメントに、以前のシステムで使用できない新しいプロパティが含まれている場合、DSC は正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="e9926-119">DSC won't work properly if the MOF documents contain newer properties which are not available on the older systems.</span></span> <span data-ttu-id="e9926-120">この場合は、管理者特権の PowerShell コンソールから次のスクリプトを実行して、DSC の状態をクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="e9926-120">In this case, run the following script from elevated PowerShell console to clean up the DSC states.</span></span>

  ```powershell
    $PreviousDSCStates = @("$env:windir\system32\configuration\*.mof",
            "$env:windir\system32\configuration\*.mof.checksum",
            "$env:windir\system32\configuration\PartialConfiguration\*.mof",
            "$env:windir\system32\configuration\PartialConfiguration\*.mof.checksum"
           )
    $PreviousDSCStates | Remove-Item -ErrorAction SilentlyContinue -Verbose
  ```

## <a name="jea-virtual-accounts"></a><span data-ttu-id="e9926-121">JEA 仮想アカウント</span><span class="sxs-lookup"><span data-stu-id="e9926-121">JEA Virtual Accounts</span></span>

<span data-ttu-id="e9926-122">WMF 5.0 で仮想アカウントを使用するように構成された JEA エンドポイントおよびセッション構成は、WMF 5.1 へのアップグレード後に仮想アカウントを使用するように構成されません。</span><span class="sxs-lookup"><span data-stu-id="e9926-122">JEA endpoints and session configurations configured to use virtual accounts in WMF 5.0 will not be configured to use a virtual account after upgrading to WMF 5.1.</span></span>
<span data-ttu-id="e9926-123">これは、JEA セッションで実行されるコマンドは一時管理者アカウントではなく接続しているユーザーの ID で実行されるため、昇格された特権を必要とするコマンドをユーザーが実行できない可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e9926-123">This means that commands run in JEA sessions will run under the connecting user's identity instead of a temporary administrator account, potentially preventing the user from running commands which require elevated privileges.</span></span>
<span data-ttu-id="e9926-124">仮想アカウントを復元するには、仮想アカウントを使用するすべてのセッション構成を登録解除し、再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9926-124">To restore the virtual accounts, you need to unregister and re-register any session configurations that use virtual accounts.</span></span>

```powershell
# Find the JEA endpoint by its name
$jea = Get-PSSessionConfiguration -Name MyJeaEndpoint

# Copy the cached PSSC file so it can be re-registered
$pssc = Copy-Item $jea.ConfigFilePath $env:temp -PassThru

# Unregister the current PSSC
Unregister-PSSessionConfiguration -Name $jea.Name

# Re-register the PSSC
Register-PSSessionConfiguration -Name $jea.Name -Path $pssc.FullName -Force

# Ensure the access policies remain the same
Set-PSSessionConfiguration -Name $newjea.Name -SecurityDescriptorSddl $jea.SecurityDescriptorSddl
```