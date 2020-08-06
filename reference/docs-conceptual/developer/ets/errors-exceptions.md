---
title: 拡張型システムのエラーと例外
ms.date: 07/09/2020
ms.openlocfilehash: f60c53e33c031168eda53726e0d296bf91139fda
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786290"
---
# <a name="errors-and-exceptions-in-the-extended-type-system"></a><span data-ttu-id="4676a-102">拡張型システムのエラーと例外</span><span class="sxs-lookup"><span data-stu-id="4676a-102">Errors and exceptions in the Extended Type System</span></span>

<span data-ttu-id="4676a-103">型データの初期化中、 **PSObject**オブジェクトのメンバーにアクセスするとき、または**言語プリミティブ**などのユーティリティクラスの1つを使用するときに、エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="4676a-103">Errors can occur in ETS during the initialization of type data and when accessing a member of an **PSObject** object or using one of the utility classes such as **LanguagePrimitives**.</span></span>

## <a name="runtime-errors"></a><span data-ttu-id="4676a-104">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="4676a-104">Runtime errors</span></span>

<span data-ttu-id="4676a-105">1つの例外として、キャスト時に、実行時に発生した例外はすべて、 **ExtendedTypeSystemException**例外または**ExtendedTypeSystemException**クラスから派生した例外のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="4676a-105">With one exception, when casting, all exceptions thrown from ETS during runtime are either an **ExtendedTypeSystemException** exception or an exception derived from the **ExtendedTypeSystemException** class.</span></span> <span data-ttu-id="4676a-106">これにより、スクリプト開発者は、スクリプト内のステートメントを使用して、これらの例外をトラップでき `Trap` ます。</span><span class="sxs-lookup"><span data-stu-id="4676a-106">This allows script developers to trap these exceptions using the `Trap` statement in their script.</span></span>

## <a name="errors-getting-member-values"></a><span data-ttu-id="4676a-107">メンバー値を取得するときのエラー</span><span class="sxs-lookup"><span data-stu-id="4676a-107">Errors getting member values</span></span>

<span data-ttu-id="4676a-108">メンバー (プロパティ、メソッド、またはパラメーター化されたプロパティ) の値を取得するときに発生するすべてのエラーにより、 **Getvalueexception**または**GetValueInvocationException** exception がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-108">All errors that occur when getting the value of an ETS member (property, method, or parameterized property) cause a **GetValueException** or **GetValueInvocationException** exception to be thrown.</span></span>
<span data-ttu-id="4676a-109">場合、エラーが発生したことを認識する**Getvalueexception**例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-109">When ETS recognizes that an error occurred a **GetValueException** exception is thrown.</span></span> <span data-ttu-id="4676a-110">参照されるメンバーの基になる getter がエラーが発生したことを認識すると、 **GetValueInvocationException**例外がスローされ、get 呼び出しエラーの原因となった内部例外が含まれる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4676a-110">When the underlying getter of a referenced member recognizes that an error occurred, a **GetValueInvocationException** exception is thrown that may or may not include the inner exception that caused the get invocation error.</span></span>

## <a name="errors-setting-member-values"></a><span data-ttu-id="4676a-111">メンバー値の設定エラー</span><span class="sxs-lookup"><span data-stu-id="4676a-111">Errors setting member values</span></span>

<span data-ttu-id="4676a-112">プロパティの値を設定するときに発生するすべてのエラーにより、 **Setvalueexception**または**SetValueInvocationException**例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-112">All errors that occur when setting the value of an ETS property cause a **SetValueException** or **SetValueInvocationException** exception to be thrown.</span></span> <span data-ttu-id="4676a-113">は、エラーが発生したことを認識すると、 **Setvalueexception**例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-113">When ETS recognizes that an error occurred a **SetValueException** exception is thrown.</span></span> <span data-ttu-id="4676a-114">参照されるプロパティの基になる setter がエラーが発生したことを認識すると、 **SetValueInvocationException**例外がスローされます。この例外は、set 呼び出しエラーの原因となった内部例外を含んでいる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4676a-114">When the underlying setter of a referenced property recognizes that an error occurred, a **SetValueInvocationException** exception is thrown that may or may not include the inner exception that caused the set invocation error.</span></span>

