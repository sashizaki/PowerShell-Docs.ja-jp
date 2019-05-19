---
title: アドバイザリ開発のガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79c9bcbc-a2eb-4253-a4b8-65ba54ce8d01
caps.latest.revision: 9
ms.openlocfilehash: 980b488800587e31286e2ca2ece924e07f8af3f3
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854877"
---
# <a name="advisory-development-guidelines"></a><span data-ttu-id="f88f2-102">お勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f88f2-102">Advisory Development Guidelines</span></span>

<span data-ttu-id="f88f2-103">このセクションでは、適切な開発とユーザー エクスペリエンスを確保するために考慮すべきガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-103">This section describes guidelines that you should consider to ensure good development and user experiences.</span></span> <span data-ttu-id="f88f2-104">場合によって次のように適用される場合がありますとありますでない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-104">Sometimes they might apply, and sometimes they might not.</span></span>

## <a name="design-guidelines"></a><span data-ttu-id="f88f2-105">デザイン ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f88f2-105">Design Guidelines</span></span>

<span data-ttu-id="f88f2-106">コマンドレットを設計するときに、次のガイドラインを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f88f2-106">The following guidelines should be considered when designing cmdlets.</span></span> <span data-ttu-id="f88f2-107">自分の状況に適用されるデザインのガイドラインを検索するときに必ずのようなガイドラインについては、コードのガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f88f2-107">When you find a Design guideline that applies to your situation, be sure to look at the Code guidelines for similar guidelines.</span></span>

### <a name="support-an-inputobject-parameter-ad01"></a><span data-ttu-id="f88f2-108">InputObject パラメーター (AD01) のサポートします。</span><span class="sxs-lookup"><span data-stu-id="f88f2-108">Support an InputObject Parameter (AD01)</span></span>

<span data-ttu-id="f88f2-109">Windows PowerShell は、Microsoft .NET Framework オブジェクトを直接機能するため、.NET Framework オブジェクトがある多くの場合、完全に一致する型、ユーザーがする必要がありますが、特定の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-109">Because Windows PowerShell works directly with Microsoft .NET Framework objects, a .NET Framework object is often available that exactly matches the type the user needs to perform a particular operation.</span></span> <span data-ttu-id="f88f2-110">`InputObject` 標準の入力としてこのようなオブジェクトを取得するパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="f88f2-110">`InputObject` is the standard name for a parameter that takes such an object as input.</span></span> <span data-ttu-id="f88f2-111">サンプルではたとえば、**停止 Proc**コマンドレット、 [StopProc チュートリアル](./stopproc-tutorial.md)定義、`InputObject`型パイプラインから入力をサポートしているプロセスのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="f88f2-111">For example, the sample **Stop-Proc** cmdlet in the [StopProc Tutorial](./stopproc-tutorial.md) defines an `InputObject` parameter of type Process that supports the input from the pipeline.</span></span> <span data-ttu-id="f88f2-112">ユーザーは、プロセス オブジェクトのセットを取得、操作を停止するには厳密なオブジェクトを選択、およびに渡して、**停止 Proc**直接コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="f88f2-112">The user can get a set of process objects, manipulate them to select the exact objects to stop, and then pass them to the **Stop-Proc** cmdlet directly.</span></span>

### <a name="support-the-force-parameter-ad02"></a><span data-ttu-id="f88f2-113">Force パラメーター (AD02) のサポート</span><span class="sxs-lookup"><span data-stu-id="f88f2-113">Support the Force Parameter (AD02)</span></span>

<span data-ttu-id="f88f2-114">場合によっては、コマンドレットは、要求された操作を実行してから、ユーザーを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-114">Occasionally, a cmdlet needs to protect the user from performing a requested operation.</span></span> <span data-ttu-id="f88f2-115">このようなコマンドレットをサポートする必要があります、`Force`パラメーターをユーザーが、ユーザーが操作を実行するアクセス許可を持っている場合、その保護を上書きできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f88f2-115">Such a cmdlet should support a `Force` parameter to allow the user to override that protection if the user has permissions to perform the operation.</span></span>

