---
ms.date: 08/24/2018
keywords: powershell,コマンドレット
title: PowerShell コマンド名の学習
ms.openlocfilehash: a65ffcdca6510093b0a77234e20546b6cc1f02bf
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "67030420"
---
# <a name="learning-powershell-command-names"></a><span data-ttu-id="fcfaa-103">PowerShell コマンド名の学習</span><span class="sxs-lookup"><span data-stu-id="fcfaa-103">Learning PowerShell command names</span></span>

<span data-ttu-id="fcfaa-104">大半のコマンドライン インターフェイスに共通して言えることは、コマンドやパラメーターの名前を覚えるために多大な時間と労力が必要であるという点です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-104">Learning names of commands and parameters requires a significant time investment with most command-line interfaces.</span></span> <span data-ttu-id="fcfaa-105">問題は、パターン化されているものが少ししかないことです。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-105">The issue is that there are few patterns.</span></span> <span data-ttu-id="fcfaa-106">定期的に使う必要があるコマンドとパラメーターを覚えるための唯一の方法は、記憶することです。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-106">Memorization is the only way to learn the commands and parameters that you need to use on a regular basis.</span></span>

<span data-ttu-id="fcfaa-107">新しいコマンドやパラメーターを使用する場合は、必ず既に備えている知識を活用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-107">When you work with a new command or parameter, you can't always use what you already know.</span></span> <span data-ttu-id="fcfaa-108">新しい名前を検索して調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-108">You have to find and learn a new name.</span></span> <span data-ttu-id="fcfaa-109">従来は、コマンドライン インターフェイスは小規模なツール セットから始まって、そこに増補していくことで拡張されました。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-109">Traditionally, command-line interfaces start with a small set of tools and grow with incremental additions.</span></span> <span data-ttu-id="fcfaa-110">このことから、標準的な構造が存在しない理由は容易にわかります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-110">It's easy to see why there's no standard structure.</span></span>
<span data-ttu-id="fcfaa-111">各コマンドは別個のツールなので、このことは、コマンド名にとっては理に適っているようです。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-111">This seems logical for command names since each command is a separate tool.</span></span> <span data-ttu-id="fcfaa-112">PowerShell は、コマンド名を扱いやすい方法を備えています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-112">PowerShell has a better way to handle command names.</span></span>

## <a name="learning-command-names-in-traditional-shells"></a><span data-ttu-id="fcfaa-113">従来のシェルのコマンド名を覚える</span><span class="sxs-lookup"><span data-stu-id="fcfaa-113">Learning command names in traditional shells</span></span>

<span data-ttu-id="fcfaa-114">ほとんどのコマンドは、サービスやプロセスなど、オペレーティング システムまたはアプリケーションの各種要素を管理する目的で作成されています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-114">Most commands are built to manage elements of the operating system or applications, such as services or processes.</span></span> <span data-ttu-id="fcfaa-115">コマンド名は、同じ系統のコマンド (コマンド ファミリ) だからといって、必ずしも決まったパターンがあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-115">The commands have names that may or may not fit into a family.</span></span> <span data-ttu-id="fcfaa-116">たとえば、Windows システムでは、`net start` コマンドと `net stop` コマンドを使用して、サービスを開始したり停止したりできます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-116">For example, on Windows systems, you can use the `net start` and `net stop` commands to start and stop a service.</span></span> <span data-ttu-id="fcfaa-117">**Sc.exe** は、Windows に対応するもう 1 つのサービス制御ツールです。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-117">**Sc.exe** is another service control tool for Windows.</span></span> <span data-ttu-id="fcfaa-118">その名前は、**net.exe** サービス コマンドの命名パターンには準拠していません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-118">That name does not fit into the naming pattern for the **net.exe** service commands.</span></span> <span data-ttu-id="fcfaa-119">プロセス管理用のコマンドはどうでしょうか。Windows には、プロセスを一覧表示するための **tasklist.exe** コマンドや、プロセスを強制終了するための **taskkill.exe** コマンドが存在します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-119">For process management, Windows has the **tasklist.exe** command to list processes and the **taskkill.exe** command to kill processes.</span></span>

