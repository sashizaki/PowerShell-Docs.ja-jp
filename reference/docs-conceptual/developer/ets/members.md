---
title: 拡張型システムクラスのメンバー
ms.date: 07/09/2020
ms.openlocfilehash: 24a57b7fd0b3db47d0d7138859aa0502ca9016f0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786273"
---
# <a name="extended-type-system-class-members"></a><span data-ttu-id="fc6c5-102">拡張型システムクラスのメンバー</span><span class="sxs-lookup"><span data-stu-id="fc6c5-102">Extended Type System class members</span></span>

<span data-ttu-id="fc6c5-103">は、 **PSMemberTypes**列挙型によって定義される型を持つさまざまな種類のメンバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-103">ETS refers to a number of different kinds of members whose types are defined by the **PSMemberTypes** enumeration.</span></span> <span data-ttu-id="fc6c5-104">これらのメンバー型には、それぞれ独自の CLR 型によって定義されるプロパティ、メソッド、メンバー、およびメンバーセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-104">These member types include properties, methods, members, and member sets that are each defined by their own CLR type.</span></span> <span data-ttu-id="fc6c5-105">たとえば、 **""** というプロパティは、独自の**psnoteproperty**型によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-105">For example, a **NoteProperty** is defined by its own **PSNoteProperty** type.</span></span> <span data-ttu-id="fc6c5-106">これらの個々の CLR 型には、独自の一意のプロパティと、 [Psmemberinfo クラス](/dotnet/api/system.management.automation.psmemberinfo)から継承される共通プロパティの両方があります。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-106">These individual CLR types have both their own unique properties and common properties that are inherited from the [PSMemberInfo class](/dotnet/api/system.management.automation.psmemberinfo).</span></span>

## <a name="the-psmemberinfo-class"></a><span data-ttu-id="fc6c5-107">PSMemberInfo クラス</span><span class="sxs-lookup"><span data-stu-id="fc6c5-107">The PSMemberInfo class</span></span>

<span data-ttu-id="fc6c5-108">**Psmemberinfo**クラスは、すべてのメンバー型の基底クラスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-108">The **PSMemberInfo** class serves as a base class for all ETS member types.</span></span> <span data-ttu-id="fc6c5-109">このクラスは、すべてのメンバー CLR 型に対して次の基本プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-109">This class provides the following base properties to all member CLR types.</span></span>

- <span data-ttu-id="fc6c5-110">**Name**プロパティ: メンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-110">**Name** property: The name of the member.</span></span> <span data-ttu-id="fc6c5-111">この名前は、適用されるメンバーまたは拡張メンバーが公開されるときに、ベースオブジェクトまたは PowerShell によって定義できます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-111">This name can be defined by the base-object or defined by PowerShell when adapted members or extended members are exposed.</span></span>
- <span data-ttu-id="fc6c5-112">**Value**プロパティ: 特定のメンバーから返される値。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-112">**Value** property: The value returned from the particular member.</span></span> <span data-ttu-id="fc6c5-113">各メンバーの種類は、メンバーの値をどのように処理するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-113">Each member type defines how it handles its member value.</span></span>
- <span data-ttu-id="fc6c5-114">**TypeNameOfValue** Property: 値プロパティによって返される値の CLR 型の名前です。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-114">**TypeNameOfValue** property: This is the name of the CLR type of the value that is returned by the Value property.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="fc6c5-115">メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fc6c5-115">Accessing members</span></span>

<span data-ttu-id="fc6c5-116">メンバーのコレクションには、 **PSObject**オブジェクトの**members**プロパティ、**メソッド**プロパティ、および**properties**プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-116">Collections of members can be accessed through the **Members**, **Methods**, and **Properties** properties of the **PSObject** object.</span></span>

## <a name="ets-properties"></a><span data-ttu-id="fc6c5-117">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="fc6c5-117">ETS properties</span></span>

<span data-ttu-id="fc6c5-118">プロパティは、プロパティとして扱うことができるメンバーです。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-118">ETS properties are members that can be treated as a property.</span></span> <span data-ttu-id="fc6c5-119">基本的に、式の左側に表示できます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-119">Essentially, they can appear on the left-hand side of an expression.</span></span> <span data-ttu-id="fc6c5-120">これには、エイリアスプロパティ、コードプロパティ、PowerShell プロパティ、メモプロパティ、およびスクリプトプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-120">They include alias properties, code properties, PowerShell properties, note properties, and script properties.</span></span> <span data-ttu-id="fc6c5-121">これらの種類のプロパティの詳細については、「[プロパティのプロパティ](properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-121">For more information about these types of properties, see [ETS properties](properties.md).</span></span>

## <a name="ets-methods"></a><span data-ttu-id="fc6c5-122">メソッドのメソッド</span><span class="sxs-lookup"><span data-stu-id="fc6c5-122">ETS methods</span></span>

<span data-ttu-id="fc6c5-123">メソッドは、引数を受け取り、結果を返す可能性があり、式の左辺には記述できないメンバーです。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-123">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="fc6c5-124">これには、コードメソッド、PowerShell メソッド、スクリプトメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-124">They include code methods, PowerShell methods, and script methods.</span></span>
<span data-ttu-id="fc6c5-125">これらの種類のメソッドの詳細については、「[メソッド](methods.md)の使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6c5-125">For more information about these types of methods, see [ETS methods](methods.md).</span></span>
