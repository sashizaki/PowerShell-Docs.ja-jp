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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858878"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="d2aa0-102">ValidatePattern 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="d2aa0-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="d2aa0-103">ValidatePattern 属性には、コマンドレット パラメーターの引数を検証する正規表現パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="d2aa0-104">この属性は、Windows PowerShell 関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="d2aa0-105">ValidatePattern がコマンドレット内で呼び出されると、Windows PowerShell ランタイムはコマンドレット パラメーターの引数を文字列に変換し、し、ValidatePattern 属性によって指定されたパターンには、その文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="d2aa0-106">コマンドレットは、引数を指定されたパターンの変換後の文字列表現に一致する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="d2aa0-107">一致しない場合は、Windows PowerShell ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2aa0-108">構文</span><span class="sxs-lookup"><span data-stu-id="d2aa0-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="d2aa0-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2aa0-109">Parameters</span></span>

<span data-ttu-id="d2aa0-110">`RegexString` ([System.String](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="d2aa0-111">パラメーターの引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="d2aa0-112">オプション ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="d2aa0-113">ビットごとの組み合わせを指定します[System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)正規表現のオプションを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2aa0-114">コメント</span><span class="sxs-lookup"><span data-stu-id="d2aa0-114">Remarks</span></span>

- <span data-ttu-id="d2aa0-115">この属性は、パラメーターごと 1 回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="d2aa0-116">使用することができます、`Option`さらに、パターンを定義する属性のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="d2aa0-117">たとえば、行うことができます、パターン大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="d2aa0-118">この属性をコレクションに適用すると、コレクション内の各要素がパターンに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="d2aa0-119">ValidatePattern 属性を定義した、 [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="d2aa0-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2aa0-120">参照</span><span class="sxs-lookup"><span data-stu-id="d2aa0-120">See Also</span></span>

[<span data-ttu-id="d2aa0-121">System.Management.Automation.Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="d2aa0-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="d2aa0-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d2aa0-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
