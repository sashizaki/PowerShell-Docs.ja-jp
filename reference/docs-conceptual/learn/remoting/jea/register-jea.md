---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA の構成の登録
ms.openlocfilehash: c85eddea2196e4db4bbeea54bde11074f3d1c927
ms.sourcegitcommit: e894ed833cef57967cdaf002f8c883f66864e836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2019
ms.locfileid: "70017713"
---
# <a name="registering-jea-configurations"></a><span data-ttu-id="ffe5b-103">JEA の構成の登録</span><span class="sxs-lookup"><span data-stu-id="ffe5b-103">Registering JEA Configurations</span></span>

<span data-ttu-id="ffe5b-104">[ロール機能](role-capabilities.md)と[セッション構成ファイル](session-configurations.md)を作成したら、最後の手順は、JEA エンドポイントを登録することです。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-104">Once you have your [role capabilities](role-capabilities.md) and [session configuration file](session-configurations.md) created, the last step is to register the JEA endpoint.</span></span> <span data-ttu-id="ffe5b-105">システムに JEA エンドポイントを登録すると、ユーザーおよび自動化エンジンでエンドポイントが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-105">Registering the JEA endpoint with the system makes the endpoint available for use by users and automation engines.</span></span>

## <a name="single-machine-configuration"></a><span data-ttu-id="ffe5b-106">単一コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="ffe5b-106">Single machine configuration</span></span>

<span data-ttu-id="ffe5b-107">小規模な環境の場合、[Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration) コマンドレットを使ってセッション構成ファイルを登録することにより、JEA を展開できます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-107">For small environments, you can deploy JEA by registering the session configuration file using the [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration) cmdlet.</span></span>

<span data-ttu-id="ffe5b-108">作業を開始する前に、次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-108">Before you begin, ensure that the following prerequisites have been met:</span></span>

- <span data-ttu-id="ffe5b-109">1 つ以上のロールが作成されて、PowerShell モジュールの **RoleCapabilities** フォルダーに配置されていること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-109">One or more roles has been created and placed in the **RoleCapabilities** folder of a PowerShell module.</span></span>
- <span data-ttu-id="ffe5b-110">セッション構成ファイルの作成とテストが済んでいること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-110">A session configuration file has been created and tested.</span></span>
- <span data-ttu-id="ffe5b-111">JEA 構成を登録するユーザーに、システムに対する管理者権限があること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-111">The user registering the JEA configuration has administrator rights on the system.</span></span>
- <span data-ttu-id="ffe5b-112">JEA エンドポイントの名前を選択していること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-112">You've selected a name for your JEA endpoint.</span></span>

