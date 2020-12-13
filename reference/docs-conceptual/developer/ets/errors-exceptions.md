---
ms.date: 07/09/2020
ms.topic: reference
title: 拡張型システムのエラーと例外
description: 拡張型システムのエラーと例外
ms.openlocfilehash: 295c16ad9abb67b0c4967bf32125bfc7ee0a35da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652470"
---
# <a name="errors-and-exceptions-in-the-extended-type-system"></a><span data-ttu-id="c3792-103">拡張型システムのエラーと例外</span><span class="sxs-lookup"><span data-stu-id="c3792-103">Errors and exceptions in the Extended Type System</span></span>

<span data-ttu-id="c3792-104">型データの初期化中、 **PSObject** オブジェクトのメンバーにアクセスするとき、または **言語プリミティブ** などのユーティリティクラスの1つを使用するときに、エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c3792-104">Errors can occur in ETS during the initialization of type data and when accessing a member of an **PSObject** object or using one of the utility classes such as **LanguagePrimitives**.</span></span>

## <a name="runtime-errors"></a><span data-ttu-id="c3792-105">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="c3792-105">Runtime errors</span></span>

<span data-ttu-id="c3792-106">1つの例外として、キャスト時に、実行時に発生した例外はすべて、 **ExtendedTypeSystemException** 例外または **ExtendedTypeSystemException** クラスから派生した例外のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="c3792-106">With one exception, when casting, all exceptions thrown from ETS during runtime are either an **ExtendedTypeSystemException** exception or an exception derived from the **ExtendedTypeSystemException** class.</span></span> <span data-ttu-id="c3792-107">これにより、スクリプト開発者は、スクリプト内のステートメントを使用して、これらの例外をトラップでき `Trap` ます。</span><span class="sxs-lookup"><span data-stu-id="c3792-107">This allows script developers to trap these exceptions using the `Trap` statement in their script.</span></span>

## <a name="errors-getting-member-values"></a><span data-ttu-id="c3792-108">メンバー値を取得するときのエラー</span><span class="sxs-lookup"><span data-stu-id="c3792-108">Errors getting member values</span></span>

<span data-ttu-id="c3792-109">メンバー (プロパティ、メソッド、またはパラメーター化されたプロパティ) の値を取得するときに発生するすべてのエラーにより、 **Getvalueexception** または **GetValueInvocationException** exception がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-109">All errors that occur when getting the value of an ETS member (property, method, or parameterized property) cause a **GetValueException** or **GetValueInvocationException** exception to be thrown.</span></span>
<span data-ttu-id="c3792-110">場合、エラーが発生したことを認識する **Getvalueexception** 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-110">When ETS recognizes that an error occurred a **GetValueException** exception is thrown.</span></span> <span data-ttu-id="c3792-111">参照されるメンバーの基になる getter がエラーが発生したことを認識すると、 **GetValueInvocationException** 例外がスローされ、get 呼び出しエラーの原因となった内部例外が含まれる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3792-111">When the underlying getter of a referenced member recognizes that an error occurred, a **GetValueInvocationException** exception is thrown that may or may not include the inner exception that caused the get invocation error.</span></span>

## <a name="errors-setting-member-values"></a><span data-ttu-id="c3792-112">メンバー値の設定エラー</span><span class="sxs-lookup"><span data-stu-id="c3792-112">Errors setting member values</span></span>

<span data-ttu-id="c3792-113">プロパティの値を設定するときに発生するすべてのエラーにより、 **Setvalueexception** または **SetValueInvocationException** 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-113">All errors that occur when setting the value of an ETS property cause a **SetValueException** or **SetValueInvocationException** exception to be thrown.</span></span> <span data-ttu-id="c3792-114">は、エラーが発生したことを認識すると、 **Setvalueexception** 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-114">When ETS recognizes that an error occurred a **SetValueException** exception is thrown.</span></span> <span data-ttu-id="c3792-115">参照されるプロパティの基になる setter がエラーが発生したことを認識すると、 **SetValueInvocationException** 例外がスローされます。この例外は、set 呼び出しエラーの原因となった内部例外を含んでいる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3792-115">When the underlying setter of a referenced property recognizes that an error occurred, a **SetValueInvocationException** exception is thrown that may or may not include the inner exception that caused the set invocation error.</span></span>

