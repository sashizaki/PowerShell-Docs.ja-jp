---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 235c775e2da4188213f4eb35612c469947b5e2fc
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219544"
---
# <span data-ttu-id="2d521-103">Get-Location</span><span class="sxs-lookup"><span data-stu-id="2d521-103">Get-Location</span></span>

## <span data-ttu-id="2d521-104">概要</span><span class="sxs-lookup"><span data-stu-id="2d521-104">SYNOPSIS</span></span>
<span data-ttu-id="2d521-105">現在の作業場所または場所スタックに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d521-105">Gets information about the current working location or a location stack.</span></span>

## <span data-ttu-id="2d521-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d521-106">SYNTAX</span></span>

### <span data-ttu-id="2d521-107">Location (既定値)</span><span class="sxs-lookup"><span data-stu-id="2d521-107">Location (Default)</span></span>

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2d521-108">スタック</span><span class="sxs-lookup"><span data-stu-id="2d521-108">Stack</span></span>

```
Get-Location [-Stack] [-StackName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2d521-109">Description</span><span class="sxs-lookup"><span data-stu-id="2d521-109">DESCRIPTION</span></span>

<span data-ttu-id="2d521-110">`Get-Location`コマンドレットは、print working directory (pwd) コマンドと同様に、現在のディレクトリを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d521-110">The `Get-Location` cmdlet gets an object that represents the current directory, much like the print working directory (pwd) command.</span></span>

<span data-ttu-id="2d521-111">PowerShell ドライブ間を移動すると、PowerShell は各ドライブ内の場所を保持します。</span><span class="sxs-lookup"><span data-stu-id="2d521-111">When you move between PowerShell drives, PowerShell retains your location in each drive.</span></span> <span data-ttu-id="2d521-112">このコマンドレットを使用すると、各ドライブ内の場所を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2d521-112">You can use this cmdlet to find your location in each drive.</span></span>

<span data-ttu-id="2d521-113">このコマンドレットを使用すると、実行時に現在のディレクトリを取得し、それを関数やスクリプト (PowerShell プロンプトで現在のディレクトリを表示する関数など) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d521-113">You can use this cmdlet to get the current directory at run time and use it in functions and scripts, such as in a function that displays the current directory in the PowerShell prompt.</span></span>

<span data-ttu-id="2d521-114">また、このコマンドレットを使用して、場所スタック内の場所を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d521-114">You can also use this cmdlet to display the locations in a location stack.</span></span> <span data-ttu-id="2d521-115">詳細については、 **Stack** および **Stackname** パラメーターのメモと説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d521-115">For more information, see the Notes and the descriptions of the **Stack** and **StackName** parameters.</span></span>

## <span data-ttu-id="2d521-116">例</span><span class="sxs-lookup"><span data-stu-id="2d521-116">EXAMPLES</span></span>

### <span data-ttu-id="2d521-117">例 1: 現在のドライブの場所を表示する</span><span class="sxs-lookup"><span data-stu-id="2d521-117">Example 1: Display your current drive location</span></span>

<span data-ttu-id="2d521-118">このコマンドを実行すると、現在の PowerShell ドライブ内の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-118">This command displays your location in the current PowerShell drive.</span></span>

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="2d521-119">たとえば、ドライブのディレクトリにいる場合は、その `Windows` `C:` ディレクトリへのパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-119">For instance, if you are in the `Windows` directory of the `C:` drive, it displays the path to that directory.</span></span>

### <span data-ttu-id="2d521-120">例 2: 異なるドライブの現在の場所を表示する</span><span class="sxs-lookup"><span data-stu-id="2d521-120">Example 2: Display your current location for different drives</span></span>

<span data-ttu-id="2d521-121">この例では、を使用し `Get-Location` て、さまざまな PowerShell ドライブに現在の場所を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2d521-121">This example demonstrates the use of `Get-Location` to display your current location in different PowerShell drives.</span></span> <span data-ttu-id="2d521-122">`Set-Location` は、異なる PSDrives 上の複数の異なるパスに場所を変更するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-122">`Set-Location` is used to change the location to several different paths on different PSDrives.</span></span>

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### <span data-ttu-id="2d521-123">例 3: スタックを使用して場所を取得する</span><span class="sxs-lookup"><span data-stu-id="2d521-123">Example 3: Get locations using stacks</span></span>

<span data-ttu-id="2d521-124">この例では、の **stack** および **stackname** パラメーターを使用して、 `Get-Location` 現在の場所スタックおよび代替位置スタック内の場所を一覧表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2d521-124">This example shows how to use the **Stack** and **StackName** parameters of `Get-Location` to list the locations in the current location stack and alternate location stacks.</span></span>

<span data-ttu-id="2d521-125">`Push-Location`コマンドレットは、3つの異なる場所に変更するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-125">The `Push-Location` cmdlet is used to change into three different locations.</span></span> <span data-ttu-id="2d521-126">3番目のプッシュでは、別のスタック名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-126">The third push uses a different stack name.</span></span> <span data-ttu-id="2d521-127">の **stack** パラメーターには、 `Get-Location` 既定のスタックの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-127">The **Stack** parameter of `Get-Location` displays the contents of the default stack.</span></span> <span data-ttu-id="2d521-128">の **Stackname** パラメーターは、 `Get-Location` という名前のスタックの内容を表示し `Stack2` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-128">The **StackName** parameter of `Get-Location` displays the contents of the stack named `Stack2`.</span></span>

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### <span data-ttu-id="2d521-129">例 4: PowerShell プロンプトをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="2d521-129">Example 4: Customize the PowerShell prompt</span></span>

<span data-ttu-id="2d521-130">この例では、PowerShell プロンプトをカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2d521-130">This example shows how to customize the PowerShell prompt.</span></span>

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

<span data-ttu-id="2d521-131">プロンプトを定義する関数には、コマンドが含まれてい `Get-Location` ます。このコマンドは、コンソールにプロンプトが表示されるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-131">The function that defines the prompt includes a `Get-Location` command, which is run whenever the prompt appears in the console.</span></span>

<span data-ttu-id="2d521-132">既定の PowerShell プロンプトの形式は、という特殊な関数によって定義され `prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-132">The format of the default PowerShell prompt is defined by a special function named `prompt`.</span></span> <span data-ttu-id="2d521-133">という名前の新しい関数を作成することにより、コンソールでプロンプトを変更でき `prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-133">You can change the prompt in your console by creating a new function named `prompt`.</span></span>

