---
title: コマンドレットのエラーの報告 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error records [PowerShell], terminating
- non-terminating errors [PowerShell]
- error records [PowerShell]
- terminating errors [PowerShell]
- error records [PowerShell], non-terminating
ms.assetid: 0b014035-52ea-44cb-ab38-bbe463c5465a
caps.latest.revision: 8
ms.openlocfilehash: 7b54fc220a66a47c25b3e8cba644882d31713cb7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857688"
---
# <a name="cmdlet-error-reporting"></a><span data-ttu-id="4360b-102">コマンドレット エラー レポート</span><span class="sxs-lookup"><span data-stu-id="4360b-102">Cmdlet Error Reporting</span></span>

<span data-ttu-id="4360b-103">コマンドレットには、エラーがエラーを終了しているかどうかに応じて異なる方法でエラーまたは終了しないエラーを報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-103">Cmdlets should report errors differently depending on whether the errors are terminating errors or nonterminating errors.</span></span> <span data-ttu-id="4360b-104">終了するエラーは、すぐに終了するパイプラインが発生したエラーまたは処理を続行する理由がない場合に発生するエラーです。</span><span class="sxs-lookup"><span data-stu-id="4360b-104">Terminating errors are errors that cause the pipeline to be terminated immediately, or errors that occur when there is no reason to continue processing.</span></span> <span data-ttu-id="4360b-105">終了しないエラーは、現在のエラー条件を報告するこれらのエラーは、コマンドレットは、入力オブジェクトの処理を継続できます。</span><span class="sxs-lookup"><span data-stu-id="4360b-105">Nonterminating errors are those errors that report a current error condition, but the cmdlet can continue to process input objects.</span></span> <span data-ttu-id="4360b-106">終了しないエラーは、通常、ユーザーは、問題の通知がコマンドレットは、[次へ] の入力オブジェクトの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="4360b-106">With nonterminating errors, the user is typically notified of the problem, but the cmdlet continues to process the next input object.</span></span>

## <a name="terminating-and-nonterminating-errors"></a><span data-ttu-id="4360b-107">終了しないエラー エラー</span><span class="sxs-lookup"><span data-stu-id="4360b-107">Terminating and Nonterminating Errors</span></span>

<span data-ttu-id="4360b-108">エラー状態が終了エラーまたは終了しないエラーを確認するのには、次のガイドラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4360b-108">The following guidelines can be used to determine if an error condition is a terminating error or a nonterminating error.</span></span>

- <span data-ttu-id="4360b-109">エラー状態は、さらに入力オブジェクトはすべてを正常に処理されないコマンドレットをできなくなりますか。</span><span class="sxs-lookup"><span data-stu-id="4360b-109">Does the error condition prevent your cmdlet from successfully processing any further input objects?</span></span> <span data-ttu-id="4360b-110">場合は、終了エラーになります。</span><span class="sxs-lookup"><span data-stu-id="4360b-110">If so, this is a terminating error.</span></span>

- <span data-ttu-id="4360b-111">特定の入力オブジェクトまたは入力オブジェクトのサブセットに関連するエラー状態ですか。</span><span class="sxs-lookup"><span data-stu-id="4360b-111">Is the error condition related to a specific input object or a subset of input objects?</span></span> <span data-ttu-id="4360b-112">そうである場合は、終了しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="4360b-112">If so, this is a nonterminating error.</span></span>

- <span data-ttu-id="4360b-113">コマンドレットは別の入力オブジェクトの処理が成功しないことなど、複数の入力オブジェクトをそのまま使用しますか。</span><span class="sxs-lookup"><span data-stu-id="4360b-113">Does the cmdlet accept multiple input objects, such that processing may succeed on another input object?</span></span> <span data-ttu-id="4360b-114">そうである場合は、終了しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="4360b-114">If so, this is a nonterminating error.</span></span>

- <span data-ttu-id="4360b-115">間で何が終了して、終了しないエラーは、特定の状況が入力オブジェクトが 1 つのみに適用される場合にも複数の入力オブジェクトを受け入れ可能なコマンドレット決定します。</span><span class="sxs-lookup"><span data-stu-id="4360b-115">Cmdlets that can accept multiple input objects should decide between what are terminating and nonterminating errors, even when a particular situation applies to only a single input object.</span></span>

- <span data-ttu-id="4360b-116">コマンドレットは、任意の数の入力オブジェクトを受信し、終了例外をスローする前に任意の数のオブジェクトの成功またはエラーを送信できます。</span><span class="sxs-lookup"><span data-stu-id="4360b-116">Cmdlets can receive any number of input objects and send any number of success or error objects before throwing a terminating exception.</span></span> <span data-ttu-id="4360b-117">受信した入力オブジェクトの数と送信オブジェクトの成功とエラーの数の間の関係はありません。</span><span class="sxs-lookup"><span data-stu-id="4360b-117">There is no relationship between the number of input objects received and the number of success and error objects sent.</span></span>