<span data-ttu-id="fcfaa-120">これらのコマンドのパラメーター仕様も不規則です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-120">Also, these commands have irregular parameter specifications.</span></span> <span data-ttu-id="fcfaa-121">`net start` コマンドを使用して、リモート コンピューター上でサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-121">You can't use the `net start` command to start a service on a remote computer.</span></span> <span data-ttu-id="fcfaa-122">**sc.exe** コマンドは、リモート コンピューター上でサービスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-122">The **sc.exe** command can start a service on a remote computer.</span></span> <span data-ttu-id="fcfaa-123">ただし、リモート コンピューターを指定するには、二重のバックスラッシュを名前の前に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-123">But to specify the remote computer, you must prefix its name with a double backslash.</span></span> <span data-ttu-id="fcfaa-124">DC01 という名前のリモート コンピューター上でスプーラー サービスを開始するには、`sc.exe \\DC01 start spooler` と入力します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-124">To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.</span></span>
<span data-ttu-id="fcfaa-125">DC01 で実行されているタスクを一覧表示するには、 **/S** パラメーターとバックスラッシュを付与していないコンピューター名を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-125">To list tasks running on DC01, you use the **/S** parameter and the computer name without backslashes.</span></span> <span data-ttu-id="fcfaa-126">たとえば、「 `tasklist /S DC01` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-126">For example, `tasklist /S DC01`.</span></span>

> [!NOTE]
> <span data-ttu-id="fcfaa-127">PowerShell v6 以前では、`sc` は `Set-Content` コマンドレットのエイリアスでした。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-127">Prior to PowerShell v6, `sc` was an alias for the `Set-Content` cmdlet.</span></span> <span data-ttu-id="fcfaa-128">そのため、v6 より前のバージョンの PowerShell で **sc.exe** コマンドを実行するには、ファイル名拡張子 **exe** を含んだ完全なファイル名 **sc.exe** を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-128">Therefore, to run the **sc.exe** command in a version of PowerShell prior to v6, you must include the full filename **sc.exe** including the file extension **exe**.</span></span>

<span data-ttu-id="fcfaa-129">サービスとプロセスは、ライフ サイクルが明確に定義されているコンピューター上で管理できる要素の例です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-129">Services and processes are examples of manageable elements on a computer that have well-defined life cycles.</span></span> <span data-ttu-id="fcfaa-130">サービスとプロセスを開始または停止したり、現在実行中のサービスやプロセスすべてを一覧表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-130">You may start or stop services and processes, or get a list of all currently running services or processes.</span></span> <span data-ttu-id="fcfaa-131">サービスとプロセスの間には、技術上は重大な区別がありますが、サービスとプロセスで実行されるアクションは、概念的には同じです。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-131">Although there are important technical distinctions between them, the actions you perform on services and processes are conceptually the same.</span></span> <span data-ttu-id="fcfaa-132">また、パラメーターを指定して動作をカスタマイズするときの選択肢も、概念的に似ている場合があります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-132">Furthermore, the choices we make to customize an action by specifying parameters may be conceptually similar as well.</span></span>

<span data-ttu-id="fcfaa-133">PowerShell ではこの類似性を活かして、コマンドレットを理解して使用するために知っておく必要がある個々の名前の数を減らしました。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-133">PowerShell exploits these similarities to reduce the number of distinct names you need to know to understand and use cmdlets.</span></span>

## <a name="cmdlets-use-verb-noun-names-to-reduce-command-memorization"></a><span data-ttu-id="fcfaa-134">コマンドレットには覚えやすいように "動詞-名詞" 形式の命名規則が使用される</span><span class="sxs-lookup"><span data-stu-id="fcfaa-134">Cmdlets use verb-noun names to reduce command memorization</span></span>

<span data-ttu-id="fcfaa-135">PowerShell では、「動詞-名詞」の命名体系を採用しています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-135">PowerShell uses a "verb-noun" naming system.</span></span> <span data-ttu-id="fcfaa-136">各コマンドレットの名前は、標準的な動詞を特定の名詞とハイフンでつないで表記されます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-136">Each cmdlet name consists of a standard verb hyphenated with a specific noun.</span></span> <span data-ttu-id="fcfaa-137">PowerShell の動詞は必ずしも文法上の動詞とは一致しませんが、PowerShell における特定の動作を表しています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-137">PowerShell verbs are not always English verbs, but they express specific actions in PowerShell.</span></span> <span data-ttu-id="fcfaa-138">名詞については、ほぼ文法上の名詞と同じと考えてかまいません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-138">Nouns are very much like nouns in any language.</span></span> <span data-ttu-id="fcfaa-139">システムを管理するうえで重要な、特定の種類のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-139">They describe specific types of objects that are important in system administration.</span></span> <span data-ttu-id="fcfaa-140">実際、名前を動詞と名詞に分けることにより、格段に覚えやすくなります。そのことは、例をいくつか考えてみればすぐに納得できます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-140">It's easy to demonstrate how these two-part names reduce learning effort by looking at a few examples.</span></span>

<span data-ttu-id="fcfaa-141">PowerShell には、推奨される標準的な動詞のセットがあります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-141">PowerShell has a recommended set of standard verbs.</span></span> <span data-ttu-id="fcfaa-142">名詞に対する制約は少ないですが、常に動詞のアクションの対象を表します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-142">Nouns are less restricted, but always describe what the verb acts upon.</span></span> <span data-ttu-id="fcfaa-143">PowerShell には、`Get-Process`、`Stop-Process`、`Get-Service`、および `Stop-Service` のようなコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-143">PowerShell has commands such as `Get-Process`, `Stop-Process`, `Get-Service`, and `Stop-Service`.</span></span>

