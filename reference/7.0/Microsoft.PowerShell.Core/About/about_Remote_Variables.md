---
description: リモート コマンドのローカル変数とリモート変数の使用方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: 2260e1a6ba4553cbdba0057972f491d17c61382d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223736"
---
# <a name="about-remote-variables"></a><span data-ttu-id="fec64-104">リモート変数について</span><span class="sxs-lookup"><span data-stu-id="fec64-104">About Remote Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="fec64-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="fec64-105">Short description</span></span>

<span data-ttu-id="fec64-106">リモート コマンドのローカル変数とリモート変数の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fec64-106">Explains how to use local and remote variables in remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="fec64-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="fec64-107">Long description</span></span>

<span data-ttu-id="fec64-108">リモートコンピューターで実行するコマンドで変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fec64-108">You can use variables in commands that you run on remote computers.</span></span> <span data-ttu-id="fec64-109">変数に値を割り当て、その変数を値の代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="fec64-109">Assign a value to the variable and then use the variable in place of the value.</span></span>

<span data-ttu-id="fec64-110">既定では、リモートコマンドの変数は、コマンドを実行するセッションで定義されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="fec64-110">By default, the variables in remote commands are assumed to be defined in the session that runs the command.</span></span> <span data-ttu-id="fec64-111">ローカルセッションで定義されている変数は、コマンドでローカル変数として識別される必要があります。</span><span class="sxs-lookup"><span data-stu-id="fec64-111">Variables that are defined in a local session, must be identified as local variables in the command.</span></span>

## <a name="using-remote-variables"></a><span data-ttu-id="fec64-112">リモート変数の使用</span><span class="sxs-lookup"><span data-stu-id="fec64-112">Using remote variables</span></span>

<span data-ttu-id="fec64-113">PowerShell では、リモートコマンドで使用される変数が、コマンドを実行するセッションで定義されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fec64-113">PowerShell assumes that the variables used in remote commands are defined in the session in which the command runs.</span></span>