<span data-ttu-id="2d521-134">現在の prompt 関数を表示するには、次のコマンドを入力します。 `Get-Content Function:\prompt`</span><span class="sxs-lookup"><span data-stu-id="2d521-134">To see the current prompt function, type the following command: `Get-Content Function:\prompt`</span></span>

## <span data-ttu-id="2d521-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d521-135">PARAMETERS</span></span>

### <span data-ttu-id="2d521-136">-PSDrive</span><span class="sxs-lookup"><span data-stu-id="2d521-136">-PSDrive</span></span>

<span data-ttu-id="2d521-137">指定した PowerShell ドライブ内の現在の場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d521-137">Gets the current location in the specified PowerShell drive.</span></span>

<span data-ttu-id="2d521-138">たとえば、ドライブにいる場合は、 `Cert:` このパラメーターを使用してドライブ内の現在の場所を見つけることができ `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-138">For instance, if you are in the `Cert:` drive, you can use this parameter to find your current location in the `C:` drive.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d521-139">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="2d521-139">-PSProvider</span></span>

<span data-ttu-id="2d521-140">指定した PowerShell プロバイダーによってサポートされるドライブ内の現在の場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d521-140">Gets the current location in the drive supported by the specified PowerShell provider.</span></span>
<span data-ttu-id="2d521-141">指定したプロバイダーが複数のドライブをサポートしている場合、このコマンドレットは、最後にアクセスしたドライブ上の場所を返します。</span><span class="sxs-lookup"><span data-stu-id="2d521-141">If the specified provider supports more than one drive, this cmdlet returns the location on the most recently accessed drive.</span></span>

<span data-ttu-id="2d521-142">たとえば、ドライブにいる場合は、 `C:` このパラメーターを使用して、PowerShell **レジストリ** プロバイダーのドライブ内の現在の場所を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2d521-142">For example, if you are in the `C:` drive, you can use this parameter to find your current location in the drives of the PowerShell **Registry** provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d521-143">-Stack</span><span class="sxs-lookup"><span data-stu-id="2d521-143">-Stack</span></span>

<span data-ttu-id="2d521-144">このコマンドレットによって、現在の場所スタックに追加された場所が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2d521-144">Indicates that this cmdlet displays the locations added to the current location stack.</span></span> <span data-ttu-id="2d521-145">コマンドレットを使用して、スタックに場所を追加でき `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-145">You can add locations to stacks by using the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="2d521-146">別の場所スタック内の場所を表示するには、 **Stackname** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d521-146">To display the locations in a different location stack, use the **StackName** parameter.</span></span> <span data-ttu-id="2d521-147">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d521-147">For information about location stacks, see the [Notes](#notes).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d521-148">-StackName</span><span class="sxs-lookup"><span data-stu-id="2d521-148">-StackName</span></span>

<span data-ttu-id="2d521-149">名前付きの場所スタックを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="2d521-149">Specifies, as a string array, the named location stacks.</span></span> <span data-ttu-id="2d521-150">1 つ以上の場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d521-150">Enter one or more location stack names.</span></span>

