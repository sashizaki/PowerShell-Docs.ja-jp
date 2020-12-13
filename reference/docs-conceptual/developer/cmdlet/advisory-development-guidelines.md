---
ms.date: 09/13/2016
ms.topic: reference
title: お勧めする開発ガイドライン
description: お勧めする開発ガイドライン
ms.openlocfilehash: 1ac18925bbc2506e6a03810d24f58c2f3113fd55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668322"
---
# <a name="advisory-development-guidelines"></a><span data-ttu-id="f9f47-103">お勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f9f47-103">Advisory Development Guidelines</span></span>

<span data-ttu-id="f9f47-104">このセクションでは、適切な開発とユーザーエクスペリエンスを確保するために考慮する必要があるガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f9f47-104">This section describes guidelines that you should consider to ensure good development and user experiences.</span></span> <span data-ttu-id="f9f47-105">場合によっては、適用される場合もあれば、ない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-105">Sometimes they might apply, and sometimes they might not.</span></span>

## <a name="design-guidelines"></a><span data-ttu-id="f9f47-106">設計ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f9f47-106">Design Guidelines</span></span>

<span data-ttu-id="f9f47-107">コマンドレットを設計するときは、次のガイドラインを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-107">The following guidelines should be considered when designing cmdlets.</span></span> <span data-ttu-id="f9f47-108">状況に当てはまる設計ガイドラインが見つかったら、同様のガイドラインのコードガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f9f47-108">When you find a Design guideline that applies to your situation, be sure to look at the Code guidelines for similar guidelines.</span></span>

### <a name="support-an-inputobject-parameter-ad01"></a><span data-ttu-id="f9f47-109">InputObject パラメーター (AD01) のサポート</span><span class="sxs-lookup"><span data-stu-id="f9f47-109">Support an InputObject Parameter (AD01)</span></span>

<span data-ttu-id="f9f47-110">Windows PowerShell は Microsoft .NET Framework オブジェクトで直接動作するため、ユーザーが特定の操作を実行するために必要な型と正確に一致する .NET Framework オブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-110">Because Windows PowerShell works directly with Microsoft .NET Framework objects, a .NET Framework object is often available that exactly matches the type the user needs to perform a particular operation.</span></span> <span data-ttu-id="f9f47-111">`InputObject` は、このようなオブジェクトを入力として受け取るパラメーターの標準名です。</span><span class="sxs-lookup"><span data-stu-id="f9f47-111">`InputObject` is the standard name for a parameter that takes such an object as input.</span></span> <span data-ttu-id="f9f47-112">たとえば、 [Stopproc チュートリアル](./stopproc-tutorial.md)の **Stop proc** コマンドレットは、 `InputObject` パイプラインからの入力をサポートする型のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="f9f47-112">For example, the sample **Stop-Proc** cmdlet in the [StopProc Tutorial](./stopproc-tutorial.md) defines an `InputObject` parameter of type Process that supports the input from the pipeline.</span></span> <span data-ttu-id="f9f47-113">ユーザーは、一連のプロセスオブジェクトを取得し、それらを操作して、停止するオブジェクトを正確に選択し、そのオブジェクトを **Stop Proc** コマンドレットに直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-113">The user can get a set of process objects, manipulate them to select the exact objects to stop, and then pass them to the **Stop-Proc** cmdlet directly.</span></span>

### <a name="support-the-force-parameter-ad02"></a><span data-ttu-id="f9f47-114">Force パラメーター (AD02) のサポート</span><span class="sxs-lookup"><span data-stu-id="f9f47-114">Support the Force Parameter (AD02)</span></span>

<span data-ttu-id="f9f47-115">場合によっては、コマンドレットでユーザーが要求された操作を実行できないように保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-115">Occasionally, a cmdlet needs to protect the user from performing a requested operation.</span></span> <span data-ttu-id="f9f47-116">このようなコマンドレットは、ユーザーが `Force` 操作を実行するアクセス許可を持っている場合に、ユーザーがその保護をオーバーライドできるようにするために、パラメーターをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-116">Such a cmdlet should support a `Force` parameter to allow the user to override that protection if the user has permissions to perform the operation.</span></span>