<span data-ttu-id="ffe5b-113">ユーザーが JEA を使ってシステムに接続するときに、JEA エンドポイントの名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-113">The name of the JEA endpoint is required when users connect to the system using JEA.</span></span> <span data-ttu-id="ffe5b-114">[Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットは、システム上のエンドポイントの名前を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-114">The [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet lists the names of the endpoints on a system.</span></span> <span data-ttu-id="ffe5b-115">`microsoft` で始まるエンドポイントは、通常、Windows に付属しています。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-115">Endpoints that start with `microsoft` are typically shipped with Windows.</span></span> <span data-ttu-id="ffe5b-116">`microsoft.powershell` エンドポイントは、リモート PowerShell エンドポイントに接続するときに使われる既定のエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-116">The `microsoft.powershell` endpoint is the default endpoint used when connecting to a remote PowerShell endpoint.</span></span>

```powershell
Get-PSSessionConfiguration | Select-Object Name
```

```Output
Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

<span data-ttu-id="ffe5b-117">次のコマンドを実行してエンドポイントを登録します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-117">Run the following command to register the endpoint.</span></span>

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="ffe5b-118">前のコマンドにより、システム上の WinRM サービスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-118">The previous command restarts the WinRM service on the system.</span></span> <span data-ttu-id="ffe5b-119">これにより、すべての PowerShell リモート処理セッションおよび実行中の DSC 構成が終了されます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-119">This terminates all PowerShell remoting sessions and any ongoing DSC configurations.</span></span> <span data-ttu-id="ffe5b-120">業務の中断を防ぐため、コマンドを実行する前に、運用環境のコンピューターをオフラインにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-120">We recommended you take production machines offline before running the command to avoid disrupting business operations.</span></span>

<span data-ttu-id="ffe5b-121">登録すると、すぐに [JEA を使用](using-jea.md)できます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-121">After registration, you're ready to [use JEA](using-jea.md).</span></span> <span data-ttu-id="ffe5b-122">セッション構成ファイルは、いつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-122">You may delete the session configuration file at any time.</span></span> <span data-ttu-id="ffe5b-123">構成ファイルは、エンドポイントの登録後には使用されません。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-123">The configuration file isn't used after registration of the endpoint.</span></span>

## <a name="multi-machine-configuration-with-dsc"></a><span data-ttu-id="ffe5b-124">DSC での複数コンピューター構成</span><span class="sxs-lookup"><span data-stu-id="ffe5b-124">Multi-machine configuration with DSC</span></span>

<span data-ttu-id="ffe5b-125">JEA を複数のコンピューターに展開するときに、最も簡単な展開モデルでは JEA の [Desired State Configuration (DSC)](/powershell/dsc/overview) リソースを使用して、各コンピューターに JEA を迅速かつ一貫して展開します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-125">When deploying JEA on multiple machines, the simplest deployment model uses the JEA [Desired State Configuration (DSC)](/powershell/dsc/overview) resource to quickly and consistently deploy JEA on each machine.</span></span>

<span data-ttu-id="ffe5b-126">DSC で JEA を展開するには、次の前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-126">To deploy JEA with DSC, ensure the following prerequisites are met:</span></span>

- <span data-ttu-id="ffe5b-127">1 つまたは複数のロール機能が作成され、PowerShell モジュールに追加されていること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-127">One or more role capabilities have been authored and added to a PowerShell module.</span></span>
- <span data-ttu-id="ffe5b-128">ロールを含む PowerShell モジュールが、各コンピューターからアクセスできる (読み取り専用の) ファイル共有に格納されていること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-128">The PowerShell module containing the roles is stored on a (read-only) file share accessible by each machine.</span></span>
- <span data-ttu-id="ffe5b-129">セッション構成の設定が決定されていること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-129">Settings for the session configuration have been determined.</span></span> <span data-ttu-id="ffe5b-130">JEA DSC リソースを使うときは、セッション構成ファイルを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-130">You don't need to create a session configuration file when using the JEA DSC resource.</span></span>
- <span data-ttu-id="ffe5b-131">各コンピューターで管理操作ができる、またはコンピューターの管理に使われる DSC プル サーバーにアクセスできる資格情報があること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-131">You have credentials that allow administrative actions on each machine or access to the DSC pull server used to manage the machines.</span></span>
- <span data-ttu-id="ffe5b-132">[JEA DSC リソース](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource)をダウンロードしてあること。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-132">You've downloaded the [JEA DSC resource](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource).</span></span>

<span data-ttu-id="ffe5b-133">ターゲット コンピューターまたはプル サーバー上で、JEA エンドポイント用の DSC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-133">Create a DSC configuration for your JEA endpoint on a target machine or pull server.</span></span> <span data-ttu-id="ffe5b-134">この構成では、**JustEnoughAdministration** DSC リソースでセッション構成ファイルを定義し、**File** リソースでファイル共有からロール機能をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-134">In this configuration, the **JustEnoughAdministration** DSC resource defines the session configuration file and the **File** resource copies the role capabilities from the file share.</span></span>

<span data-ttu-id="ffe5b-135">DSC リソースを使って次のプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-135">The following properties are configurable using the DSC resource:</span></span>

- <span data-ttu-id="ffe5b-136">ロールの定義</span><span class="sxs-lookup"><span data-stu-id="ffe5b-136">Role Definitions</span></span>
- <span data-ttu-id="ffe5b-137">仮想アカウント グループ</span><span class="sxs-lookup"><span data-stu-id="ffe5b-137">Virtual account groups</span></span>
- <span data-ttu-id="ffe5b-138">グループ管理されたサービス アカウント名</span><span class="sxs-lookup"><span data-stu-id="ffe5b-138">Group-managed service account name</span></span>
- <span data-ttu-id="ffe5b-139">トランスクリプト ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="ffe5b-139">Transcript directory</span></span>
- <span data-ttu-id="ffe5b-140">ユーザー ドライブ</span><span class="sxs-lookup"><span data-stu-id="ffe5b-140">User drive</span></span>
- <span data-ttu-id="ffe5b-141">条件付きアクセス規則</span><span class="sxs-lookup"><span data-stu-id="ffe5b-141">Conditional access rules</span></span>
- <span data-ttu-id="ffe5b-142">JEA セッションのスタートアップ スクリプト</span><span class="sxs-lookup"><span data-stu-id="ffe5b-142">Startup scripts for the JEA session</span></span>

<span data-ttu-id="ffe5b-143">DSC 構成でのこれらの各プロパティの構文は、PowerShell セッションの構成ファイルと一致しています。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-143">The syntax for each of these properties in a DSC configuration is consistent with the PowerShell session configuration file.</span></span>

<span data-ttu-id="ffe5b-144">一般的なサーバー メンテナンス モジュールの DSC 構成の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-144">Below is a sample DSC configuration for a general server maintenance module.</span></span> <span data-ttu-id="ffe5b-145">ここでは、ロール機能を含む有効な PowerShell モジュールが `\\myfileshare\JEA` ファイル共有に配置されていることを前提にしています。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-145">It assumes that a valid PowerShell module containing role capabilities is located on the `\\myfileshare\JEA` file share.</span></span>

```powershell
Configuration JEAMaintenance
{
    Import-DscResource -Module JustEnoughAdministration, PSDesiredStateConfiguration

    File MaintenanceModule
    {
        SourcePath = "\\myfileshare\JEA\ContosoMaintenance"
        DestinationPath = "C:\Program Files\WindowsPowerShell\Modules\ContosoMaintenance"
        Checksum = "SHA-256"
        Ensure = "Present"
        Type = "Directory"
        Recurse = $true
    }

    JeaEndpoint JEAMaintenanceEndpoint
    {
        EndpointName = "JEAMaintenance"
        RoleDefinitions = "@{ 'CONTOSO\JEAMaintenanceAuditors' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit' }; 'CONTOSO\JEAMaintenanceAdmins' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit', 'GeneralServerMaintenance-Admin' } }"
        TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
        DependsOn = '[File]MaintenanceModule'
    }
}
```

<span data-ttu-id="ffe5b-146">その後、[ローカル構成マネージャー](/powershell/dsc/managing-nodes/metaConfig)を直接呼び出すことにより、または[プル サーバーの構成](/powershell/dsc/pull-server/pullServer)を更新することにより、この構成がシステムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-146">Next, the configuration is applied on a system by directly invoking the [Local Configuration Manager](/powershell/dsc/managing-nodes/metaConfig) or updating the [pull server configuration](/powershell/dsc/pull-server/pullServer).</span></span>

<span data-ttu-id="ffe5b-147">DSC リソースを使うと、既定の **Microsoft.PowerShell** エンドポイントを置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-147">The DSC resource also allows you to replace the default **Microsoft.PowerShell** endpoint.</span></span> <span data-ttu-id="ffe5b-148">置き換えると、リソースで **Microsoft.PowerShell.Restricted** という名前のバックアップ エンドポイントが自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-148">When replaced, the resource automatically registers a backup endpoint named **Microsoft.PowerShell.Restricted**.</span></span> <span data-ttu-id="ffe5b-149">バックアップ エンドポイントには、リモート管理ユーザーとローカルの Administrators グループのメンバーのアクセスを許可する既定の WinRM ACL があります。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-149">The backup endpoint has the default WinRM ACL that allows Remote Management Users and local Administrators group members to access it.</span></span>

## <a name="unregistering-jea-configurations"></a><span data-ttu-id="ffe5b-150">JEA の構成の登録解除</span><span class="sxs-lookup"><span data-stu-id="ffe5b-150">Unregistering JEA configurations</span></span>

<span data-ttu-id="ffe5b-151">[Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) コマンドレットは、JEA エンドポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-151">The [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) cmdlet removes a JEA endpoint.</span></span> <span data-ttu-id="ffe5b-152">JEA エンドポイントの登録を解除すると、新しいユーザーがシステムに新しい JEA セッションを作成できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-152">Unregistering a JEA endpoint prevents new users from creating new JEA sessions on the system.</span></span> <span data-ttu-id="ffe5b-153">また、同じエンドポイント名を使って更新されたセッション構成ファイルを再登録することで、JEA 構成を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-153">It also allows you to update a JEA configuration by re-registering an updated session configuration file using the same endpoint name.</span></span>

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="ffe5b-154">JEA エンドポイントの登録を解除すると、WinRM サービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-154">Unregistering a JEA endpoint causes the WinRM service to restart.</span></span> <span data-ttu-id="ffe5b-155">これにより、他の PowerShell セッション、WMI 呼び出し、一部の管理ツールなど、実行中のほとんどのリモート管理操作が中断されます。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-155">This interrupts most remote management operations in progress, including other PowerShell sessions, WMI invocations, and some management tools.</span></span> <span data-ttu-id="ffe5b-156">計画されたメンテナンス期間中にのみ、PowerShell エンドポイントの登録を解除してください。</span><span class="sxs-lookup"><span data-stu-id="ffe5b-156">Only unregister PowerShell endpoints during planned maintenance windows.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffe5b-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="ffe5b-157">Next steps</span></span>

[<span data-ttu-id="ffe5b-158">JEA エンドポイントをテストする</span><span class="sxs-lookup"><span data-stu-id="ffe5b-158">Test the JEA endpoint</span></span>](using-jea.md)