<span data-ttu-id="f88f2-116">たとえば、 [Remove-item](/powershell/module/microsoft.powershell.management/remove-item)コマンドレットが読み取り専用ファイルを正常に削除しません。</span><span class="sxs-lookup"><span data-stu-id="f88f2-116">For example, the [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item) cmdlet does not normally remove a read-only file.</span></span> <span data-ttu-id="f88f2-117">ただし、このコマンドレットをサポートしています、`Force`パラメーターため、ユーザーは読み取り専用ファイルの削除を強制できますの。</span><span class="sxs-lookup"><span data-stu-id="f88f2-117">However, this cmdlet supports a `Force` parameter so a user can force removal of a read-only file.</span></span> <span data-ttu-id="f88f2-118">場合は、読み取り専用属性を変更するアクセス許可をユーザーが既に存在して、ユーザーがファイルを削除を使用して、`Force`パラメーターは、操作を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-118">If the user already has permission to modify the read-only attribute, and the user removes the file, use of the `Force` parameter simplifies the operation.</span></span> <span data-ttu-id="f88f2-119">ただし、ユーザーが、ファイルを削除するアクセス許可を持っていない場合、`Force`パラメーターが影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="f88f2-119">However, if the user does not have permission to remove the file, the `Force` parameter has no effect.</span></span>

### <a name="handle-credentials-through-windows-powershell-ad03"></a><span data-ttu-id="f88f2-120">Windows PowerShell (AD03) を使って資格情報を処理します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-120">Handle Credentials Through Windows PowerShell (AD03)</span></span>