<span data-ttu-id="f9f47-117">たとえば、項目の [削除](/powershell/module/microsoft.powershell.management/remove-item) コマンドレットは、通常、読み取り専用ファイルを削除しません。</span><span class="sxs-lookup"><span data-stu-id="f9f47-117">For example, the [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item) cmdlet does not normally remove a read-only file.</span></span> <span data-ttu-id="f9f47-118">ただし、このコマンドレットではパラメーターがサポートされている `Force` ため、ユーザーは読み取り専用ファイルを強制的に削除できます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-118">However, this cmdlet supports a `Force` parameter so a user can force removal of a read-only file.</span></span> <span data-ttu-id="f9f47-119">読み取り専用属性を変更するアクセス許可がユーザーに既に与えられていて、ユーザーがファイルを削除した場合、パラメーターを使用すると `Force` 操作が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-119">If the user already has permission to modify the read-only attribute, and the user removes the file, use of the `Force` parameter simplifies the operation.</span></span> <span data-ttu-id="f9f47-120">ただし、ファイルを削除する権限がユーザーに与えられていない場合、パラメーターを指定して `Force` も効果はありません。</span><span class="sxs-lookup"><span data-stu-id="f9f47-120">However, if the user does not have permission to remove the file, the `Force` parameter has no effect.</span></span>

### <a name="handle-credentials-through-windows-powershell-ad03"></a><span data-ttu-id="f9f47-121">Windows PowerShell (AD03) を使用して資格情報を処理する</span><span class="sxs-lookup"><span data-stu-id="f9f47-121">Handle Credentials Through Windows PowerShell (AD03)</span></span>

<span data-ttu-id="f9f47-122">コマンドレットでは、 `Credential` 資格情報を表すパラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-122">A cmdlet should define a `Credential` parameter to represent credentials.</span></span> <span data-ttu-id="f9f47-123">このパラメーターは [、型が system.servicemodel で、](/dotnet/api/System.Management.Automation.PSCredential) Credential 属性の宣言を使用して定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-123">This parameter must be of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) and must be defined using a Credential attribute declaration.</span></span> <span data-ttu-id="f9f47-124">このサポートによって、ユーザーは、パスワードのユーザー名を入力するか、完全な資格情報が直接指定されていない場合の両方に対して自動的にプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-124">This support automatically prompts the user for the user name, for the password, or for both when a full credential is not supplied directly.</span></span> <span data-ttu-id="f9f47-125">Credential 属性の詳細については、「 [Credential 属性の宣言](./credential-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9f47-125">For more information about the Credential attribute, see [Credential Attribute Declaration](./credential-attribute-declaration.md).</span></span>

### <a name="support-encoding-parameters-ad04"></a><span data-ttu-id="f9f47-126">パラメーターのエンコード (AD04) のサポート</span><span class="sxs-lookup"><span data-stu-id="f9f47-126">Support Encoding Parameters (AD04)</span></span>

<span data-ttu-id="f9f47-127">ファイルシステム内のファイルへの書き込みやファイルからの読み取りなど、バイナリ形式のテキストの読み取りまたは書き込みを行うコマンドレットでは、バイナリ形式でテキストをエンコードする方法を指定する Encoding パラメーターをコマンドレットに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-127">If your cmdlet reads or writes text to or from a binary form, such as writing to or reading from a file in a filesystem, then your cmdlet has to have Encoding parameter that specifies how the text is encoded in the binary form.</span></span>

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a><span data-ttu-id="f9f47-128">テストコマンドレットはブール値 (AD05) を返す必要があります</span><span class="sxs-lookup"><span data-stu-id="f9f47-128">Test Cmdlets Should Return a Boolean (AD05)</span></span>

<span data-ttu-id="f9f47-129">リソースに対してテストを実行するコマンドレットは、条件式で使用できるように、システムのブール型をパイプラインに返す必要があり[ます。](/dotnet/api/System.Boolean)</span><span class="sxs-lookup"><span data-stu-id="f9f47-129">Cmdlets that perform tests against their resources should return a [System.Boolean](/dotnet/api/System.Boolean) type to the pipeline so that they can be used in conditional expressions.</span></span>

## <a name="code-guidelines"></a><span data-ttu-id="f9f47-130">コードのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f9f47-130">Code Guidelines</span></span>

