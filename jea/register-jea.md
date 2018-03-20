---
ms.date: 2017-06-12
author: rpsqrd
ms.topic: conceptual
keywords: "JEA, PowerShell, セキュリティ"
title: "JEA の構成の登録"
ms.openlocfilehash: d6b007fed97be6470bfe4cf4d42f72cb4edc3a45
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="registering-jea-configurations"></a><span data-ttu-id="52d1b-103">JEA の構成の登録</span><span class="sxs-lookup"><span data-stu-id="52d1b-103">Registering JEA Configurations</span></span>

> <span data-ttu-id="52d1b-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="52d1b-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="52d1b-105">[ロール機能](role-capabilities.md)と[セッション構成ファイル](session-configurations.md)を作成した後、JEA を使用できるようにする前の最後のステップは、JEA エンドポイントを登録することです。</span><span class="sxs-lookup"><span data-stu-id="52d1b-105">The last step before you can use JEA once you have your [role capabilities](role-capabilities.md) and [session configuration file](session-configurations.md) created is to register the JEA endpoint.</span></span>
<span data-ttu-id="52d1b-106">このプロセスでは、セッション構成情報をシステムに適用し、ユーザーおよび自動化エンジンがエンドポイントを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="52d1b-106">This process applies the session configuration information to the system and makes the endpoint available for use by users and automation engines.</span></span>

## <a name="single-machine-configuration"></a><span data-ttu-id="52d1b-107">単一コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="52d1b-107">Single machine configuration</span></span>

<span data-ttu-id="52d1b-108">小規模な環境の場合、[Register-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/register-pssessionconfiguration) コマンドレットを使ってセッション構成ファイルを登録することにより、JEA を展開できます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-108">For small environments, you can deploy JEA by registering the session configuration file using the [Register-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/register-pssessionconfiguration) cmdlet.</span></span>

<span data-ttu-id="52d1b-109">作業を開始する前に、次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52d1b-109">Before you begin, ensure that the following prerequisites have been met:</span></span>
- <span data-ttu-id="52d1b-110">1 つ以上のロールが作成されて、有効な PowerShell モジュールの "RoleCapabilities" フォルダーに配置されていること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-110">One or more roles has been created and placed in the 'RoleCapabilities' folder of a valid PowerShell module.</span></span>
- <span data-ttu-id="52d1b-111">セッション構成ファイルの作成とテストが済んでいること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-111">A session configuration file has been created and tested.</span></span>
- <span data-ttu-id="52d1b-112">JEA 構成を登録するユーザーに、システムに対する管理者権限があること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-112">The user registering the JEA configuration has administrator rights on the system(s).</span></span>