<span data-ttu-id="f88f2-121">コマンドレットを定義する必要があります、`Credential`を資格情報を表すパラメーター。</span><span class="sxs-lookup"><span data-stu-id="f88f2-121">A cmdlet should define a `Credential` parameter to represent credentials.</span></span> <span data-ttu-id="f88f2-122">このパラメーターは、型でなければなりません[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)と資格情報の属性宣言を使用して定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-122">This parameter must be of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) and must be defined using a Credential attribute declaration.</span></span> <span data-ttu-id="f88f2-123">このサポートでは、完全な資格情報が直接指定されていないときにユーザー名、パスワード、または両方のユーザーが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f88f2-123">This support automatically prompts the user for the user name, for the password, or for both when a full credential is not supplied directly.</span></span> <span data-ttu-id="f88f2-124">資格情報の属性の詳細については、次を参照してください。[資格情報の属性宣言](./credential-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-124">For more information about the Credential attribute, see [Credential Attribute Declaration](./credential-attribute-declaration.md).</span></span>

### <a name="support-encoding-parameters-ad04"></a><span data-ttu-id="f88f2-125">エンコード パラメーター (AD04) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f88f2-125">Support Encoding Parameters (AD04)</span></span>

<span data-ttu-id="f88f2-126">コマンドレットは、読み取るか、またはへの書き込みや、ファイル システム内のファイルからの読み取りなどのバイナリ形式からテキストを書き込む場合、コマンドレットに Encoding パラメーターをバイナリ形式でテキストをエンコードする方法を指定するには。</span><span class="sxs-lookup"><span data-stu-id="f88f2-126">If your cmdlet reads or writes text to or from a binary form, such as writing to or reading from a file in a filesystem, then your cmdlet has to have Encoding parameter that specifies how the text is encoded in the binary form.</span></span>

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a><span data-ttu-id="f88f2-127">テスト コマンドレットは、ブール値 (AD05) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-127">Test Cmdlets Should Return a Boolean (AD05)</span></span>

<span data-ttu-id="f88f2-128">リソースに対してテストを実行するコマンドレットが返す必要があります、 [System.Boolean](/dotnet/api/System.Boolean)条件式で使えるようにをパイプラインに入力します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-128">Cmdlets that perform tests against their resources should return a [System.Boolean](/dotnet/api/System.Boolean) type to the pipeline so that they can be used in conditional expressions.</span></span>

## <a name="code-guidelines"></a><span data-ttu-id="f88f2-129">コードのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f88f2-129">Code Guidelines</span></span>

<span data-ttu-id="f88f2-130">コマンドレットのコードを記述する場合は、次のガイドラインを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f88f2-130">The following guidelines should be considered when writing cmdlet code.</span></span> <span data-ttu-id="f88f2-131">自分の状況に適用されるガイドラインを検索するときに必ずのようなガイドラインについては、デザイン ガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f88f2-131">When you find a guideline that applies to your situation, be sure to look at the Design guidelines for similar guidelines.</span></span>

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a><span data-ttu-id="f88f2-132">次のコマンドレットのクラスの名前付け規則 (AC01)</span><span class="sxs-lookup"><span data-stu-id="f88f2-132">Follow Cmdlet Class Naming Conventions (AC01)</span></span>

<span data-ttu-id="f88f2-133">次の標準的な名前付け規則によって、コマンドレットの発見しやすくすることし、ユーザーがコマンドレットによって実行と正確に理解する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f88f2-133">By following standard naming conventions, you make your cmdlets more discoverable, and you help the user understand exactly what the cmdlets do.</span></span> <span data-ttu-id="f88f2-134">この方法は、コマンドレットはパブリック型であるために、Windows PowerShell を使用して他の開発者にとって特に重要です。</span><span class="sxs-lookup"><span data-stu-id="f88f2-134">This practice is particularly important for other developers using Windows PowerShell because cmdlets are public types.</span></span>

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a><span data-ttu-id="f88f2-135">正しい Namespace でコマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-135">Define a Cmdlet in the Correct Namespace</span></span>

<span data-ttu-id="f88f2-136">通常、.NET Framework 名前空間に追加されるでコマンドレットのクラスを定義する"。コマンド"コマンドレットを実行する製品を表す名前空間にします。</span><span class="sxs-lookup"><span data-stu-id="f88f2-136">You normally define the class for a cmdlet in a .NET Framework namespace that appends ".Commands" to the namespace that represents the product in which the cmdlet runs.</span></span> <span data-ttu-id="f88f2-137">Windows PowerShell に含まれているコマンドレットを定義するなど、`Microsoft.PowerShell.Commands`名前空間。</span><span class="sxs-lookup"><span data-stu-id="f88f2-137">For example, cmdlets that are included with Windows PowerShell are defined in the `Microsoft.PowerShell.Commands` namespace.</span></span>

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a><span data-ttu-id="f88f2-138">コマンドレット名と一致するコマンドレット クラスの名前します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-138">Name the Cmdlet Class to Match the Cmdlet Name</span></span>

<span data-ttu-id="f88f2-139">コマンドレットを実装する .NET Framework クラス、名前を付けるときに、クラスの名前を"*\<動詞 >**\<名詞 >**\<コマンド >*"、を交換します。*\<動詞 >* と*\<名詞 >* プレース ホルダーを動詞と名詞コマンドレット名に使用します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-139">When you name the .NET Framework class that implements a cmdlet, name the class "*\<Verb>**\<Noun>**\<Command>*", where you replace the *\<Verb>* and *\<Noun>* placeholders with the verb and noun used for the cmdlet name.</span></span> <span data-ttu-id="f88f2-140">たとえば、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットがという名前のクラスによって実装される`GetProcessCommand`します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-140">For example, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet is implemented by a class called `GetProcessCommand`.</span></span>

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a><span data-ttu-id="f88f2-141">パイプラインの入力には、BeginProcessing メソッド (AC02) が上書きされない場合</span><span class="sxs-lookup"><span data-stu-id="f88f2-141">If No Pipeline Input Override the BeginProcessing Method (AC02)</span></span>

<span data-ttu-id="f88f2-142">処理を実装する必要があります、コマンドレットが、パイプラインからの入力を受け付けない場合、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="f88f2-142">If your cmdlet does not accept input from the pipeline, processing should be implemented in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span> <span data-ttu-id="f88f2-143">このメソッドの使用は、Windows PowerShell のコマンドレット間で順序を維持するためにできます。</span><span class="sxs-lookup"><span data-stu-id="f88f2-143">Use of this method allows Windows PowerShell to maintain ordering between cmdlets.</span></span> <span data-ttu-id="f88f2-144">パイプラインの残りのコマンドレットは、これらの処理を起動するチャンスを取得する前に、パイプラインの最初のコマンドレットは常にそのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-144">The first cmdlet in the pipeline always returns its objects before the remaining cmdlets in the pipeline get a chance to start their processing.</span></span>

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a><span data-ttu-id="f88f2-145">StopProcessing メソッド (AC03) をオーバーライドしている停止要求を処理するには</span><span class="sxs-lookup"><span data-stu-id="f88f2-145">To Handle Stop Requests Override the StopProcessing Method (AC03)</span></span>

<span data-ttu-id="f88f2-146">上書き、 [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing)メソッド コマンドレットは、停止信号を処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f88f2-146">Override the [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) method so that your cmdlet can handle stop signal.</span></span> <span data-ttu-id="f88f2-147">一部のコマンドレットの操作を完了する時間がかかるし、時間など、コマンドレットが実行時間の長い RPC 呼び出しでスレッドをブロックするときに、Windows PowerShell ランタイムへの呼び出しの間で渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f88f2-147">Some cmdlets take a long time to complete their operation, and they let a long time pass between calls to the Windows PowerShell runtime, such as when the cmdlet blocks the thread in long-running RPC calls.</span></span> <span data-ttu-id="f88f2-148">呼び出しを行うコマンドレットが含まれます、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド、およびその他のフィードバック完了までに時間がかかる場合がありますメカニズム。</span><span class="sxs-lookup"><span data-stu-id="f88f2-148">This includes cmdlets that make calls to the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method, to the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, and to other feedback mechanisms that may take a long time to complete.</span></span> <span data-ttu-id="f88f2-149">このような場合、ユーザーは、これらのコマンドレットに停止シグナルを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-149">For these cases the user might need to send a stop signal to these cmdlets.</span></span>

### <a name="implement-the-idisposable-interface-ac04"></a><span data-ttu-id="f88f2-150">IDisposable インターフェイス (AC04) の実装します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-150">Implement the IDisposable Interface (AC04)</span></span>

<span data-ttu-id="f88f2-151">コマンドレットに (パイプラインに書き込まれます) の破棄されていないオブジェクトがある場合は、によって、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドでは、コマンドレットは、その他のオブジェクトの破棄を必要があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-151">If your cmdlet has objects that are not disposed of (written to the pipeline) by the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, your cmdlet might require additional object disposal.</span></span> <span data-ttu-id="f88f2-152">例では、コマンドレットがファイル ハンドルを開いた場合、その[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドと保持で使用するためのハンドルを開く、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)処理の最後に終了する方法、このハンドルが。</span><span class="sxs-lookup"><span data-stu-id="f88f2-152">For example, if your cmdlet opens a file handle in its [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, this handle has to be closed at the end of processing.</span></span>

<span data-ttu-id="f88f2-153">Windows PowerShell ランタイムが常に呼び出していない、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="f88f2-153">The Windows PowerShell runtime does not always call the  [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="f88f2-154">たとえば、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)コマンドレットを途中の操作をキャンセルするか、コマンドレットのすべての部分でエラーが発生した場合は、終了した場合、メソッドは呼び出されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f88f2-154">For example, the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method might not be called if the cmdlet is canceled midway through its operation or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="f88f2-155">したがって、オブジェクトのクリーンアップが必要なコマンドレットの .NET Framework クラスを完全に実装[System.IDisposable](/dotnet/api/System.IDisposable)インターフェイス パターン、ファイナライザーを含む、Windows PowerShell ランタイムは、両方を呼び出すことができます、[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)と[System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。</span><span class="sxs-lookup"><span data-stu-id="f88f2-155">Therefore, the .NET Framework class for a cmdlet that requires object cleanup should implement the complete  [System.IDisposable](/dotnet/api/System.IDisposable) interface pattern, including the finalizer, so that the Windows PowerShell runtime can call both the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>

### <a name="use-serialization-friendly-parameter-types-ac05"></a><span data-ttu-id="f88f2-156">シリアル化に適したパラメーターの型 (AC05) を使用して、</span><span class="sxs-lookup"><span data-stu-id="f88f2-156">Use Serialization-friendly Parameter Types (AC05)</span></span>

<span data-ttu-id="f88f2-157">リモート コンピューターで、コマンドレットの実行をサポートするには、クライアント コンピューターで簡単にシリアル化し、サーバー コンピューターにリハイド レートする型を使用します。</span><span class="sxs-lookup"><span data-stu-id="f88f2-157">To support running your cmdlet on remote computers, use types that can be easily serialized on the client computer and then rehydrated on the server computer.</span></span> <span data-ttu-id="f88f2-158">次の種類は、シリアル化に適したです。</span><span class="sxs-lookup"><span data-stu-id="f88f2-158">The follow types are serialization-friendly.</span></span>

<span data-ttu-id="f88f2-159">プリミティブの種類:</span><span class="sxs-lookup"><span data-stu-id="f88f2-159">Primitive types:</span></span>

- <span data-ttu-id="f88f2-160">Byte、SByte、10 進数、単一、Double、Int16、Int32、Int64、Uint16、UInt32、および UInt64。</span><span class="sxs-lookup"><span data-stu-id="f88f2-160">Byte, SByte, Decimal, Single, Double, Int16, Int32, Int64, Uint16, UInt32, and UInt64.</span></span>

- <span data-ttu-id="f88f2-161">ブール値、Guid、Byte、TimeSpan、DateTime、Uri、およびバージョン。</span><span class="sxs-lookup"><span data-stu-id="f88f2-161">Boolean, Guid, Byte[], TimeSpan, DateTime, Uri, and Version.</span></span>

- <span data-ttu-id="f88f2-162">Char、String、XmlDocument です。</span><span class="sxs-lookup"><span data-stu-id="f88f2-162">Char, String, XmlDocument.</span></span>

<span data-ttu-id="f88f2-163">組み込みの rehydratable 型:</span><span class="sxs-lookup"><span data-stu-id="f88f2-163">Built-in rehydratable types:</span></span>

- <span data-ttu-id="f88f2-164">PSPrimitiveDictionary</span><span class="sxs-lookup"><span data-stu-id="f88f2-164">PSPrimitiveDictionary</span></span>

- <span data-ttu-id="f88f2-165">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f88f2-165">SwitchParameter</span></span>

- <span data-ttu-id="f88f2-166">PSListModifier</span><span class="sxs-lookup"><span data-stu-id="f88f2-166">PSListModifier</span></span>

- <span data-ttu-id="f88f2-167">PSCredential</span><span class="sxs-lookup"><span data-stu-id="f88f2-167">PSCredential</span></span>

- <span data-ttu-id="f88f2-168">IPAddress, MailAddress</span><span class="sxs-lookup"><span data-stu-id="f88f2-168">IPAddress, MailAddress</span></span>

- <span data-ttu-id="f88f2-169">CultureInfo</span><span class="sxs-lookup"><span data-stu-id="f88f2-169">CultureInfo</span></span>

- <span data-ttu-id="f88f2-170">X509Certificate2、X500DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f88f2-170">X509Certificate2, X500DistinguishedName</span></span>

- <span data-ttu-id="f88f2-171">DirectorySecurity、FileSecurity、RegistrySecurity</span><span class="sxs-lookup"><span data-stu-id="f88f2-171">DirectorySecurity, FileSecurity, RegistrySecurity</span></span>

<span data-ttu-id="f88f2-172">他の種類:</span><span class="sxs-lookup"><span data-stu-id="f88f2-172">Other types:</span></span>

- <span data-ttu-id="f88f2-173">SecureString</span><span class="sxs-lookup"><span data-stu-id="f88f2-173">SecureString</span></span>

- <span data-ttu-id="f88f2-174">コンテナー (リストとディクショナリが上記の型の)</span><span class="sxs-lookup"><span data-stu-id="f88f2-174">Containers (lists and dictionaries of the above type)</span></span>

### <a name="use-securestring-for-sensitive-data-ac06"></a><span data-ttu-id="f88f2-175">SecureString を使用して、機密性の高いデータ (AC06)</span><span class="sxs-lookup"><span data-stu-id="f88f2-175">Use SecureString for Sensitive Data (AC06)</span></span>

<span data-ttu-id="f88f2-176">常に機密データを処理するときに使用して、 [System.Security.Securestring](/dotnet/api/System.Security.SecureString)データ型。</span><span class="sxs-lookup"><span data-stu-id="f88f2-176">When handling sensitive data always use the [System.Security.Securestring](/dotnet/api/System.Security.SecureString) data type.</span></span> <span data-ttu-id="f88f2-177">これには、パイプラインに機密データを返すことに加えて、パラメーターにパイプラインの入力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f88f2-177">This could include pipeline input to parameters, as well as returning sensitive data to the pipeline.</span></span>

## <a name="see-also"></a><span data-ttu-id="f88f2-178">参照</span><span class="sxs-lookup"><span data-stu-id="f88f2-178">See Also</span></span>

[<span data-ttu-id="f88f2-179">必要な開発のガイドライン</span><span class="sxs-lookup"><span data-stu-id="f88f2-179">Required Development Guidelines</span></span>](./required-development-guidelines.md)

[<span data-ttu-id="f88f2-180">強くお勧めします開発のガイドライン</span><span class="sxs-lookup"><span data-stu-id="f88f2-180">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

[<span data-ttu-id="f88f2-181">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="f88f2-181">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