## <a name="errors-invoking-a-method"></a><span data-ttu-id="c3792-116">メソッドの呼び出しエラー</span><span class="sxs-lookup"><span data-stu-id="c3792-116">Errors invoking a method</span></span>

<span data-ttu-id="c3792-117">メソッドの呼び出し時に発生したすべてのエラーによって、 **MethodException** または **MethodInvocationException** 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-117">All errors that occur when invoking an ETS method cause a **MethodException** or **MethodInvocationException** exception to be thrown.</span></span> <span data-ttu-id="c3792-118">**MethodException** は、エラーが発生したことを認識すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-118">When ETS recognizes that an error occurred a **MethodException** exception is thrown.</span></span> <span data-ttu-id="c3792-119">参照されたメソッドがエラーが発生したことを認識すると、 **MethodInvocationException** 例外がスローされます。これには、呼び出しエラーの原因となった内部例外が含まれる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3792-119">When the referenced method recognizes that an error occurred, a **MethodInvocationException** exception is thrown that may or may not include the inner exception that caused the invocation error.</span></span>

## <a name="casting-errors"></a><span data-ttu-id="c3792-120">キャストエラー</span><span class="sxs-lookup"><span data-stu-id="c3792-120">Casting errors</span></span>

<span data-ttu-id="c3792-121">無効なキャストが試行されると、 **PSInvalidCastException** がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-121">When an invalid cast is attempted, an **PSInvalidCastException** is thrown.</span></span> <span data-ttu-id="c3792-122">この例外は **InvalidCastException** から派生するため、スクリプトから直接トラップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c3792-122">Because this exception derives from **System.InvalidCastException**, it is not able to be directly trapped from script.</span></span> <span data-ttu-id="c3792-123">キャストを試行するエンティティは、スクリプトによってトラップできるように、 **Psruntimeexception** で **PSInvalidCastException** をラップする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3792-123">Be aware that the entity attempting the cast would need to wrap **PSInvalidCastException** in an **PSRuntimeException** for this to be trappable by scripts.</span></span> <span data-ttu-id="c3792-124">**PSPropertySet**、 **psmemberset** セット、 **Psmemberset**、または **ReadOnlyPSMemberInfoCollection ' 1** のメンバーの値を設定しようとすると、 **NotSupportedException** がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3792-124">If an attempt is made to set the value of an **PSPropertySet**, **PSMemberSet**, **PSMethodInfo**, or a member of the **ReadOnlyPSMemberInfoCollection\`1**, a **NotSupportedException** is thrown.</span></span>

## <a name="common-runtime-errors"></a><span data-ttu-id="c3792-125">一般的なランタイムエラー</span><span class="sxs-lookup"><span data-stu-id="c3792-125">Common runtime errors</span></span>

<span data-ttu-id="c3792-126">その他の一般的なランタイムエラーは、 **ExtendedTypeSystemException** exception 型であり、追加の特定の例外の種類はありません。</span><span class="sxs-lookup"><span data-stu-id="c3792-126">Any other common runtime errors that occur are of type **ExtendedTypeSystemException** exception with no additional specific exception types.</span></span>

## <a name="initialization-errors"></a><span data-ttu-id="c3792-127">初期化エラー</span><span class="sxs-lookup"><span data-stu-id="c3792-127">Initialization errors</span></span>

<span data-ttu-id="c3792-128">の初期化中にエラーが発生する可能性があり `types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="c3792-128">Errors may occur when initializing `types.ps1xml`.</span></span> <span data-ttu-id="c3792-129">通常、これらのエラーは、PowerShell ランタイムの起動時に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3792-129">Typically, these errors are displayed when the PowerShell runtime starts.</span></span> <span data-ttu-id="c3792-130">ただし、モジュールが読み込まれたときに表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3792-130">However, they can also be displayed when a module is loaded.</span></span>
