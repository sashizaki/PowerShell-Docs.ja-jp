---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "変数を使用したオブジェクトの保存"
ms.assetid: b1688d73-c173-491e-9ba6-6d0c1cc852de
ms.openlocfilehash: 9a95d421fa2686608a565987c16fecc41c3c6d20
ms.sourcegitcommit: f069ff0689006fece768f178c10e3e3eeaee09f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2017
---
# <a name="using-variables-to-store-objects"></a><span data-ttu-id="83f26-103">変数を使用したオブジェクトの保存</span><span class="sxs-lookup"><span data-stu-id="83f26-103">Using Variables to Store Objects</span></span>
<span data-ttu-id="83f26-104">PowerShell ではオブジェクトを操作します。</span><span class="sxs-lookup"><span data-stu-id="83f26-104">PowerShell works with objects.</span></span> <span data-ttu-id="83f26-105">PowerShell では、変数 (本質的には名前付きのオブジェクト) を作成し、後で使用するために出力を保持できます。</span><span class="sxs-lookup"><span data-stu-id="83f26-105">PowerShell lets you create variables, essentially named objects, to preserve output for later use.</span></span> <span data-ttu-id="83f26-106">他のシェルで変数を使用することに慣れている場合、PowerShell の変数はテキストではなくオブジェクトであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="83f26-106">If you are used to working with variables in other shells remember that PowerShell variables are objects, not text.</span></span>

<span data-ttu-id="83f26-107">変数は常に最初の文字が $ で指定され、名前には任意の英数字またはアンダースコアを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="83f26-107">Variables are always specified with the initial character $, and can include any alphanumeric characters or the underscore in their names.</span></span>

### <a name="creating-a-variable"></a><span data-ttu-id="83f26-108">変数の作成</span><span class="sxs-lookup"><span data-stu-id="83f26-108">Creating a Variable</span></span>
<span data-ttu-id="83f26-109">次のように有効な変数名を入力することで、変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="83f26-109">You can create a variable by typing a valid variable name:</span></span>

```
PS> $loc
PS>
```

<span data-ttu-id="83f26-110">**$loc** に値がないため、これは結果を返しません。</span><span class="sxs-lookup"><span data-stu-id="83f26-110">This returns no result because **$loc** does not have a value.</span></span> <span data-ttu-id="83f26-111">変数の作成と値の割り当てを同一の手順で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83f26-111">You can create a variable and assign it a value in the same step.</span></span> <span data-ttu-id="83f26-112">PowerShell では、変数の作成はその変数が存在しない場合にのみ行われます。存在する場合は、指定した値が既存の変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="83f26-112">PowerShell only creates the variable if it does not exist; otherwise, it assigns the specified value to the existing variable.</span></span> <span data-ttu-id="83f26-113">変数 **$loc** に現在の場所を格納するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="83f26-113">To store your current location in the variable **$loc**, type:</span></span>

```
$loc = Get-Location
```

<span data-ttu-id="83f26-114">このコマンドを入力しても出力は表示されません。出力が $loc に送られるためです。</span><span class="sxs-lookup"><span data-stu-id="83f26-114">There is no output displayed when you type this command because the output is sent to $loc.</span></span> <span data-ttu-id="83f26-115">PowerShell で出力が表示されるのは、他に行き先のないデータが決まって画面に送られることの副作用です。</span><span class="sxs-lookup"><span data-stu-id="83f26-115">In PowerShell, displayed output is a side effect of the fact that data, which is not otherwise directed, always gets sent to the screen.</span></span> <span data-ttu-id="83f26-116">$loc と入力することで現在の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83f26-116">Typing $loc will show your current location:</span></span>

```
PS> $loc

Path
----
C:\temp
```

<span data-ttu-id="83f26-117">**Get-Member** を使用して変数の内容に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="83f26-117">You can use **Get-Member** to display information about the contents of variables.</span></span> <span data-ttu-id="83f26-118">$loc を Get-Member へパイプ処理すると、Get-Location からの出力と同様、これが **PathInfo** オブジェクトであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="83f26-118">Piping $loc to Get-Member will show you that it is a **PathInfo** object, just like the output from Get-Location:</span></span>

```
PS> $loc | Get-Member -MemberType Property

   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   System.String Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {...
ProviderPath Property   System.String ProviderPath {get;}
```

