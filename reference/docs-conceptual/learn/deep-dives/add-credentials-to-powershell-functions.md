---
title: PowerShell 関数への資格情報サポートの追加
description: PowerShell のスクリプト、関数、およびコマンドレットに資格情報パラメーターを追加する方法。
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: fb85d47121dc106ae04742254f418e2c727f6157
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143155"
---
# <a name="add-credential-support-to-powershell-functions"></a><span data-ttu-id="86ef4-103">PowerShell 関数への資格情報サポートの追加</span><span class="sxs-lookup"><span data-stu-id="86ef4-103">Add Credential support to PowerShell functions</span></span>

> [!NOTE]
> <span data-ttu-id="86ef4-104">この記事の[オリジナル バージョン][]は、[@joshduffney][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-104">The [original version][] of this article appeared on the blog written by [@joshduffney][].</span></span> <span data-ttu-id="86ef4-105">この記事は、このサイトに追加するために編集されています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-105">This article has been edited for inclusion on this site.</span></span> <span data-ttu-id="86ef4-106">このコンテンツを共有してくださった Josh 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-106">The PowerShell team thanks Josh for sharing this content with us.</span></span> <span data-ttu-id="86ef4-107">同氏のブログは [duffney.io][] で確認してください。</span><span class="sxs-lookup"><span data-stu-id="86ef4-107">Please check out his blog at [duffney.io][].</span></span>

<span data-ttu-id="86ef4-108">この記事では、PowerShell 関数に資格情報パラメーターを追加する方法と、それが必要な理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-108">This article shows you how to add credential parameters to PowerShell functions and why you'd want to.</span></span> <span data-ttu-id="86ef4-109">資格情報パラメーターを使用すると、関数またはコマンドレットを別のユーザーとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-109">A credential parameter is to allow you to run the function or cmdlet as a different user.</span></span> <span data-ttu-id="86ef4-110">最も一般的な用途は、関数またはコマンドレットを管理者特権のユーザー アカウントとして実行することです。</span><span class="sxs-lookup"><span data-stu-id="86ef4-110">The most common use is to run the function or cmdlet as an elevated user account.</span></span>

<span data-ttu-id="86ef4-111">たとえば、コマンドレット `New-ADUser` には **Credential** パラメーターがあり、ドメイン管理者の資格情報を指定してドメイン内にアカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-111">For example, the cmdlet `New-ADUser` has a **Credential** parameter, which you could provide domain admin credentials to create an account in a domain.</span></span> <span data-ttu-id="86ef4-112">PowerShell セッションが実行されている通常のアカウントに、まだそのアクセス権がないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-112">Assuming your normal account running the PowerShell session doesn't have that access already.</span></span>

## <a name="creating-credential-object"></a><span data-ttu-id="86ef4-113">資格情報オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="86ef4-113">Creating credential object</span></span>

<span data-ttu-id="86ef4-114">[PSCredential][] オブジェクトは、ユーザー名やパスワードなどの一連のセキュリティ資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-114">The [PSCredential][] object represents a set of security credentials such as a user name and password.</span></span> <span data-ttu-id="86ef4-115">オブジェクトは、その資格情報オブジェクト内でユーザー アカウントとして実行される関数にパラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-115">The object can be passed as a parameter to a function that runs as the user account in that credential object.</span></span> <span data-ttu-id="86ef4-116">資格情報オブジェクトを作成するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-116">There are a few ways that you can create a credential object.</span></span> <span data-ttu-id="86ef4-117">資格情報オブジェクトを作成する 1 つ目の方法は、PowerShell コマンドレット `Get-Credential` を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-117">The first way to create a credential object is to use the PowerShell cmdlet `Get-Credential`.</span></span> <span data-ttu-id="86ef4-118">パラメーターを指定せずに実行すると、ユーザー名とパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-118">When you run without parameters, it prompts you for a username and password.</span></span> <span data-ttu-id="86ef4-119">または、省略可能なパラメーターをいくつか指定してそのコマンドレットを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-119">Or you can call the cmdlet with some optional parameters.</span></span>

<span data-ttu-id="86ef4-120">ドメイン名とユーザー名を事前に指定するには、 **Credential** パラメーターまたは **UserName** パラメーターのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-120">To specify the domain name and username ahead of time you can use either the **Credential** or **UserName** parameters.</span></span> <span data-ttu-id="86ef4-121">**UserName** パラメーターを使用するときは、 **Message** 値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-121">When you use the **UserName** parameter, you're also required to provide a **Message** value.</span></span> <span data-ttu-id="86ef4-122">以下のコードは、そのコマンドレットの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-122">The code below demonstrates using the cmdlet.</span></span> <span data-ttu-id="86ef4-123">資格情報オブジェクトを変数に格納して、その資格情報が複数回使用されるように設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-123">You can also store the credential object in a variable so that you can use the credential multiple times.</span></span> <span data-ttu-id="86ef4-124">次の例は、その資格情報オブジェクトが変数 `$Cred` に格納されています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-124">In the example below, the credential object is stored in the variable `$Cred`.</span></span>

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

<span data-ttu-id="86ef4-125">場合によっては、前の例で示したように、資格情報オブジェクトを作成する対話型のメソッドを使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-125">Sometimes, you can't use the interactive method of creating credential objects shown in the previous example.</span></span> <span data-ttu-id="86ef4-126">ほとんどの自動化ツールには、非対話型のメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-126">Most automation tools require a non-interactive method.</span></span> <span data-ttu-id="86ef4-127">ユーザーの操作なしで資格情報を作成するには、パスワードが含まれるセキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-127">To create a credential without user interaction, create a secure string containing the password.</span></span> <span data-ttu-id="86ef4-128">その後、セキュリティで保護された文字列とユーザー名を `System.Management.Automation.PSCredential()` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-128">Then pass the secure string and user name to the `System.Management.Automation.PSCredential()` method.</span></span>

<span data-ttu-id="86ef4-129">次のコマンドを使用して、パスワードが含まれるセキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-129">Use the following command to create a secure string containing the password:</span></span>

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

<span data-ttu-id="86ef4-130">**AsPlainText** パラメーターと **Force** パラメーターは両方とも必須です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-130">Both the **AsPlainText** and **Force** parameters are required.</span></span> <span data-ttu-id="86ef4-131">これらのパラメーターを指定しないと、セキュリティで保護された文字列にプレーン テキストを渡してはならないことを示す警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-131">Without those parameters, you receive a message warning that you shouldn't pass plain text into a secure string.</span></span> <span data-ttu-id="86ef4-132">プレーン テキストのパスワードがさまざまなログに記録されるため、PowerShell によってこの警告が返されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-132">PowerShell returns this warning because the plain text password gets recorded in various logs.</span></span> <span data-ttu-id="86ef4-133">セキュリティで保護された文字列を作成したら、それを `PSCredential()` メソッドに渡して資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-133">Once you have a secure string created, you need to pass it to the `PSCredential()` method to create the credential object.</span></span> <span data-ttu-id="86ef4-134">次の例では、`$password` 変数に資格情報オブジェクトが含まれるセキュリティで保護された文字列 `$Cred` が格納されています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-134">In the following example, the variable `$password` contains the secure string `$Cred` contains the credential object.</span></span>

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

<span data-ttu-id="86ef4-135">ここまでで、資格情報オブジェクトを作成する方法について説明しました。次は、資格情報パラメーターを PowerShell 関数に追加します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-135">Now that you know how to create credential objects, you can add credential parameters to your PowerShell functions.</span></span>

## <a name="adding-a-credential-parameter"></a><span data-ttu-id="86ef4-136">資格情報パラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="86ef4-136">Adding a Credential Parameter</span></span>

<span data-ttu-id="86ef4-137">まずは他のパラメーターと同様に、関数の `param` ブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-137">Just like any other parameter, you start off by adding it in the `param` block of your function.</span></span>
<span data-ttu-id="86ef4-138">パラメーターの名前は、`$Credential` に指定することをお勧めします。これが既存の PowerShell コマンドレットで使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="86ef4-138">It's recommended that you name the parameter `$Credential` because that's what existing PowerShell cmdlets use.</span></span> <span data-ttu-id="86ef4-139">パラメーターの型は `[System.Management.Automation.PSCredential]` にしてください。</span><span class="sxs-lookup"><span data-stu-id="86ef4-139">The type of the parameter should be `[System.Management.Automation.PSCredential]`.</span></span>

<span data-ttu-id="86ef4-140">次の例は、`Get-Something` と呼ばれる関数のパラメーター ブロックを示しています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-140">The following example shows the parameter block for a function called `Get-Something`.</span></span> <span data-ttu-id="86ef4-141">`$Name` と `$Credential` という 2 つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-141">It has two parameters: `$Name` and `$Credential`.</span></span>

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

<span data-ttu-id="86ef4-142">この例のコードは、資格情報パラメーターとして十分に実用的ですが、いくつかの機能を追加して、より堅牢性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-142">The code in this example is enough to have a working credential parameter, however there are a few things you can add to make it more robust.</span></span>

- <span data-ttu-id="86ef4-143">`[ValidateNotNull()]` 検証属性を追加して、 **Credential** に渡される値を確認する。</span><span class="sxs-lookup"><span data-stu-id="86ef4-143">Add the `[ValidateNotNull()]` validation attribute to check that the value being passed to **Credential**.</span></span> <span data-ttu-id="86ef4-144">パラメーター値が null の場合、この属性により無効な資格情報で関数が実行されなくなります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-144">If the parameter value is null, this attribute prevents the function from executing with invalid credentials.</span></span>

- <span data-ttu-id="86ef4-145">`[System.Management.Automation.Credential()]`を追加します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-145">Add `[System.Management.Automation.Credential()]`.</span></span> <span data-ttu-id="86ef4-146">これにより、ユーザー名を文字列として渡し、パスワードの入力を求める対話型のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-146">This allows you to pass in a username as a string and have an interactive prompt for the password.</span></span>

- <span data-ttu-id="86ef4-147">`$Credential` パラメーターの既定値を `[System.Management.Automation.PSCredential]::Empty` に設定する。</span><span class="sxs-lookup"><span data-stu-id="86ef4-147">Set a default value for the `$Credential` parameter to `[System.Management.Automation.PSCredential]::Empty`.</span></span> <span data-ttu-id="86ef4-148">この関数では、ユーザーはこの `$Credential` オブジェクトを既存の PowerShell コマンドレットに渡している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-148">Your function you might be passing this `$Credential` object to existing PowerShell cmdlets.</span></span> <span data-ttu-id="86ef4-149">関数内で呼び出されたコマンドレットに null 値を指定すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-149">Providing a null value to the cmdlet called inside your function causes an error.</span></span> <span data-ttu-id="86ef4-150">空の資格情報オブジェクトを指定すると、このエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-150">Providing an empty credential object avoids this error.</span></span>

> [!TIP]
> <span data-ttu-id="86ef4-151">資格情報パラメーターを受け取る一部のコマンドレットで、サポートされる必要がある `[System.Management.Automation.PSCredential]::Empty` がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="86ef4-151">Some cmdlets that accept a credential parameter do not support `[System.Management.Automation.PSCredential]::Empty` as they should.</span></span> <span data-ttu-id="86ef4-152">回避策については、「[レガシ コマンドレットの処理」](#dealing-with-legacy-cmdlets)のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86ef4-152">See the [Dealing with Legacy Cmdlets](#dealing-with-legacy-cmdlets) section for a workaround.</span></span>

## <a name="using-credential-parameters"></a><span data-ttu-id="86ef4-153">資格情報パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="86ef4-153">Using credential parameters</span></span>

<span data-ttu-id="86ef4-154">次の例は、資格情報パラメーターを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-154">The following example demonstrates how to use credential parameters.</span></span> <span data-ttu-id="86ef4-155">この例は、[The Pester Book][] から抜粋した `Set-RemoteRegistryValue` と呼ばれる関数を示します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-155">This example shows a function called `Set-RemoteRegistryValue`, which is out of [The Pester Book][].</span></span> <span data-ttu-id="86ef4-156">この関数により、前のセクションで説明した手法を使用して、資格情報パラメーターが定義されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-156">This function defines the credential parameter using the techniques describe in the previous section.</span></span> <span data-ttu-id="86ef4-157">その関数により、その関数によって作成された `$Credential` 変数を使用して `Invoke-Command` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-157">The function calls `Invoke-Command` using the `$Credential` variable created by the function.</span></span> <span data-ttu-id="86ef4-158">これにより、`Invoke-Command` を実行しているユーザーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-158">This allows you to change the user who's running `Invoke-Command`.</span></span> <span data-ttu-id="86ef4-159">`$Credential` の既定値は空の資格情報であるため、その関数は資格情報の指定なしで実行されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-159">Because the default value of `$Credential` is an empty credential, the function can run without providing credentials.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

<span data-ttu-id="86ef4-160">次のセクションでは、`Set-RemoteRegistryValue` に資格情報を指定するさまざまな方法を示します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-160">The following sections show different methods of providing credentials to `Set-RemoteRegistryValue`.</span></span>

### <a name="prompting-for-credentials"></a><span data-ttu-id="86ef4-161">資格情報の入力を求めるダイアログを表示する</span><span class="sxs-lookup"><span data-stu-id="86ef4-161">Prompting for credentials</span></span>

<span data-ttu-id="86ef4-162">実行時に `Get-Credential` を かっこ (`()`) 内で使用すると、最初に `Get-credential` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-162">Using `Get-Credential` in parentheses `()` at run time causes the `Get-credential` to run first.</span></span> <span data-ttu-id="86ef4-163">ユーザー名とパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-163">You are prompted for a username and password.</span></span> <span data-ttu-id="86ef4-164">`Get-credential` の **Credential** パラメーターまたは **UserName** パラメーターを使用して、ユーザー名とドメインを事前に設定できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-164">You could use the **Credential** or **UserName** parameters of `Get-credential` to pre-populate the username and domain.</span></span> <span data-ttu-id="86ef4-165">次の例では、スプラッティングという手法を使用して、`Set-RemoteRegistryValue` 関数にパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-165">The following example uses a technique called splatting to pass parameters to the `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="86ef4-166">スプラッティングの詳細については、「[about_Splatting][]」の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86ef4-166">For more information about splatting, check out the [about_Splatting][] article.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![実行時に資格情報を取得する](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

<span data-ttu-id="86ef4-168">`(Get-Credential)` を使用することは、一見煩雑です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-168">Using `(Get-Credential)` seems cumbersome.</span></span> <span data-ttu-id="86ef4-169">通常、ユーザー名のみが指定された **Credential** パラメーターを使用すると、そのコマンドレットによって自動的にパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-169">Normally, when you use the **Credential** parameter with only a username, the cmdlet automatically prompts for the password.</span></span> <span data-ttu-id="86ef4-170">`[System.Management.Automation.Credential()]` 属性を使用すると、この動作が有効になります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-170">The `[System.Management.Automation.Credential()]` attribute enables this behavior.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![資格情報の要求](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> <span data-ttu-id="86ef4-172">表示されるレジストリ値を設定するために、これらの例では、Windows の **Web サーバー** 機能がインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-172">To set the registry value shown, these examples assume you have the **Web Server** features of Windows installed.</span></span> <span data-ttu-id="86ef4-173">必要に応じて、`Install-WindowsFeature Web-Server` と `Install-WindowsFeature web-mgmt-tools` を実行します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-173">Run `Install-WindowsFeature Web-Server` and `Install-WindowsFeature web-mgmt-tools` if required.</span></span>

### <a name="provide-credentials-in-a-variable"></a><span data-ttu-id="86ef4-174">変数に資格情報を指定する</span><span class="sxs-lookup"><span data-stu-id="86ef4-174">Provide credentials in a variable</span></span>

<span data-ttu-id="86ef4-175">資格情報変数を事前に設定し、`Set-RemoteRegistryValue` 関数の **Credential** パラメーターに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-175">You can also populate a credential variable ahead of time and pass it to the **Credential** parameter of `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="86ef4-176">この方法は、Jenkins、TeamCity、Octopus Deploy などの継続的インテグレーション/継続的配置 (CI/CD) ツールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-176">Use this method with Continuous Integration / Continuous Deployment (CI/CD) tools such as Jenkins, TeamCity, and Octopus Deploy.</span></span> <span data-ttu-id="86ef4-177">Jenkins の使用例については、Hodge のブログ記事「[Windows での Jenkins と PowerShell を使用した自動化 - パート 2][]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86ef4-177">For an example using Jenkins, check out Hodge's blog post [Automating with Jenkins and PowerShell on Windows - Part 2][].</span></span>

<span data-ttu-id="86ef4-178">この例では、.NET メソッドを使用してその資格情報オブジェクトとセキュリティで保護された文字列を作成し、パスワードを渡します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-178">This example uses the .NET method to create the credential object and a secure string to pass in the password.</span></span>

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

<span data-ttu-id="86ef4-179">この例の場合、クリア テキストのパスワードを使用して、セキュリティで保護された文字列が作成されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-179">For this example, the secure string is created using a clear text password.</span></span> <span data-ttu-id="86ef4-180">以前に説明した CI/CD にはすべて、実行時にそのパスワードを指定する、セキュリティで保護されたメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="86ef4-180">All of the previously mentioned CI/CD have a secure method of providing that password at run time.</span></span> <span data-ttu-id="86ef4-181">これらのツールを使用するときは、プレーン テキストのパスワードを、使用する CI/CD ツール内で定義された変数に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-181">When using those tools, replace the plain text password with the variable defined within the CI/CD tool you use.</span></span>

### <a name="run-without-credentials"></a><span data-ttu-id="86ef4-182">資格情報を使用しないで実行する</span><span class="sxs-lookup"><span data-stu-id="86ef4-182">Run without credentials</span></span>

<span data-ttu-id="86ef4-183">`$Credential` の既定値は空の資格情報オブジェクトであるため、次の例に示すように、資格情報なしでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-183">Since `$Credential` defaults to an empty credential object, you can run the command without credentials, as shown in this example:</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a><span data-ttu-id="86ef4-184">レガシ コマンドレットに対処する</span><span class="sxs-lookup"><span data-stu-id="86ef4-184">Dealing with legacy cmdlets</span></span>

<span data-ttu-id="86ef4-185">すべてのコマンドレットで、資格情報オブジェクトがサポートされていたり、空の資格情報が許可されていたりするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="86ef4-185">Not all cmdlets support credential objects or allow empty credentials.</span></span> <span data-ttu-id="86ef4-186">代わりに、コマンドレットには文字列としてのユーザー名とパスワードのパラメーターが求められます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-186">Instead, the cmdlet wants username and password parameters as strings.</span></span> <span data-ttu-id="86ef4-187">この制限を回避するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-187">There are a few ways to work around this limitation.</span></span>

### <a name="using-if-else-to-handle-empty-credentials"></a><span data-ttu-id="86ef4-188">if-else を使用して空の資格情報を処理する</span><span class="sxs-lookup"><span data-stu-id="86ef4-188">Using if-else to handle empty credentials</span></span>

<span data-ttu-id="86ef4-189">このシナリオでは、実行するコマンドレットで空の資格情報オブジェクトは受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="86ef4-189">In this scenario, the cmdlet you want to run doesn't accept an empty credential object.</span></span> <span data-ttu-id="86ef4-190">この例では、 **Credential** パラメーターが空でない場合にのみ、`Invoke-Command` に追加します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-190">This example adds the **Credential** parameter to `Invoke-Command` only if it's not empty.</span></span> <span data-ttu-id="86ef4-191">それ以外の場合は、 **Credential** パラメーターなしで `Invoke-Command` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-191">Otherwise, it runs the `Invoke-Command` without the **Credential** parameter.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a><span data-ttu-id="86ef4-192">スプラッティングを使用して空の資格情報を処理する</span><span class="sxs-lookup"><span data-stu-id="86ef4-192">Using splatting to handle empty credentials</span></span>

<span data-ttu-id="86ef4-193">この例では、パラメーターのスプラッティングを使用して、レガシ コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-193">This example uses parameter splatting to call the legacy cmdlet.</span></span> <span data-ttu-id="86ef4-194">`$Credential` オブジェクトは、スプラッティングのためにハッシュ テーブルに条件付きで追加され、`Invoke-Command` スクリプト ブロックを繰り返す必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-194">The `$Credential` object is conditionally added to the hash table for splatting and avoids the need to repeat the `Invoke-Command` script block.</span></span> <span data-ttu-id="86ef4-195">関数内のスプラッティングの詳細については、「[高度な関数内でのパラメーターのスプラッティング][]」のブログ記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86ef4-195">To learn more about splatting inside functions, see the [Splatting Parameters Inside Advanced Functions][] blog post.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a><span data-ttu-id="86ef4-196">文字列のパスワードを使用する</span><span class="sxs-lookup"><span data-stu-id="86ef4-196">Working with string passwords</span></span>

<span data-ttu-id="86ef4-197">`Invoke-Sqlcmd` コマンドレットは、文字列をパスワードとして受け取るコマンドレットの例です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-197">The `Invoke-Sqlcmd` cmdlet is an example of a cmdlet that accepts a string as a password.</span></span>
<span data-ttu-id="86ef4-198">`Invoke-Sqlcmd` を使用すると、SQL の単純な insert、update、および delete ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-198">`Invoke-Sqlcmd` allows you to run simple SQL insert, update, and delete statements.</span></span> <span data-ttu-id="86ef4-199">`Invoke-Sqlcmd` には、よりセキュリティで保護された資格情報オブジェクトではなく、クリアテキストのユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="86ef4-199">`Invoke-Sqlcmd` requires a clear-text username and password rather than a more secure credential object.</span></span> <span data-ttu-id="86ef4-200">この例では、資格情報オブジェクトからユーザー名とパスワードを抽出する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-200">This example shows how to extract the username and password from a credential object.</span></span>

<span data-ttu-id="86ef4-201">この例の `Get-AllSQLDatabases` 関数では、`Invoke-Sqlcmd` コマンドレットを呼び出して、SQL Server のすべてのデータベースに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="86ef4-201">The `Get-AllSQLDatabases` function in this example calls the `Invoke-Sqlcmd` cmdlet to query a SQL server for all its databases.</span></span> <span data-ttu-id="86ef4-202">その関数により、前の例で使用したのと同じ属性を持つ **Credential** パラメーターが定義されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-202">The function defines a **Credential** parameter with the same attribute used in the previous examples.</span></span> <span data-ttu-id="86ef4-203">ユーザー名とパスワードは `$Credential` 変数内に存在するため、それらの値を抽出して `Invoke-Sqlcmd` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-203">Since the username and password exist within the `$Credential` variable, you can extract those values for use with `Invoke-Sqlcmd`.</span></span>

<span data-ttu-id="86ef4-204">ユーザー名は `$Credential` 変数の **UserName** プロパティから使用できます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-204">The user name is available from the **UserName** property of the `$Credential` variable.</span></span> <span data-ttu-id="86ef4-205">パスワードを取得するには、`$Credential` オブジェクトの `GetNetworkCredential()` メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-205">To obtain the password, you have to use the `GetNetworkCredential()` method of the `$Credential` object.</span></span> <span data-ttu-id="86ef4-206">値は、`Invoke-Sqlcmd` へのパラメーターのスプラッティングのために使用されるハッシュ テーブルに追加された変数に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-206">The values are extracted into variables that are added to a hash table used for splatting parameters to `Invoke-Sqlcmd`.</span></span>

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a><span data-ttu-id="86ef4-207">資格情報の管理を継続的に学習する</span><span class="sxs-lookup"><span data-stu-id="86ef4-207">Continued learning credential management</span></span>

<span data-ttu-id="86ef4-208">資格情報オブジェクトを安全に作成して保存することは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="86ef4-208">Creating and storing credential objects securely can be difficult.</span></span> <span data-ttu-id="86ef4-209">次のリソースは、PowerShell 資格情報の管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86ef4-209">The following resources can help you maintain PowerShell credentials.</span></span>

- <span data-ttu-id="86ef4-210">[BetterCredentials][]</span><span class="sxs-lookup"><span data-stu-id="86ef4-210">[BetterCredentials][]</span></span>
- <span data-ttu-id="86ef4-211">[Azure Key Vault][]</span><span class="sxs-lookup"><span data-stu-id="86ef4-211">[Azure Key Vault][]</span></span>
- <span data-ttu-id="86ef4-212">[Vault Project][]</span><span class="sxs-lookup"><span data-stu-id="86ef4-212">[Vault Project][]</span></span>
- <span data-ttu-id="86ef4-213">[SecretManagement モジュール][]</span><span class="sxs-lookup"><span data-stu-id="86ef4-213">[SecretManagement module][]</span></span>

<!-- link references -->
[オリジナル バージョン]: https://duffney.io/addcredentialstopowershellfunctions/
[original version]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[Vault Project]: https://www.vaultproject.io/
[高度な関数内でのパラメーターのスプラッティング]: http://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Splatting Parameters Inside Advanced Functions]: http://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Windows での Jenkins と PowerShell を使用した自動化 - パート 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[Automating with Jenkins and PowerShell on Windows - Part 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[SecretManagement モジュール]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
[SecretManagement module]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
