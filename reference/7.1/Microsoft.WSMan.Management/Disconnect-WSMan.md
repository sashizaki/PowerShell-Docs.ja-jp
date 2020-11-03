---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: 7e2cfc6db38d6537ba83c4dced769dd41a351602
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211712"
---
# <span data-ttu-id="edcfe-103">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="edcfe-103">Disconnect-WSMan</span></span>

## <span data-ttu-id="edcfe-104">概要</span><span class="sxs-lookup"><span data-stu-id="edcfe-104">SYNOPSIS</span></span>
<span data-ttu-id="edcfe-105">リモート コンピューター上の WinRM サービスからクライアントを切断します。</span><span class="sxs-lookup"><span data-stu-id="edcfe-105">Disconnects the client from the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="edcfe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="edcfe-106">SYNTAX</span></span>

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="edcfe-107">Description</span><span class="sxs-lookup"><span data-stu-id="edcfe-107">DESCRIPTION</span></span>
<span data-ttu-id="edcfe-108">**切断-WSMan** コマンドレットは、リモートコンピューター上の WinRM サービスからクライアントを切断します。</span><span class="sxs-lookup"><span data-stu-id="edcfe-108">The **Disconnect-WSMan** cmdlet disconnects the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="edcfe-109">WS-Management セッションを変数に保存した場合、セッションオブジェクトは変数に残りますが、WS-Management セッションの状態は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="edcfe-109">If you saved the WS-Management session in a variable, the session object remains in the variable, but the state of the WS-Management session is Closed.</span></span>
<span data-ttu-id="edcfe-110">WSMan プロバイダーのコンテキスト内でこのコマンドレットを使用すると、リモート コンピューター上の WinRM サービスからクライアントを切断できます。</span><span class="sxs-lookup"><span data-stu-id="edcfe-110">You can use this cmdlet within the context of the WSMan provider to disconnect the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="edcfe-111">ただし、WSMan プロバイダーに変更する前に、このコマンドレットを使用して、リモート コンピューター上の WinRM サービスから切断することもできます。</span><span class="sxs-lookup"><span data-stu-id="edcfe-111">However, you can also use this cmdlet to disconnect from the WinRM service on remote computers before you change to the WSMan provider.</span></span>

<span data-ttu-id="edcfe-112">リモート コンピューター上の WinRM サービスに接続する方法の詳細については、「Connect-WSMan」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edcfe-112">For more information about how to connect to the WinRM service on a remote computer, see Connect-WSMan.</span></span>

## <span data-ttu-id="edcfe-113">例</span><span class="sxs-lookup"><span data-stu-id="edcfe-113">EXAMPLES</span></span>

### <span data-ttu-id="edcfe-114">例 1: リモートコンピューターへの接続を削除する</span><span class="sxs-lookup"><span data-stu-id="edcfe-114">Example 1: Delete a connection to a remote computer</span></span>

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

<span data-ttu-id="edcfe-115">このコマンドは、server01 という名前のリモートコンピューターへの接続を削除します。</span><span class="sxs-lookup"><span data-stu-id="edcfe-115">This command deletes the connection to the remote computer named server01.</span></span>

<span data-ttu-id="edcfe-116">このコマンドレットは、通常、リモート コンピューター (この場合は、server01 コンピューター) から切断するために、WSMan プロバイダーのコンテキスト内で使用します。</span><span class="sxs-lookup"><span data-stu-id="edcfe-116">This cmdlet is generally used within the context of the WSMan provider to disconnect from a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="edcfe-117">ただし、WSMan プロバイダーに変更する前に、 **切断-wsman** を使用してリモートコンピューターへの接続を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="edcfe-117">However, you can also use **Disconnect-WSMan** to remove connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="edcfe-118">これらの接続は、ComputerName の一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="edcfe-118">Those connections do not appear in the ComputerName list.</span></span>

## <span data-ttu-id="edcfe-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="edcfe-119">PARAMETERS</span></span>

### <span data-ttu-id="edcfe-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="edcfe-120">-ComputerName</span></span>
<span data-ttu-id="edcfe-121">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="edcfe-121">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="edcfe-122">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="edcfe-122">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="edcfe-123">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="edcfe-123">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="edcfe-124">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="edcfe-124">The local computer is the default.</span></span>
<span data-ttu-id="edcfe-125">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edcfe-125">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="edcfe-126">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="edcfe-126">You can pipe a value for this parameter to the cmdlet.</span></span>

<span data-ttu-id="edcfe-127">ローカルホストから切断することはできません。</span><span class="sxs-lookup"><span data-stu-id="edcfe-127">You cannot disconnect from the local host.</span></span>
<span data-ttu-id="edcfe-128">つまり、ローカルコンピューターへの既定の接続を切断することはできません。</span><span class="sxs-lookup"><span data-stu-id="edcfe-128">That is, you cannot disconnect the default connection to the local computer.</span></span>
<span data-ttu-id="edcfe-129">ただし、たとえば、コンピューター名を使用して、ローカルコンピューターへの別の接続を作成する場合。</span><span class="sxs-lookup"><span data-stu-id="edcfe-129">However, if you create a separate connection to the local computer, for example, by using the computer name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edcfe-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="edcfe-130">CommonParameters</span></span>
<span data-ttu-id="edcfe-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="edcfe-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="edcfe-132">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edcfe-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="edcfe-133">入力</span><span class="sxs-lookup"><span data-stu-id="edcfe-133">INPUTS</span></span>

### <span data-ttu-id="edcfe-134">なし</span><span class="sxs-lookup"><span data-stu-id="edcfe-134">None</span></span>
<span data-ttu-id="edcfe-135">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="edcfe-135">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="edcfe-136">出力</span><span class="sxs-lookup"><span data-stu-id="edcfe-136">OUTPUTS</span></span>

### <span data-ttu-id="edcfe-137">なし</span><span class="sxs-lookup"><span data-stu-id="edcfe-137">None</span></span>
<span data-ttu-id="edcfe-138">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="edcfe-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="edcfe-139">注</span><span class="sxs-lookup"><span data-stu-id="edcfe-139">NOTES</span></span>

## <span data-ttu-id="edcfe-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="edcfe-140">RELATED LINKS</span></span>

[<span data-ttu-id="edcfe-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="edcfe-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="edcfe-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="edcfe-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="edcfe-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="edcfe-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="edcfe-144">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="edcfe-144">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="edcfe-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="edcfe-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="edcfe-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="edcfe-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="edcfe-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="edcfe-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="edcfe-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="edcfe-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="edcfe-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="edcfe-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="edcfe-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="edcfe-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="edcfe-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="edcfe-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="edcfe-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="edcfe-152">Test-WSMan</span></span>](Test-WSMan.md)

