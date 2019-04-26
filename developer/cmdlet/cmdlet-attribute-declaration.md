---
title: コマンドレットの属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlet attribute, described
- attributes, Cmdlet
- Cmdlet attribute
ms.assetid: 1d323332-f773-4c0e-8a69-2aada765afb2
caps.latest.revision: 12
ms.openlocfilehash: 6887467ad5ccafe6edf8f03f531b4750133aa9e9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068625"
---
# <a name="cmdlet-attribute-declaration"></a><span data-ttu-id="e851e-102">コマンドレット属性の宣言</span><span class="sxs-lookup"><span data-stu-id="e851e-102">Cmdlet Attribute Declaration</span></span>

<span data-ttu-id="e851e-103">コマンドレット属性は、コマンドレットとして Microsoft .NET Framework クラスを識別し、コマンドレットを呼び出すために使用する名詞と動詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-103">The Cmdlet attribute identifies a Microsoft .NET Framework class as a cmdlet and specifies the verb and noun used to invoke the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="e851e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e851e-104">Syntax</span></span>

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="e851e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e851e-105">Parameters</span></span>

<span data-ttu-id="e851e-106">`VerbName` ([System.String](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e851e-106">`VerbName` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="e851e-107">コマンドレットの動詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-107">Specifies the cmdlet verb.</span></span> <span data-ttu-id="e851e-108">この動詞は、コマンドレットによって実行されるアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-108">This verb specifies the action taken by the cmdlet.</span></span> <span data-ttu-id="e851e-109">承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)と[開発ガイドラインのために必要な](./required-development-guidelines.md)します。</span><span class="sxs-lookup"><span data-stu-id="e851e-109">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md) and [Required Development Guidelines](./required-development-guidelines.md).</span></span>

<span data-ttu-id="e851e-110">`NounName` ([System.String](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e851e-110">`NounName` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="e851e-111">コマンドレットの名詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-111">Specifies the cmdlet noun.</span></span> <span data-ttu-id="e851e-112">この名詞では、コマンドレットが実行されるリソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-112">This noun specifies the resource that the cmdlet acts upon.</span></span> <span data-ttu-id="e851e-113">コマンドレットの名詞の詳細については、次を参照してください。[コマンドレット宣言](./cmdlet-class-declaration.md)と[推奨される開発ガイドライン強く](./strongly-encouraged-development-guidelines.md)します。</span><span class="sxs-lookup"><span data-stu-id="e851e-113">For more information about cmdlet nouns, see [Cmdlet Declaration](./cmdlet-class-declaration.md) and [Strongly Encouraged Development Guidelines](./strongly-encouraged-development-guidelines.md).</span></span>

<span data-ttu-id="e851e-114">`SupportsShouldProcess` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="e851e-114">`SupportsShouldProcess` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="e851e-115">`True` このコマンドレットへの呼び出しをサポートしていることを示します、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)コマンドレットをシステムを変更する操作を実行する前にユーザーに確認する方法を提供するメソッド。</span><span class="sxs-lookup"><span data-stu-id="e851e-115">`True` indicates that the cmdlet supports calls to the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, which provides the cmdlet with a way to prompt the user before an action that changes the system is performed.</span></span> <span data-ttu-id="e851e-116">`False`、既定値は、コマンドレットでは、への呼び出しはサポートされていないことを示します、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。</span><span class="sxs-lookup"><span data-stu-id="e851e-116">`False`, the default value, indicates that the cmdlet does not support calls to the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="e851e-117">確認要求の詳細については、次を参照してください。[確認を要求する](./requesting-confirmation-from-cmdlets.md)します。</span><span class="sxs-lookup"><span data-stu-id="e851e-117">For more information about confirmation requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

<span data-ttu-id="e851e-118">`ConfirmImpact` ([System.Management.Automation.Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="e851e-118">`ConfirmImpact` ([System.Management.Automation.Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) Optional named parameter.</span></span> <span data-ttu-id="e851e-119">呼び出しによって、コマンドレットのアクションを確認する場合を指定します、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。</span><span class="sxs-lookup"><span data-stu-id="e851e-119">Specifies when the action of the cmdlet should be confirmed by a call to the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="e851e-120">[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) (既定では Medium)、コマンドレットの ConfirmImpact 値が等しくまたはの値よりも大きい場合にのみ呼び出される、`$ConfirmPreference`変数。</span><span class="sxs-lookup"><span data-stu-id="e851e-120">[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) will only be called when the ConfirmImpact value of the cmdlet (by default, Medium) is equal to or greater than the value of the `$ConfirmPreference` variable.</span></span> <span data-ttu-id="e851e-121">このパラメーターを指定する必要がある場合にのみ、`SupportsShouldProcess`パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-121">This parameter should be specified only when the `SupportsShouldProcess` parameter is specified.</span></span>

<span data-ttu-id="e851e-122">`DefaultParameterSetName` ([System.String](/dotnet/api/System.String)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="e851e-122">`DefaultParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="e851e-123">Windows PowerShell ランタイムが使用するパラメーターの設定を判断できないときに使用しようとする既定のパラメーターの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e851e-123">Specifies the default parameter set that the Windows PowerShell runtime attempts to use when it cannot determine which parameter set to use.</span></span> <span data-ttu-id="e851e-124">このような状況は、必須のパラメーターを設定する各パラメーターの一意のパラメーターを削除できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e851e-124">Notice that this situation can be eliminated by making the unique parameter of each parameter set a mandatory parameter.</span></span>

<span data-ttu-id="e851e-125">Windows PowerShell が設定の既定のパラメーター セット名が指定した場合でも、既定のパラメーターを使用できない場合は。</span><span class="sxs-lookup"><span data-stu-id="e851e-125">There is one case where Windows PowerShell cannot use the default parameter set even if a default parameter set name is specified.</span></span> <span data-ttu-id="e851e-126">Windows PowerShell ランタイムは、オブジェクトの種類のみに基づくパラメーター セットを区別できません。</span><span class="sxs-lookup"><span data-stu-id="e851e-126">The Windows PowerShell runtime cannot distinguish between parameter sets based solely on object type.</span></span> <span data-ttu-id="e851e-127">たとえばがある場合、ファイル パスと別のセットとして文字列を受け取る 1 つのパラメーター セットは、 **FileInfo**オブジェクトを直接の Windows PowerShell に渡される値に基づいてパラメーターを使用する設定を確認することはできません、コマンドレットでは、既定のパラメーター セットが使用されることもできません。</span><span class="sxs-lookup"><span data-stu-id="e851e-127">For example, if you have one parameter set that takes a string as the file path, and another set that takes a **FileInfo** object directly, Windows PowerShell cannot determine which parameter set to use based on the values passed to the cmdlet, nor does it use the default parameter set.</span></span> <span data-ttu-id="e851e-128">この場合、既定のパラメーター セット名を指定した場合でも、Windows PowerShell はあいまいなパラメーター セット エラー メッセージをスローします。</span><span class="sxs-lookup"><span data-stu-id="e851e-128">In this case, even if you specify a default parameter set name, Windows PowerShell throws an ambiguous parameter set error message.</span></span>

<span data-ttu-id="e851e-129">`SupportsTransactions` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="e851e-129">`SupportsTransactions` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="e851e-130">`True` トランザクション内でコマンドレットを使用できることを示します。</span><span class="sxs-lookup"><span data-stu-id="e851e-130">`True` indicates that the cmdlet can be used within a transaction.</span></span> <span data-ttu-id="e851e-131">ときに`True`を指定すると、Windows PowerShell ランタイムを追加、`UseTransaction`コマンドレットのパラメーター リストのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="e851e-131">When `True` is specified, the Windows PowerShell runtime adds the `UseTransaction` parameter to the parameter list of the cmdlet.</span></span> <span data-ttu-id="e851e-132">`False`で、既定値は、トランザクション内でコマンドレットを使用できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e851e-132">`False`, the default value, indicates that the cmdlet cannot be used within a transaction.</span></span>

## <a name="remarks"></a><span data-ttu-id="e851e-133">コメント</span><span class="sxs-lookup"><span data-stu-id="e851e-133">Remarks</span></span>

- <span data-ttu-id="e851e-134">同時に、動詞と名詞は、スクリプト内でコマンドレットを呼び出すと、登録されているコマンドレットを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e851e-134">Together, the verb and noun are used to identify your registered cmdlet and to invoke your cmdlet within a script.</span></span>

- <span data-ttu-id="e851e-135">コマンドレットは、Windows PowerShell コンソールから起動されるのコマンドは、次のコマンドと似ています。</span><span class="sxs-lookup"><span data-stu-id="e851e-135">When the cmdlet is invoked from the Windows PowerShell console, the command resembles the following command:</span></span>

<span data-ttu-id="e851e-136">**VerbName-NounName**</span><span class="sxs-lookup"><span data-stu-id="e851e-136">**VerbName-NounName**</span></span>

- <span data-ttu-id="e851e-137">Windows PowerShell の外部のリソースを変更するすべてのコマンドレットを含める必要があります、 `SupportsShouldProcess` 、コマンドレットを呼び出すことができるキーワード コマンドレット属性が宣言されている場合、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドの前に、そのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e851e-137">All cmdlets that change resources outside of Windows PowerShell should include the `SupportsShouldProcess` keyword when the Cmdlet attribute is declared, which allows the cmdlet to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method before the cmdlet performs its action.</span></span> <span data-ttu-id="e851e-138">場合、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)返しますを呼び出す`false`、この操作を実行しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="e851e-138">If the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call returns `false`, the action should not be taken.</span></span> <span data-ttu-id="e851e-139">によって生成される確認要求の詳細については、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しを参照してください[確認を要求する](./requesting-confirmation-from-cmdlets.md)します。</span><span class="sxs-lookup"><span data-stu-id="e851e-139">For more information about the confirmation requests generated by the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

<span data-ttu-id="e851e-140">`Confirm`と`WhatIf`コマンドレットのパラメーターはサポートするコマンドレットでのみ使用できます[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出し。</span><span class="sxs-lookup"><span data-stu-id="e851e-140">The `Confirm` and `WhatIf` cmdlet parameters are available only for cmdlets that support [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) calls.</span></span>

## <a name="example"></a><span data-ttu-id="e851e-141">例</span><span class="sxs-lookup"><span data-stu-id="e851e-141">Example</span></span>

<span data-ttu-id="e851e-142">次のクラス定義の .NET Framework クラスを識別するためにコマンドレットの属性を使用して、 **Get-proc**ローカル コンピューターで実行されているプロセスに関する情報を取得するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="e851e-142">The following class definition uses the Cmdlet attribute to identify the .NET Framework class for a **Get-Proc** cmdlet that retrieves information about the processes running on the local computer.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="e851e-143">詳細については、 **Get-proc**コマンドレットを参照してください[GetProc チュートリアル](./getproc-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="e851e-143">For more information about the **Get-Proc** cmdlet, see [GetProc Tutorial](./getproc-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e851e-144">参照</span><span class="sxs-lookup"><span data-stu-id="e851e-144">See Also</span></span>

[<span data-ttu-id="e851e-145">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="e851e-145">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