- <span data-ttu-id="4360b-118">0 ~ 1 のオブジェクトを入力して生成が 0 ~ 1 に受け入れ可能なコマンドレットの出力オブジェクトのエラーを終了するエラーとして扱うし、終端の例外を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-118">Cmdlets that can accept only 0-1 input objects and generate only 0-1 output objects should treat errors as terminating errors and generate terminating exceptions.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="4360b-119">終了しないエラーの報告</span><span class="sxs-lookup"><span data-stu-id="4360b-119">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="4360b-120">終了しないエラーの報告する必要がありますを行うまでのコマンドレットの実装内で、 [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド、または[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="4360b-120">The reporting of a nonterminating error should always be done within the cmdlet's implementation of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method, the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, or the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="4360b-121">この種のエラーが呼び出すことによって報告された、 [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)さらに、エラー ストリームにエラー レコードを送信するメソッド。</span><span class="sxs-lookup"><span data-stu-id="4360b-121">These types of errors are reported by calling the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method that in turn sends an error record to the error stream.</span></span>

## <a name="reporting-terminating-errors"></a><span data-ttu-id="4360b-122">終了するエラーを報告</span><span class="sxs-lookup"><span data-stu-id="4360b-122">Reporting Terminating Errors</span></span>

<span data-ttu-id="4360b-123">例外がスローされても呼び出すことによって、終了するエラーが報告された、 [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッド。</span><span class="sxs-lookup"><span data-stu-id="4360b-123">Terminating errors are reported by throwing exceptions or by calling the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method.</span></span> <span data-ttu-id="4360b-124">ただし、Windows PowerShell ランタイムはそれらをキャッチも例外を再びスローする必要はありません、コマンドレットのキャッチし再 OutOfMemory などの例外をスローできますもことに注意します。</span><span class="sxs-lookup"><span data-stu-id="4360b-124">Be aware that cmdlets can also catch and re-throw exceptions such as OutOfMemory, however, they are not required to re-throw exceptions as the Windows PowerShell runtime will catch them as well.</span></span>

<span data-ttu-id="4360b-125">状況に固有の問題に対して、独自の例外を定義または、そのエラー レコードを使用して既存の例外に情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4360b-125">You can also define your own exceptions for issues specific to your situation, or add additional information to an existing exception using its error record.</span></span>

## <a name="error-records"></a><span data-ttu-id="4360b-126">エラー レコード</span><span class="sxs-lookup"><span data-stu-id="4360b-126">Error Records</span></span>

<span data-ttu-id="4360b-127">Windows PowerShell を使用すると、終了しないエラー状態の説明[System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4360b-127">Windows PowerShell describes a nonterminating error condition through the use of [System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord) objects.</span></span> <span data-ttu-id="4360b-128">各[System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトは、エラー カテゴリの情報、省略可能なターゲット オブジェクト、およびエラーの状態に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4360b-128">Each [System.Management.Automation.Errorrecord](/dotnet/api/System.Management.Automation.ErrorRecord) object provides error category information, an optional target object, and details about the error condition.</span></span>

### <a name="error-identifiers"></a><span data-ttu-id="4360b-129">エラー識別子</span><span class="sxs-lookup"><span data-stu-id="4360b-129">Error Identifiers</span></span>

<span data-ttu-id="4360b-130">エラー識別子は、コマンドレット内のエラー条件を識別する単純な文字列です。</span><span class="sxs-lookup"><span data-stu-id="4360b-130">The error identifier is a simple string that identifies the error condition within the cmdlet.</span></span> <span data-ttu-id="4360b-131">Windows PowerShell は、特定のエラーに応答する場合は、エラー ストリームまたはエラーのログ記録をフィルター処理する場合は、後で使用できるエラーの完全修飾識別子を作成するコマンドレットの識別子を使用またはその他のユーザー固有のアクティビティでは、この識別子を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="4360b-131">Windows PowerShell combines this identifier with a cmdlet identifier to create a fully qualified error identifier that can be used later when filtering error streams or logging errors, when responding to specific errors, or with other user-specific activities.</span></span>

<span data-ttu-id="4360b-132">エラーの識別子を指定するときに、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="4360b-132">The following guidelines should be followed when specifying error identifiers.</span></span>

- <span data-ttu-id="4360b-133">異なるコード パスを別の高い特定のエラーの識別子を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4360b-133">Assign different, highly specific, error identifiers to different code paths.</span></span> <span data-ttu-id="4360b-134">呼び出すコード パスの各[System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)または[System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)独自のエラー識別子があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-134">Each code path that calls [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) or [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) should have its own error identifier.</span></span>

- <span data-ttu-id="4360b-135">エラー識別子は終了し、終了しないエラーの例外型を CLR に一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-135">Error identifiers should be unique to CLR exception types for both terminating and nonterminating errors.</span></span>

- <span data-ttu-id="4360b-136">コマンドレットまたは Windows PowerShell プロバイダーのバージョン間でのエラー識別子のセマンティクスは変更されません。</span><span class="sxs-lookup"><span data-stu-id="4360b-136">Do not change the semantics of an error identifier between versions of your cmdlet or Windows PowerShell provider.</span></span> <span data-ttu-id="4360b-137">エラー識別子のセマンティクスが確立されるは、コマンドレットのライフ サイクル全体で一定維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-137">After the semantics of an error identifier is established, it should remain constant throughout the life cycle of your cmdlet.</span></span>

- <span data-ttu-id="4360b-138">終了するエラーを特定の CLR 例外型の一意のエラー識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="4360b-138">For terminating errors, use a unique error identifier for a particular CLR exception type.</span></span> <span data-ttu-id="4360b-139">例外の種類が変更された場合は、新しいエラー識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="4360b-139">If the exception type changes, use a new error identifier.</span></span>

- <span data-ttu-id="4360b-140">終了しないエラーの場合は、特定の入力オブジェクトの特定のエラー識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="4360b-140">For nonterminating errors, use a specific error identifier for a specific input object.</span></span>

- <span data-ttu-id="4360b-141">答えました報告されるエラーに対応する識別子のテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="4360b-141">Choose text for the identifier that tersely corresponds to the error being reported.</span></span> <span data-ttu-id="4360b-142">空白や句読点を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4360b-142">Do not use white space or punctuation.</span></span>

- <span data-ttu-id="4360b-143">再現可能でないエラー識別子を生成することはありません。</span><span class="sxs-lookup"><span data-stu-id="4360b-143">Do not generate error identifiers that are not reproducible.</span></span> <span data-ttu-id="4360b-144">たとえば、プロセス識別子が含まれる識別子を生成しません。</span><span class="sxs-lookup"><span data-stu-id="4360b-144">For example, do not generate identifiers that include a process identifier.</span></span> <span data-ttu-id="4360b-145">エラー識別子は、同じ問題が発生している他のユーザーに表示される識別子に対応する場合にのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4360b-145">Error identifiers are useful only when they correspond to identifiers that are seen by other users who are experiencing the same problem.</span></span>

### <a name="error-categories"></a><span data-ttu-id="4360b-146">エラー カテゴリ</span><span class="sxs-lookup"><span data-stu-id="4360b-146">Error Categories</span></span>

<span data-ttu-id="4360b-147">エラー カテゴリは、エンドユーザーのエラーをグループ化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4360b-147">Error categories are used to group errors for the end-user.</span></span> <span data-ttu-id="4360b-148">Windows PowerShell は、これらのカテゴリを定義し、エラー レコードを生成するときにそれらの間のコマンドレットと Windows PowerShell プロバイダーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-148">Windows PowerShell defines these categories and cmdlets and Windows PowerShell providers must choose between them when generating the error record.</span></span>

<span data-ttu-id="4360b-149">使用可能なエラー カテゴリの説明は、次を参照してください。、 [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)列挙体。</span><span class="sxs-lookup"><span data-stu-id="4360b-149">For a description of the error categories that are available, see the [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory) enumeration.</span></span> <span data-ttu-id="4360b-150">一般に、NoError、UndefinedError、および GenericError 可能な限り使用を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4360b-150">In general, you should avoid using NoError, UndefinedError, and GenericError whenever possible.</span></span>

<span data-ttu-id="4360b-151">ユーザーが設定されている場合は、カテゴリに基づいてエラーを表示できます"`$ErrorView`""CategoryView"にします。</span><span class="sxs-lookup"><span data-stu-id="4360b-151">Users can view errors based on category when they set "`$ErrorView`" to "CategoryView".</span></span>

## <a name="see-also"></a><span data-ttu-id="4360b-152">参照</span><span class="sxs-lookup"><span data-stu-id="4360b-152">See Also</span></span>

[<span data-ttu-id="4360b-153">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="4360b-153">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="4360b-154">コマンドレットの出力</span><span class="sxs-lookup"><span data-stu-id="4360b-154">Cmdlet Output</span></span>](./types-of-cmdlet-output.md)

[<span data-ttu-id="4360b-155">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="4360b-155">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
