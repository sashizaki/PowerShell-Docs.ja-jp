---
title: コマンドレットの属性宣言 |Microsoft Docs
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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363541"
---
# <a name="cmdlet-attribute-declaration"></a><span data-ttu-id="4cc1c-102">コマンドレット属性の宣言</span><span class="sxs-lookup"><span data-stu-id="4cc1c-102">Cmdlet Attribute Declaration</span></span>

<span data-ttu-id="4cc1c-103">コマンドレット属性は、コマンドレットとして Microsoft .NET Framework クラスを識別し、コマンドレットを呼び出すために使用される動詞と名詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-103">The Cmdlet attribute identifies a Microsoft .NET Framework class as a cmdlet and specifies the verb and noun used to invoke the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="4cc1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="4cc1c-104">Syntax</span></span>

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="4cc1c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cc1c-105">Parameters</span></span>

<span data-ttu-id="4cc1c-106">`VerbName` ([system.string](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-106">`VerbName` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="4cc1c-107">コマンドレットの動詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-107">Specifies the cmdlet verb.</span></span> <span data-ttu-id="4cc1c-108">この動詞は、コマンドレットによって実行されるアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-108">This verb specifies the action taken by the cmdlet.</span></span> <span data-ttu-id="4cc1c-109">承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」および「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-109">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md) and [Required Development Guidelines](./required-development-guidelines.md).</span></span>

<span data-ttu-id="4cc1c-110">`NounName` ([system.string](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-110">`NounName` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="4cc1c-111">コマンドレットの名詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-111">Specifies the cmdlet noun.</span></span> <span data-ttu-id="4cc1c-112">この名詞は、コマンドレットが処理するリソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-112">This noun specifies the resource that the cmdlet acts upon.</span></span> <span data-ttu-id="4cc1c-113">コマンドレットの名詞の詳細については、「[コマンドレットの宣言](./cmdlet-class-declaration.md)」を[参照してください。](./strongly-encouraged-development-guidelines.md)</span><span class="sxs-lookup"><span data-stu-id="4cc1c-113">For more information about cmdlet nouns, see [Cmdlet Declaration](./cmdlet-class-declaration.md) and [Strongly Encouraged Development Guidelines](./strongly-encouraged-development-guidelines.md).</span></span>

<span data-ttu-id="4cc1c-114">`SupportsShouldProcess` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-114">`SupportsShouldProcess` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="4cc1c-115">`True` は、コマンドレット[が、システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を変更する操作を実行する前にユーザーにプロンプトを表示する方法を提供する、コマンドレットの呼び出しをサポートしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-115">`True` indicates that the cmdlet supports calls to the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, which provides the cmdlet with a way to prompt the user before an action that changes the system is performed.</span></span> <span data-ttu-id="4cc1c-116">既定値である `False`は、このコマンドレットが、 [system.object メソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しをサポートしていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-116">`False`, the default value, indicates that the cmdlet does not support calls to the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="4cc1c-117">確認要求の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-117">For more information about confirmation requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

<span data-ttu-id="4cc1c-118">`ConfirmImpact` ([System. Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-118">`ConfirmImpact` ([System.Management.Automation.Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) Optional named parameter.</span></span> <span data-ttu-id="4cc1c-119">コマンドレットのアクションを、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しによって確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-119">Specifies when the action of the cmdlet should be confirmed by a call to the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="4cc1c-120">コマンドレットの ConfirmImpact 値 (既定では、Medium) が `$ConfirmPreference` 変数の値以上である場合にのみ、指定[された](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)値が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-120">[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) will only be called when the ConfirmImpact value of the cmdlet (by default, Medium) is equal to or greater than the value of the `$ConfirmPreference` variable.</span></span> <span data-ttu-id="4cc1c-121">このパラメーターは、`SupportsShouldProcess` パラメーターが指定されている場合にのみ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-121">This parameter should be specified only when the `SupportsShouldProcess` parameter is specified.</span></span>

<span data-ttu-id="4cc1c-122">`DefaultParameterSetName` ([system.string](/dotnet/api/System.String)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-122">`DefaultParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="4cc1c-123">使用するパラメーターセットを判別できない場合に、Windows PowerShell ランタイムが使用を試みる既定のパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-123">Specifies the default parameter set that the Windows PowerShell runtime attempts to use when it cannot determine which parameter set to use.</span></span> <span data-ttu-id="4cc1c-124">各パラメーターの unique パラメーターに必須パラメーターを設定することで、この状況を解消できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-124">Notice that this situation can be eliminated by making the unique parameter of each parameter set a mandatory parameter.</span></span>

<span data-ttu-id="4cc1c-125">既定のパラメーターセット名が指定されている場合でも、Windows PowerShell で既定のパラメーターセットを使用できないケースが1つあります。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-125">There is one case where Windows PowerShell cannot use the default parameter set even if a default parameter set name is specified.</span></span> <span data-ttu-id="4cc1c-126">Windows PowerShell ランタイムでは、オブジェクトの種類のみを基にしたパラメーターセットを区別できません。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-126">The Windows PowerShell runtime cannot distinguish between parameter sets based solely on object type.</span></span> <span data-ttu-id="4cc1c-127">たとえば、ファイルパスとして文字列を受け取る1つのパラメーターセットと、 **FileInfo**オブジェクトを直接受け取る別のセットがある場合、Windows PowerShell は、コマンドレットに渡された値に基づいて、使用するパラメーターセットを決定できません。また、既定のパラメーターセットを使用しません。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-127">For example, if you have one parameter set that takes a string as the file path, and another set that takes a **FileInfo** object directly, Windows PowerShell cannot determine which parameter set to use based on the values passed to the cmdlet, nor does it use the default parameter set.</span></span> <span data-ttu-id="4cc1c-128">この場合、既定のパラメーターセット名を指定しても、Windows PowerShell はあいまいなパラメーターセットのエラーメッセージをスローします。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-128">In this case, even if you specify a default parameter set name, Windows PowerShell throws an ambiguous parameter set error message.</span></span>

<span data-ttu-id="4cc1c-129">`SupportsTransactions` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-129">`SupportsTransactions` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="4cc1c-130">`True` は、コマンドレットをトランザクション内で使用できることを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-130">`True` indicates that the cmdlet can be used within a transaction.</span></span> <span data-ttu-id="4cc1c-131">`True` が指定されている場合、Windows PowerShell ランタイムは、コマンドレットのパラメーターリストに `UseTransaction` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-131">When `True` is specified, the Windows PowerShell runtime adds the `UseTransaction` parameter to the parameter list of the cmdlet.</span></span> <span data-ttu-id="4cc1c-132">既定値の `False`は、コマンドレットをトランザクション内で使用できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-132">`False`, the default value, indicates that the cmdlet cannot be used within a transaction.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cc1c-133">コメント</span><span class="sxs-lookup"><span data-stu-id="4cc1c-133">Remarks</span></span>

- <span data-ttu-id="4cc1c-134">動詞と名詞を一緒に使用して、登録されているコマンドレットを識別し、スクリプト内でコマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-134">Together, the verb and noun are used to identify your registered cmdlet and to invoke your cmdlet within a script.</span></span>

- <span data-ttu-id="4cc1c-135">コマンドレットが Windows PowerShell コンソールから呼び出されると、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-135">When the cmdlet is invoked from the Windows PowerShell console, the command resembles the following command:</span></span>

<span data-ttu-id="4cc1c-136">**VerbName-NounName**</span><span class="sxs-lookup"><span data-stu-id="4cc1c-136">**VerbName-NounName**</span></span>

- <span data-ttu-id="4cc1c-137">コマンドレット属性が宣言されている場合は、Windows PowerShell の外部でリソースを変更するすべてのコマンドレットに `SupportsShouldProcess` キーワードを含める必要があります。これにより、コマンドレットは、コマンドレットがアクションを実行する前[に、このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-137">All cmdlets that change resources outside of Windows PowerShell should include the `SupportsShouldProcess` keyword when the Cmdlet attribute is declared, which allows the cmdlet to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method before the cmdlet performs its action.</span></span> <span data-ttu-id="4cc1c-138">この呼び出し[によって `false`](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)が返された場合、アクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-138">If the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call returns `false`, the action should not be taken.</span></span> <span data-ttu-id="4cc1c-139">[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しによって生成される確認要求の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-139">For more information about the confirmation requests generated by the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

<span data-ttu-id="4cc1c-140">`Confirm` および `WhatIf` のコマンドレットパラメーターは、の呼び出しをサポートするコマンドレットでのみ使用[できます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="4cc1c-140">The `Confirm` and `WhatIf` cmdlet parameters are available only for cmdlets that support [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) calls.</span></span>

## <a name="example"></a><span data-ttu-id="4cc1c-141">例</span><span class="sxs-lookup"><span data-stu-id="4cc1c-141">Example</span></span>

<span data-ttu-id="4cc1c-142">次のクラス定義では、コマンドレット属性を使用して、ローカルコンピューター上で実行されているプロセスに関する情報を取得する**Get Proc**コマンドレットの .NET Framework クラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-142">The following class definition uses the Cmdlet attribute to identify the .NET Framework class for a **Get-Proc** cmdlet that retrieves information about the processes running on the local computer.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="4cc1c-143">**Get proc**コマンドレットの詳細については、「 [getproc チュートリアル](./getproc-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-143">For more information about the **Get-Proc** cmdlet, see [GetProc Tutorial](./getproc-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cc1c-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cc1c-144">See Also</span></span>

[<span data-ttu-id="4cc1c-145">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="4cc1c-145">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