<span data-ttu-id="f9f47-131">コマンドレットコードを記述するときは、次のガイドラインを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-131">The following guidelines should be considered when writing cmdlet code.</span></span> <span data-ttu-id="f9f47-132">状況に当てはまるガイドラインが見つかった場合は、設計ガイドラインで同様のガイドラインを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f9f47-132">When you find a guideline that applies to your situation, be sure to look at the Design guidelines for similar guidelines.</span></span>

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a><span data-ttu-id="f9f47-133">コマンドレットクラスの名前付け規則に従う (AC01)</span><span class="sxs-lookup"><span data-stu-id="f9f47-133">Follow Cmdlet Class Naming Conventions (AC01)</span></span>

<span data-ttu-id="f9f47-134">標準的な名前付け規則に従うことで、コマンドレットをより見つけやすくなり、コマンドレットの動作を正確に理解することができます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-134">By following standard naming conventions, you make your cmdlets more discoverable, and you help the user understand exactly what the cmdlets do.</span></span> <span data-ttu-id="f9f47-135">この方法は、コマンドレットがパブリック型であるため、Windows PowerShell を使用する他の開発者にとって特に重要です。</span><span class="sxs-lookup"><span data-stu-id="f9f47-135">This practice is particularly important for other developers using Windows PowerShell because cmdlets are public types.</span></span>

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a><span data-ttu-id="f9f47-136">正しい名前空間のコマンドレットを定義する</span><span class="sxs-lookup"><span data-stu-id="f9f47-136">Define a Cmdlet in the Correct Namespace</span></span>

<span data-ttu-id="f9f47-137">通常は、"を追加する .NET Framework 名前空間のコマンドレットのクラスを定義します。コマンドレットを実行する製品を表す名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9f47-137">You normally define the class for a cmdlet in a .NET Framework namespace that appends ".Commands" to the namespace that represents the product in which the cmdlet runs.</span></span> <span data-ttu-id="f9f47-138">たとえば、Windows PowerShell に含まれているコマンドレットは、名前空間で定義されてい `Microsoft.PowerShell.Commands` ます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-138">For example, cmdlets that are included with Windows PowerShell are defined in the `Microsoft.PowerShell.Commands` namespace.</span></span>

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a><span data-ttu-id="f9f47-139">コマンドレット名と一致するようにコマンドレットクラスの名前を指定します</span><span class="sxs-lookup"><span data-stu-id="f9f47-139">Name the Cmdlet Class to Match the Cmdlet Name</span></span>

<span data-ttu-id="f9f47-140">コマンドレットを実装する .NET Framework クラスに名前を付けた場合は、クラスに "" という名前を付け *\<Verb>**\<Noun>**\<Command>* ます。ここで、とのプレースホルダーを、 *\<Verb>* *\<Noun>* コマンドレット名に使用される動詞と名詞に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-140">When you name the .NET Framework class that implements a cmdlet, name the class "*\<Verb>**\<Noun>**\<Command>*", where you replace the *\<Verb>* and *\<Noun>* placeholders with the verb and noun used for the cmdlet name.</span></span> <span data-ttu-id="f9f47-141">たとえば、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットは、というクラスによって実装され `GetProcessCommand` ます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-141">For example, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet is implemented by a class called `GetProcessCommand`.</span></span>

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a><span data-ttu-id="f9f47-142">パイプライン入力が BeginProcessing メソッドをオーバーライドしない場合 (AC02)</span><span class="sxs-lookup"><span data-stu-id="f9f47-142">If No Pipeline Input Override the BeginProcessing Method (AC02)</span></span>

