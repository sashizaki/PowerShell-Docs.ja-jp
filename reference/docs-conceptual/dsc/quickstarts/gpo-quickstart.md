---
ms.date: 07/09/2019
keywords: DSC, GPO, PowerShell, 構成, セットアップ
title: クイック スタート - グループ ポリシーを DSC に変換する
ms.openlocfilehash: a9ce9cecd71fe00d2908024a3ee474ec836af3ba
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808250"
---
# <a name="quickstart-convert-group-policy-into-dsc"></a><span data-ttu-id="6c039-103">クイック スタート:グループ ポリシーを DSC に変換する</span><span class="sxs-lookup"><span data-stu-id="6c039-103">Quickstart: Convert Group Policy into DSC</span></span>

> <span data-ttu-id="6c039-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c039-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6c039-105">グループ ポリシーまたは Azure Security Center ベースラインから DSC 構成を生成できます。</span><span class="sxs-lookup"><span data-stu-id="6c039-105">You can generate a DSC configuration from a Group Policy or Azure Security Center baseline.</span></span> <span data-ttu-id="6c039-106">[BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) モジュールには、このタスクを達成するために、次のコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c039-106">The [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) module includes the following commands for accomplishing this task.</span></span>

- <span data-ttu-id="6c039-107">`ConvertFrom-GPO` - グループ ポリシーを変換します。ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c039-107">`ConvertFrom-GPO` - Converts Group Policies, stored as files.</span></span> <span data-ttu-id="6c039-108">1 つの構成に結合される複数のポリシーを含むディレクトリを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c039-108">You can also specify a directory containing multiple policies that will be combined into one Configuration.</span></span>
  - <span data-ttu-id="6c039-109">ご利用の環境でグループ ポリシーをエクスポートするには、[Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) コマンドレットを使用するか、「[Export a GPO to a File](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file)」 (GPO をファイルエクスポートする) の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6c039-109">To export Group Policies in your environment, use the [Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) cmdlet, or follow the instructions in [Export a GPO to a File](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span></span>
- <span data-ttu-id="6c039-110">`ConvertFrom-SCM` - セキュリティ コンプライアンス マネージャー ベースラインを変換します。`.xml` ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c039-110">`ConvertFrom-SCM` - Converts Security Compliance Manager baselines, stored as `.xml` files.</span></span>
- <span data-ttu-id="6c039-111">`ConvertFrom-ASC` - Azure Security Center ベースラインを変換します。`.json` ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c039-111">`ConvertFrom-ASC` - Converts Azure Security Center baselines, stored as `.json` files.</span></span>
- <span data-ttu-id="6c039-112">`Merge-GPOs` - ターゲット コンピューターに適用されたグループ ポリシーを変換します。</span><span class="sxs-lookup"><span data-stu-id="6c039-112">`Merge-GPOs` - Converts Group Policies applied to a target computer.</span></span>

<span data-ttu-id="6c039-113">上述のコマンドレットによって、ベースラインが DSC `.mof` ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="6c039-113">The cmdlets listed above convert a baseline into a DSC `.mof` file.</span></span> <span data-ttu-id="6c039-114">編集して再コンパイルすることができる、構成スクリプト (`.ps1`) を出力することを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c039-114">You can also choose to output a Configuration script (`.ps1`), that you can edit and recompile.</span></span> <span data-ttu-id="6c039-115">このコマンドレットでは、不足しているリソースや重複したリソース ブロックに対する複雑なエラーを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="6c039-115">The cmdlets detect compilation errors for missing resources, or duplicate resource blocks.</span></span> <span data-ttu-id="6c039-116">複雑なエラーの原因になるリソース ブロックは、コメント アウトされます。</span><span class="sxs-lookup"><span data-stu-id="6c039-116">Resource blocks that would cause compilation errors are commented out.</span></span>

<span data-ttu-id="6c039-117">次の例では、[Microsoft セキュリティ ベースライン](https://www.microsoft.com/en-us/download/details.aspx?id=55319)が DSC 構成スクリプト (`.ps1`) と `.mof` ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="6c039-117">The following example converts a [Microsoft Security Baseline](https://www.microsoft.com/en-us/download/details.aspx?id=55319) into a DSC configuration script (`.ps1`) and `.mof` file.</span></span>

```powershell
Install-Module BaselineManagement
Import-Module BaselineManagement
ConvertFrom-GPO -Path '.\Windows 10 Version 1903 and Windows Server Version 1903 Security Baseline\GPOs\' -OutputConfigurationScript
```

<span data-ttu-id="6c039-118">コマンドを実行した後、現在のパスの下に作成された既定の "Output" ディレクトリに 2 つのファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c039-118">After running the commands, you see two files in the default "Output" directory created under your current path.</span></span>

```powershell
Get-ChildItem -Path .\Output
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----         7/9/2019   9:35 AM   227.37KB DSCFromGPO.ps1
-a----         7/9/2019   9:35 AM   410.03KB localhost.mof
```

<span data-ttu-id="6c039-119">管理ノードごとに、次の 2 つのモジュールも必要です。</span><span class="sxs-lookup"><span data-stu-id="6c039-119">Each managed node will also need the following two modules:</span></span>

- [<span data-ttu-id="6c039-120">SecurityPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="6c039-120">SecurityPolicyDSC</span></span>](https://www.powershellgallery.com/packages/SecurityPolicyDsc)
- [<span data-ttu-id="6c039-121">AuditPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="6c039-121">AuditPolicyDSC</span></span>](https://www.powershellgallery.com/packages/AuditPolicyDsc)

> [!NOTE]
> <span data-ttu-id="6c039-122">**BaselineManagement** は、Microsoft からではなく、プロジェクト保守管理者からのコミュニティ ソリューションに対するサポートを、DSC でより検索しやすくするように、コミュニティによって開発されたソリューションです。</span><span class="sxs-lookup"><span data-stu-id="6c039-122">**BaselineManagement** is a solution developed by the community to make DSC more discoverable for Support for community solutions come from the project maintainers and not from Microsoft.</span></span> <span data-ttu-id="6c039-123">[GitHub](https://github.com/microsoft/BaselineManagement) 上で **BaselineManagement** に対して新しい問題を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6c039-123">You can open a new issue for **BaselineManagement** on [GitHub](https://github.com/microsoft/BaselineManagement).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c039-124">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6c039-124">Next steps</span></span>

- <span data-ttu-id="6c039-125">構成スクリプトを Azure Automation State Configuration にアップロードするには、[作業の開始](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c039-125">To upload your configuration script into Azure Automation State Configuration, see [Getting Started](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span></span>
- <span data-ttu-id="6c039-126">**SecurityPolicyDSC** モジュールと **AuditPolicyDSC** モジュールを [Automation Account](/azure/automation/shared-resources/modules) に追加します。</span><span class="sxs-lookup"><span data-stu-id="6c039-126">Add the **SecurityPolicyDSC** and **AuditPolicyDSC** modules to your [Automation Account](/azure/automation/shared-resources/modules).</span></span>
- <span data-ttu-id="6c039-127">「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。</span><span class="sxs-lookup"><span data-stu-id="6c039-127">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