## <a name="errors-invoking-a-method"></a><span data-ttu-id="4676a-115">メソッドの呼び出しエラー</span><span class="sxs-lookup"><span data-stu-id="4676a-115">Errors invoking a method</span></span>

<span data-ttu-id="4676a-116">メソッドの呼び出し時に発生したすべてのエラーによって、 **MethodException**または**MethodInvocationException**例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-116">All errors that occur when invoking an ETS method cause a **MethodException** or **MethodInvocationException** exception to be thrown.</span></span> <span data-ttu-id="4676a-117">**MethodException**は、エラーが発生したことを認識すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-117">When ETS recognizes that an error occurred a **MethodException** exception is thrown.</span></span> <span data-ttu-id="4676a-118">参照されたメソッドがエラーが発生したことを認識すると、 **MethodInvocationException**例外がスローされます。これには、呼び出しエラーの原因となった内部例外が含まれる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4676a-118">When the referenced method recognizes that an error occurred, a **MethodInvocationException** exception is thrown that may or may not include the inner exception that caused the invocation error.</span></span>

## <a name="casting-errors"></a><span data-ttu-id="4676a-119">キャストエラー</span><span class="sxs-lookup"><span data-stu-id="4676a-119">Casting errors</span></span>

<span data-ttu-id="4676a-120">無効なキャストが試行されると、 **PSInvalidCastException**がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-120">When an invalid cast is attempted, an **PSInvalidCastException** is thrown.</span></span> <span data-ttu-id="4676a-121">この例外は**InvalidCastException**から派生するため、スクリプトから直接トラップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4676a-121">Because this exception derives from **System.InvalidCastException**, it is not able to be directly trapped from script.</span></span> <span data-ttu-id="4676a-122">キャストを試行するエンティティは、スクリプトによってトラップできるように、 **Psruntimeexception**で**PSInvalidCastException**をラップする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4676a-122">Be aware that the entity attempting the cast would need to wrap **PSInvalidCastException** in an **PSRuntimeException** for this to be trappable by scripts.</span></span> <span data-ttu-id="4676a-123">**PSPropertySet**、 **psmemberset**セット、 **Psmemberset**、または**ReadOnlyPSMemberInfoCollection ' 1**のメンバーの値を設定しようとすると、 **NotSupportedException**がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4676a-123">If an attempt is made to set the value of an **PSPropertySet**, **PSMemberSet**, **PSMethodInfo**, or a member of the **ReadOnlyPSMemberInfoCollection\`1**, a **NotSupportedException** is thrown.</span></span>

## <a name="common-runtime-errors"></a><span data-ttu-id="4676a-124">一般的なランタイムエラー</span><span class="sxs-lookup"><span data-stu-id="4676a-124">Common runtime errors</span></span>

<span data-ttu-id="4676a-125">その他の一般的なランタイムエラーは、 **ExtendedTypeSystemException** exception 型であり、追加の特定の例外の種類はありません。</span><span class="sxs-lookup"><span data-stu-id="4676a-125">Any other common runtime errors that occur are of type **ExtendedTypeSystemException** exception with no additional specific exception types.</span></span>

## <a name="initialization-errors"></a><span data-ttu-id="4676a-126">初期化エラー</span><span class="sxs-lookup"><span data-stu-id="4676a-126">Initialization errors</span></span>

<span data-ttu-id="4676a-127">の初期化中にエラーが発生する可能性があり `types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="4676a-127">Errors may occur when initializing `types.ps1xml`.</span></span> <span data-ttu-id="4676a-128">通常、これらのエラーは、PowerShell ランタイムの起動時に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4676a-128">Typically, these errors are displayed when the PowerShell runtime starts.</span></span> <span data-ttu-id="4676a-129">ただし、モジュールが読み込まれたときに表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="4676a-129">However, they can also be displayed when a module is loaded.</span></span>