<span data-ttu-id="fcfaa-144">この名詞と動詞 2 つずつの例では、一貫性のおかげで覚えやすくなるという実感は、それほどありません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-144">For this example of two nouns and verbs, consistency does not simplify learning that much.</span></span> <span data-ttu-id="fcfaa-145">これを動詞と名詞 10 個 ずつの標準化されたセットに拡大します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-145">Extend that list to a standardized set of 10 verbs and 10 nouns.</span></span> <span data-ttu-id="fcfaa-146">この場合、覚える単語は 20 個だけですが、</span><span class="sxs-lookup"><span data-stu-id="fcfaa-146">Now you only have 20 words to understand.</span></span>
<span data-ttu-id="fcfaa-147">単語を組み合わせることで、個々のコマンド名として 100 通りが成立します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-147">But those words can be combined to form 100 distinct command names.</span></span>

<span data-ttu-id="fcfaa-148">名前を読めば、PowerShell コマンドの動作を簡単に理解できます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-148">It's easy to understand what a PowerShell command does by reading its name.</span></span> <span data-ttu-id="fcfaa-149">コンピューターをシャット ダウンするコマンドは、`Stop-Computer` です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-149">The command to shut down a computer is `Stop-Computer`.</span></span> <span data-ttu-id="fcfaa-150">ネットワーク上にあるすべてのコンピューターを一覧表示するコマンドは、`Get-Computer` です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-150">The command to list all computers on a network is `Get-Computer`.</span></span> <span data-ttu-id="fcfaa-151">システム日付を取得するコマンドは、`Get-Date` です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-151">The command to get the system date is `Get-Date`.</span></span>

<span data-ttu-id="fcfaa-152">`Get-Command` の **Verb** パラメーターを使って、特定の動詞を含むすべてのコマンドを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-152">You can list all commands that include a particular verb with the **Verb** parameter for `Get-Command`.</span></span> <span data-ttu-id="fcfaa-153">たとえば、`Get` という動詞が使用されているすべてのコマンドレットを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-153">For example, to see all cmdlets that use the verb `Get`, type:</span></span>

```
PS> Get-Command -Verb Get

CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Get-Acl                         Get-Acl [[-Path] <String[]>]...
Cmdlet          Get-Alias                       Get-Alias [[-Name] <String[]...
Cmdlet          Get-AuthenticodeSignature       Get-AuthenticodeSignature [-...
Cmdlet          Get-ChildItem                   Get-ChildItem [[-Path] <Stri...
...
```

<span data-ttu-id="fcfaa-154">**Noun** パラメーターを使用すると、同じ種類のオブジェクトに影響を及ぼすコマンド ファミリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-154">Use the **Noun** parameter to see a family of commands that affect the same type of object.</span></span> <span data-ttu-id="fcfaa-155">たとえば、サービスの管理に使用できるコマンドを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-155">For example, run following command to see the commands  available for managing services:</span></span>

```
PS> Get-Command -Noun Service

CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Get-Service                     Get-Service [[-Name] <String...
Cmdlet          New-Service                     New-Service [-Name] <String>...
Cmdlet          Restart-Service                 Restart-Service [-Name] <Str...
Cmdlet          Resume-Service                  Resume-Service [-Name] <Stri...
Cmdlet          Set-Service                     Set-Service [-Name] <String>...
Cmdlet          Start-Service                   Start-Service [-Name] <Strin...
Cmdlet          Stop-Service                    Stop-Service [-Name] <String...
Cmdlet          Suspend-Service                 Suspend-Service [-Name] <Str...
...
```

## <a name="cmdlets-use-standard-parameters"></a><span data-ttu-id="fcfaa-156">コマンドレットでは標準的なパラメーターが使用される</span><span class="sxs-lookup"><span data-stu-id="fcfaa-156">Cmdlets use standard parameters</span></span>

<span data-ttu-id="fcfaa-157">前述のように、従来のコマンドライン インターフェイスで使用されるコマンドには、必ずしもパラメーター名に一貫性はありません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-157">As noted earlier, commands used in traditional command-line interfaces don't always have consistent parameter names.</span></span> <span data-ttu-id="fcfaa-158">パラメーターは 1 文字または略称で表記されることが多く、簡単に入力できるという利点はありますが、未経験のユーザーには決してわかりすいものではありません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-158">Parameters are often single-character or abbreviated words that are easy to type but aren't easily understood by new users.</span></span>