<span data-ttu-id="2d521-151">現在の場所スタック内の場所を表示するには、 **stack** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d521-151">To display the locations in the current location stack, use the **Stack** parameter.</span></span> <span data-ttu-id="2d521-152">場所スタックを現在の場所スタックにするには、 `Set-Location` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d521-152">To make a location stack the current location stack, use the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="2d521-153">このコマンドレットでは、現在のスタックでない限り、名前のない既定のスタック内の場所を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d521-153">This cmdlet cannot display the locations in the unnamed default stack unless it is the current stack.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d521-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d521-154">CommonParameters</span></span>

<span data-ttu-id="2d521-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2d521-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d521-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d521-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d521-157">入力</span><span class="sxs-lookup"><span data-stu-id="2d521-157">INPUTS</span></span>

### <span data-ttu-id="2d521-158">なし</span><span class="sxs-lookup"><span data-stu-id="2d521-158">None</span></span>

<span data-ttu-id="2d521-159">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2d521-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2d521-160">出力</span><span class="sxs-lookup"><span data-stu-id="2d521-160">OUTPUTS</span></span>

### <span data-ttu-id="2d521-161">..................... PathInfo スタック</span><span class="sxs-lookup"><span data-stu-id="2d521-161">System.Management.Automation.PathInfo or System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="2d521-162">**Stack** パラメーターまたは **stackname** パラメーターを使用すると、このコマンドレットは **pathinfostack** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2d521-162">If you use the **Stack** or **StackName** parameters, this cmdlet returns a **PathInfoStack** object.</span></span> <span data-ttu-id="2d521-163">それ以外の場合は、 **Pathinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2d521-163">Otherwise, it returns a **PathInfo** object.</span></span>

## <span data-ttu-id="2d521-164">注</span><span class="sxs-lookup"><span data-stu-id="2d521-164">NOTES</span></span>

<span data-ttu-id="2d521-165">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2d521-165">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="2d521-166">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="2d521-166">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="2d521-167">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="2d521-167">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="2d521-168">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2d521-168">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>
<span data-ttu-id="2d521-169">コマンドレットにより、 `Get-Location` 現在の PowerShell 実行空間の現在のディレクトリが返されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-169">The `Get-Location` cmdlet returns the current directory of the current PowerShell runspace.</span></span>

<span data-ttu-id="2d521-170">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="2d521-170">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="2d521-171">セッションのプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="2d521-171">To list the providers in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="2d521-172">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d521-172">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="2d521-173">**Psprovider** 、 **PSDrive** 、 **Stack** 、 **stackname** の各パラメーターがどのように対話するかは、プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d521-173">The ways that the **PSProvider** , **PSDrive** , **Stack** , and **StackName** parameters interact depends on the provider.</span></span> <span data-ttu-id="2d521-174">ドライブとそのドライブを公開していないプロバイダーを指定した場合など、エラーになる組み合わせもあります。</span><span class="sxs-lookup"><span data-stu-id="2d521-174">Some combinations will result in errors, such as specifying both a drive and a provider that does not expose that drive.</span></span> <span data-ttu-id="2d521-175">パラメーターが指定されていない場合、このコマンドレットは、現在の作業場所を含むプロバイダーの **Pathinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2d521-175">If no parameters are specified, this cmdlet returns the **PathInfo** object for the provider that contains the current working location.</span></span>

<span data-ttu-id="2d521-176">スタックとは、最後に追加された項目のみがアクセス可能な後入れ先出しリストです。</span><span class="sxs-lookup"><span data-stu-id="2d521-176">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span> <span data-ttu-id="2d521-177">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d521-177">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="2d521-178">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="2d521-178">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="2d521-179">PowerShell では、名前のない既定の場所スタックが作成され、複数の名前付きロケーションスタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2d521-179">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="2d521-180">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d521-180">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="2d521-181">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2d521-181">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="2d521-182">場所スタックを管理するには、次のように PowerShell `*-Location` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d521-182">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows.</span></span>

- <span data-ttu-id="2d521-183">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-183">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="2d521-184">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-184">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="2d521-185">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-185">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="2d521-186">名前付きの場所スタック内の場所を表示するには、コマンドレットの **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-186">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="2d521-187">新しい場所スタックを作成するには、コマンドレットの **Stackname** パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-187">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span>
  <span data-ttu-id="2d521-188">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2d521-188">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="2d521-189">場所スタックを現在の場所スタックにするには、コマンドレットの **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-189">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="2d521-190">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2d521-190">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="2d521-191">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、このコマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d521-191">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use this cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="2d521-192">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="2d521-192">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="2d521-193">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2d521-193">RELATED LINKS</span></span>

[<span data-ttu-id="2d521-194">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="2d521-194">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="2d521-195">Push-Location</span><span class="sxs-lookup"><span data-stu-id="2d521-195">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="2d521-196">Set-Location</span><span class="sxs-lookup"><span data-stu-id="2d521-196">Set-Location</span></span>](Set-Location.md)