### <a name="manipulating-variables"></a><span data-ttu-id="83f26-119">変数の操作</span><span class="sxs-lookup"><span data-stu-id="83f26-119">Manipulating Variables</span></span>
<span data-ttu-id="83f26-120">PowerShell には変数を操作するためのコマンドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="83f26-120">PowerShell provides several commands to manipulate variables.</span></span> <span data-ttu-id="83f26-121">次のように入力すると、完全な一覧が読みやすい形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="83f26-121">You can see a complete listing in a readable form by typing:</span></span>

```
Get-Command -Noun Variable | Format-Table -Property Name,Definition -AutoSize -Wrap
```

<span data-ttu-id="83f26-122">現在の PowerShell セッションで作成する変数に加えて、いくつかのシステム定義の変数があります。</span><span class="sxs-lookup"><span data-stu-id="83f26-122">In addition to the variables you create in your current PowerShell session, there are several system-defined variables.</span></span> <span data-ttu-id="83f26-123">**Remove-Variable** コマンドレットを使用して、PowerShell によって制御されない変数をすべてクリアできます。</span><span class="sxs-lookup"><span data-stu-id="83f26-123">You can use the **Remove-Variable** cmdlet to clear out all of the variables which are not controlled by PowerShell.</span></span> <span data-ttu-id="83f26-124">すべての変数をクリアするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="83f26-124">Type the following command to clear all variables:</span></span>

```
Remove-Variable -Name * -Force -ErrorAction SilentlyContinue
```

<span data-ttu-id="83f26-125">これにより、以下に示される確認プロンプトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="83f26-125">This will produce the confirmation prompt you see below.</span></span>

```
Confirm
Are you sure you want to perform this action?
Performing operation "Remove Variable" on Target "Name: Error".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):A
```

<span data-ttu-id="83f26-126">その後で **Get-Variable** コマンドレットを実行すると、残りの PowerShell 変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83f26-126">If you then run the **Get-Variable** cmdlet, you will see the remaining PowerShell variables.</span></span> <span data-ttu-id="83f26-127">変数 PowerShell ドライブもあるため、次のように入力してすべての PowerShell 変数を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="83f26-127">Since there is also a variable PowerShell drive, you can also display all PowerShell variables by typing:</span></span>

```
Get-ChildItem variable:
```

### <a name="using-cmdexe-variables"></a><span data-ttu-id="83f26-128">Cmd.exe 変数の使用</span><span class="sxs-lookup"><span data-stu-id="83f26-128">Using Cmd.exe Variables</span></span>
<span data-ttu-id="83f26-129">PowerShell は Cmd.exe ではありませんが、コマンド シェル環境で実行され、Windows のあらゆる環境で使用できるものと同じ変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="83f26-129">Although PowerShell is not Cmd.exe, it runs in a command shell environment and can use the same variables available in any environment in Windows.</span></span> <span data-ttu-id="83f26-130">これらの変数は **env** という名前のドライブを介して公開されます。</span><span class="sxs-lookup"><span data-stu-id="83f26-130">These variables are exposed through a drive named **env**:.</span></span> <span data-ttu-id="83f26-131">これらの変数を表示するには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="83f26-131">You can view these variables by typing:</span></span>

```
Get-ChildItem env:
```

<span data-ttu-id="83f26-132">標準的な変数コマンドレットは **env:** 変数を処理するよう設計されてはいませんが、**env:** プレフィックスを指定して引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="83f26-132">Although the standard variable cmdlets are not designed to work with **env:** variables, you can still use them by specifying the **env:** prefix.</span></span> <span data-ttu-id="83f26-133">たとえば、PowerShell 内から次のように入力してコマンドシェル **%SystemRoot%** 変数を使用すると、オペレーティング システムのルート ディレクトリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="83f26-133">For example, to see the operating system root directory, you can use the command-shell **%SystemRoot%** variable from within PowerShell by typing:</span></span>

```
PS> $env:SystemRoot
C:\WINDOWS
```

<span data-ttu-id="83f26-134">さらに、PowerShell 内から環境変数を作成および変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="83f26-134">You can also create and modify environment variables from within PowerShell.</span></span> <span data-ttu-id="83f26-135">Windows PowerShell からアクセスされる環境変数は、Windows の他の場所の環境変数に適用される通常の規則に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="83f26-135">Environment variables accessed from Windows PowerShell conform to the normal rules for environment variables elsewhere in Windows.</span></span>

