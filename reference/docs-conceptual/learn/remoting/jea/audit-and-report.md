---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA の監査とレポート
ms.openlocfilehash: 2afefe83acecc1fc3643d49766120ffecc25378f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "70017793"
---
# <a name="auditing-and-reporting-on-jea"></a><span data-ttu-id="38805-103">JEA の監査とレポート</span><span class="sxs-lookup"><span data-stu-id="38805-103">Auditing and Reporting on JEA</span></span>

<span data-ttu-id="38805-104">JEA を展開したら、JEA 構成を定期的に監査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38805-104">After you've deployed JEA, you need to regularly audit the JEA configuration.</span></span> <span data-ttu-id="38805-105">監査は、JEA エンドポイントに適切なユーザーがアクセスしていること、ロールの割り当てが適切であることを評価するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38805-105">Auditing helps you assess that the correct people have access to the JEA endpoint and their assigned roles are still appropriate.</span></span>

## <a name="find-registered-jea-sessions-on-a-machine"></a><span data-ttu-id="38805-106">コンピューターに登録されている JEA セッションを見つける</span><span class="sxs-lookup"><span data-stu-id="38805-106">Find registered JEA sessions on a machine</span></span>

<span data-ttu-id="38805-107">コンピューターに登録されている JEA セッションを確認するには、[Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="38805-107">To check which JEA sessions are registered on a machine, use the [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet.</span></span>

```powershell
# Filter for sessions that are configured as 'RestrictedRemoteServer' to find JEA-like session configurations
Get-PSSessionConfiguration | Where-Object { $_.SessionType -eq 'RestrictedRemoteServer' }
```

```Output
Name          : JEAMaintenance
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : CONTOSO\JEA_DNS_ADMINS AccessAllowed, CONTOSO\JEA_DNS_OPERATORS AccessAllowed,
                CONTOSO\JEA_DNS_AUDITORS AccessAllowed
```

<span data-ttu-id="38805-108">エンドポイントに対して有効な権限は **Permission** プロパティで確認できます。</span><span class="sxs-lookup"><span data-stu-id="38805-108">The effective rights for the endpoint are listed in the **Permission** property.</span></span> <span data-ttu-id="38805-109">これらのユーザーには、JEA エンドポイントに接続する権限が与えられています。</span><span class="sxs-lookup"><span data-stu-id="38805-109">These users have the right to connect to the JEA endpoint.</span></span> <span data-ttu-id="38805-110">ただし、アクセスできるロールとコマンドは、エンドポイントの登録に使用された**セッション構成ファイル**の [RoleDefinitions](session-configurations.md) プロパティによって決まります。</span><span class="sxs-lookup"><span data-stu-id="38805-110">However, the roles and commands they have access to is determined by the **RoleDefinitions** property in the [session configuration file](session-configurations.md) that was used to register the endpoint.</span></span> <span data-ttu-id="38805-111">**RoleDefinitions** プロパティを展開して、登録されている JEA エンドポイントのロール マッピングを評価します。</span><span class="sxs-lookup"><span data-stu-id="38805-111">Expand the **RoleDefinitions** property to evaluate the role mappings in a registered JEA endpoint.</span></span>

```powershell
# Get the desired session configuration
$jea = Get-PSSessionConfiguration -Name 'JEAMaintenance'

# Enumerate users/groups and which roles they have access to
$jea.RoleDefinitions.GetEnumerator() | Select-Object Name, @{
  Name = 'Role Capabilities'
  Expression = { $_.Value.RoleCapabilities }
}
```

## <a name="find-available-role-capabilities-on-the-machine"></a><span data-ttu-id="38805-112">コンピューターで利用できるロール機能を見つける</span><span class="sxs-lookup"><span data-stu-id="38805-112">Find available role capabilities on the machine</span></span>

<span data-ttu-id="38805-113">JEA では、PowerShell モジュール内の `.psrc`RoleCapabilities**フォルダーに格納されている** ファイルからロール機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="38805-113">JEA gets role capabilities from the `.psrc` files stored in the **RoleCapabilities** folder inside a PowerShell module.</span></span> <span data-ttu-id="38805-114">次の関数は、コンピューターで使用可能なすべてのロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="38805-114">The following function finds all role capabilities available on a computer.</span></span>

```powershell
function Find-LocalRoleCapability {
    $results = @()

    # Find modules with a "RoleCapabilities" subfolder and add any PSRC files to the result set
    Get-Module -ListAvailable | ForEach-Object {
        $psrcpath = Join-Path -Path $_.ModuleBase -ChildPath 'RoleCapabilities'
        if (Test-Path $psrcpath) {
            $results += Get-ChildItem -Path $psrcpath -Filter *.psrc
        }
    }

    # Format the results nicely to make it easier to read
    $results | Select-Object @{ Name = 'Name'; Expression = { $_.Name.TrimEnd('.psrc') }}, @{
        Name = 'Path'; Expression = { $_.FullName }
    } | Sort-Object Name
}
```

> [!NOTE]
> <span data-ttu-id="38805-115">この関数の結果の順序は、必ずしも、複数のロール機能で同じ名前が共有されているときのロール機能の選択順に一致しません。</span><span class="sxs-lookup"><span data-stu-id="38805-115">The order of results from this function is not necessarily the order in which the role capabilities will be selected if multiple role capabilities share the same name.</span></span>

## <a name="check-effective-rights-for-a-specific-user"></a><span data-ttu-id="38805-116">特定のユーザーに対して有効な権限を確認する</span><span class="sxs-lookup"><span data-stu-id="38805-116">Check effective rights for a specific user</span></span>

<span data-ttu-id="38805-117">[Get-PSSessionCapability](/powershell/module/microsoft.powershell.core/Get-PSSessionCapability) コマンドレットは、ユーザーのグループ メンバーシップに基づいて、JEA エンドポイントで使用可能なすべてのコマンドを列挙します。</span><span class="sxs-lookup"><span data-stu-id="38805-117">The [Get-PSSessionCapability](/powershell/module/microsoft.powershell.core/Get-PSSessionCapability) cmdlet enumerates all the commands available on a JEA endpoint based on a user's group memberships.</span></span>
<span data-ttu-id="38805-118">`Get-PSSessionCapability` の出力は、JEA セッションで `Get-Command -CommandType All` を実行している指定ユーザーのそれと同じになります。</span><span class="sxs-lookup"><span data-stu-id="38805-118">The output of `Get-PSSessionCapability` is identical to that of the specified user running `Get-Command -CommandType All` in a JEA session.</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName 'JEAMaintenance' -Username 'CONTOSO\Alice'
```

<span data-ttu-id="38805-119">ユーザーが、追加 JEA 権限が与えられるグループの永続的なメンバーではないとき、このコマンドレットでこれらの追加のアクセス許可が反映されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="38805-119">If your users aren't permanent members of groups that would grant them additional JEA rights, this cmdlet may not reflect those extra permissions.</span></span> <span data-ttu-id="38805-120">これは Just-In-Time の特権アクセス (必要なときに必要な許可を与える) 管理システムを利用し、セキュリティ グループに一時的に属することをユーザーに許可する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="38805-120">This happens when using just-in-time privileged access management systems to allow users to temporarily belong to a security group.</span></span> <span data-ttu-id="38805-121">ユーザーがジョブを正常に実行するために必要なアクセスのレベルだけを得られるように、ユーザーのロールと機能へのマッピングを注意深く評価します。</span><span class="sxs-lookup"><span data-stu-id="38805-121">Carefully evaluate the mapping of users to roles and capabilities to ensure that users only get the level of access needed to do their jobs successfully.</span></span>

## <a name="powershell-event-logs"></a><span data-ttu-id="38805-122">PowerShell イベント ログ</span><span class="sxs-lookup"><span data-stu-id="38805-122">PowerShell event logs</span></span>

<span data-ttu-id="38805-123">システムでモジュールやスクリプト ブロックのログ記録を有効にしている場合、ユーザーが JEA セッションで実行したコマンドごとに、Windows イベント ログでイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="38805-123">If you enabled module or script block logging on the system, you can see events in the Windows event logs for each command a user runs in a JEA session.</span></span> <span data-ttu-id="38805-124">これらのイベントを検索するには、**Microsoft-Windows-PowerShell/Operational** イベント ログを開き、イベント ID が **4104** のイベントを探します。</span><span class="sxs-lookup"><span data-stu-id="38805-124">To find these events, open **Microsoft-Windows-PowerShell/Operational** event log and look for events with event ID **4104**.</span></span>

<span data-ttu-id="38805-125">各イベント ログ エントリに、コマンドを実行したセッションに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38805-125">Each event log entry includes information about the session in which the command was run.</span></span> <span data-ttu-id="38805-126">JEA セッションの場合、イベントには **ConnectedUser** と **RunAsUser** に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38805-126">For JEA sessions, the event includes information about the **ConnectedUser** and the **RunAsUser**.</span></span> <span data-ttu-id="38805-127">**ConnectedUser** は JEA セッションを作成した実際のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="38805-127">The **ConnectedUser** is the actual user who created the JEA session.</span></span> <span data-ttu-id="38805-128">**RunAsUser** は JEA でコマンドを実行するために使用されたアカウントです。</span><span class="sxs-lookup"><span data-stu-id="38805-128">The **RunAsUser** is the account JEA used to execute the command.</span></span>

<span data-ttu-id="38805-129">アプリケーション イベント ログには、**RunAsUser** により行われた変更が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38805-129">Application event logs show changes being made by the **RunAsUser**.</span></span> <span data-ttu-id="38805-130">そのため、特定のコマンドの呼び出しを **ConnectedUser** にさかのぼって追跡するには、モジュールおよびスクリプトのログ記録を有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="38805-130">So having module and script logging enabled is required to trace a specific command invocation back to the **ConnectedUser**.</span></span>

## <a name="application-event-logs"></a><span data-ttu-id="38805-131">アプリケーション イベント ログ</span><span class="sxs-lookup"><span data-stu-id="38805-131">Application event logs</span></span>

<span data-ttu-id="38805-132">外部のアプリケーションやサービスと情報を交換する JEA セッションでコマンドを実行すると、独自のイベント ログにイベントが記録されることがあります。</span><span class="sxs-lookup"><span data-stu-id="38805-132">Commands run in a JEA session that interact with external applications or services may log events to their own event logs.</span></span> <span data-ttu-id="38805-133">PowerShell ログおよびトランスクリプトと異なり、他のログ記録メカニズムでは JEA セッションの接続されているユーザーは取得されません。</span><span class="sxs-lookup"><span data-stu-id="38805-133">Unlike PowerShell logs and transcripts, other logging mechanisms don't capture the connected user of the JEA session.</span></span> <span data-ttu-id="38805-134">代わりに、これらのアプリケーションでは、仮想実行ユーザーのみが記録されます。</span><span class="sxs-lookup"><span data-stu-id="38805-134">Instead, those applications only log the virtual run-as user.</span></span>
<span data-ttu-id="38805-135">コマンドの実行ユーザーを判断するには、[セッション トランスクリプト](#session-transcripts)を確認するか、PowerShell イベント ログと、アプリケーション イベント ログに表示されている時刻とユーザーを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="38805-135">To determine who ran the command, you need to consult a [session transcript](#session-transcripts) or correlate PowerShell event logs with the time and user shown in the application event log.</span></span>

<span data-ttu-id="38805-136">WinRM ログは、アプリケーション イベント ログの実行ユーザーと接続ユーザーを関連付けることにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38805-136">The WinRM log can also help you correlate run-as users to the connecting user in an application event log.</span></span> <span data-ttu-id="38805-137">**Microsoft-Windows-Windows Remote Management/Operational** ログのイベント ID **193** では、すべての新しい JEA セッションの接続ユーザーと実行ユーザーの両方に対して、セキュリティ識別子 (SID) とアカウント名が記録されます。</span><span class="sxs-lookup"><span data-stu-id="38805-137">Event ID **193** in the **Microsoft-Windows-Windows Remote Management/Operational** log records the security identifier (SID) and account name for both the connecting user and run as user for every new JEA session.</span></span>

## <a name="session-transcripts"></a><span data-ttu-id="38805-138">セッションのトランスクリプト</span><span class="sxs-lookup"><span data-stu-id="38805-138">Session transcripts</span></span>

<span data-ttu-id="38805-139">ユーザー セッションごとにトランスクリプトを作成するように JEA を構成した場合、すべてのユーザーのアクションのテキスト コピーが指定のフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="38805-139">If you configured JEA to create a transcript for each user session, a text copy of every user's actions are stored in the specified folder.</span></span>

<span data-ttu-id="38805-140">次のコマンドでは (管理者として実行した場合)、すべてのトランスクリプト ディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="38805-140">The following command (as an administrator) finds all transcript directories.</span></span>

```powershell
Get-PSSessionConfiguration |
  Where-Object { $_.TranscriptDirectory -ne $null } |
    Format-Table Name, TranscriptDirectory
```

<span data-ttu-id="38805-141">各トランスクリプトは、セッションの開始時刻、セッションに接続したユーザー、そのユーザーに割り当てられた JEA ID に関する情報で始まります。</span><span class="sxs-lookup"><span data-stu-id="38805-141">Each transcript starts with information about the time the session started, which user connected to the session, and which JEA identity was assigned to them.</span></span>

```
**********************
Windows PowerShell transcript start
Start time: 20160710144736
Username: CONTOSO\Alice
RunAs User: WinRM Virtual Users\WinRM VA_1_CONTOSO_Alice
Machine: SERVER01 (Microsoft Windows NT 10.0.14393.0)
[...]
```

<span data-ttu-id="38805-142">トランスクリプトの本文には、ユーザーが呼び出した各コマンドに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38805-142">The body of the transcript contains information about each command the user invoked.</span></span> <span data-ttu-id="38805-143">使用されたコマンドの正確な構文は、PowerShell リモート処理のためにコマンドが変換される方法のため、JEA セッションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="38805-143">The exact syntax of the command used is unavailable in JEA sessions because of the way commands are transformed for PowerShell remoting.</span></span> <span data-ttu-id="38805-144">ただし、実行された有効なコマンドを判断することはできます。</span><span class="sxs-lookup"><span data-stu-id="38805-144">However, you can still determine the effective command that was executed.</span></span> <span data-ttu-id="38805-145">次は、JEA セッションでユーザーが `Get-Service Dns` を実行した場合のトランスクリプト例からの抜粋です。</span><span class="sxs-lookup"><span data-stu-id="38805-145">Below is an example transcript snippet from a user running `Get-Service Dns` in a JEA session:</span></span>

```
PS>CommandInvocation(Get-Service): "Get-Service"
>> ParameterBinding(Get-Service): name="Name"; value="Dns"
>> CommandInvocation(Out-Default): "Out-Default"
>> ParameterBinding(Out-Default): name="InputObject"; value="Dns"

Running  Dns                DNS Server
```

<span data-ttu-id="38805-146">ユーザーが実行するコマンドごとに、**CommandInvocation** 行が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="38805-146">A **CommandInvocation** line is written for each command a user runs.</span></span> <span data-ttu-id="38805-147">**ParameterBindings** はコマンドと共に指定された各パラメーターとその値を記録します。</span><span class="sxs-lookup"><span data-stu-id="38805-147">**ParameterBindings** record each parameter and value supplied with the command.</span></span> <span data-ttu-id="38805-148">前の例では、**コマンドレットでパラメーター**Name**に値**Dns`Get-Service` が指定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="38805-148">In the previous example, you can see that the parameter **Name** was supplied the with value **Dns** for the `Get-Service` cmdlet.</span></span>

<span data-ttu-id="38805-149">各コマンドの出力も **CommandInvocation** をトリガーします (通常は `Out-Default` に)。</span><span class="sxs-lookup"><span data-stu-id="38805-149">The output of each command also triggers a **CommandInvocation**, usually to `Out-Default`.</span></span> <span data-ttu-id="38805-150">**の**InputObject`Out-Default` は、コマンドから返される PowerShell オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="38805-150">The **InputObject** of `Out-Default` is the PowerShell object returned from the command.</span></span> <span data-ttu-id="38805-151">そのオブジェクトの詳細が数行下に出力されています。ユーザーに表示される内容と同様のものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38805-151">The details of that object are printed a few lines below, closely mimicking what the user would have seen.</span></span>

## <a name="see-also"></a><span data-ttu-id="38805-152">参照</span><span class="sxs-lookup"><span data-stu-id="38805-152">See also</span></span>

[<span data-ttu-id="38805-153">*PowerShell ♥ the Blue Team* のセキュリティに関するブログ投稿</span><span class="sxs-lookup"><span data-stu-id="38805-153">*PowerShell ♥ the Blue Team* blog post on security</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
