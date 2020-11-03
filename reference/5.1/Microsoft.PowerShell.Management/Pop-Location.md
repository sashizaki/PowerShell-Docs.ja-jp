---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 6843a598b5d20ebd9819b2ed0b180cd21f0416f4
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "93219187"
---
# <span data-ttu-id="3f412-103">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="3f412-103">Pop-Location</span></span>

## <span data-ttu-id="3f412-104">概要</span><span class="sxs-lookup"><span data-stu-id="3f412-104">SYNOPSIS</span></span>
<span data-ttu-id="3f412-105">現在の場所を、最後にスタックにプッシュした場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="3f412-105">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="3f412-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f412-106">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="3f412-107">Description</span><span class="sxs-lookup"><span data-stu-id="3f412-107">DESCRIPTION</span></span>

<span data-ttu-id="3f412-108">コマンドレットは、 `Pop-Location` コマンドレットを使用して、現在の場所を最後にスタックにプッシュした場所に変更し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-108">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="3f412-109">既定のスタックから、またはコマンドを使用して作成したスタックから、場所をポップでき `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-109">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="3f412-110">例</span><span class="sxs-lookup"><span data-stu-id="3f412-110">EXAMPLES</span></span>

### <span data-ttu-id="3f412-111">例 1: 最新の場所に変更する</span><span class="sxs-lookup"><span data-stu-id="3f412-111">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="3f412-112">このコマンドを実行すると、現在のスタックに最後に追加した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f412-112">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="3f412-113">例 2: 名前付きスタック内の最新の場所に変更する</span><span class="sxs-lookup"><span data-stu-id="3f412-113">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="3f412-114">このコマンドを実行すると、場所スタック Stack2 に最後に追加した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f412-114">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="3f412-115">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f412-115">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="3f412-116">例 3: 異なるプロバイダーの場所を移動する</span><span class="sxs-lookup"><span data-stu-id="3f412-116">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="3f412-117">これらのコマンドは、コマンドレットとコマンドレットを使用して、 `Push-Location` `Pop-Location` 異なる PowerShell プロバイダーでサポートされる場所間を移動します。</span><span class="sxs-lookup"><span data-stu-id="3f412-117">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="3f412-118">これらのコマンドは、 `pushd` の別名 `Push-Location` との別名を使用し `popd` `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-118">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="3f412-119">最初のコマンドは、現在のファイルシステムの場所をスタックにプッシュし、PowerShell レジストリプロバイダーでサポートされている HKLM ドライブに移動します。</span><span class="sxs-lookup"><span data-stu-id="3f412-119">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="3f412-120">2番目のコマンドは、レジストリの場所をスタックにプッシュし、PowerShell 証明書プロバイダーでサポートされている場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f412-120">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="3f412-121">最後の 2 つのコマンドにより、これらの場所がスタックからポップされます。</span><span class="sxs-lookup"><span data-stu-id="3f412-121">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="3f412-122">最初の `popd` コマンドはレジストリドライブに戻り、2番目のコマンドはファイルシステムドライブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="3f412-122">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="3f412-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f412-123">PARAMETERS</span></span>

### <span data-ttu-id="3f412-124">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3f412-124">-PassThru</span></span>

<span data-ttu-id="3f412-125">位置を表すオブジェクトをパイプラインに渡します。</span><span class="sxs-lookup"><span data-stu-id="3f412-125">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="3f412-126">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3f412-126">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f412-127">-StackName</span><span class="sxs-lookup"><span data-stu-id="3f412-127">-StackName</span></span>

<span data-ttu-id="3f412-128">場所をポップする場所スタックを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f412-128">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="3f412-129">場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f412-129">Enter a location stack name.</span></span>

<span data-ttu-id="3f412-130">このパラメーターを指定しないと、は `Pop-Location` 現在の場所スタックから場所をポップします。</span><span class="sxs-lookup"><span data-stu-id="3f412-130">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="3f412-131">既定では、現在の場所スタックは、PowerShell によって作成される名前のない既定の場所スタックです。</span><span class="sxs-lookup"><span data-stu-id="3f412-131">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="3f412-132">場所スタックを現在の場所スタックにするには、コマンドレットの **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-132">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="3f412-133">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f412-133">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="3f412-134">`Pop-Location` 現在の場所スタックでない限り、名前のない既定のスタックから場所をポップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3f412-134">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3f412-135">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="3f412-135">-UseTransaction</span></span>