<span data-ttu-id="fec64-114">この例では、 `$ps` 変数は、コマンドが実行される一時的なセッションで定義されてい `Get-WinEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="fec64-114">In this example, the `$ps` variable is defined in the temporary session in which the `Get-WinEvent` command runs.</span></span>

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

<span data-ttu-id="fec64-115">コマンドが永続的なセッションで実行されている場合、 **PSSession** では、そのセッションでリモート変数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fec64-115">When the command runs in a persistent session, **PSSession** , the remote variable must be defined in that session.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a><span data-ttu-id="fec64-116">ローカル変数の使用</span><span class="sxs-lookup"><span data-stu-id="fec64-116">Using local variables</span></span>

<span data-ttu-id="fec64-117">リモートコマンドでローカル変数を使用できますが、変数はローカルセッションで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fec64-117">You can use local variables in remote commands, but the variable must be defined in the local session.</span></span>

<span data-ttu-id="fec64-118">PowerShell 3.0 以降では、スコープ修飾子を使用して、 `Using` リモートコマンドでローカル変数を識別できます。</span><span class="sxs-lookup"><span data-stu-id="fec64-118">Beginning in PowerShell 3.0, you can use the `Using` scope modifier to identify a local variable in a remote command.</span></span>

<span data-ttu-id="fec64-119">の構文 `Using` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fec64-119">The syntax of `Using` is as follows:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="fec64-120">次の例では、 `$ps` 変数はローカルセッションで作成されますが、コマンドを実行するセッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec64-120">In the following example, the `$ps` variable is created in the local session, but is used in the session in which the command runs.</span></span> <span data-ttu-id="fec64-121">`Using`スコープ修飾子は、 `$ps` ローカル変数としてを識別します。</span><span class="sxs-lookup"><span data-stu-id="fec64-121">The `Using` scope modifier identifies `$ps` as a local variable.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

<span data-ttu-id="fec64-122">`Using`スコープ修飾子は **PSSession** で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fec64-122">The `Using` scope modifier can be used in a **PSSession**.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

<span data-ttu-id="fec64-123">などの変数参照は、 `$using:var` `$var` 呼び出し元のコンテキストから変数の値に展開されます。</span><span class="sxs-lookup"><span data-stu-id="fec64-123">A variable reference such as `$using:var` expands to the value of variable `$var` from the caller's context.</span></span> <span data-ttu-id="fec64-124">呼び出し元の変数オブジェクトにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fec64-124">You do not get access to the caller's variable object.</span></span>
<span data-ttu-id="fec64-125">スコープ修飾子を使用して、 `Using` **PSSession** 内のローカル変数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="fec64-125">The `Using` scope modifier cannot be used to modify a local variable within the **PSSession**.</span></span> <span data-ttu-id="fec64-126">たとえば、次のコードは機能しません。</span><span class="sxs-lookup"><span data-stu-id="fec64-126">For example, the following code does not work:</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

<span data-ttu-id="fec64-127">の詳細について `Using` は、「」を参照してください [about_Scopes](./about_Scopes.md)</span><span class="sxs-lookup"><span data-stu-id="fec64-127">For more information about `Using`, see [about_Scopes](./about_Scopes.md)</span></span>

### <a name="using-splatting"></a><span data-ttu-id="fec64-128">スプラッティングの使用</span><span class="sxs-lookup"><span data-stu-id="fec64-128">Using splatting</span></span>

<span data-ttu-id="fec64-129">PowerShell スプラッティングは、パラメーターの名前と値のコレクションをコマンドに渡します。</span><span class="sxs-lookup"><span data-stu-id="fec64-129">PowerShell splatting passes a collection of parameter names and values to a command.</span></span> <span data-ttu-id="fec64-130">詳細については、「 [about_Splatting](about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec64-130">For more information, see [about_Splatting](about_Splatting.md).</span></span>

<span data-ttu-id="fec64-131">この例では、スプラッティング変数は、 `$Splat` ローカルコンピューターに設定されているハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="fec64-131">In this example, the splatting variable, `$Splat` is a hash table that is set up on the local computer.</span></span> <span data-ttu-id="fec64-132">は、 `Invoke-Command` リモートコンピューターセッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="fec64-132">The `Invoke-Command` connects to a remote computer session.</span></span> <span data-ttu-id="fec64-133">**ScriptBlock** は、 `Using` splatted 変数を表すために、アットマーク () を使用して、スコープ修飾子を使用し `@` ます。</span><span class="sxs-lookup"><span data-stu-id="fec64-133">The **ScriptBlock** uses the `Using` scope modifier with the At (`@`) symbol to represent the splatted variable.</span></span>

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a><span data-ttu-id="fec64-134">' Using ' スコープ修飾子が必要なその他の状況</span><span class="sxs-lookup"><span data-stu-id="fec64-134">Other situations where the 'Using' scope modifier is needed</span></span>

<span data-ttu-id="fec64-135">セッションが不足しているスクリプトまたはコマンドについては、 `Using` 呼び出し元のセッションスコープから変数の値を埋め込むためにスコープ修飾子が必要です。これにより、セッションコードが不足してしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="fec64-135">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="fec64-136">`Using`スコープ修飾子は、次のコンテキストでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fec64-136">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="fec64-137">リモートで実行されたコマンド。 `Invoke-Command` **ComputerName** 、 **HostName** 、 **SSHConnection** 、または **Session** パラメーター (リモートセッション) の使用を開始しました。</span><span class="sxs-lookup"><span data-stu-id="fec64-137">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="fec64-138">バックグラウンドジョブ、で開始 `Start-Job` (アウトプロセスセッション)</span><span class="sxs-lookup"><span data-stu-id="fec64-138">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="fec64-139">スレッドジョブ `Start-ThreadJob` 。または `ForEach-Object -Parallel` (個別のスレッドセッション) を使用して開始</span><span class="sxs-lookup"><span data-stu-id="fec64-139">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="fec64-140">コンテキストによっては、埋め込み変数の値は、呼び出し元のスコープ内のデータの独立したコピーか、またはそれに対する参照です。</span><span class="sxs-lookup"><span data-stu-id="fec64-140">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="fec64-141">リモートとアウトプロセスのセッションでは、これらは常に独立したコピーです。</span><span class="sxs-lookup"><span data-stu-id="fec64-141">In remote and out-of-process sessions, they are always independent copies.</span></span> <span data-ttu-id="fec64-142">スレッドセッションでは、参照によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="fec64-142">In thread sessions, they are passed by reference.</span></span>

## <a name="serialization-of-variable-values"></a><span data-ttu-id="fec64-143">変数値のシリアル化</span><span class="sxs-lookup"><span data-stu-id="fec64-143">Serialization of variable values</span></span>

<span data-ttu-id="fec64-144">リモートで実行されるコマンドとバックグラウンドジョブはアウトプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fec64-144">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="fec64-145">アウトプロセスセッションでは、XML ベースのシリアル化と逆シリアル化を使用して、プロセスの境界を越えて変数の値を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fec64-145">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="fec64-146">シリアル化プロセスでは、オブジェクトは元のオブジェクトのプロパティを含む **PSObject** に変換されますが、そのメソッドは含まれません。</span><span class="sxs-lookup"><span data-stu-id="fec64-146">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="fec64-147">型の限定されたセットでは、逆シリアル化によって元の型に復元オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="fec64-147">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="fec64-148">復元オブジェクトは、元のオブジェクトインスタンスのコピーです。</span><span class="sxs-lookup"><span data-stu-id="fec64-148">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="fec64-149">これには、型のプロパティとメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="fec64-149">It has the type properties and methods.</span></span> <span data-ttu-id="fec64-150">System.string などの単純型の **場合、コピー** は完全に一致します。</span><span class="sxs-lookup"><span data-stu-id="fec64-150">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="fec64-151">複合型の場合、コピーは不完全です。</span><span class="sxs-lookup"><span data-stu-id="fec64-151">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="fec64-152">たとえば、復元された証明書オブジェクトには、秘密キーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="fec64-152">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="fec64-153">他のすべての型のインスタンスは **PSObject** インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="fec64-153">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="fec64-154">**PSTypeNames** プロパティには、 **逆シリアル化** された元の型名 (たとえば、Deserialized.System) が含まれてい **ます。Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="fec64-154">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

## <a name="using-local-variables-with-argumentlist-parameter"></a><span data-ttu-id="fec64-155">**ArgumentList** パラメーターでのローカル変数の使用</span><span class="sxs-lookup"><span data-stu-id="fec64-155">Using local variables with **ArgumentList** parameter</span></span>

<span data-ttu-id="fec64-156">リモートコマンドでローカル変数を使用するには、リモートコマンドのパラメーターを定義し、コマンドレットの **ArgumentList** パラメーターを使用して `Invoke-Command` ローカル変数をパラメーター値として指定します。</span><span class="sxs-lookup"><span data-stu-id="fec64-156">You can use local variables in a remote command by defining parameters for the remote command and using the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

- <span data-ttu-id="fec64-157">キーワードを使用して `param` 、リモートコマンドのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="fec64-157">Use the `param` keyword to define parameters for the remote command.</span></span> <span data-ttu-id="fec64-158">パラメーター名は、ローカル変数の名前と一致する必要がないプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="fec64-158">The parameter names are placeholders that don't need to match the local variable's name.</span></span>

- <span data-ttu-id="fec64-159">コマンドでキーワードで定義されているパラメーターを使用し `param` ます。</span><span class="sxs-lookup"><span data-stu-id="fec64-159">Use the parameters defined by the `param` keyword in the command.</span></span>

- <span data-ttu-id="fec64-160">コマンドレットの **ArgumentList** パラメーターを使用し `Invoke-Command` て、ローカル変数をパラメーター値として指定します。</span><span class="sxs-lookup"><span data-stu-id="fec64-160">Use the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

<span data-ttu-id="fec64-161">たとえば、次のコマンドでは、 `$ps` ローカルセッションで変数を定義し、リモートコマンドで使用します。</span><span class="sxs-lookup"><span data-stu-id="fec64-161">For example, the following commands define the `$ps` variable in the local session and then use it in a remote command.</span></span> <span data-ttu-id="fec64-162">このコマンドでは、パラメーター名としてを使用し、ローカル変数を値として使用し `$log` `$ps` ます。</span><span class="sxs-lookup"><span data-stu-id="fec64-162">The command uses `$log` as the parameter name and the local variable, `$ps`, as its value.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a><span data-ttu-id="fec64-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="fec64-163">See also</span></span>

[<span data-ttu-id="fec64-164">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="fec64-164">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="fec64-165">about_Remote</span><span class="sxs-lookup"><span data-stu-id="fec64-165">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="fec64-166">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="fec64-166">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="fec64-167">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="fec64-167">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="fec64-168">about_Variables</span><span class="sxs-lookup"><span data-stu-id="fec64-168">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="fec64-169">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="fec64-169">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="fec64-170">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fec64-170">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="fec64-171">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="fec64-171">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="fec64-172">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="fec64-172">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)

[<span data-ttu-id="fec64-173">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="fec64-173">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