<span data-ttu-id="f9f47-143">コマンドレットがパイプラインからの入力を受け付けない場合は、処理を実行する必要があります。そのためには、 [このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 使用します。</span><span class="sxs-lookup"><span data-stu-id="f9f47-143">If your cmdlet does not accept input from the pipeline, processing should be implemented in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span> <span data-ttu-id="f9f47-144">この方法を使用すると、Windows PowerShell でコマンドレット間の順序を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-144">Use of this method allows Windows PowerShell to maintain ordering between cmdlets.</span></span> <span data-ttu-id="f9f47-145">パイプラインの最初のコマンドレットは、パイプラインの残りのコマンドレットが処理を開始する前に、常にそのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f9f47-145">The first cmdlet in the pipeline always returns its objects before the remaining cmdlets in the pipeline get a chance to start their processing.</span></span>

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a><span data-ttu-id="f9f47-146">停止要求を処理するには、StopProcessing メソッド (AC03) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f9f47-146">To Handle Stop Requests Override the StopProcessing Method (AC03)</span></span>

<span data-ttu-id="f9f47-147">コマンドレットが停止シグナルを処理できるように、 [このメソッドをオーバーライドします](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) 。</span><span class="sxs-lookup"><span data-stu-id="f9f47-147">Override the [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) method so that your cmdlet can handle stop signal.</span></span> <span data-ttu-id="f9f47-148">一部のコマンドレットでは、操作が完了するまでに長い時間がかかります。また、コマンドレットが長時間の RPC 呼び出しでスレッドをブロックしている場合など、Windows PowerShell ランタイムの呼び出しの間に長い時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-148">Some cmdlets take a long time to complete their operation, and they let a long time pass between calls to the Windows PowerShell runtime, such as when the cmdlet blocks the thread in long-running RPC calls.</span></span> <span data-ttu-id="f9f47-149">これには、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) メソッドへの呼び出しを行うコマンドレット、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) メソッド、および完了までに時間がかかる可能性のあるその他のフィードバック機構が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-149">This includes cmdlets that make calls to the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method, to the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, and to other feedback mechanisms that may take a long time to complete.</span></span> <span data-ttu-id="f9f47-150">このような場合、ユーザーはこれらのコマンドレットに停止シグナルを送信することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-150">For these cases the user might need to send a stop signal to these cmdlets.</span></span>

### <a name="implement-the-idisposable-interface-ac04"></a><span data-ttu-id="f9f47-151">IDisposable インターフェイス (AC04) を実装する</span><span class="sxs-lookup"><span data-stu-id="f9f47-151">Implement the IDisposable Interface (AC04)</span></span>

<span data-ttu-id="f9f47-152">コマンドレット [に、(](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) パイプラインに書き込まれる) の破棄されないオブジェクトが含まれている場合、コマンドレットでは追加のオブジェクトの破棄が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-152">If your cmdlet has objects that are not disposed of (written to the pipeline) by the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, your cmdlet might require additional object disposal.</span></span> <span data-ttu-id="f9f47-153">たとえば、コマンドレットが、その [システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) のファイルハンドルを開いて、そのハンドルを開いたままにして [、プロセスの](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 終了時にハンドルを開いたままにした場合、このハンドルを閉じておく必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="f9f47-153">For example, if your cmdlet opens a file handle in its [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, this handle has to be closed at the end of processing.</span></span>

<span data-ttu-id="f9f47-154">Windows PowerShell ランタイムで  [は、必ずしも system.servicemodel メソッドが](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 呼び出されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f9f47-154">The Windows PowerShell runtime does not always call the  [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="f9f47-155">たとえば、コマンドレットが操作の途中で取り消された場合、またはコマンドレットのいずれかの部分で終了エラーが発生した場合、 [このメソッドは](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 呼び出されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f9f47-155">For example, the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method might not be called if the cmdlet is canceled midway through its operation or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="f9f47-156">したがって、オブジェクトのクリーンアップを必要とするコマンドレットの .NET Framework クラスは、ファイナライザーを含む完全な system.servicemodel インターフェイスパターンを実装する必要があります。これにより、Windows PowerShell ランタイムは、処理の最後に、[システム](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)の両方[のメソッドを](/dotnet/api/System.IDisposable.Dispose)呼び出すことができるように[なります。](/dotnet/api/System.IDisposable)</span><span class="sxs-lookup"><span data-stu-id="f9f47-156">Therefore, the .NET Framework class for a cmdlet that requires object cleanup should implement the complete  [System.IDisposable](/dotnet/api/System.IDisposable) interface pattern, including the finalizer, so that the Windows PowerShell runtime can call both the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>

### <a name="use-serialization-friendly-parameter-types-ac05"></a><span data-ttu-id="f9f47-157">シリアル化に対応したパラメーターの型 (AC05) を使用する</span><span class="sxs-lookup"><span data-stu-id="f9f47-157">Use Serialization-friendly Parameter Types (AC05)</span></span>

<span data-ttu-id="f9f47-158">リモートコンピューターでコマンドレットを実行できるようにするには、クライアントコンピューターで簡単にシリアル化できる型を使用し、その後でサーバーコンピューター上で復元することができます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-158">To support running your cmdlet on remote computers, use types that can be easily serialized on the client computer and then rehydrated on the server computer.</span></span> <span data-ttu-id="f9f47-159">次の型はシリアル化に適しています。</span><span class="sxs-lookup"><span data-stu-id="f9f47-159">The follow types are serialization-friendly.</span></span>

<span data-ttu-id="f9f47-160">プリミティブ型:</span><span class="sxs-lookup"><span data-stu-id="f9f47-160">Primitive types:</span></span>

- <span data-ttu-id="f9f47-161">Byte、SByte、Decimal、Single、Double、Int16、Int32、Int64、Uint16、UInt32、および UInt64。</span><span class="sxs-lookup"><span data-stu-id="f9f47-161">Byte, SByte, Decimal, Single, Double, Int16, Int32, Int64, Uint16, UInt32, and UInt64.</span></span>

- <span data-ttu-id="f9f47-162">ブール値、Guid、Byte []、TimeSpan、DateTime、Uri、Version。</span><span class="sxs-lookup"><span data-stu-id="f9f47-162">Boolean, Guid, Byte[], TimeSpan, DateTime, Uri, and Version.</span></span>

- <span data-ttu-id="f9f47-163">Char、String、XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="f9f47-163">Char, String, XmlDocument.</span></span>

<span data-ttu-id="f9f47-164">組み込みの rehydratable 型:</span><span class="sxs-lookup"><span data-stu-id="f9f47-164">Built-in rehydratable types:</span></span>

- <span data-ttu-id="f9f47-165">PSPrimitiveDictionary</span><span class="sxs-lookup"><span data-stu-id="f9f47-165">PSPrimitiveDictionary</span></span>

- <span data-ttu-id="f9f47-166">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f9f47-166">SwitchParameter</span></span>

- <span data-ttu-id="f9f47-167">PSListModifier</span><span class="sxs-lookup"><span data-stu-id="f9f47-167">PSListModifier</span></span>

- <span data-ttu-id="f9f47-168">PSCredential</span><span class="sxs-lookup"><span data-stu-id="f9f47-168">PSCredential</span></span>

- <span data-ttu-id="f9f47-169">IPAddress、MailAddress</span><span class="sxs-lookup"><span data-stu-id="f9f47-169">IPAddress, MailAddress</span></span>

- <span data-ttu-id="f9f47-170">CultureInfo</span><span class="sxs-lookup"><span data-stu-id="f9f47-170">CultureInfo</span></span>

- <span data-ttu-id="f9f47-171">X509Certificate2、System.security.cryptography.x509certificates.x500distinguishedname</span><span class="sxs-lookup"><span data-stu-id="f9f47-171">X509Certificate2, X500DistinguishedName</span></span>

- <span data-ttu-id="f9f47-172">DirectorySecurity、System.security.accesscontrol.filesecurity、RegistrySecurity</span><span class="sxs-lookup"><span data-stu-id="f9f47-172">DirectorySecurity, FileSecurity, RegistrySecurity</span></span>

<span data-ttu-id="f9f47-173">その他の種類:</span><span class="sxs-lookup"><span data-stu-id="f9f47-173">Other types:</span></span>

- <span data-ttu-id="f9f47-174">SecureString</span><span class="sxs-lookup"><span data-stu-id="f9f47-174">SecureString</span></span>

- <span data-ttu-id="f9f47-175">コンテナー (上記の種類のリストとディクショナリ)</span><span class="sxs-lookup"><span data-stu-id="f9f47-175">Containers (lists and dictionaries of the above type)</span></span>

### <a name="use-securestring-for-sensitive-data-ac06"></a><span data-ttu-id="f9f47-176">機密データに SecureString を使用する (AC06)</span><span class="sxs-lookup"><span data-stu-id="f9f47-176">Use SecureString for Sensitive Data (AC06)</span></span>

<span data-ttu-id="f9f47-177">機微なデータを処理するときは、常に [Securestring](/dotnet/api/System.Security.SecureString) データ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9f47-177">When handling sensitive data always use the [System.Security.Securestring](/dotnet/api/System.Security.SecureString) data type.</span></span> <span data-ttu-id="f9f47-178">これには、パラメーターへのパイプライン入力だけでなく、機密データをパイプラインに返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f9f47-178">This could include pipeline input to parameters, as well as returning sensitive data to the pipeline.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9f47-179">参照</span><span class="sxs-lookup"><span data-stu-id="f9f47-179">See Also</span></span>

[<span data-ttu-id="f9f47-180">必要な開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f9f47-180">Required Development Guidelines</span></span>](./required-development-guidelines.md)

[<span data-ttu-id="f9f47-181">強くお勧めする開発ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f9f47-181">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

[<span data-ttu-id="f9f47-182">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="f9f47-182">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