<span data-ttu-id="3f412-136">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f412-136">Includes the command in the active transaction.</span></span> <span data-ttu-id="3f412-137">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="3f412-137">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="3f412-138">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f412-138">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f412-139">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f412-139">CommonParameters</span></span>

<span data-ttu-id="3f412-140">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3f412-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3f412-141">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f412-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3f412-142">入力</span><span class="sxs-lookup"><span data-stu-id="3f412-142">INPUTS</span></span>

### <span data-ttu-id="3f412-143">なし</span><span class="sxs-lookup"><span data-stu-id="3f412-143">None</span></span>

<span data-ttu-id="3f412-144">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3f412-144">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3f412-145">出力</span><span class="sxs-lookup"><span data-stu-id="3f412-145">OUTPUTS</span></span>

### <span data-ttu-id="3f412-146">なし、システムの管理. PathInfo</span><span class="sxs-lookup"><span data-stu-id="3f412-146">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="3f412-147">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、場所を表す **system.string オブジェクトを** 生成します。</span><span class="sxs-lookup"><span data-stu-id="3f412-147">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="3f412-148">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3f412-148">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3f412-149">注</span><span class="sxs-lookup"><span data-stu-id="3f412-149">NOTES</span></span>

<span data-ttu-id="3f412-150">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3f412-150">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="3f412-151">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="3f412-151">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="3f412-152">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="3f412-152">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="3f412-153">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f412-153">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="3f412-154">場所のコマンドレットでプロセス全体の現在のディレクトリが設定されていても、別の実行空間によっていつでも変更される可能性があるため、このディレクトリに依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="3f412-154">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="3f412-155">現在の実行空間に固有の現在の作業ディレクトリを使用して、パスベースの操作を実行するには、location コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f412-155">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="3f412-156">スタックとは、最後に追加された項目だけにアクセスできる、後入れ先出しのリストです。</span><span class="sxs-lookup"><span data-stu-id="3f412-156">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="3f412-157">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f412-157">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="3f412-158">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="3f412-158">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="3f412-159">PowerShell では、名前のない既定の場所スタックが作成され、複数の名前付きロケーションスタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f412-159">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="3f412-160">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f412-160">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="3f412-161">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3f412-161">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="3f412-162">場所スタックを管理するには、次のように PowerShell `*-Location` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f412-162">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="3f412-163">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-163">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="3f412-164">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-164">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="3f412-165">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-165">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="3f412-166">名前付きの場所スタック内の場所を表示するには、コマンドレットの **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-166">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="3f412-167">新しい場所スタックを作成するには、コマンドレットの **Stackname** パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-167">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="3f412-168">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3f412-168">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="3f412-169">場所スタックを現在の場所スタックにするには、コマンドレットの **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-169">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="3f412-170">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f412-170">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="3f412-171">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、コマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなり `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-171">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="3f412-172">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$Null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-172">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="3f412-173">また、組み込みエイリアスであるを参照することもでき `Pop-Location` `popd` ます。</span><span class="sxs-lookup"><span data-stu-id="3f412-173">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="3f412-174">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f412-174">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="3f412-175">`Pop-Location` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3f412-175">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3f412-176">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="3f412-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3f412-177">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f412-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3f412-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3f412-178">RELATED LINKS</span></span>

[<span data-ttu-id="3f412-179">Get-Location</span><span class="sxs-lookup"><span data-stu-id="3f412-179">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="3f412-180">Push-Location</span><span class="sxs-lookup"><span data-stu-id="3f412-180">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="3f412-181">Set-Location</span><span class="sxs-lookup"><span data-stu-id="3f412-181">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="3f412-182">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="3f412-182">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="3f412-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3f412-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
