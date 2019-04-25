---
title: ValidatePattern 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067129"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="c08d7-102">ValidatePattern 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c08d7-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="c08d7-103">ValidatePattern 属性には、コマンドレット パラメーターの引数を検証する正規表現パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c08d7-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="c08d7-104">この属性は、Windows PowerShell 関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c08d7-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="c08d7-105">ValidatePattern がコマンドレット内で呼び出されると、Windows PowerShell ランタイムはコマンドレット パラメーターの引数を文字列に変換し、し、ValidatePattern 属性によって指定されたパターンには、その文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="c08d7-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="c08d7-106">コマンドレットは、引数を指定されたパターンの変換後の文字列表現に一致する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="c08d7-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="c08d7-107">一致しない場合は、Windows PowerShell ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="c08d7-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="c08d7-108">構文</span><span class="sxs-lookup"><span data-stu-id="c08d7-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="c08d7-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c08d7-109">Parameters</span></span>

<span data-ttu-id="c08d7-110">`RegexString` ([System.String](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c08d7-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="c08d7-111">パラメーターの引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="c08d7-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="c08d7-112">オプション ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="c08d7-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="c08d7-113">ビットごとの組み合わせを指定します[System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)正規表現のオプションを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="c08d7-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="c08d7-114">コメント</span><span class="sxs-lookup"><span data-stu-id="c08d7-114">Remarks</span></span>

- <span data-ttu-id="c08d7-115">この属性は、パラメーターごと 1 回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c08d7-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="c08d7-116">使用することができます、`Option`さらに、パターンを定義する属性のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c08d7-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="c08d7-117">たとえば、行うことができます、パターン大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="c08d7-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="c08d7-118">この属性をコレクションに適用すると、コレクション内の各要素がパターンに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c08d7-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="c08d7-119">ValidatePattern 属性を定義した、 [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="c08d7-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c08d7-120">参照</span><span class="sxs-lookup"><span data-stu-id="c08d7-120">See Also</span></span>

[<span data-ttu-id="c08d7-121">System.Management.Automation.Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="c08d7-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="c08d7-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c08d7-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