<span data-ttu-id="52d1b-113">JEA エンドポイントの名前を選ぶ必要もあります。</span><span class="sxs-lookup"><span data-stu-id="52d1b-113">You will also need to select a name for your JEA endpoint.</span></span>
<span data-ttu-id="52d1b-114">ユーザーが JEA を使ってシステムに接続するときに、JEA エンドポイントの名前が必要になります。</span><span class="sxs-lookup"><span data-stu-id="52d1b-114">The name of the JEA endpoint will be required when users want to connect to the system using JEA.</span></span>
<span data-ttu-id="52d1b-115">[Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットを使って、システム上の既存のエンドポイントの名前を確認できます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-115">You can use the [Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) cmdlet to check the names of existing endpoints on the system.</span></span>
<span data-ttu-id="52d1b-116">"microsoft" で始まるエンドポイントは、通常、Windows に付属しています。</span><span class="sxs-lookup"><span data-stu-id="52d1b-116">Endpoints that start with 'microsoft' are typically shipped with Windows.</span></span>
<span data-ttu-id="52d1b-117">"microsoft.powershell" エンドポイントは、リモート PowerShell エンドポイントに接続するときに使われる既定のエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="52d1b-117">The 'microsoft.powershell' endpoint is the default endpoint used when connecting to a remote PowerShell endpoint.</span></span>

```powershell
PS C:\> Get-PSSessionConfiguration | Select-Object Name

Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

<span data-ttu-id="52d1b-118">JEA エンドポイントに対して適切な名前を決定した後、次のコマンドを実行してエンドポイントを登録します。</span><span class="sxs-lookup"><span data-stu-id="52d1b-118">When you have determined an appropriate name for your JEA endpoint, run the following command to register the endpoint.</span></span>

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="52d1b-119">上記のコマンドは、システム上の WinRM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="52d1b-119">The above command will restart the WinRM service on the system.</span></span>
> <span data-ttu-id="52d1b-120">これにより、すべての PowerShell リモート処理セッションおよび実行中の DSC 構成が終了されます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-120">This will terminate all PowerShell remoting sessions as well as any ongoing DSC configurations.</span></span>
> <span data-ttu-id="52d1b-121">業務の中断を防ぐため、コマンドを実行する前に、運用環境のコンピューターをオフラインにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52d1b-121">It is recommended that you take any production machines offline before running the command to avoid disrupting business operations.</span></span>

<span data-ttu-id="52d1b-122">登録が成功すると、[JEA を使用](using-jea.md)できる状態になります。</span><span class="sxs-lookup"><span data-stu-id="52d1b-122">If registration was successful, you are ready to [use JEA](using-jea.md).</span></span>
<span data-ttu-id="52d1b-123">セッション構成ファイルは、登録後は使用されないので、いつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-123">You may delete the session configuration file at any time; it is not used after registration.</span></span>

## <a name="multi-machine-configuration-with-dsc"></a><span data-ttu-id="52d1b-124">DSC での複数コンピューター構成</span><span class="sxs-lookup"><span data-stu-id="52d1b-124">Multi-machine configuration with DSC</span></span>

<span data-ttu-id="52d1b-125">JEA を複数のコンピューターに展開する場合、最も簡単な展開モデルである JEA の [Desired State Configuration](https://msdn.microsoft.com/en-us/powershell/dsc/overview) リソースを使うと、各コンピューターに JEA を迅速かつ一貫して展開できます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-125">If you are deploying JEA on multiple machines, the simplest deployment model is to use the JEA [Desired State Configuration](https://msdn.microsoft.com/en-us/powershell/dsc/overview) resource to quickly and consistently deploy JEA on each machine.</span></span>

<span data-ttu-id="52d1b-126">DSC で JEA を展開するには、次の前提条件が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52d1b-126">To deploy JEA with DSC, you will need to ensure the following prerequisites are met:</span></span>
- <span data-ttu-id="52d1b-127">1 つまたは複数のロール機能が作成され、有効な PowerShell モジュールに追加されていること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-127">One or more role capabilities have been authored and added to a valid PowerShell module.</span></span>
- <span data-ttu-id="52d1b-128">ロールを含む PowerShell モジュールが、各コンピューターからアクセスできる (読み取り専用の) ファイル共有に格納されていること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-128">The PowerShell module containing the roles is stored on a (read-only) file share accessible by each machine.</span></span>
- <span data-ttu-id="52d1b-129">セッション構成の設定が決定されていること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-129">Settings for the session configuration have been determined.</span></span> <span data-ttu-id="52d1b-130">JEA DSC リソースを使うときは、セッション構成ファイルを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52d1b-130">You do not need to create a session configuration file when using the JEA DSC resource.</span></span>
- <span data-ttu-id="52d1b-131">各コンピューターで管理操作を実行できる資格情報があること、またはコンピューターの管理に使われる DSC プル サーバーにアクセスできること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-131">You have credentials that will allow you to perform administrative actions on each machine, or have access to a DSC pull server used to manage the machines.</span></span>
- <span data-ttu-id="52d1b-132">[JEA DSC リソース](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource)をダウンロードしてあること。</span><span class="sxs-lookup"><span data-stu-id="52d1b-132">You have downloaded the [JEA DSC resource](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource)</span></span>

<span data-ttu-id="52d1b-133">ターゲット コンピューター (または、プル サーバーを使っている場合はプル サーバー) 上で、JEA エンドポイント用の DSC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="52d1b-133">On a target machine (or pull server, if you are using one), create a DSC configuration for your JEA endpoint.</span></span>
<span data-ttu-id="52d1b-134">この構成では、JustEnoughAdministration DSC リソースを使って、ファイル共有からロール機能経由でコピーするセッション構成ファイルと File リソースを設定します。</span><span class="sxs-lookup"><span data-stu-id="52d1b-134">In this configuration, you will use the JustEnoughAdministration DSC resource to set up the session configuration file and the File resource to copy over the role capabilities from the file share.</span></span>

<span data-ttu-id="52d1b-135">DSC リソースを使って次のプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-135">The following properties are configurable using the DSC resource:</span></span>
- <span data-ttu-id="52d1b-136">ロールの定義</span><span class="sxs-lookup"><span data-stu-id="52d1b-136">Role Definitions</span></span>
- <span data-ttu-id="52d1b-137">仮想アカウント グループ</span><span class="sxs-lookup"><span data-stu-id="52d1b-137">Virtual Account groups</span></span>
- <span data-ttu-id="52d1b-138">グループ管理されたサービス アカウント名</span><span class="sxs-lookup"><span data-stu-id="52d1b-138">Group Managed Service Account name</span></span>
- <span data-ttu-id="52d1b-139">トランスクリプト ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="52d1b-139">Transcript directory</span></span>
- <span data-ttu-id="52d1b-140">ユーザー ドライブ</span><span class="sxs-lookup"><span data-stu-id="52d1b-140">User drive</span></span>
- <span data-ttu-id="52d1b-141">条件付きアクセス規則</span><span class="sxs-lookup"><span data-stu-id="52d1b-141">Conditional access rules</span></span>
- <span data-ttu-id="52d1b-142">JEA セッションのスタートアップ スクリプト</span><span class="sxs-lookup"><span data-stu-id="52d1b-142">Startup scripts for the JEA session</span></span>

<span data-ttu-id="52d1b-143">DSC 構成でのこれらの各プロパティの構文は、PowerShell セッションの構成ファイルと一致しています。</span><span class="sxs-lookup"><span data-stu-id="52d1b-143">The syntax for each of these properties in a DSC configuration is consistent with the PowerShell session configuration file.</span></span>

<span data-ttu-id="52d1b-144">一般的なサーバー メンテナンス モジュールの DSC 構成の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="52d1b-144">Below is a sample DSC configuration for a general server maintenance module.</span></span>

<span data-ttu-id="52d1b-145">ここで、"RoleCapabilities" サブフォルダー内のロール機能を含む有効な PowerShell モジュールは "\\\\myfileshare\\JEA" ファイル共有にあるものと想定しています。</span><span class="sxs-lookup"><span data-stu-id="52d1b-145">It assumes that a valid PowerShell module containing role capabilities in a 'RoleCapabilities' subfolder is located on the '\\\\myfileshare\\JEA' file share.</span></span>


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

<span data-ttu-id="52d1b-146">その後、[ローカル構成マネージャーを直接呼び出す](https://msdn.microsoft.com/en-us/powershell/dsc/metaconfig)ことにより、または[プル サーバーの構成](https://msdn.microsoft.com/en-us/powershell/dsc/pullserver)を更新することにより、この構成をシステムに適用できます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-146">This configuration can then be applied on a system by [directly invoking the Local Configuration Manager](https://msdn.microsoft.com/en-us/powershell/dsc/metaconfig) or updating the [pull server configuration](https://msdn.microsoft.com/en-us/powershell/dsc/pullserver).</span></span>

<span data-ttu-id="52d1b-147">DSC リソースを使うと、既定の Microsoft.PowerShell リモート処理エンドポイントを置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-147">The DSC resource also allows you to replace the default Microsoft.PowerShell remoting endpoint.</span></span>
<span data-ttu-id="52d1b-148">これを行うと、リソースは、既定の WinRM ACL (リモート管理ユーザーとローカル管理者グループのメンバーにアクセスを許可します) を持つ "Microsoft.PowerShell.Restricted" という名前のバックアップ非制約エンドポイントを自動的に登録します。</span><span class="sxs-lookup"><span data-stu-id="52d1b-148">If you do this, the resource will automatically register a backup unconstrainted endpoint named "Microsoft.PowerShell.Restricted" which has the default WinRM ACL (allowing Remote Management Users and local Administrators group members to access it).</span></span>

## <a name="unregistering-jea-configurations"></a><span data-ttu-id="52d1b-149">JEA の構成の登録解除</span><span class="sxs-lookup"><span data-stu-id="52d1b-149">Unregistering JEA configurations</span></span>

<span data-ttu-id="52d1b-150">システムの JEA エンドポイントを削除するには、[Unregister-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Unregister-PSSessionConfiguration) コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="52d1b-150">To remove a JEA endpoint on a system, use the [Unregister-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Unregister-PSSessionConfiguration) cmdlet.</span></span>
<span data-ttu-id="52d1b-151">JEA エンドポイントの登録を解除すると、新しいユーザーがシステムに新しい JEA セッションを作成できなくなります。</span><span class="sxs-lookup"><span data-stu-id="52d1b-151">Unregistering a JEA endpoint will prevent new users from creating new JEA sessions on the system.</span></span>
<span data-ttu-id="52d1b-152">また、同じエンドポイント名を使って更新されたセッション構成ファイルを再登録することで、JEA 構成を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-152">It also allows you to update a JEA configuration by re-registering an updated session configuration file using the same endpoint name.</span></span>

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="52d1b-153">JEA エンドポイントの登録を解除すると、WinRM サービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-153">Unregistering a JEA endpoint will cause the WinRM service to restart.</span></span>
> <span data-ttu-id="52d1b-154">これにより、他の PowerShell セッション、WMI 呼び出し、一部の管理ツールなど、実行中のほとんどのリモート管理操作が中断されます。</span><span class="sxs-lookup"><span data-stu-id="52d1b-154">This will interrupt most remote management operations in progress, including other PowerShell sessions, WMI invocations, and some management tools.</span></span>
> <span data-ttu-id="52d1b-155">計画されたメンテナンス期間中にのみ、PowerShell エンドポイントの登録を解除してください。</span><span class="sxs-lookup"><span data-stu-id="52d1b-155">Only unregister PowerShell endpoints during planned maintenance windows.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52d1b-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="52d1b-156">Next steps</span></span>

- [<span data-ttu-id="52d1b-157">JEA エンドポイントをテストする</span><span class="sxs-lookup"><span data-stu-id="52d1b-157">Test the JEA endpoint</span></span>](using-jea.md)