<span data-ttu-id="fcfaa-159">従来のほとんどのコマンドライン インターフェイスとは異なり、PowerShell では、パラメーターが直接処理されます。また、パラメーターへのこの直接アクセスは、パラメーター名を標準化する開発者向けのガイドラインに準拠して使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-159">Unlike most other traditional command-line interfaces, PowerShell processes parameters directly, and it uses this direct access to the parameters along with developer guidance to standardize parameter names.</span></span> <span data-ttu-id="fcfaa-160">このガイドラインは役立ちますが、すべてのコマンドレットが標準に準拠していることを保証するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-160">This guidance encourages but does not guarantee that every cmdlet conforms to the standard.</span></span>

<span data-ttu-id="fcfaa-161">また、PowerShell では、パラメーターの区切り記号も標準化しています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-161">PowerShell also standardizes the parameter separator.</span></span> <span data-ttu-id="fcfaa-162">PowerShell コマンドでは、パラメーター名の前には常に '-' が付加されます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-162">Parameter names always have a '-' prepended to them with a PowerShell command.</span></span> <span data-ttu-id="fcfaa-163">次の例を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-163">Consider the following example:</span></span>

```powershell
Get-Command -Name Clear-Host
```

<span data-ttu-id="fcfaa-164">パラメーターの名前は **Name** ですが、コマンド ライン上でパラメーターとして使用される場合は、`-Name` と入力されています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-164">The parameter's name is **Name**, but it is typed as `-Name` when used on the command line as a parameter.</span></span>

<span data-ttu-id="fcfaa-165">以降、標準的なパラメーター名と使用法について、一般的な特徴をいくつか取り上げます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-165">Here are some of the general characteristics of the standard parameter names and usages.</span></span>

### <a name="the-help-parameter-"></a><span data-ttu-id="fcfaa-166">ヘルプ パラメーター (?)</span><span class="sxs-lookup"><span data-stu-id="fcfaa-166">The Help parameter (?)</span></span>

<span data-ttu-id="fcfaa-167">任意のコマンドレットで `-?` パラメーターを指定すると、PowerShell によりコマンドレットのヘルプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-167">When you specify the `-?` parameter on any cmdlet, PowerShell displays help for the cmdlet.</span></span>
<span data-ttu-id="fcfaa-168">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-168">The cmdlet is not executed.</span></span>

### <a name="common-parameters"></a><span data-ttu-id="fcfaa-169">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcfaa-169">Common parameters</span></span>

<span data-ttu-id="fcfaa-170">PowerShell には、複数の*共通パラメーター*があります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-170">PowerShell has several *common parameters*.</span></span> <span data-ttu-id="fcfaa-171">これらのパラメーターは、PowerShell エンジンによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-171">These parameters are controlled by the PowerShell engine.</span></span> <span data-ttu-id="fcfaa-172">共通パラメーターは、常に同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-172">Common parameters always behave the same way.</span></span> <span data-ttu-id="fcfaa-173">共通パラメーターには、**WhatIf**、**Confirm**、**Verbose**、**Debug**、**Warn**、**ErrorAction**、**ErrorVariable**、**OutVariable**、**OutBuffer** などがあります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-173">The common parameters are **WhatIf**, **Confirm**, **Verbose**, **Debug**, **Warn**, **ErrorAction**, **ErrorVariable**, **OutVariable**, and **OutBuffer**.</span></span>

### <a name="recommended-parameter-names"></a><span data-ttu-id="fcfaa-174">推奨されるパラメーター名</span><span class="sxs-lookup"><span data-stu-id="fcfaa-174">Recommended parameter names</span></span>

<span data-ttu-id="fcfaa-175">PowerShell のコア コマンドレットでは、類似のパラメーターに対して標準名を使用しています。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-175">The PowerShell core cmdlets use standard names for similar parameters.</span></span> <span data-ttu-id="fcfaa-176">これらの標準名の使用は強制ではありませんが、標準化を推進するための明確なガイドラインがあります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-176">The use of these standard names is not enforced, but there is explicit guidance to encourage standardization.</span></span>

<span data-ttu-id="fcfaa-177">たとえば、コンピューターを参照するパラメーターに推奨される名前は、Server、Host、System、Node や、それ以外の共通の別名ではなく、**ComputerName** です。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-177">For example, the recommended name for a parameter that refers to a computer is **ComputerName**, rather than Server, Host, System, Node, or some other common alternative.</span></span> <span data-ttu-id="fcfaa-178">推奨される他の重要なパラメーター名としては、**Force**、**Exclude**、**Include**、**PassThru**、**Path**、および **CaseSensitive** があります。</span><span class="sxs-lookup"><span data-stu-id="fcfaa-178">Other important recommended parameter names are **Force**, **Exclude**, **Include**, **PassThru**, **Path**, and **CaseSensitive**.</span></span>
